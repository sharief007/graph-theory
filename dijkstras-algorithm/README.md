# Dijkstra's Algorithm

Dijkstra's Algorithm is a method used to find the shortest path from a specified starting point (source) to all other points (nodes) in a weighted graph, where the edge weights represents `non-negative distances` between nodes. It ensures that the shortest path to each node is determined accurately, considering all possible routes through the graph, and is commonly employed in navigation and network routing applications.

### Implementation

```java
import java.util.*;

public class DijkstraAlgorithm {

    // Define a class to represent a node in the graph
    static class Node implements Comparable<Node> {
        int id;
        int distance;

        public Node(int id, int distance) {
            this.id = id;
            this.distance = distance;
        }

        @Override
        public int compareTo(Node other) {
            return Integer.compare(this.distance, other.distance);
        }
    }

    static void dijkstra(int[][] graph, int source) {
        int n = graph.length;
        Set<Integer> visited = new HashSet<>();
        int[] distances = new int[n];
        Arrays.fill(distances, Integer.MAX_VALUE);

        // Create priority queue
        PriorityQueue<Node> pq = new PriorityQueue<>();
        pq.add(new Node(source, 0));
        distances[source] = 0;

        while (!pq.isEmpty()) {
            Node current = pq.poll();
            int currentId = current.id;

            if (visited.contains(currentId)) continue;

            visited.add(currentId);

            for (int neighbor = 0; neighbor < n; neighbor++) {
                if (graph[currentId][neighbor] != 0) {
                    int distanceThroughCurrent = distances[currentId] + graph[currentId][neighbor];
                    if (distanceThroughCurrent < distances[neighbor]) {
                        distances[neighbor] = distanceThroughCurrent;
                        pq.add(new Node(neighbor, distanceThroughCurrent));
                    }
                }
            }
        }

        // Print the distances from source to each node
        for (int i = 0; i < n; i++) {
            System.out.println("Distance from source to node " + i + " is " + distances[i]);
        }
    }

    public static void main(String[] args) {
        int[][] graph = {
            {0, 10, 0, 0, 0},
            {10, 0, 20, 0, 0},
            {0, 20, 0, 10, 0},
            {0, 0, 10, 0, 50},
            {0, 0, 0, 50, 0}
        };

        int source = 0;
        dijkstra(graph, source);
    }
}
```
**Edge Cases Covered:**

**Directed Graph:** The provided code handles directed graphs where edges may only go in one direction.

**Weighted Edges:** The graph is represented using an adjacency matrix, allowing for weighted edges.

**Disconnected Nodes:** The algorithm can handle cases where some nodes are not reachable from the source.

**Non-Negative Weights:** Dijkstra's algorithm assumes non-negative edge weights. If there are negative weights, you'd need to use a different algorithm like Bellman-Ford.

**Handling Infinite Distances:** The initial distances are set to Integer.MAX_VALUE, representing infinity. When a valid path is found, the distance is updated.

### Complexity Analysis

**Time Complexity:**
- **Worst Case:** O((V + E) log V)
- **Best Case (dense graph):** O((V^2) log V)
- **Best Case (sparse graph):** O((V + E) log V)
- **Average Case:** O((V + E) log V)

**Space Complexity:**
- **Visited Set:** O(V)
- **Distances Array:** O(V)
- **Priority Queue (Binary Heap):** O(V)
- **Adjacency Matrix:** O(V^2)

The total space complexity is O(V^2) due to the adjacency matrix. In some implementations, you might use an adjacency list instead, which can reduce space complexity to O(V + E).

Here, V is the number of vertices.E is the number of edges.

**Note:** If you're using a Fibonacci heap or a more efficient data structure for the priority queue, the time complexity could potentially be improved. However, the space complexity may also increase.