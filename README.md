# GraphGenerators
Collection of generators for various different graph classes. The output format is [GraphML](http://graphml.graphdrawing.org/).

## Graph classes
The list below contains all graph classes supported so far. All graphs are simple, which means they have no loops or multi-edges. The parameter *n* stands for number of vertices, *m* for number of edges, *d* for dimension, *p* for a probability, *g/g1/g2* for a graph, *s* for a seed.

- `createEdgelessGraph(n)`, the [edgeless graph](https://en.wikipedia.org/wiki/Null_graph#Edgeless_graph) *\bar{K_n}*, also called empty graph, or null graph
- `createPath(n)`, the [path graph](https://en.wikipedia.org/wiki/Path_graph) *P_n*
- `createCycle(n)`, the [cycle](https://en.wikipedia.org/wiki/Cycle_graph) *C_n* (not to confuse with a [circle graph](https://en.wikipedia.org/wiki/Circle_graph))
- `createPrueferTree(n)`, a (unlabelled) tree based on a random [Prüfer sequence](https://en.wikipedia.org/wiki/Pr%C3%BCfer_sequence)
- `createStar(n)`, a [star graph](https://en.wikipedia.org/wiki/Star_(graph_theory)) *S_n* with *n-1* leaves
- `createMaxOuterplanarGraph(n, s)`, a random [maximal outerplanar graph](https://en.wikipedia.org/wiki/Outerplanar_graph)
- `createApollonianNetwork(n, s)`, a random [Apollonian network](https://en.wikipedia.org/wiki/Apollonian_network)
- `createMaxPlanarGraph(n, flips, s)`, a random maximal [planar graph](https://en.wikipedia.org/wiki/Planar_graph) generated by starting with a random [Apollonian network](https://en.wikipedia.org/wiki/Apollonian_network) and then doing `steps` many random edge flips (recommended to use at least *n^3* many flips)
- `createHamiltonianMaxPlanarGraph(n, s)`, a random maximal [planar graph](https://en.wikipedia.org/wiki/Planar_graph) that is Hamiltonian, i.e. contains a [Hamiltonian cycle](https://en.wikipedia.org/wiki/Hamiltonian_path), based on the merging two maximal outerplanar graphs
- `createMaxOnePlanarGraph(n, flips, s)`, creates a random [1-planar graph](https://en.wikipedia.org/wiki/1-planar_graph) by adding edges to quadrangles of a first created maximal planar graph
- `createKPlanarGraph(n, k, s)`, a [*k*-planar graph](https://en.wikipedia.org/wiki/1-planar_graph) generated from a random point set that is swept from left to right and edges added if they do not introduce more than $k$ crossings
- `createKTree(n, k, s)`, a [*k*-tree](https://en.wikipedia.org/wiki/K-tree) (generated as defined recursively, i.e. adding vertex and connecting it to random *k*-clique)
- `createHypercube(d)`, the [hypercube](https://en.wikipedia.org/wiki/Hypercube) *Q_d*
- `cubeConnectedCycle(d)`, the [cube-connected cycles graph](https://en.wikipedia.org/wiki/Cube-connected_cycles) based on the hypercube *Q_d*
- `createKAryNCube(k, n)`, a *k*-ary *n*-cube which is the product of *n* cycles *C_k*
- `createSquareGrid(n1, n2)`, a [square grid](https://en.wikipedia.org/wiki/Lattice_graph) of size *n1* times *n2*, i.e. the product of *P_n1* and *P_n2*
- `createToroidalGrid(n1, n2)`, the product of the cycles *C_n1* and *C_n2*
- `createCirculantGraph(n, int[] ... steps)`, a [circulant graph](https://en.wikipedia.org/wiki/Circulant_graph) with given steps, e.g. by the array {1, 2, 4}
- `createPermuation(n, s)` or `permutation(int[] perm)`, [permutation graph](https://en.wikipedia.org/wiki/Permutation_graph) for a random or given permutation
- `createCompleteGraph(n)`, the [complete graph](https://en.wikipedia.org/wiki/Complete_graph) *K_n*
- `createTuranGraph(n, r)`, the [Turán graph](https://en.wikipedia.org/wiki/Tur%C3%A1n_graph) *T(n,r)*, for example with *r = 2* (resp. *r = 3*) this can be used to create a complete balanced biparite (resp. tripartite) graph

There are also some operators that can be applied on the graph.

- `shuffleGraph(g)`, randomises the order of the vertices in the data structure and the order of the edges in the adjacency lists
- `thinOutGraph(g, p)`, thins out the given graph *g* by only keeping edges with probability *p* in *[0,1]* (see [model of Gilbert](https://en.wikipedia.org/wiki/Random_graph))
- `createCartesianGraphProduct(g1, g2)`, creates the [product of the two graphs](https://en.wikipedia.org/wiki/Graph_product)

The following tests can be applied to graphs. They might be of interest, if the `thinOutGraph` method has been used.
- `isConnected(g)`, returns whether the graph is connected_cycles
- `isBipartite(g)`, returns whether the graph is bipartite
- `isTree(g)`, returns whether the graph is a tree, but false if it is a forest

## Disclaimer
Most included algorithms are tested and edge cases should be covered. Some tests are included here, some aren't, and some testing was done via println-testing. However, of course, I neither can nor want to guarantee that they are bug free. Feel free to report any bugs and issues.

Please contact me if you are actually using this repository! Feel also free to request more graph classes or features. 


