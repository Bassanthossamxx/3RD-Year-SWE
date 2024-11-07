# Lecture 3  "Informed Search and Heuristic Search (A*)"

---
# Greedy algoeithm
## What is a Greedy Algorithm?
- **Definition**: Greedy algorithms select the best immediate option without considering future consequences.
- **Decision-Making**: They do not reverse choices, even if it leads to a suboptimal solution.

## Key Properties for Greedy Algorithms to Work
1. **Greedy Choice Property**: Making the best choice at each step leads to a globally optimal solution.
2. **Optimal Substructure**: The optimal solution contains optimal solutions for its subproblems.

### Example: Finding the Shortest Path
- **Problem**: Find the shortest path between cities.
- **Approach**: Start at the source, select the shortest direct path to the next city, and avoid cycles until reaching the destination.

## Limitations of Greedy Algorithms
- **Locally Optimal, Not Always Globally**: Best local choices may not lead to the best overall solution.
- **Correctness Challenges**: Difficult to prove that the solution is the best.
- **Not Universally Applicable**: Ineffective with negative edges, as in Dijkstra’s algorithm.

## Applications of Greedy Algorithms
1. **Minimum Spanning Trees**: Prim’s and Kruskal’s algorithms.
2. **Huffman Encoding**: Used for lossless file compression.

## Greedy Search Algorithm and the Heuristic Function (h(n))
- **Heuristic Function (h(n))**: Estimates the cost from the current node to the goal.
- **Formula**: \( f(n) = h(n) \) (only relies on the heuristic).
  
## Advantages of Greedy Search
- **Efficiency**: Faster than exhaustive search methods.
- **Memory Usage**: Requires less memory as it tracks only the best paths.
- **Simplicity**: Easy to implement due to its direct approach.

## Disadvantages of Greedy Search
- **Non-Optimal**: May not yield the shortest or best solution.
- **Incomplete**: May not find a solution if there are dead ends.
- **Heuristic Dependency**: Performance heavily relies on the quality of the heuristic.

--- 
# A* Algorithm

## How A* Algorithm Works
- **Formula Components**: A* uses two main functions:
  - **g(n)**: The actual cost from the start node to the current node \(n\).
  - **h(n)**: A heuristic that estimates the cost from the current node \(n\) to the target node.
- **Total Cost Estimation**: The algorithm calculates \( f(n) = g(n) + h(n) \) to estimate the total cost from the start to the target node.

## Advantages of A* Algorithm
1. **Optimal Solution**: Finds the shortest path if the heuristic is admissible (never overestimates the actual cost).
2. **Completeness**: Always finds a solution in a finite graph if one exists.
3. **Memory Efficiency**: More efficient than algorithms like BFS as it stores fewer nodes.
4. **Customizable Heuristics**: Can adjust performance by fine-tuning heuristics.
5. **Real-Time Applications**: Works well in dynamic environments (e.g., web search, robotics).

## Disadvantages of A* Algorithm
1. **Heuristic Dependency**: Performance depends on the heuristic's accuracy.
2. **High Memory Usage**: Requires storing all explored nodes, which can become costly in large graphs.
3. **Time Complexity**: Can be slow for large graphs with less accurate heuristics.
4. **Bottlenecks**: May explore distant nodes unnecessarily if the heuristic isn’t ideal.
---

# Applications of A* in AI
1. **Pathfinding in Games**: Used for AI character movement.
2. **Robotics & Autonomous Vehicles**: Assists in optimal route planning while avoiding obstacles.
3. **Maze Solving**: Finds the shortest route through complex mazes.
4. **Route Planning in GPS**: Optimizes routes by considering traffic and distance.
5. **Puzzle Solving**: Applied to problems like the 8-puzzle, Sudoku, and resource allocation.
6. **Network Routing**: Determines efficient paths for data packets in networks.
