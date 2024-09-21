---
title: Steering Behaviours Demonstration
order: 1
permalink: /projects/steering-behaviours/
excerpt: "Steering Behaviours Demonstration"
header:
  teaser: /assets/img/SteeringBehaviours/PathFollowing.gif
  overlay_image: /assets/img/SteeringBehaviours/PathFollowing.gif
  overlay_color: "#000"
  overlay_filter: "0.4"
  actions:
    - label: "Go to Github"
      url: "https://github.com/IlDirettore95/AIExperiments/tree/main"
Presentation1:
  - url: /assets/img/SteeringBehaviours/Configs.png
    image_path: /assets/img/SteeringBehaviours/Configs.png
Presentation2:
  - url: /assets/img/SteeringBehaviours/PathFollowing.png
    image_path: /assets/img/SteeringBehaviours/PathFollowing.png
SeekFlee:
  - url: /assets/img/SteeringBehaviours/SeekFlee.gif
    image_path: /assets/img/SteeringBehaviours/SeekFlee.gif
Arrive:
  - url: /assets/img/SteeringBehaviours/Arrive.gif
    image_path: /assets/img/SteeringBehaviours/Arrive.gif
Wander:
  - url: /assets/img/SteeringBehaviours/Wander.gif
    image_path: /assets/img/SteeringBehaviours/Wander.gif
PathFollowing:
  - url: /assets/img/SteeringBehaviours/PathFollowing.gif
    image_path: /assets/img/SteeringBehaviours/PathFollowing.gif
sidebar:
  - title: "Role"
    text: " <ul>
                <li>AI Programmer</li>
                <li>Tool Programmer</li>
            </ul>"
  - title: "Responsibilities"
    text: " <ul>
                <li>AI movement</li>
                <li>ECS </li>
                <li>Debug tools</li>
            </ul>"
  - title: "Engine"
    text: " <ul>
                <li>No engine</li>
            </ul>"
  - title: "Tech"
    text: " <ul>
                <li>C++</li>
                <li>STL</li>
                <li>SFML</li> 
            </ul>"
  - title: "Team size"
    text: " <ul>
                <li>Solo project</li>
            </ul>"
  - title: "Time"
    text: " <ul>
                <li>1 month</li>
            </ul>"
---

[//]: # "DI CHE PROGETTO SI TRATTA"

<h2 id="main_goals" class="" style="margin-top: 0em">Project Overview</h2>

This project is a demonstration of some of the most popular steering behaviours.

It is completely implemented in C++. A simple ECS is used as game architecture and the SFML library handles the graphics backend.
The steering parameters are editable through a GUI window implemented using IMGUI.

I implemented some of the algorithms mentioned by Ian Millington in his book *AI for Games* and I also built an ECS following the C++ game programming lessons taught by Dave Churchill.
This was a deep dive into the AI movement and the C++ language. I deliberately didn't use an existing game engine like Unreal or Unity to get more hands-on experience with C++ and the so popular ECS architecture.

{% include gallery id="Presentation1"%}
{% include gallery id="Presentation2" caption="Configs window and the Path Following debug gizmos."%}

## Kinematic and Steering movement
Movement algorithms use data to represent agents. We call *static* data the position and orientation of an agent and *dynamic* data its velocity and angular velocity.

A kinematic movement algorithm operates on static data and its output is a new velocity and rotation. This imply that an agent's velocity (or orientation) can change instantly.
In the real physical world an object velocity can change only if a force is applied (i.e. an acceleration). A steering movement algorithm tries to achieve that taking dynamic data into account and producing accelerations as outputs.

Aside from this distinction, this type of algorithm can be used to achieve a variety of things, such as: chasing another agent, avoiding collisions, following a path, etc.

## Steering Behaviours
In this project, I implemented 7 steering behaviours: Seek, Flee, Arrive, Wander, Pursue, Evade and PathFollowing.

### Seek and Flee
One of the simplest family of steering algorithm try to match a variable of a target position or orientation.
For example, a Seek behaviour tries to match agent's position to a target's one accelerating the agent towards the target.
This algorithm is meant to be used on a chasing agent. If the agent reaches the target it will overshoot it and will start to orbit around it.

A Flee behaviour can be obtained negating the acceleration output of the Seek behaviour.

{% include gallery id="SeekFlee" caption="The Seek/Flee steering behaviours."%}

### Arrive
The Arrive behaviour works similarly to a Seek, but, as the agent gets close to the target, it will start to slowing it down and, eventually, stop it when the target is reached.

{% include gallery id="Arrive" caption="The Arrive steering behaviour."%}

### Pursue and Evade
Pursue and Evade are ones of the so called "delegated behaviour". A delegated behaviour uses another steering behaviour to produce its output (e.g. in this case a Seek algorithm is used).
The agent aims to a future position based on the target's current one and its velocity.

An Evade behaviour can be obtained negating the acceleration output of the Pursue behaviour.

### Wander
The Wander behaviour can be used to simulate an agent that moves *randomly* in the environment. It is implemented using the Face behaviour which uses the Align behaviour.
It creates a target that moves randomly on a circumference in front of the agent. It uses the Face behaviour to rotate the agent towards that location and then accelerate the agent towards it.

{% include gallery id="Wander" caption="The Wander steering behaviour."%}

### Path Following
This behaviour allows an agent to follow a path given as input. The path is a sequence of locations. 
Two adiacent locations are linked with a straight line and the distances between adiacent points are all precomputed.

Path Following computes two things:
 - the projection of the agent position on the path
 - a forward offset position that is used as a target for a Seek behaviour

The latter is fairly easy to compute. The first one, instead, is much more complicated. Given the current agent's position finding its counterpart on the path is an ambiguous problem.
One could try to project the point on every path segment, discarding every projection that ended outside of the path and maybe choosing the closest to the agent's location, but this can cause problems if there are two close segments.
I chose to use the last projection as a guide. The output is the *next* projection found starting from the last one.

I found a flaw in this approach. 
If the projection is on a segment, the Seek target ends up to be on the next one and the angle between these two adiacent segments is sharp enough, depending on the steering this behaviour can get the agent *stuck*. 


{% include gallery id="PathFollowing" caption="The Path Following steering behaviour."%}