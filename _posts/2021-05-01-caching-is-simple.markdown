---
layout: post
title:  "Caching is simple if you do it right"
date:   Sat May  1 16:48:16 IST 2021 
categories: cache go 
---

Caching is a common and useful technique in Software Engineering.
Some of its common use-cases are as follows:
1. Cache frequently executed APIs to improve performance.
2. Improve resiliency by protecting against downstream dependencies
 by using last cached value.

Caching is so familiar to engineers that we don't think twice before
introducing it naively in any code. 
It is common to introduce a map and add a map lookup before the API
call for introducing a cache.

Let's consider following example (The code examples are in Golang, but
concepts are applicable across languages).
Assume you have a configuration service which holds key-value pairs and
provides a `Get` API to retrieve value for a key.
You have a client-side method for boolean configurations to check if
a particular configuration is enabled or not.

{% highlight golang linenos %}
type BoolConfigProvider struct {
  confClient ConfigurationSvcClient
}

func NewBoolConfigProvider(confClient *ConfigurationSvcClient) {
  return &BoolConfigProvider{confClient: confClient}
}

func (c *BoolConfigProvider) IsEnabled(
  ctx context.Context,
  confKey string,
) (bool, error) {
  value, err := c.confClient.Get(confKey)
  if err != nil {
    return false, err
  }

  return strings.ToLower(value) == "true", nil
}
{% endhighlight %}

## Caching is Easy
You realize that your application invokes this method frequently and with
limited number of keys, so you decide to add caching to speed it up.

{% highlight golang linenos %}
type BoolConfigProvider struct {
  confClient ConfigurationSvcClient
  cache map[string]bool
}

func NewBoolConfigProvider(confClient *ConfigurationSvcClient) {
  return &BoolConfigProvider{
    confClient: confClient,
    cache:      make(map[string]bool),
  }
}

func (c *BoolConfigProvider) IsEnabled(
  ctx context.Context,
  confKey string,
) (bool, error) {
  if enabled, ok := c.cache[confKey]; ok {
    return enabled, nil 
  }

  value, err := c.confClient.Get(confKey)
  if err != nil {
    return false, err
  }

  enabled = strings.ToLower(value) == "true"
  cache[confKey] = enabled
  return enabled, nil
}

{% endhighlight %}

This was easy, isn't it?

Is it [simple][Simple-Made-Easy]? Perhaps, you would say yes!

Is it correct and simple? Well, that depends! Let's analyze the correctness of the code.
1. Is it thread-safe? No.
<br/>
Note that it is okay for a code to be non thread-safe depending on its context
(e.g. Golang's [map][map-thread-safe] is not thread-safe),
but if this was a library method which you expect to be used in concurrent
code, you should think about thread-safety carefully.
2. Do we have a cache eviction policy? No.
<br/>
This is one of the common miss in these quick cache implementations.
It affects both correctness and performance because your application might want
near latest result or might accumulate lot of cached key/values as time passes by.
3. Do you have a way to measure cache effective-ness? No.
<br/>
What if your application query pattern changes over time and cache becomes
obsolete?
4. Do clients have a way to use a non-cached version of the API or choose a
different caching strategy? No.
<br/>
For non-cached version, you may say that anyone could directly call `confClient.Get`
directly, but that would lead to code duplication in parsing the return value.
You are also binding all clients to a single cache policy which is harder to get
right if you are providing a common library since different clients would have
different access patterns.

Not all of these would be applicable in every cache usage, but typically few of
these would be applicable in any production code. This brings us to list down
key properties we require from any cache implementation.

## Properties of a good cache
1. It should be possible for clients to use a non-cached API if they need.
This shouldn't require a code duplication.
2. It should be possible for clients to choose a caching strategy (e.g. LRU, TTL etc.)
they need.
Note that it is fine to not support all possible caching strategies upfront, but key
requirement is that it should be possible to add a new caching strategy without
introducing code duplication.
3. It should be possible to measure cache effectiveness, e.g. hit ratios.

## Caching is Simple
Let's try to design a simple cache which meets our desired properties.
We will implement the same non thread-safe cache as before.

{% highlight golang linenos %}
type ThreadUnsafeCachedBoolConfigProvider struct {
  provider *BoolConfigProvider
  cache     map[string]bool
  hits      uint64
  total     uint64
}

func NewThreadUnsafeCachedBoolConfigProvider() {
  return &ThreadUnsafeCachedBoolConfigProvider{
    provider: NewBoolConfigProvider(),
    cache:    make(map[string]bool),
  }
}

func (c *ThreadUnsafeCachedBoolConfigProvider) IsEnabled(
  ctx context.Context,
  confKey string,
) (bool, error) {
  c.total += 1
  if enabled, ok := c.cache[confKey]; ok {
    c.hits += 1
    return enabled, nil 
  }

  enabled, err := c.provider.IsEnabled(confKey)
  if err != nil {
    return false, err
  }
  cache[confKey] = enabled
  return enabled, nil
}

func (c *ThreadUnsafeCachedBoolConfigProvider) HitRatio() float64 {
  return (float64)hits/(float64)total
}
{% endhighlight %}

It provides same interface as that of `BoolConfigProvider`, so any client which was
using `BoolConfigProvider` can use `ThreadUnsafeCachedBoolConfigProvider` with minimal
changes.
However, it separates caching strategy from the base implementation provided by
`BoolConfigProvider`.
In future, if client wants to change the caching policy, they can write a
different caching decorator which may use LRU or any other caching strategy.
This won't require us to re-implement the base functionality provided by
`BoolConfigProvider`.

You might realize that this is nothing but [Decorator][decorator] pattern at work.

For production usage, I would strongly recommend to identify a good caching
library in your language and use it, rather than building a naive cache whenever
you need one.

[Simple-Made-Easy]: https://www.infoq.com/presentations/Simple-Made-Easy/
[map-thread-safe]: https://blog.golang.org/maps#TOC_6
[decorator]: https://refactoring.guru/design-patterns/decorator
