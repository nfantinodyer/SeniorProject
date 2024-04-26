# Machine Learning Models: Evolutionary vs Q-Learning

## Objective
The objective of this project was to compare machine learning models to determine which is most effective at navigating to the end of a maze.

## Models Used
- Evolutionary Model
- Q-Learning Model
- A* Algorithm

## Designs

### Maze Environment
- **Size:** 10x10 grid
- **Complexity:** Maze is randomly generated so the paths are different every time.
- **Goal State Criteria:** The goal and start positions are also chosen randomly within the maze.

### Q-Learning
- **Rewards and Penalties:** Each step incurs a -0.05 reward to encourage efficiency, with a +1 reward for reaching the goal.
- **Reset:** After completing 50 steps or reaching the goal, the model resets, storing the episode’s data in the Q-table.

### Evolution
- **Genes:** Each creature is randomly assigned 50 genes corresponding to moves (left, right, up, down).
- **Selection Process:** Post-run, creatures are ranked by fitness; the top two breed, with a 10% mutation rate in the offspring.
- **Fitness:** -10 for hitting a wall, -100 for not reaching the goal, -1 per movement, additional fitness based on proximity to the goal, +1000 for reaching the goal.

### A* Algorithm
- **Optimal Path:** Nodes are created around open blocks adjacent to the start node, expanding towards the closest goal node. Pathfinding continues until the goal is reached, tracing back via ancestor nodes.

## Conclusion
Both the evolutionary and Q-learning models have unique advantages and disadvantages:
- **Evolutionary Model:** Efficiency hinges on the initial gene pool. Can be stuck at dead ends without reaching the goal. Adjusting fitness calculations could mitigate this.
- **Q-Learning Model:** Requires extensive training. Its effectiveness could be enhanced by integrating additional objectives or avoiding hazards.

