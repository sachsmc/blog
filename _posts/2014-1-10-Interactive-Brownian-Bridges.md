---
layout: post
category : tutorial
tagline: "Supporting tagline"
tags : [intro, tutorial, how-to, d3.js, brownian-motion]
---
{% include JB/setup %}



Creating Interactive Brownian Bridges using d3.js
========================================================

For my first post, I'd like to write a brief tutorial on how I made the cool interactive "Brownian Viaducts" as seen on my [homepage](http://sachsmc.github.io). There were a number of steps invovled in getting from the idea to the [d3](http://d3js.org) implementation that I plan to work through. But first, what is a Brownian Viaduct?

Brownian Bridges and Viaducts
-------------------------------------------------------
A [Brownian bridge](https://en.wikipedia.org/wiki/Brownian_bridge) is a Gaussian process indexed by (0, 1) that is pinned down to 0 at both ends. In statistics, Brownian bridges come up when we talk about the [empirical process](https://en.wikipedia.org/wiki/Empirical_process), that is the empirical cumulative distribution function (cdf). 

To solidify things, lets consider a sample from the Uniform distribution on (0, 1). The empirical cdf at _t_ is simply the proportion of samples that are less than _t_. 



{% highlight r %}
mean(runif(100) < 0.25)
{% endhighlight %}



{% highlight text %}
## [1] 0.36
{% endhighlight %}



Here I took _t_ = 0.25, but the empirical process is just the random function of _t_. Let's plot it:


{% highlight r %}
empcdf.unif <- function(t) {
    sapply(t, function(x) mean(runif(100) < x))
}
curve(empcdf.unif, from = 0, to = 1)
{% endhighlight %}

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 


