# Delivery-Robot-Path-Planning-AI-

Overview
This project presents a delivery robot path-planning simulation using the Q-Learning reinforcement learning algorithm. The robot is designed to navigate a grid environment from a defined start location to a goal destination while avoiding random obstacles. The project also compares the performance of multiple search and optimization algorithms for path planning, including informed, uninformed, and local search techniques.

1. Environment Description
A 10x10 and 30x30 grid environment.
Start position: (0, 0); Goal position: (9, 9) or (29, 29).
The robot must avoid randomly placed obstacles.
Action Space
Up
Down
Left
Right
Transition Function
Moves to neighboring cells unless obstructed or out-of-bounds.
2. Q-Learning Algorithm
The robot learns optimal actions through Q-Learning, balancing exploration and exploitation.

Key Parameters
Alpha: 0.1 (Learning Rate)
Gamma: 0.9 (Discount Factor)
Epsilon: 1.0 (Initial Exploration Rate)
Epsilon Decay: 0.99
Minimum Epsilon: 0.1
Episodes: 1000
Key Functions
is_valid_state(state): Validates state within grid and avoids obstacles.
take_action(state, action): Determines the next valid state.
get_reward(state): Rewards: +100 for goal, -10 for obstacle, -1 per move.
3. Implementation and Results
The robot was trained over 1000 episodes.
Gradual improvement in learning as epsilon decays.
Final policy is represented through a Q-table.
The robot learns to avoid obstacles and reach the goal efficiently.
4. Search Algorithm Comparison
Uninformed Search
BFS: Complete, optimal (O(b^d))
DFS: Incomplete, non-optimal
UCS: Complete, optimal for uniform cost
IDS: Complete, optimal, memory-efficient
Informed Search
Greedy Best-First Search (GBFS): Fast but not optimal
A*: Complete and optimal with admissible heuristic
Heuristics Used
Manhattan Distance
Euclidean Distance
Local Search
Hill Climbing: Fast but gets stuck in local minima
Simulated Annealing: Escapes local minima probabilistically
Genetic Algorithm: Evolves solutions but time-consuming
5. Summary of Algorithm Performance
| Algorithm            | Time Complexity              | Space Complexity | Completeness       | Optimality      |
|----------------------|------------------------------|------------------|--------------------|-----------------|
| BFS                 | O(b^d)                       | High             | Yes                | Yes             |
| DFS                 | O(b^m)                       | Low              | No                 | No              |
| UCS                 | O(b^(1 + C/ε))               | High             | Yes                | Yes             |
| IDS                 | O(b^d)                       | Low              | Yes                | Yes             |
| GBFS                | O(b^d)                       | Low              | Sometimes          | No              |
| A*                  | O(b^d)                       | High             | Yes                | Yes             |
| Hill Climbing       | O(n)                         | Very Low         | No                 | No              |
| Simulated Annealing | Variable                     | Medium           | No                 | Near-optimal    |
| Genetic Algorithm   | O(p * g)                     | High             | Yes (eventual)     | Possibly        |

6. Conclusion
This project demonstrates the effectiveness of Q-Learning in enabling autonomous navigation in grid-based environments. It also provides a comparative study of classical and heuristic-based search algorithms for solving the pathfinding problem. Among all, A* and BFS prove to be both complete and optimal for grid navigation, while local search methods offer useful alternatives for approximate solutions in complex or high-dimensional spaces.

