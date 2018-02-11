---
layout: post
title:  "Inline Functions"
date:   Sun Feb 11 20:57:12 IST 2018 
categories: c++ 
---

**TL;DR**:

1. This post is not about guidance regarding when to declare a function as inline or not. 
   [C++ FAQ][isocpp] covers that.

2. If a class member function is defined in the class body itself, then it gets assigned
   inline keyword automatically.

3. Inline functions are exported as weak symbols.

4. Compiler is free to inline any function regardless of whether it is declared inline or
   not, or vice-versa. [pfunct][dwarves] tool can be used to see such details.

## Inspecting class member function's inline tag
Let's consider following class definition. It includes definition of `getData` in the class
body itself, whereas `doubleData` is defined in a separate cpp file.

{% highlight c++ linenos %}
// object.h
class Object
{
public:
    Object(int data): m_data(data) {}

    int getData() { return m_data; }

    int doubleData();
private:
    int m_data;
};
{% endhighlight %}

{% highlight c++ linenos %}
// object.cpp
#include <object.h>

int Object::doubleData()
{
    return 2 * m_data;
}
{% endhighlight %}

Compiling it and inspecting the object file using [pfunct][dwarves] shows that inline keyword
is automatically added.

{% highlight bash %}
$ g++ -O3 -I. -g -c object.cpp -o object.o
$ pfunct -V object.o | grep getData
inline void getData(class Object \*const this);
{% endhighlight %}

## Inline functions are exported as weak symbols
Inline functions are exported as [weak symbols][weak-symbol]. This allows inline function
to be part of multiple translation units, and still linker doesn't complain about it
under the assumption that the definition of the function should be same across all
translation units.

If inline function is defined in a header file, and that header file is included in
multiple shared libraries, then definition of the function can be picked from any of the
shared libraries depending on library search path. This means that any change in the inline
function might require a full rebuild of all the dependent shared libraries.

{% highlight c++ linenos %}
// mathHelper.cpp
inline int doubleIt(int value)
{
    return 2 * value;
}

int quadrupleIt(int value)
{
    return doubleIt( doubleIt( value ) );
}
{% endhighlight %}

Compiling it in un-optimized mode, otherwise compiler removes `doubleIt` method altogether.
{% highlight bash %}
$ g++ -I. -g -c mathHelper.cpp -o mathHelper.o
$ nm mathHelper.o | grep doubleIt
0000000000000000 W \_Z8doubleIti
{% endhighlight %}

[isocpp]:      https://isocpp.org/wiki/faq/inline-functions
[dwarves]:     https://community.linuxmint.com/software/view/dwarves
[weak-symbol]: https://en.wikipedia.org/wiki/Weak_symbol
