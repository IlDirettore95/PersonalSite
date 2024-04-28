---
title: Trauma
order: 1
permalink: /projects/trauma/
excerpt: "3D Survival Horror"
header:
  teaser: /assets/img/Trauma/TraumaAppeared.gif
  overlay_image: /assets/img/Trauma/TraumaAppeared.gif
Trauma:
  - image_path: /assets/img/Trauma/Trauma.png
TraumaStateMachine:
  - url: /assets/img/Trauma/TraumaStateMachineDiagram.png
    image_path: /assets/img/Trauma/TraumaStateMachineDiagram.png
TraumaStateTree:
  - url: /assets/img/Trauma/TraumaStateTree.jpg
    image_path: /assets/img/Trauma/TraumaStateTree.jpg
TraumaMetaSoundData:
  - url: /assets/img/Trauma/TraumaMetaSoundInput.png
    image_path: /assets/img/Trauma/TraumaMetaSoundInput.png
  - url: /assets/img/Trauma/TraumaMetaSoundDataPassing.png
    image_path: /assets/img/Trauma/TraumaMetaSoundDataPassing.png
TraumaMetaSoundExamples:
  - url: /assets/img/Trauma/TraumaMetaSoundStatsFeedback.png
    image_path: /assets/img/Trauma/TraumaMetaSoundStatsFeedback.png
  - url: /assets/img/Trauma/TraumaMetaSoundInvestigationBrutalizer.png
    image_path: /assets/img/Trauma/TraumaMetaSoundInvestigationBrutalizer.png
sidebar:
  - title: "Role"
    text: " <ul>
                <li>AI Programmer</li>
                <li>Gameplay Programmer</li> 
                <li>Audio Programmer</li>
                <li>Music Producer</li>
                <li>Light Artist</li>
            </ul>"
  - title: "Responsibilities"
    text: " <ul>
                <li>Monster AI</li>
                <li>AI-world interfacing</li>
                <li>Interaction between gameplay and audio</li>
            </ul>"
  - title: "Engine"
    text: " <ul>
                <li>Unreal Engine 5</li>
            </ul>"
  - title: "Tech"
    text: " <ul>
                <li>Blueprints</li> 
                <li>Behaviour Trees</li>
                <li>State Trees</li>
                <li>AIPerception</li>
                <li>Environment Query System (EQS)</li>
                <li>MetaSound</li>
            </ul>"
  - title: "Team size"
    text: " <ul>
                <li>8 people</li>
            </ul>"
  - title: "Time"
    text: " <ul>
                <li>3 months</li>
            </ul>"
---

[//]: # "DI CHE PROGETTO SI TRATTA"
<h2 id="introduction-to-trauma" class="" style="margin-top: 0em">Introduction to Trauma</h2>

Trauma is a **3D First Person Survival Horror** project I have worked on during the DBGA Game Programming course.
The game is about proceeding through a story, solving puzzles and being hunted by a monster called Trauma.

Some of the most important mechanics are:
- Two main stats: *mental health* and *fear* 
    - Mental health is the same as "health"
    - Fear increases if the players stay in the dark or are chased by the Trauma
- **Interaction** with some objects:
    - Using **matches** to light **candles**   
    - **Pickup** objects
    - Open/close closets to hide from the monster
- Using the **torch**:
    - Explore dark areas
    - Slay/stun enemies
- Rest in a **safe room**
    - Save the game

[//]: # "DI COSA MI SONO OCCUPATO"
## My Role
I worked on:
- Monster AI
- Various interactions between the AI and environment
- Audio programming of loops and audio effects to give feedbacks to the players
- Helping/Bugfixes on other gameplay features

### AI Programming
My primarly role was architecting and implementing the main AI. 
I started investigating Unreal tools for AI and researching ways to model an agent of this kind.

{% include gallery id="TraumaStateMachine" caption="Trauma AI State Machine diagram."%}

{% include gallery id="TraumaStateTree" caption="Trauma AI State Machine implementation."%}

The Trauma has two "modes":
- *Back mode*
- *Front mode*

While in the back mode, it is invisible and it teleports in random places, searching for the players. 
It reacts to high fear and noises and, if it does, it will switch to front mode.
The players can detect it by hearing its noises.

In front mode, the monster patrols between random rooms searching for the player. 
If it hears or sees something, it will start investigating that location. 
Then, if the players are detected, a chase will start.

### AI-world interfacing
The AI needs information about the world. This is done mainly using Unreal **AIPerception** system, but there is more to it.
When the players enters the safe room, the Trauma disappears switching to the "None" state. 

If the players can't be found during a chase, the monster will go searching around for *hiding spots*.

The players have a *light score* that is used to determine how well the monster can see them.
When the players are in Trauma's sight cone they are not detected instantly. 
If the monster's sight is stimulated enough, it will try to investigate towards that location and, eventually, will detect the players.

### Audio Programming
Gameplay interfacing with SFX and Music has been made using Unreal Engine 5 MetaSound. 

Gameplay variables and events are sent to a Master MetaSound which then propagates information to specialized ones.
This approach let me test the audio of (almost) the entire main game loop directly on the Master MetaSound asset.

{% include gallery id="TraumaMetaSoundData" caption="Gameplay events and data sent to MetaSound and then propagated to other ones."%}

Several techiques, for example, low pass filters and adjustments on volume or pitch, were used to emphasize game loop situations. 

{% include gallery id="TraumaMetaSoundExamples" caption="MetaSound examples to shape audio according to gameplay data."%}

## What I learned
This was my team's first Unreal project and the biggest one we worked on during the DBGA Game programming course. 
Hence, we decided to only use Blueprints to make our life easier while exploring the Unreal toolset.

I worked side by side with a designer on the iterations on the Trauma AI.
We started using Behaviour Trees, but it was quickly clear that our ideas were very "state driven" and hierarchical.
Hence, we switched to Unreal's new State Tree.

I worked following the agent architecture presented in *Artificial Intelligence: A Modern Approach* by Russel and Norvig, trying to adapt to the Unreal framework.
Moreover, I researched various techniques presented in *AI for Games* by Ian Millington.

In summary, I used several tools provided by Unreal Eninge 5:
- Blueprints
- Behaviour Trees
- State Trees
- AI Perception
- EQS (Environment Query System)
- MetaSound