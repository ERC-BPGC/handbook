# A-Star Algorithm
A-star is a graph-based, path search algorithm. It is used in many fields of computer science as a search algorithm. It is often used due to its completeness, optimality, and optimal efficiency.
### Salient Features of the Algorithm
1. **Resolution complete** and **Resolution optimal** : The algorithm finds the optimal solution to the given problem at a chosen discretization, if one exits.
2. A-Star uses a **hueristic** to estimate the total cost of a solution constrained to pass through a state. Thus, it searches in order of decreasing solution quality and is *optimally efficient*.
3. Any other optimal algorithm using the same hueristic will expand at least as many vertices as A-Star.
### Idea of Hueristics Functions
- Hueristic functions are used to map every node in the graph to a *non-negative* value.
- #### Criteria for Hueristics Functions
    - Should be a `monotonic function`
    - Should satisfy ```H(goal) = 0```
    - For any two adjacent nodes `x` and `y`:
        ```
            H(x) <= H(y) + d(x, y)
            d(x,y) = weight/length of edge from x to y
        ```
    - These properties ensure that for all nodes n:
        ```
            H(n) <= Length of Shortese Path from node n to goal
        ```
- #### For path Planning on a grid:
    - **Euclidean Distance**
    ```
        H(xn, yn) = sqrt((xn-xg)^2 + (yn-yg)^2)
    ```
    - **Manhattan Distance**
    ```
        H(xn, yn) = abs((xn - xg) + (yn - yg))
    ```
where `xn, yn` and `xg, yg` are the `x, y` coordinates of a the node and the goal respectively.
### Psuedo Code for the Algorithm
```python
def Astar(start, goal, graph):
    # Set the g, f values for all nodes in the graph
    for node in graph:
        node.f = Infinity
        node.g = Infinity

    # Create an empty list to store visited nodes
    nodes = []

    # Add Start to nodes list
    nodes.add(start)

    # Loop to traverse the graph
    while nodes is not EMPTY:
        # Obtain bode with the least f-value
        CURRENT = argmin(node, criteria=node.f)

        # Check if current node is the goal Node
        # which means the graph has been completely traversed
        if CURRENT == goal:
            report "SUCCESS"
            break
        # Update parameters for adjacent nodes
        for adjacent_node in CURRENT.adjacent_nodes:
            if adjacent_node.g > CURRENT.g + cost of edge from n to current:
                adjacent_node.g = CURRENT.g + cost of edge from n to current
                adjacent_node.f = adjacent_node.g + H(node)
                adjacent_node.parent = CURRENT

                # Add the adjacent node to nodes list if not there already
                if adjacent_node not in nodes:
                    nodes.add(adjacent_node)
```
**Notations in the Psuedo Code explained**:
```
g-value = distance between a node and the start node
H-function = Hueristic funciton
f-value = g-value + Hueristic value of the node
```

### References
1. Original [paper](https://ieeexplore.ieee.org/document/4082128) on A-Star path planning algorithm.
2. Psuedo Code can be found [here](https://mat.uab.cat/~alseda/MasterOpt/AStar-Algorithm.pdf)
3. Video explainig A-star can be found [here](https://www.youtube.com/watch?v=5n8OtzqVOyg)