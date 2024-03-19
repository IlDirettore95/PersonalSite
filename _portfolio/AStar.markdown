---
title: A* Implementation and Profiling
permalink: /projects/astar/
excerpt: "3D Adventure platformer"
header:
  teaser: /assets/img/AStar.gif
AStar:
  - image_path: /assets/img/AStar.gif
    alt: "AStar"
sidebar:
  - title: "Role"
    text: " <ul>
                <li>Programmer</li>
            </ul>"
  - title: "Responsibilities"
    text: " <ul>
                <li>A* implementation</li>
                <li>World representation</li>
                <li>Performance measurement</li>
            </ul>"
  - title: "Engine"
    text: " <ul>
                <li>No engine</li>
            </ul>"
  - title: "Tech"
    text: " <ul>
                <li>C++</li>
                <li>STL library</li>
            </ul>"
  - title: "Team size"
    text: " <ul>
                <li>2 people</li>
            </ul>"
  - title: "Time"
    text: " <ul>
                <li>1 week</li>
            </ul>"
---
{% include gallery id="AStar"%}
## Intro to A*
This is an implementation of the famous A* algorithm. 
This algorithm is primarly used in movement planning and solves the following problem:

*Does a path exist between two points A and B? And if it does, which is the best?* 
{: style="text-align: center; margin-top: 2em"}

The algorithm operates on a graph data structure and it can be visualized on the console terminal.
For semplicity, a grid is created and then converted to a graph, which is then passed to the algorithm as input.

All the techniques used are described in the book "AI for Games" written by *Ian Millington*. 

## Implementation
The algorithm tries to find a good path between two points A and B guided by a heuristic function. In this case, we used the euclidean distance.
This means it "thinks" that approaching to the target as the agent could fly is a good approximation. 
As Millington stated this is a good choice for outdoor maps, where there is a lot of movement freedom but performs badly in an indoor ones.

For every iteration, a good node is chosen between the opened ones, that is a node adjacent to an already visited node which is labeled as not visited yet.
The cost of a node is calculated by the sum of the cost to arrive to the current one and the estimated cost given by the heuristic.

If there are no more open nodes and the goal was never reached, then a path won't exists.

### Node Array A*
The author proposes an implementation which ereases the need of a closed list.

### Heap Node Array A*
L'algoritmo usa un grafo non diretto, il quale stato definito con una struttura dati persoanlizzata.

## Profiler
Le migliorie sono state certificate da un scope Profiler ispirato da quello esposto da TheCherno.