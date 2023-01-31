# Graphs

---

## Vocabulary / Definition List

* **Graph -**  Non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.

* **Vertex -**  Data object that can have zero or more adjacent vertices. Also called `node`.

* **Edge -** Connection between two nodes.

* **Neighbor -** The neighbors of a node are its adjacent nodes. Connected via an edge.

* **Degree -** The number of edges connected to a vertex.

* **Undirected Graph -** A graph where each edge is undirected or bi-directional. The undirected graph does not move in any direction.

* **Directed Graph -** A graph where every edge is directed. It has direction. Each node is directed at another node with a specific requirement of what node should be referenced next. Also called `Digraph`. 

* **Complete Graph -** A graph where all nodes are connected to all other nodes.

* **Connected Graph -** A graph where each node is connected to at least one other node or vertex. A `Tree` is a form of a connected graph.

* **Disconnected Graph -** A graph where some vertices may not have edges.

* **Acyclic Graph -** A directed graph without cycles. A directed acyclic graph is also called a `DAG`. This can also be represented as what we know as a tree.
  * **Cycle -** When a node can be traversed through and potentially end up back at itself.

* **Cyclic Graph -** A graph that has cycles.
  * **Cycle -** A path of a positive length that starts and ends at the same vertex.

* **Adjacency Matrix -** Represented through a 2-dimensional array. If there are `n` vertices, then we are looking at an `n x n` Boolean matrix.

* **Sparse Graph -** When there are very few connections.

* **Dense Graph -** When there are many connections.

* **Adjacency List -** A collection of linked lists or lists that list all the other vertices that are connected. This is the most common way to represent graphs.

* **Weighted Graphs -** A graph with numbers assigned to its edges. These numbers are called `weights`.

---

[*source*](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)

---

[-back](https://alexriverau.github.io/reading-notes/code401)
