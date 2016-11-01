output: pdf\_document

Distribution of the Number of Triangles in an Erdös-Rényi RG
============================================================

Here I investigate numericaly the limiting distribution of the number of
triangles in a *E**R*(*n*, *p* = *λ*/*n*) graph. I want to confirm that
as the number of nodes *n* → ∞, the number of triangles
*Δ*<sub>*n*</sub> → *P**o**i**s*(*λ*<sup>3</sup>/6) in distribution.

First, I show the R package that I used, igraph.

igraph
------

There is a nice R package to work with graphs called
[igraph](http://igraph.org/).

    library(igraph)

igraph is a collection of network analysis tools. Among them, there are
functions to easily sample *E**R*(*n*, *p* = *λ*/*n*) graphs, plot them,
and count the number of triangles, which is what we need. Let's generate
a graph with *n* = 100, *λ* = 3, and count the triangles with the
function count\_triangles, which returns how many triangles each vertex
is part of.

    set.seed(2016)
    rg <- sample_gnp(n = 100, p = 3/100)
    count_triangles(rg) %>%
        sum/3

    ## [1] 6

we can also plot rg (See Figure 1).

    plot(rg, vertex.label = NA, vertex.size = 2)

![A realization of
*E**R*(*n* = 100, *p* = 3/100)](triangles_files/figure-markdown_strict/unnamed-chunk-4-1.png)

Random sample from *E**R*(*n*, *p* = *λ*/*n*)
---------------------------------------------

Now, we want to confirm that as the number of nodes *n* → ∞, the number
of triangles *Δ*<sub>*n*</sub> → *P**o**i**s**s*(*λ*<sup>3</sup>/6) in
distribution. For that, I generate a random sample of *N* = 10000 random
graphs for *λ* = 0.1, 1, 2, 5, and *n* = 100, 200, 500, 1000, 5000, and
then analyze the empirical distribution of *Δ*<sub>*n*</sub> in each
case.

We can compare the empirical distribution with the theoretical
probability mass function.

![Observed frequency distribution and expected Poisson
distribution](triangles_files/figure-markdown_strict/unnamed-chunk-6-1.png)

The qqplots look like this, but they are not very promising

![QQ-plots of the sample versus the Poisson distribution
quantiles](triangles_files/figure-markdown_strict/unnamed-chunk-7-1.png)
