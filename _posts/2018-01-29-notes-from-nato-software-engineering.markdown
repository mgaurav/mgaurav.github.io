---
layout: post
title:  "Excerpts From NATO Software Engineering Conference (1968)"
date:   Mon Jan 29 12:18:53 IST 2018
categories: software-engineering 
---

I recently read transcript of a seminal NATO conference held in 1968 with the
title "Software Engineering" ([pdf](http://homepages.cs.ncl.ac.uk/brian.randell/NATO/nato1968.PDF)). I am astonishingly surprised to see that the
issues being discussed in a conference half a century ago are still prevalent.
Below are some excerpts from the report (*emphasis is mine*).

1. There are two classes of system designers. The first, if given five problems
will solve them one at a time. The second will come back and announce that
these aren't the real problems, and will eventually propose a solution to the
single problem which underlies the original five. This is the ‘system type’ who
is great during the initial stages of a design project. However, you had better
get rid of him after the first six months if you want to get a working system. - **Kinslow**
 
2. Part of the discussion was concerned with the sources of the right attitude
to design. The suggestion that software designers should record their wrong
decisions, to avoid having them repeated, met the following response:

    **McClure**: Confession is good for the soul

    **d'Agapeyeff**: -- but bad for your career.

3. There is a tendency that designers use fuzzy terms, like 'elegant' or
'powerful' or 'flexible'. Designers do not describe how the design works, or
the way it may be used, or the way it would operate. What is lacking is
discipline, which is caused by people falling back on fuzzy concepts, instead
of on some razors of Occam, which they can really use to make design decisions.
Also designers don't seem to realize what mental processes they go through when
they design. Later they can neither explain, nor justify, nor even rationalize,
the processes they used to build a particular system. I think that a few
Occam's razors floating around can lead to great simplifications in building
software. Just the simple: how something will be used, can often really sharpen
and simplify the design process. Similarly, *if we use the criterion: it should
be easy to explain, it is remarkable how simple the design process becomes. As
soon as one tries to put into the system something that takes more than a 
paragraph or a line to explain, throw it out - it is not worth it*. We have
applied this to at least one system and it worked beautifully. As a result we
had documentation at the same time as we had the system. Another beautiful razor is: the user should have no feeling that he is dealing with an inanimate
object, rather he should feel that he is dealing with some responsive
personality, who always responds in some reasonable way. Criteria like these 
have nothing to do with 'powerful linguistic features' or 'flexibility' and
right at the beginning I think we should throw these fuzzy terms out of the
window. - **Smith**

4. I just want to make the point that reliability really is a design issue, in
the sense that unless you are conscious of the need for reliability throughout
the design, you might as well give up. - **Fraser**

5. To-day we tend to go on for years, with tremendous investments, to find that
the system, which was not well understood to start with, does not work as
anticipated. We work like the Wright brothers built airplanes: build the whole
thing, push it off the cliff, let it crash, and start over again. Simulation is
a way to do trial and error experiment - **Graham**

6. In debates like this most people agree on the benefits of high-level
languages, but back in the field very few large projects use such languages. I
believe the reason is that project managers, if left to make the decision, will
decide on the basis of their own small world. They will seek to optimise the
easily measurable figures on which they expect to be judged, and will aim to
minimise core store used and maximise speed. They will ignore advantages such
as portability, ease of recoding, etc., even though in the long term these
factors may well be of paramount importance. If such decisions were made at a
higher level of the organisation, the outcome would be very different - **Randell**

7. I have a point with respect to the fact that people are willing to write
programs and fail to make the documentation afterwards. I had a student who was
orally examined to show that he could program. He had to program a loop, and
programmed the body of it and had to fill in the Boolean condition used to stop
the repetition. I did not say a thing, and actually saw him, reading, following
line by line with his finger, five times the whole interior part of his coding.
Only then did he decide to fill in the Boolean condition -- and made it wrong.
Apparently the poor boy spent ten minutes to discover what was meant by what he
had written down. I then covered up the whole thing and asked him, what was it
supposed to do, and forced out of him a sentence describing what it had to do,
regardless of how it had been worked out. When this formulation had been given,
then one line of reasoning was sufficient to fill in the condition. The
conclusion is that making the predocumentation at the proper moment, and using
it, will improve the efficiency with which you construct your whole thing
incredibly. One may wonder, if this is so obvious, why doesn't it happen? I
would suggest that the reason why many programmers experience the making of
predocumentation as an additional burden, instead of a tool, is that whatever
predocumentation he produces can never be used mechanically. Only if we provide
him with more profitable means, preferably mechanical, for using
predocumentation, only then will the spiritual barrier be crossed. - **Dijkstra**

8. There is a principle, a kind of corollary to Parkinson's Law, called the
Peter Principle, named after a high school principal in Long Island. It goes
like this: 'In the real world people are eventually promoted to their final level of incompetence' - **David**

9. If the job has been done before, estimates are fairly easy. If the research
content is high, estimates are difficult. The trouble is that it is not always
possible to tell beforehand which jobs are which. - **Genuys**

10. Computing has one property, unique I think, that seriously aggravates the
uncertainties associated with software efforts. *In computing, the research,
development, and production phases are often telescoped into one process. In
the competitive rush to make available the latest techniques, such as on-line
consoles served by time-shared computers, we strive to take great forward leaps
across gulfs of unknown width and depth*. In the cold light of day, we know that
a step-by-step approach separating research and development from production is
less risky and more likely to be successful. Experience indeed indicates that
for software tasks similar to previous ones, estimates are accurate to within
10–30% in many cases. This situation is familiar in all fields lacking a firm
theoretical base. Thus, there are good reasons why software tasks that include
novel concepts involve not only uncalculated but also uncalculable risks. - **David**

11. Before undertaking a project to produce a new software system or component,
read the following statements, checking all that apply:
    1. The new system will be substantially superior to its predecessor and to
       competitive systems.
    2. The new system corrects a basic philosophical defect in the previous
       system.
    3. The specification is not yet complete, but it will be finished before
       any important programming decisions are made.
    4. The specification is absolutely firm, unless, of course, the Acme
       Company signs a big order and requests some slight changes.
    5. The programming team will be made up by selecting only the best
       programmers from other projects.
    6. Because of expansion, a fresh team of programmers with applicable
       experience will be hired.
    7. The new computer is a great machine; the programmers will love it as
       soon as they can get their manuals.
    8. The programmers will, of course, have to share the machine with the
       hardware team checking out the new peripherals and the diagnostic
       package.
    9. Interfacing this system to the rest of the software is trivial and can be
       easily worked out later.
    10. Although the assembler (compiler, loader, file system, etc.) is not
        completely checked out, it will be ready long before coding is complete.
    11. The debug package isn't done but this system can easily be checked out
        at the console.
    12. The budget is only preliminary but it's obviously conservative.
    13. The project manager may have missed his budget on his last project, but
        he has learned his lesson and won't miss this time.

    For each statement checked on the preceding list add ten percent to the
estimated cost and one month to the estimated time. If statement six is checked,
add thirty per cent and six months. The result should come much closer to the
final result than the original estimate under the assumption that the original
estimate was honestly made. - **McClure**

12. Another interesting concept we might apply is that used in the Air Force,
to fly a number of hours each month, in order to retain one's 'wings'. So, in
a system which will take a long time to complete, for example a year, nobody
should be allowed to function permanently at one level, but should percolate.
*In a situation where code actually has to be produced, nobody should be allowed
in the system who doesn't write some given number of lines of code per month*.
I think that one of the major problems with the very large programming projects
has been the lack of competence in programming which one observes as soon as
one goes above the very bottom level. People begin to talk in vague general
terms using words like 'module', and very rarely ever get down to the detail of
what a module actually is. They use phrases like 'communicate across modules by
going up and then down' — all of the vague administratese which in a sense must
cover up a native and total incompetence. - **Perlis**

13. The initial release of a software system should work well (albeit with
limited facilities) and must contain the basic system philosophies that ensure
orderly growth. - **Babcock**

14. Testing is a very inefficient way of convincing oneself of the correctness
of a program. - **Dijkstra**
