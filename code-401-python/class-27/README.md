# Graphs

A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.

Here is some common terminology used when working with Graphs:

1. Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.

2. Edge - An edge is a connection between two nodes.

3. Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.

4. Degree - The degree of a vertex is the number of edges connected to that vertex.

## Directed vs Undirected

**Undirected Graphs**

An Undirected Graph is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

For example, in the graph below, Node C is connected to Node A, Node E and Node B. There are no “directions” given to point to specific vertices. The connection is bi-directional.

![Undirected Graphs](/code-401-python/class-27/Capture.PNG)

The undirected graph we are looking at has 6 vertices and 7 undirected edges.

**Directed Graphs (Digraph)**

A Directed Graph also called a Digraph is a graph where every edge is directed.

Unlike an undirected graph, a Digraph has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.

![Undirected Graphs](/code-401-python/class-27/Capture1.PNG)

The directed graph above has six vertices and eight directed edges

## Complete vs Connected vs Disconnected

**Complete Graphs**

A complete graph is when all nodes are connected to all other nodes.

![Undirected Graphs](/code-401-python/class-27/Capture2.PNG)

Each vertex is actually connected to every other node on the graph. That is what makes it a complete graph.

**Connected**

A connected graph is graph that has all of vertices/nodes have at least one edge.

![Undirected Graphs](/code-401-python/class-27/Capture3.PNG)

**Disconnected**

A disconnected graph is a graph where some vertices may not have edges.

![Undirected Graphs](/code-401-python/class-27/Capture4.PNG)

## Acyclic vs Cyclic

In addition to undirected and directed graphs, we also have acyclic and cyclic graphs.

**Acyclic Graph**

An acyclic graph is a directed graph without cycles.

A cycle is when a node can be traversed through and potentially end up back at itself.

![Undirected Graphs](/code-401-python/class-27/Capture5.PNG)

**Cyclic Graphs**

A Cyclic graph is a graph that has cycles.

A cycle is defined as a path of a positive length that starts and ends at the same vertex.

![Undirected Graphs](/code-401-python/class-27/Capture6.PNG)

## Graph Representation

We represent graphs through:

1. Adjacency Matrix

3. Adjacency List

We will represent the following graph as both an Adjacency Matrix and an Adjacency List:

![Undirected Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)

**Adjacency Matrix**

An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix

Each Row and column represents each vertex of the data structure. The elements of both the column and the row must add up to 1 if there is an edge that connects the two, or zero if there isn’t a connection.

![Undirected Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjMatrix.PNG)

a **sparse** graph is when there are very few connections. a **dense** graph is when there are many connections

Within an adjacency matrix, an undirected graph will always be symmetric. This is not the case for a directed graph

**Adjacency List**

An adjacency list is the most common way to represent graphs.

An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.

Adjacency lists make it easy to view if one vertices connects to another.

![Undirected Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjList.PNG)

**Weighted Graphs**

A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights.

![Undirected Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightGraph.PNG)

When representing a weighted graph in a matrix, you set the element in the 2D array to represent the actual weight between the two paths. If there is not a connection between the two vertices, you can put a 0, although it is known for some people to put the infinity sign instead.

![Undirected Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightMatrix.PNG)

Within adjacency lists, you must include both the weight and the name of the adjacent vertex.

![Undirected Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightList.PNG)

## Traversals

You will be required to traverse through a graph. The traversals itself are like those of trees. Below is a breakdown of how you would traverse a graph.

**Breadth First**

In a breadth first traversal, you are starting at a specific vertex/node. This node must be specified when calling the BreadthFirst() method. The breadth first traversal of a graph is like that of a tree, with the exception that graphs can have cycles. Traversing a graph that has cycles will result in an infinite loop….this is bad. To prevent such behavior, we need to have some way to keep track of whether a vertex has been “visited” before. Upon each visit, we’ll add the previously-unvisited vertex to a visited set, so we know not to visit it again as traversal continues.

**Depth First**

In a depth first traversal, our approach is a bit different than the approach used for breadth first. While the breadth first traversal uses a Queue to visit all children at a given level, the depth first traversal uses a Stack to visit all children of a given subtree. (This differs from our approach to tree traversal, where we visit nodes via recursive calls. Recursive calls use a call stack internally.)

## Real World Uses of Graphs

Graphs are extremely popular when it comes to it’s uses. Here are just a few examples of graphs in use:

- GPS and Mapping

- Driving Directions

- Social Networks

- Airline Traffic

- Netflix uses graphs for suggestions of products

# Things I want to know more about

- DSA

# References

[1] <https://online.ltuc.com/d2l/lms/dropbox/user/folder_submit_files.d2l?db=95871&grpid=0&isprv=False&bp=0&ou=42425>
