---
tags:
  - "pure-maths indigo"
created: 16/12/2024 22:00
---
# Analysis and Topology

This is my own version of the Cambridge Part IB Analysis and Topology course, that was discontinued the year I took it (because it was too long, lol). I've added as much intuition and as many diagrams as I can, to try and motivate things more. Hopefully I can provide an intuitive view of these foundational topics that might not be present elsewhere.

Philosophically, this is a barebones, from-the-ground-up course that is fundamental in further mathematical study. There are no concrete prerequisites, but mathematical maturity (i.e. not being afraid to ponder things) is important.

## Introduction

In the real world, we can measure distances between things - the distance between two points is the length of the straight line connecting them.

But the word "distance" comes up in many many other situations too. For example, if you're planning a train journey, you want to take the route that minimises the "distance" to your destination, where "distance" can mean any combination of time, money spent, comfort etc. This is genuinely different from just measuring the straight-line distance to your destination - behold, the train journey from Cambridge to Luton:

<div className="flex justify-center w-full py-4"> <img src="/assets/analysis-and-topology/camb-luton.jpg" width="600"/> </div>

Or, for another example, have you ever heard of "six degrees of separation"? The claim is that any two people on earth are six or fewer social connections away from each other. Here our notion of "distance" is the minimum number of jumps between social connections requried to link two people.

More abstractly, we can even measure the "distance" between functions:

<div class='flex flex-wrap space-x-4 justify-center py-4 items-center'>
  <AUTOSVG src='analysis-and-topology/intro/functiongraph.svg' width='300' height='200'/>
  <div class='flex-[1_1_200px] min-w-[200px]'>
    <p>There are many ways of quantifying how far $f$ and $g$ are from each other, e.g. maximum distance over all $x$, or total area.</p>
  </div>
</div>

As a mathematician we seek to generalize, so that we can study *all of the above situations at once*. In general, we have some *set of points*, equipped with a *metric*, which is a function that measures the distance between two points. Points can be anything - functions, people, laptops, red blood cells etc. And we can really allow this "metric" (distance function) to be as weird and wacky as we want, as long as it satisfies some sensible properties (e.g. distance is always nonnegative, and if the distance is zero then the two points must be the same). Which properties should we impose for our definition? Again, as a mathematician, we try to impose *as little as possible* on the definition of metric - then try to deduce all the results that we can. The more restrictions we impose, the less general we are, so the less of the above situations we can study at once.[^1] It turns out, that imposing only three properties on the definition of metric, we can deduce many very cool results.
[^1]: You can think of this like the "Don't Repeat Yourself" principle in software development.

<div class="py-4"><hr/></div>

In the second section of the course, we generalise even more, to study "topological spaces". Broadly, these are objects where there is a notion of *closeness*, even if there is no proper definition of *distance*. This is a generalisation because if we have a distance function, then we have a notion of closeness - points that are close together are just those for which the distance between them is small. But the point is that even when there might not be a good way to equip your space with a distance function, you might still be able to talk about when points are "close together".

<div class='flex flex-wrap space-x-4 justify-center py-4 items-center'>
  <AUTOSVG src='analysis-and-topology/intro/paperdeformation.svg' width='300' height='300'/>
  <div class='flex-[1_1_200px] min-w-[200px] space-y-4'>
    <p>For example, let's say I have a piece of paper lying flat on a table. There is a notion of distance - indeed, it's the everyday straight-line-distance we're familiar with.</p>
    <p>But say I pick the paper up and it bends. The points that were close before are still close; conversely, if two points are close on the bent paper, then they were close before. So bending the paper didn't change our idea of which points are close together.</p>
    <p>We're not really giving the bent paper a notion of distance - instead, we're saying "these two points were close before and the thing I did to the paper didn't change that".[^1]</p>
  </div>
</div>

[^1]: However, there is a perfectly good and natural way to define a distance function on the bent paper: we define the distance between the two points on the bent paper to be the distance between them before the paper was scrunched up. See "metrizability is topologically invariant" in section B, chapter 3.2.

The same thing is true if I scrunch up the paper! The points that are "close together" in the scrunched up paper are precisely those that are close together in the original flat piece. This special kind of transformation is called a "homeomorphism" - meaning that it does not change the idea of which points are close.

For example, we glued two ends of the flat paper together to make a cylinder, then this is NOT a homeomorphism:

<div class="flex justify-center pb-8">
  <AUTOSVG src="analysis-and-topology/intro/gluepaper.svg" width="400" height="150"/>
</div>

We will define and study concepts like continuity, homeomorphisms, open sets etc. in detail.

<div class="py-4"><hr/></div>

Finally, we will look at the special metric space $\mathbb{R}^n$ (n-dimensional space), where we will study differentiation. One of the things that makes $\mathbb{R}^n$ special is that it's a special type of metric space, called a "normed space", where not only is there a metric (distance function), but also a way of measuring *lengths* (how big points are). We won't study these in this course, but see Part II Linear Analysis where they are studied in-depth.

<div class="flex justify-center pb-8 pt-4">
  <AUTOSVG src="analysis-and-topology/intro/spacesvenn.svg" width="400" height="300"/>
</div>

<div class="py-4"><hr/></div>

I hope this motivates you as to why we want to study analysis and topology. Ready to get started? <ProminentLink href="analysis-and-topology/a-metric-spaces/1-basics" internal>Go to the first page!</ProminentLink>


## Resources

- <DiscreetLink href="https://www.dpmms.cam.ac.uk/study/IB/AnalysisandTopology/Syllabus.pdf">Overview of topics</DiscreetLink>
- <DiscreetLink href="https://www.dpmms.cam.ac.uk/study/IB/AnalysisandTopology/">Example sheet questions</DiscreetLink>
- <DiscreetLink href="https://questions.tripos.org/courses/analysis%20and%20topology/">Past exam questions</DiscreetLink>

## Conventions

The following conventions are used for the sake of brevity:

- defn = definition
- iff = if and only if
- $\subset$ means the same thing as $\subseteq$ (i.e. "is a subset of, could be equal to")