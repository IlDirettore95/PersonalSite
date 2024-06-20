---
title: Cyberpunk2077 AI Experiments
order: 1
permalink: /projects/cyberpunk/
excerpt: "AI Experiments"
header:
  teaser: /assets/img/Cyberpunk/CyberpunkScreenShot.png
  overlay_image: /assets/img/Cyberpunk/CyberpunkScreenShot.png
CyberpunkDebugGizmos:
  - url: /assets/img/Cyberpunk/CyberpunkDebugGizmos.png
    image_path: /assets/img/Cyberpunk/CyberpunkDebugGizmos.png
CyberpunkAIDebug:
  - url: /assets/img/Cyberpunk/CyberpunkDebugTool.png
    image_path: /assets/img/Cyberpunk/CyberpunkDebugTool.png
sidebar:
  - title: "Role"
    text: " <ul>
                <li>AI Programmer</li>
                <li>Tool Programmer</li>
                <li>Gameplay Programmer</li> 
            </ul>"
  - title: "Responsibilities"
    text: " <ul>
                <li>AI system</li>
                <li>AI behaviours authoring</li>
                <li>Debug tools</li>
                <li>Data-driven approach for designers</li>
            </ul>"
  - title: "Engine"
    text: " <ul>
                <li>Unreal Engine 5</li>
            </ul>"
  - title: "Tech"
    text: " <ul>
                <li>C++</li>
                <li>Blueprints</li> 
                <li>State Trees</li>
                <li>AIPerception</li>
                <li>Environment Query System (EQS)</li>
            </ul>"
  - title: "Team size"
    text: " <ul>
                <li>5 people</li>
            </ul>"
  - title: "Time"
    text: " <ul>
                <li>Work in progress</li>
            </ul>"
---

[//]: # "DI CHE PROGETTO SI TRATTA"

<h2 id="main_goals" class="" style="margin-top: 0em">Main goals</h2>

This project is a working in progress where I tried to do some experiments within UnrealEngine aiming to simulate Cyberpunk2077 AI.

I implemented an AI system using C++ and Blueprints which reproduce the "local network" of Cyberpunk2077 enemies.
This *zone* is used by enemies to communicate and share information.

I tried to visualize much of the beliefs and decision of the agents through gizmos.

{% include gallery id="CyberpunkDebugGizmos" caption="AI system gizmos."%}

I created a tool that allow the developer to inspect the knowledge base of an AI agent and command some action.

{% include gallery id="CyberpunkAIDebug" caption="AI knowledge inspected through the debug tool."%}