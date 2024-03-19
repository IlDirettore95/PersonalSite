---
title: Procedural2DPlatformer
permalink: /projects/procedural-2d-platformer/
header:
  teaser: /assets/img/Procedural2DPlatformerGeneration.gif
sidebar:
  - title: "Role"
    text: " <ul>
                <li>Gameplay Programmer</li>
                <li>Tool Programmer</li>
            </ul>"
  - title: "Responsibilities"
    text: " <ul>
                <li>Character controller implementation</li>
                <li>Dedicated tool for the procedural generation</li>
            </ul>"
  - title: "Engine"
    text: " <ul>
                <li>Unity3D</li>
            </ul>"
  - title: "Tech"
    text: " <ul>
                <li>C#, PCG, State machines and Unity custom windows</li>
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

For project I had to build a 2D platformer using some form of PCG to construct the level. 

## What I have done

I focused on the Character controller and for the PCG I used Wave Function Collapse to compose the level from several predesigned chunks. 
I also explored a Data driven approach that lead me building a tool to help designers using my algorithm. 

The tool let you create a level, decide which type of chunks to use and for each one dece its constraints. This date can be then saved in an XML file.

For the character controller, I used a state machine and architected it like an AI following the structure illustrated by Ian Millington in "AI for Games". 
In this case, user input are treated as knowledge captured by sensors. The WFC algorithm was built trying to let it being debuggable. 
I used Unity's coroutine to let the user decide to construct the level in one frame or starting an animation of the algorithm that was really helpful during the development.