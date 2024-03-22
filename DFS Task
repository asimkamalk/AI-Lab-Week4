class Graph:
    def __init__(self):
        # Initialize an empty dictionary to store the graph
        self.graph = {}

    def add_edge(self, u, v):
        # Add an edge from vertex u to vertex v
        if u not in self.graph:
            self.graph[u] = []
        self.graph[u].append(v)

    def dfs(self, start_node):
        # Perform a Depth-First Search (DFS) starting from start_node
        visited = set()  # Set to keep track of visited nodes
        stack = [start_node]  # Stack to manage the nodes to be visited

        while stack:
            current_node = stack.pop()  # Get the last node from the stack
            if current_node not in visited:
                print(current_node, end=" ")  # Process the current node
                visited.add(current_node)  # Mark the current node as visited

                # Add unvisited adjacent nodes to the stack
                for neighbor in reversed(self.graph.get(current_node, [])):
                    if neighbor not in visited:
                        stack.append(neighbor)

# Example usage
if __name__ == "__main__":
    g = Graph()
    # Constructing the graph by adding edges
    g.add_edge(0, 1)
    g.add_edge(0, 2)
    g.add_edge(1, 2)
    g.add_edge(2, 0)
    g.add_edge(2, 3)
    g.add_edge(3, 3)

    print("DFS traversal starting from node 2:")
    g.dfs(2)  # Start the DFS from node 2
