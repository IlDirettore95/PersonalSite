---
title: Steering Behaviours Demonstration
order: 2
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
SeekFlee:
  - url: /assets/img/SteeringBehaviours/SeekFlee.gif
    image_path: /assets/img/SteeringBehaviours/SeekFlee.gif
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

I implemented some of the algorithms mentioned by Ian Millington in his book "AI for Games" and I also used an ECS following the C++ game programming lessons taught by Dave Churchill.
This was a deep dive into the AI movement and the C++ language. I deliberately didn't use an existing game engine like Unreal or Unity to get more hands-on experience with C++ and the so popular ECS architecture.

## Steering vs Kinematic movement
One of the first things to point out is the difference between a kinematic movement algorithm and a steering one.
If the velocity of an agent changes instantly, then a kinematic algorithm should be used. This is not possible in the real world, the velocity of an object can change only if a force is applied (i.e. an acceleration). 
We call a movement algorithm that controls the velocity of an object indirectly through applying an acceleration a "steering behaviour".

Aside from this distinction, this type of algorithm can be used to achieve a variety of things, such as: chasing another agent, avoiding collisions, following a path, etc.

## Steering Behaviours
In this project, I implemented 7 steering behaviours: Seek, Flee, Arrive, Wander, Pursue, Evade and PathFollowing.

{% include gallery id="SeekFlee" caption="The Seek/Flee steering behaviours."%}