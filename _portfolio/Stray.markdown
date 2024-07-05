---
title: Stray
permalink: /projects/stray/
order: 4
excerpt: "3D Adventure Platformer"
header:
  teaser: /assets/img/Stray/StrayOverview.gif
  overlay_image: /assets/img/Stray/StrayOverview.gif
  overlay_color: "#000"
  overlay_filter: "0.4"
  actions:
    - label: "Go to Github"
      url: "https://github.com/IlDirettore95/VR_Project/tree/main/Unified2/Assets/Scripts"
Stray:
  - image_path: /assets/img/Stray/StrayOverview.gif
    alt: "Stray"
sidebar:
  - title: "Role"
    text: " <ul>
                <li>Gameplay Programmer</li>
                <li>UI Programmer</li>
                <li>Level Designer</li> 
                <li>Music Producer</li>
            </ul>"
  - title: "Responsibilities"
    text: " <ul>
                <li>Character controller implementation</li>
                <li>Character statistics and abilities</li>
                <li>Interaction system</li>
                <li>Tutorial design and implementation</li> 
                <li>Plot events</li>
            </ul>"
  - title: "Engine"
    text: " <ul>
                <li>Unity3D</li>
            </ul>"
  - title: "Tech"
    text: " <ul>
                <li>C# </li>
            </ul>"
  - title: "Team size"
    text: " <ul>
                <li>3 people</li>
            </ul>"
  - title: "Time"
    text: " <ul>
                <li>5 months</li>
            </ul>"
---

<h2 id="what_i_learned" style="margin-top:0em">What I learned</h2>

This was a deep dive into Unity and Game Programming. 

I made use of 3D math and the Unity physics engine to control the main character and manipulate objects.
I applied my knowledge of algorithms and data structures and games to implement gameplay features effectively.
I used many features of the Unity Engine such as scripting, physics, UI and rendering.

## Intrduction to Stray

Stray (not that one!) was a group project I did during a Game Programming course at the University of Calabria and also my first Unity project.

In this game the main character is a robot that tries to escape from a spaceship called Prometheus. 
The main enemy is the spaceship AI that tries to stop the robot by blocking doors and alarming other robots in the area.

The main mechanics of this game are:
- **Character movement**
    - Walking
    - Running
    - Jumping
    - Crouching
    - Jetpack
- **Gravity powers** (very similar to HalfLife2 Gravity Gun)
- **Interact** with objects
- Slaying two types of **enemies**: Drones and Mining Spiders 

{% include gallery id="Stray" caption="Overview of Stray's mechanics."%}

## My Role
I worked on several mechanincs using 3D vector maths concepts and Unity's Physics library. 

I also explored many Unity's features:
- C# Scripting
- RigidBody Physics
- UI
- Rendering
    - All types of light
    - Light backing
    - Light probes
    - Reflection probes
    - Emissive materials
    - PostProcessing
- Particle System

Finally, I also worked to the level design and music production for the game.

### Character Controller
The main character movement is based on Unity's CharacterControllerComponent. It checks for the users' input and act accordingly to the current "state".
The state is gathered querying the geometry around the players using raycasts (e.g. checking if they are gorunded, if they can jump or stand up).
The actuation of the movement is not physics based, every tick the next position in calculated and used to move the underlying CharacterMovementComponent.

### Gravity powers
Forces are used to implement the main character's powers. These powers let the player grab, for a certain duration, every object that are interactable (even the enemies).
This can be used to reach high places or throw object to enemies (or enemies to walls).