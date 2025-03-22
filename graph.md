# Graph Theory Comprehensive Guide

## 1. Basics of Graphs
### Definition and Terminology
- [Graph (G = V, E)](#graph-g--v-e)
- [Vertices (Nodes) and Edges](#vertices-nodes-and-edges)
- [Directed and Undirected Graphs](#directed-and-undirected-graphs)
- [Weighted and Unweighted Graphs](#weighted-and-unweighted-graphs)
- [Degree of a Node (In-degree, Out-degree)](#degree-of-a-node-in-degree-out-degree)
- [Paths, Walks, and Circuits](#paths-walks-and-circuits)
- [Connected and Disconnected Graphs](#connected-and-disconnected-graphs)
- [Diameter of a Graph](#diameter-of-a-graph)

### Types of Graphs
- [Simple Graph](#simple-graph)
- [Multi-Graph and Pseudo-Graph](#multi-graph-and-pseudo-graph)
- [Complete Graph (Kₙ)](#complete-graph-kₙ)
- [Bipartite Graph](#bipartite-graph)
- [Cyclic and Acyclic Graph](#cyclic-and-acyclic-graph)
- [Subgraph, Induced Subgraph](#subgraph-induced-subgraph)
- [Regular Graph](#regular-graph)
- [Planar Graph](#planar-graph)
- [Eulerian and Hamiltonian Graph](#eulerian-and-hamiltonian-graph)
- [Chordal Graph](#chordal-graph)
- [Line Graph](#line-graph)

---

## 2. Graph Representations
- [Adjacency Matrix](#adjacency-matrix)
- [Adjacency List](#adjacency-list)
- [Incidence Matrix](#incidence-matrix)

---

## 3. Graph Traversal Algorithms
- **[Breadth-First Search (BFS)](#breadth-first-search-bfs)**
  - Level Order Traversal
  - Shortest Path in Unweighted Graphs
- **[Depth-First Search (DFS)](#depth-first-search-dfs)**
  - Recursive and Iterative DFS
  - Connected Components
  - Topological Sorting (using DFS)

---

## 4. Shortest Path Algorithms
- [Dijkstra’s Algorithm (Single-Source Shortest Path)](#dijkstras-algorithm)
- [Bellman-Ford Algorithm (Handles Negative Weights)](#bellman-ford-algorithm)
- [Floyd-Warshall Algorithm (All-Pairs Shortest Path)](#floyd-warshall-algorithm)

---

## 5. Minimum Spanning Tree (MST) Algorithms
- [Properties of MST](#properties-of-mst)
- [Kruskal’s Algorithm](#kruskals-algorithm)
- [Prim’s Algorithm](#prims-algorithm)

---

## 6. Cycle Detection in Graphs
- [Cycle Detection in Undirected Graphs](#cycle-detection-in-undirected-graphs)
- [Cycle Detection in Directed Graphs (Using DFS)](#cycle-detection-in-directed-graphs)
- [Union-Find for Cycle Detection](#union-find-for-cycle-detection)

---

## 7. Strongly Connected Components (SCCs)
- [Kosaraju’s Algorithm](#kosarajus-algorithm)
- [Tarjan’s Algorithm](#tarjans-algorithm)

---

## 8. Topological Sorting
- [Kahn’s Algorithm (BFS-Based)](#kahns-algorithm)
- [DFS-Based Topological Sorting](#dfs-based-topological-sorting)

---

## 9. Graph Coloring
- [Chromatic Number](#chromatic-number)
- [Greedy Coloring Algorithm](#greedy-coloring-algorithm)
- [Bipartite Graph Checking (2-Coloring)](#bipartite-graph-checking)

---

## 10. Network Flow Algorithms
- [Ford-Fulkerson Algorithm (Maximum Flow)](#ford-fulkerson-algorithm)
- [Edmonds-Karp Algorithm](#edmonds-karp-algorithm)
- [Dinics Algorithm](#dinics-algorithm)

---

## 11. Eulerian and Hamiltonian Paths
- [Eulerian Path and Circuit](#eulerian-path-and-circuit)
  - Fleurs Algorithm
- [Hamiltonian Path and Circuit](#hamiltonian-path-and-circuit)
  - Backtracking Approach

---

## 12. Matching in Graphs
- [Bipartite Matching](#bipartite-matching)
- [Hopcroft-Karp Algorithm](#hopcroft-karp-algorithm)

---

## 13. Lowest Common Ancestor (LCA)
- [Binary Lifting Method](#binary-lifting-method)
- [Tarjan’s Offline LCA Algorithm](#tarjans-offline-lca-algorithm)

---

## 14. Tree Algorithms
- [Tree Diameter (DFS/BFS)](#tree-diameter)
- [Rooting a Tree](#rooting-a-tree)
- [Centroid Decomposition](#centroid-decomposition)
- [Heavy-Light Decomposition (HLD)](#heavy-light-decomposition)

---

## 15. Union-Find Data Structure
- [Disjoint Set Union (DSU)](#disjoint-set-union)
- [Path Compression](#path-compression)
- [Union by Rank](#union-by-rank)
- [Applications in Graphs](#applications-in-graphs)

---

## 16. Advanced Graph Algorithms
- [Bridges in Graphs (Tarjan’s Algorithm)](#bridges-in-graphs)
- [Articulation Points (Cut Vertices)](#articulation-points)
- [2-SAT (Implication Graph)](#2-sat)
- [Planarity Testing (Kuratowski's Theorem)](#planarity-testing)
- [Graph Isomorphism](#graph-isomorphism)

---

## 17. Dynamic Graph Algorithms
- [Dynamic Connectivity (Union-Find with Path Compression)](#dynamic-connectivity)
- [Dynamic Shortest Path (Dijkstra’s with Lazy Updates)](#dynamic-shortest-path)

---

## 18. Cycle Detection Methods
###Undirected Graphs:
  - DFS-based cycle detection
  - Union-Find method
  
###Directed Graphs:
 - DFS with recursion stack
 - Kahn Algorithm (Topological Sorting)


------------



------------



# Basics of Graphs

## Graph (G = V, E)
A **graph** is a collection of vertices (V) and edges (E) connecting them.
- **Notation:** G = (V, E)
- **Types of Graphs:** Directed, Undirected, Weighted, Unweighted
- **Representation:** Adjacency List, Adjacency Matrix

---

## Vertices (Nodes) and Edges
- **Vertices (V):** The fundamental units of a graph.
- **Edges (E):** Connections between vertices.
- **Types of Edges:**
  - **Undirected Edge (u, v):** Bidirectional connection.
  - **Directed Edge u → v:** Unidirectional connection.
  - **Weighted Edge (u, v, w):** Has an associated weight w.

---

## Directed and Undirected Graphs
- **Directed Graph (Digraph):** Edges have direction, represented as ordered pairs (u, v).
- **Undirected Graph:** Edges have no direction, represented as unordered pairs {u, v}.

---

## Weighted and Unweighted Graphs
- **Weighted Graph:** Each edge has a weight or cost associated with it.
- **Unweighted Graph:** All edges are considered to have equal weight.

---

## Degree of a Node (In-degree, Out-degree)
- **Degree (deg(v)):** Number of edges connected to vertex v.
- **In-degree (for directed graphs):** Number of edges directed **toward** the vertex.
- **Out-degree (for directed graphs):** Number of edges directed **away** from the vertex.

---

## Paths, Walks, and Circuits
- **Walk:** A sequence of vertices and edges.
- **Path:** A walk with **no repeated vertices**.
- **Circuit (Cycle):** A path that **starts and ends at the same vertex**.
- **Simple Path:** No repeated edges or vertices (except start and end in a cycle).

---

## Connected and Disconnected Graphs
- **Connected Graph:** Every vertex is reachable from any other vertex.
- **Disconnected Graph:** Some vertices are not reachable from others.
- **Strongly Connected (Directed Graphs):** Every vertex has a path to every other vertex.
- **Weakly Connected (Directed Graphs):** The graph is connected when considering edges as undirected.

---

## Diameter of a Graph
The **diameter** of a graph is the longest shortest path between any two vertices.
- **Formula:** \( d(G) = \max_{u,v \in V} d(u, v) \)
- **Computation:**
  - **Unweighted Graphs:** BFS from all nodes → O(VE) complexity
  - **Weighted Graphs:** Floyd-Warshall (O(V³)) or Dijkstra’s Algorithm (O(E log V))
