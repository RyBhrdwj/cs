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
- [Kahn’s Algorithm (BFS-Based)](#kahns-algorithm-bfs-based)
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
- [Union by Size](#union-by-size)
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

---

## Types of Graphs

### Simple Graph
A graph with no loops or multiple edges.

### Multi-Graph and Pseudo-Graph
- **Multi-Graph:** A graph that allows multiple edges between the same pair of vertices.
- **Pseudo-Graph:** A multi-graph that also allows loops.

### Complete Graph (Kₙ)
A graph in which every pair of distinct vertices is connected by a unique edge.
- **Number of edges:** \( $$E = \frac{n(n-1)}{2}$$ \) for an undirected graph.

### Bipartite Graph
A graph whose vertices can be divided into two disjoint sets such that no two graph vertices within the same set are adjacent.

### Cyclic and Acyclic Graph
- **Cyclic Graph:** Contains at least one cycle.
- **Acyclic Graph:** Does not contain any cycles.
  - **DAG (Directed Acyclic Graph):** A directed graph with no cycles.

### Subgraph, Induced Subgraph
- **Subgraph:** A subset of vertices and edges from a graph.
- **Induced Subgraph:** A subgraph formed by selecting vertices and including all edges between them from the original graph.

### Regular Graph
A graph where each vertex has the same degree.
- **k-Regular Graph:** Every vertex has exactly k edges.

### Planar Graph
A graph that can be drawn on a plane without edges crossing.
- **Euler's Formula:** For a connected planar graph, \( V - E + F = 2 \), where F is the number of faces.

### Eulerian and Hamiltonian Graph
- **Eulerian Graph:** A graph containing an Eulerian circuit (a cycle that visits every edge exactly once).
- **Hamiltonian Graph:** A graph containing a Hamiltonian cycle (a cycle that visits every vertex exactly once).

### Chordal Graph
A graph in which all cycles of four or more vertices have a chord (an edge that connects two non-adjacent vertices in the cycle).

### Line Graph
A graph formed by representing the edges of an original graph as vertices.

------

# Graph Representations

## Adjacency Matrix
A **V × V** matrix where each cell **(i, j)** represents an edge weight or presence between node **i** and **j**.

### Properties:
- Space Complexity: **O(V²)**
- Best for dense graphs.
- Checking edge existence: **O(1)**
- Iterating neighbors: **O(V)**

### Example:
```
  0  1  2  3
0 0  1  0  1
1 1  0  1  0
2 0  1  0  1
3 1  0  1  0
```

---

## Adjacency List
A list where each vertex has an array of connected vertices.

### Properties:
- Space Complexity: **O(V + E)**
- Best for sparse graphs.
- Checking edge existence: **O(V)**
- Iterating neighbors: **O(E)**

### Example:
```
0 -> [1, 3]
1 -> [0, 2]
2 -> [1, 3]
3 -> [0, 2]
```

------

## 8. Topological Sorting
### Kahn’s Algorithm (BFS-Based)
A **BFS-based** method to find a valid topological ordering of a DAG.

#### Algorithm:
1. Compute the **in-degree** of each node.
2. Push all nodes with **in-degree = 0** into a queue.
3. While the queue is not empty:
   - Pop a node, add it to the topological order.
   - Reduce the in-degree of its neighbors.
   - If a neighbor’s in-degree becomes 0, push it into the queue.
4. If all nodes are processed, the topological order is valid; otherwise, a cycle exists.

#### Pseudo Code:
```cpp
vector<int> kahnTopoSort(int V, vector<vector<int>>& adj) {
    vector<int> in_degree(V, 0), topo_order;
    queue<int> q;
    
    for (int u = 0; u < V; u++)
        for (int v : adj[u]) in_degree[v]++;
    
    for (int i = 0; i < V; i++)
        if (in_degree[i] == 0) q.push(i);
    
    while (!q.empty()) {
        int u = q.front(); q.pop();
        topo_order.push_back(u);
        for (int v : adj[u])
            if (--in_degree[v] == 0) q.push(v);
    }
    return (topo_order.size() == V) ? topo_order : vector<int>(); // Empty if cycle exists
}
```

**Time Complexity:** O(V + E)
**Space Complexity:** O(V)

---

### DFS-Based Topological Sorting
A **DFS-based** method to find a valid topological ordering of a DAG.

#### Algorithm:
1. Initialize a **visited** array and an empty **stack**.
2. Perform **DFS** on unvisited nodes, pushing nodes to the stack **after** visiting all descendants.
3. The stack contains the topological order in reverse order.

#### Pseudo Code:
```cpp
void dfs(int node, vector<vector<int>>& adj, vector<bool>& visited, stack<int>& st) {
    visited[node] = true;
    for (int v : adj[node]) {
        if (!visited[v]) dfs(v, adj, visited, st);
    }
    st.push(node);
}

vector<int> dfsTopoSort(int V, vector<vector<int>>& adj) {
    vector<bool> visited(V, false);
    stack<int> st;
    for (int i = 0; i < V; i++)
        if (!visited[i]) dfs(i, adj, visited, st);
    
    vector<int> topo_order;
    while (!st.empty()) {
        topo_order.push_back(st.top());
        st.pop();
    }
    return topo_order;
}
```

**Time Complexity:** O(V + E)
**Space Complexity:** O(V)

------

# 15. Union-Find Data Structure
### Disjoint Set Union
A data structure to manage disjoint sets efficiently, used for cycle detection and connected components.
- **Operations:** Find, Union
- **Applications:** Kruskal's MST, Connected Components

#### Abstract Implementation
```cpp
class AbstractDSU {
    std::vector<int> parent, rank, size;

public:
    AbstractDSU(int n) : parent(n), rank(n, 0), size(n, 1) {
        for (int i = 0; i < n; i++) parent[i] = i;
    }

    virtual int find(int x) = 0;
    virtual void unite(int x, int y) = 0;
};
```

### Path Compression
- Optimizes the `find` operation by making every node point directly to the root.
- **Time Complexity:** O(α(N)) (inverse Ackermann function, nearly constant)

#### Pseudo Code:
```cpp
int find(int x) {
    if (parent[x] == x) return x;
    return parent[x] = find(parent[x]); // Path compression
}
```

### Union by Rank
- **What is Rank?** Rank represents an estimate of tree height.
- **Default Value:** Initially, all nodes have rank 0.
- **How It Increases:** Rank only increases when two trees of the same rank are merged.
- **Balancing Strategy:** Attach the tree with a lower rank under the tree with a higher rank.

#### Pseudo Code:
```cpp
void unionSet(int x, int y) {
    int rootX = find(x);
    int rootY = find(y);
    if (rootX != rootY) {
        if (rank[rootX] > rank[rootY]) parent[rootY] = rootX;
        else if (rank[rootX] < rank[rootY]) parent[rootX] = rootY;
        else { parent[rootY] = rootX; rank[rootX]++; }
    }
}
```

### Union by Size
- **What is Size?** The number of nodes in a set.
- **Default Value:** Each node starts with size 1.
- **How It Increases:** The parent node accumulates the size of the merged tree.
- **Balancing Strategy:** Attach the smaller tree under the larger tree.

#### Pseudo Code:
```cpp
void unionSet(int x, int y) {
    int rootX = find(x);
    int rootY = find(y);
    if (rootX != rootY) {
        if (size[rootX] > size[rootY]) {
            parent[rootY] = rootX;
            size[rootX] += size[rootY];
        } else {
            parent[rootX] = rootY;
            size[rootY] += size[rootX];
        }
    }
}
```

### Applications in Graphs
1. **Cycle Detection in an Undirected Graph**
   - Check if two nodes are in the same set before merging.
2. **Kruskal's Algorithm for MST**
   - Sort edges and use DSU to build the Minimum Spanning Tree.
3. **Connected Components**
   - Group nodes into sets to determine connectivity.
