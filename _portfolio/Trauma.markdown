---
title: Trauma
permalink: /projects/trauma/
excerpt: "3D Survival Horror"
header:
  teaser: /assets/img/TraumaAppeared.gif
Trauma:
  - image_path: /assets/img/Trauma.png
    alt: "Trauma"
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
                <li>AI world interfacing</li>
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
{% include gallery id="Trauma"%}
## Introduction to Trauma

Trauma is a 3D First Person Survival Horror project I have worked on during the DBGA Game Programming course.
 
In this game the players must solve puzzles and proceed through the story while hunted by a monster called Trauma.

The main mechanics of this game are:
- Staying in the dark build up your **fear**
- Using a **torch** to see better and slay/stun enemies
- Using **matches** to light **candles**
- **Interact** with objects
- **Pickup** objects


## What I have done

I worked on the monster AI, the interaction between AI and environment, and the audio programming of various effects and loops that give feedbacks to the players.

I used various technologies provided by Unreal Engine 5:
- Behaviour Trees
- State Trees
- AI Perception
- EQS (Environment Query System)
- MetaSound

This was our first project with Unreal and the one with the biggest scope we ever worked on, so we decided to do it entirely in Blueprints.

### AI and Gameplay Programming

My role has been primarly to architect and implement the main AI of the game.

I started investigating Unreal tools for AI and researching for ways to model such an agent.

The monster has two modes: the Front mode and the Back mode. 
In the Front mode it patrols and reacts to the sight of the players and to noises. 
During the Back mode it teleports in different locations on the map, trying to hear noises or to feel players' fear.
Moreover, during the Front mode, the AI can be in one of the three states: Patrolling, Investigation and Chasing.

It has been clear from the start that my ideas and the designer's ones were very "state driven" and hierarchical. 
This, after several research on the book "AI for Games" by Ian Millington and on GDC talks, drove me away from the idea of using Behaviour Trees for the decision making phase. 
So I decided to give Unreal State Trees a shot and they paid off.

I worked also on some interaction the monster has with the players and the environment, such as interacting with closets where the players can hide and a score to estimate the main character's visibility.

### Audio Programming

Gameplay interfacing with SFX and Music has been made using Unreal Engine 5 MetaSound. 

Gameplay variables and events are sent to a Master MetaSound which then propagates information to specialized ones.
This approach let me test the audio of (almost) the entire main game loop directly on the Master MetaSound asset.

## What I have learned

This project was helpful to start using Unreal toolset. My takaway from the AI programming on this demo is that AI is a design problem first of all. 
We did a lot of things that sounded great on paper but were unoticeble while playing.
Regarding the implementation, I worked following the agent architecture presented by "Artificial Intelligence: A Modern Approach" by Russel and Norvig, trying to adapt to the Unreal framework.
I learned how to use gameplay events and variables to drive audio feedbacks using MetaSound and to test them easely.

For the next Unreal projects I will use C++ combined with Blueprints and dive in more complex AI reasoning. I am still reaserching about AI modeling, expecially making it clean and flexible.

