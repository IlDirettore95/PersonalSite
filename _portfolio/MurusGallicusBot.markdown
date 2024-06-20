---
title: Murus Gallicus Bot
permalink: /projects/murus-gallicus-bot/
order: 4
excerpt: "Murus Gallicus AI bot"
header:
  teaser: /assets/img/MurusGallicus/MurusGallicus.jpg
  overlay_image: /assets/img/MurusGallicus/MurusGallicus.jpg
  overlay_color: "#000"
  overlay_filter: "0.6"
MurusGallicus:
  - image_path: /assets/img/MurusGallicus/MurusGallicus.jpg
MurusGallicus2:
  - image_path: /assets/img/MurusGallicus/MurusGallicus2.jpg
Algorithm:
  - image_path: /assets/img/MurusGallicus/SearchAlgorithm.jpg
    alt: "Algorithm"
sidebar:
  - title: "Role"
    text: " <ul>
                <li>AI Programmer</li>
            </ul>"
  - title: "Responsibilities"
    text: " <ul>
                <li>Decision Making Layer</li>
            </ul>"
  - title: "Engine"
    text: " <ul>
                <li>No engine</li>
            </ul>"
  - title: "Tech"
    text: " <ul>
                <li>Java</li> 
            </ul>"
  - title: "Team size"
    text: " <ul>
                <li>3 people</li>
            </ul>"
  - title: "Time"
    text: " <ul>
                <li>3 months</li>
            </ul>"
---

[//]: # "DI CHE PROGETTO SI TRATTA"
<h2 id="introduction-to-murus-gallicus-ai-competition" class="" style="margin-top: 0em">Introduction to Murus Gallicus AI competition</h2>

I had an AI course during my master in computer engineering, where every year the entire class partecipates to a competition.
That year, we had to implement a bot playing a board game called Murus Gallicus.

Murus Gallicus is a two-player board game played on a 8x7 board. The objective is reaching the other player's row or leave the opponent without legal moves.
You can look at Murus Gallicus rules <a href="https://www.iggamecenter.com/en/rules/murusgallicus">here</a>.

My group and another one won the competition with 26 victories, 0 ties and 4 defeats.

{% include gallery id="MurusGallicus" caption="Murus Gallicus tournament."%}

[//]: # "DI COSA MI SONO OCCUPATO"
## My Role
I was the responsable for the decision making layer of the bot. This involved experimenting with different search algorithm based on MinMax.

### AI Programming
During the first stage I developed a simple MinMax algorithm and Alpha-Beta Pruning optimization. 
Then, I started experimenting with more advanced algorithms, such as:
 - NegaMax
 - Iterative Deepening
 - Negascout
 - Aspiration window
 - Parallel search

{% include gallery id="Algorithm" caption="Code performed by a thread of the parallel search."%}

 The experiments where guided by metrics I implemented, such as:
  - Move generation speed
  - Move ordering effectiveness with Negascout
  - Profiling code performance

My group and I didn't know about Murus Gallicus and finding another bot online was difficult. So, we had problem measuring our bot strength. 
At the end, we created several versions of the bot with different algorithms, knowledge representations and heuristics, and we established the strongest one
as the winner of a tournament between the versions.

{% include gallery id="MurusGallicus2" caption="I built a simple application to visualize a match."%}

## What I learned
This was my first experience working on an AI. I learned the importance of a practical approach to the problem.
That is, many ideas that sounded perfect didn't work well in practice, so we have been guided more by AI real performances than theoretical promises.

There is another thing I thought was really cool. The other winner had a total different approach. They focused on the heuristic and their search algorithm was very basic, for example,
where they reach level 4 of depth searching, we managed to reach level 8. 
I think that is another proof that experimenting was the best way to determine if the bot was strong or not, it couldn't be decided by design.