# Lecture 4: Game Playing and Adversarial Search
---

## Adversarial Search & Game-Playing
- **Definition**: Planning strategies in competitive settings with opposing goals.
- **Examples**: Board games like chess, checkers.
- **Environment Characteristics**:
  - **Fully Observable**: Both players see the full game state.
  - **Discrete & Multi-Agent**: Turn-based interactions between two players.
  - **Sequential**: Actions alternate between two agents.

---

## Minimax Algorithm (Main Algorithm for Adversarial Search)
- **Purpose**: Aids in decision-making for two-player games.
- **Goal**: Optimize one’s outcome while minimizing the opponent’s.
- **Types**:
  1. **Exhaustive Minimax for Nim (Splitting Stacks)**: Explores entire game trees for optimal strategies (e.g., Nim game).
  2. **Minimax to Fixed Depth**: Limits search to a specified depth, using heuristics to estimate values at that depth, reducing computation.
  
- **Minimax**: Computes the optimal strategy for MAX, assuming MIN plays optimally.
  - **Look-ahead**: Calculates values at terminal nodes and propagates them backward.
  - **Minimax Decision**: MAX chooses the highest value, considering MIN’s best responses.

- **Steps**:
  1. **Generate Game Tree**: From the current position to terminal states.
  2. **Apply Utility Functions**: At terminal nodes.
  3. **Propagate Values**: Up the tree, with MIN nodes choosing minimums and MAX nodes choosing maximums.
  
- **Properties**:
  - **Complete**: If the tree is finite.
  - **Optimal**: Given both players play optimally.
  - **Complexity**: Time: O(b^m), Space: O(bm), where `b` is the branching factor and `m` is the depth.

---

## Game Tree
- **Search Tree**: Represents all possible moves and outcomes.
- **Tree Size**: Determined by branching factor (b) and depth (d): 𝑶(𝒃^𝒅).
  - For example, in chess: b ~ 35, d ~ 100, creating impractically large search spaces.

---

### Alpha-Beta Pruning
- **Purpose**: Optimizes minimax by cutting off branches that won’t affect the final decision.
  - **Alpha (for MAX)**: The best score MAX can achieve.
  - **Beta (for MIN)**: The best score MIN can achieve.

- **Process**:
  1. Initialize alpha = -∞ and beta = +∞.
  2. Update alpha/beta values during tree traversal.
  3. Prune branches where alpha >= beta.

- **Evaluation Functions**:
  1. **Evaluation Function**: Estimates the value of a board configuration.
     - Example: Chess (difference in piece values), Othello (difference in disc count).
     - Typically ranges from -∞ (loss) to +∞ (win).
  2. **Heuristic Techniques**: Techniques like the null-move heuristic to improve efficiency.

---

### Heuristic Search Techniques
- **Purpose**: Use heuristics to avoid exhaustive search, especially in vast search spaces.
- **Handling Diverse Variables**:
  - **Continuous Variables**: Such as numeric values.
  - **Discrete Categories**: Example, categorical values like “A, B, C.”
  - **Boolean**: Example, true/false conditions.

- **What Are Heuristics?**
  - **Definition**: Strategies that find good solutions efficiently without exploring the entire solution space.
  - **Application**: Used in search algorithms to speed up decision-making processes.

- **Examples**:
  - **A***: Finds optimal paths by combining cost with heuristics.
  - **Greedy Search**: Chooses immediate best moves, though it may get trapped in local optima.
  - **Genetic Algorithms**: Inspired by natural selection, explores large search spaces but doesn’t guarantee a global optimum.
