# Dijkstra's Algorithm
Dijkstra's Algorithm is an algorithm for finding the shortest path between one source node and all the other nodes in a graph, thereby producing a `shortest-path-tree`.
### Psuedo Code
```python
# Set the distances if all nodes in the graph to infinty
for node in graph:
    node.distance = INFINITY

# Create an empty list
nodes = []

# Set the start distance to ZERO
START.distance = 0

# Add start to the list
nodes.add(START)

# Loop to update distances
while nodes is not empty:
    CURRENT = argmin(node, criteria=node.distance)

    if CURRENT == GOAL:
        report "Success"
        break

    for adjacent_node in CURRENT.adjacent_nodes:
        if adjacent_node.distance > CURRENT.distance + cost of edge from CURRENT to adjacent_node:
            adjacent_node.distance = CURRENT.distance + cost of edge from CURRENT to adjacent_node
            adjacent_node.parent = CURRENT

            # Add adjacent_node to the list, if it is not already present
            if adjacent_node not in nodes:
                nodes.add(adjacent_node)
```
### References:
1. Psuedo Code for Dijkstra's Algorithm can be found [here](http://www.gitta.info/Accessibiliti/en/html/Dijkstra_learningObject1.html)
2. A video explaining Dijkstra's Algorithm can be found [here](https://www.youtube.com/watch?v=GazC3A4OQTE)
