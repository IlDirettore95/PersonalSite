---
title: Procedural2DPlatformer
permalink: /projects/procedural-2d-platformer/
excerpt: "2D Procedural Platformer"
order: 5
header:
  teaser: /assets/img/Procedural2DPlatformer/LevelGeneration.gif
  overlay_image: /assets/img/Procedural2DPlatformer/LevelGeneration.gif
  overlay_color: "#000"
  overlay_filter: "0.6"
  actions:
    - label: "Go to GitHub"
      url: "https://github.com/IlDirettore95/Basic_2D_Platformer/tree/main"
StateMachine:
  - url: /assets/img/Procedural2DPlatformer/STDiagram.png
    image_path: /assets/img/Procedural2DPlatformer/STDiagram.png
StateMachineImplementation:
  - url: /assets/img/Procedural2DPlatformer/STImplementation.png
    image_path: /assets/img/Procedural2DPlatformer/STImplementation.png
Debug:
  - url: /assets/img/Procedural2DPlatformer/Debug.gif
    image_path: /assets/img/Procedural2DPlatformer/Debug.gif
Tool1:
  - url: /assets/img/Procedural2DPlatformer/PCGTool1.png
    image_path: /assets/img/Procedural2DPlatformer/PCGTool1.png
Tool2:
  - url: /assets/img/Procedural2DPlatformer/PCGTool2.png
    image_path: /assets/img/Procedural2DPlatformer/PCGTool2.png
Tool3:
  - url: /assets/img/Procedural2DPlatformer/PCGTool3.png
    image_path: /assets/img/Procedural2DPlatformer/PCGTool3.png
Tool4:
  - url: /assets/img/Procedural2DPlatformer/PCGTool4.png
    image_path: /assets/img/Procedural2DPlatformer/PCGTool4.png
Generation:
  - url: /assets/img/Procedural2DPlatformer/LevelGeneration.gif
    image_path: /assets/img/Procedural2DPlatformer/LevelGeneration.gif
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
<h2 id="introduction" style="margin-top: 0em">Introduction</h2>

For project I had to build a 2D platformer using some form of PCG to build three levels. 

## My Role
I focused on the **character controller** and the **procedural content generation**.
Then, I used a **data-driven** approach to the pcg to help me tweaking the parameters for the level generation.

### Character controller
The book *AI for Games* by Ian Millington inspired me to use an AI agent structure for the character controller.

{% include gallery id="StateMachine" caption="Character movement State Machine diagram."%}

User input is handled as information captured by some *sensors*. Input and a geometry analysis of the level around the character consitutes the agent's *knowledge*.
The decision making is implemented through **state machine**. 

{% include gallery id="StateMachineImplementation" caption="Character movement State Machine C# implementation."%}

I used visual debug features to help while building the controller.

{% include gallery id="Debug" caption="Some visual debug for the character controller."%}

The controller implements some classic jump mechanics:
- **Coyote time**
- **Jump buffer**
- **Dynamic gravity**
- High of jump linked to key holding (the jump will be much shorter if the key is released earlier)

### PCG and tooling
I experimented with the **wave function collapse** algorithm to generate a platformer level. 
I designed several chucks for each level and defined constraints for them.

All the data the algorithm works on (settings, constraints, etc.) is defined using a data driven through a XML file.
I developed a tool inside Unity to edit this file directly in engine with a functional UI.

{% include gallery id="Tool1" %}
{% include gallery id="Tool2" %}
{% include gallery id="Tool3" %}
{% include gallery id="Tool4" caption="Custom tool to edit WFC settings."%}

I used Unity's coroutine to let the user decide to construct the level in one frame or performing an animation of the algorithm. 
This was really helpful during the development.

{% include gallery id="Generation" caption="Animation of a level generation."%}