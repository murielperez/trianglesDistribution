Distribution of the Number of Triangles in an Erdös-Rényi RG
============================================================

There is a nice R package to work with graphs called
[igraph](http://igraph.org/).

    library(igraph)

igraph is a collection of network analysis tools. It comes with useful
functions to easily generate random $ER(n,p=\\frac{\\lambda}{n})$
graphs, plot them, and count the number of triangles, which is what we
need. Let's generate a graph with *n* = 100 *λ* = 3,

    rg <- sample_gnp(n = 100, p = 3/100)
    count_triangles(rg)

    ##   [1] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1 0 0 0 0 0 0 1
    ##  [36] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
    ##  [71] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
