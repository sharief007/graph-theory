
# Graph Algorithms

- [**Breadth First Search (BFS)**](./breadth-first-search/): Finds the shortest path from a source vertex to all other vertices in an unweighted graph.

- [**Depth First Search (DFS)**](./depth-first-search/): Explores as far as possible along each branch before backtracking, used to traverse or search in graphs.

- [**Dijkstra's Algorithm**](./dijkstras-algorithm/): Finds the shortest path between nodes in a weighted graph, where the edges have non-negative weights.

- [**Bellman-Ford Algorithm**](./bellman-ford-algorithm/): Finds the shortest path between nodes in a weighted graph, even when the edges have negative weights.

- [**Floyd-Warshall Algorithm**](./floyd-warshall-algorithm/): Finds the shortest paths between all pairs of nodes in a weighted graph. It works with both positive and negative edge weights.

- [**Prim's Algorithm**](./prims-algorithm/): Finds the minimum spanning tree (MST) of a weighted undirected graph, which connects all the vertices with the minimum total edge weight.

- Kruskal's Algorithm: Finds the minimum spanning tree of a weighted undirected graph, also by selecting edges with minimum weight.

- Topological Sort: Arranges the nodes in a directed acyclic graph (DAG) in a linear order such that for every directed edge (u, v), node u comes before node v.

- Strongly Connected Components (SCC): Identifies groups of nodes in a directed graph where each node is reachable from every other node in the same group.

- Articulation Points and Bridges: Identifies critical nodes and edges in an undirected graph. Articulation points are nodes whose removal increases the number of connected components, while bridges are edges whose removal increases the number of connected components.

- Tarjan's Algorithm: Identifies strongly connected components in a directed graph.

- Fleury's Algorithm: Finds an Eulerian circuit in a connected, directed or undirected graph.

- Hierholzer's Algorithm: Finds an Eulerian circuit in a directed graph.

- Bipartite Graph Check: Determines if a given graph is bipartite, meaning its vertices can be divided into two disjoint sets such that no two adjacent vertices are in the same set.

- Maximum Flow (Ford-Fulkerson Algorithm, Edmonds-Karp Algorithm, etc.): Finds the maximum flow in a flow network, which represents the movement of a resource from a source to a sink through a directed graph.

- Minimum Cut (Stoer-Wagner Algorithm, Karger's Algorithm, etc.): Finds the minimum cut in an undirected weighted graph.

- Traveling Salesman Problem (TSP): Finds the shortest possible tour that visits each city exactly once and returns to the origin city.

- Minimum Spanning Arborescence (Chu-Liu/Edmonds' Algorithm): Finds a minimum spanning arborescence (a directed spanning tree) in a directed graph.

- A Search Algorithm:* Finds the shortest path between nodes in a weighted graph, using a heuristic to guide the search.

- Johnson's Algorithm: Finds the shortest paths between all pairs of vertices in a weighted, directed graph, even when there are negative edge weights.