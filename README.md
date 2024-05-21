# Best Pokémon Team

## Abstract

This bachelor's thesis concerns itself with the finding of the best Pokémon Team under several given assumptions. With the Pokémon franchise now encompassing over 1000 Pokémon and additional ~100 being released every generation, each with their own set of stats and features, identifying the best team poses a very challenging question. This Study makes use of a dataset and uses different approaches to find the best pokemon team. The methodology includes simulation of battles between individual pokemon and teams and also several graph theory approaches to find the best team. We can show that the selection of our algorithm is significantly better than a more common selection technique employed by most players. This work is not only interesting for the pokemon community by providing them with a scientific approach of team selection but has its roots in many optimization problems such as ?. Future research directions could include a less restricted definition of the problem statement and including more probabilities.

## Table of Contents
<details>
<summary>1. Introduction</summary>

- [1. Introduction](#1-introduction)
    - [1.1 Motivation](#11-motivation)
    - [1.2 Problem Statement](#12-problem-statement)
    - [1.3 Objectives](#13-objectives)
    - [1.4 Methodology Overview](#14-methodology-overview)
    - [1.5 Thesis Structure](#15-thesis-structure)
</details>
<details>
<summary>2. Methodology</summary>
    
- [2. Methodology](#2-methodology)
    - [2.1 Introduction to Methodology](#21-introduction-to-methodology)
    - [2.2 Research Design](#22-research-design)
    - [2.3 Data Collection and Assumptions](#23-data-collection-and-assumptions)
    - [2.4 Data Analysis](#24-data-analysis)
        - [2.4.1 Assumptions](#241-assumptions)
        - [2.4.2 Battle Simulation](#242-battle-simulation)
    - [2.5 Algorithmic Approaches](#25-algorithmic-approaches)
        - [2.5.1 Graph Theory Algorithms](#251-graph-theory-algorithms)
        - [2.5.2 Iterative Methods](#252-iterative-methods)
        - [2.5.3 Simulation-Based Approach](#253-simulation-based-approach)
    - [2.6 Conclusion](#26-conclusion)
</details>
<details>
<summary>3. Implementation</summary>

- [3. Implementation](#3-implementation)
</details>
<details>
<summary>4. Results</summary>
    
- [4. Results](#4-results)
</details>
<details>
<summary>5. Discussion</summary>
    
- [5. Discussion](#5-discussion)
</details>
<details>
<summary>6. Conclusion</summary>
    
- [6. Conclusion](#6-conclusion)
</details>
<details>
<summary>7. References</summary>
    
- [7. References](#7-references)
</details>


## 1. Introduction
For many, unlike myself, Pokémon was their first portal into the realm of gaming. Pokemon is set in a world where you and the namegiving creatures, Pokemon, are best friends. You can catch Pokemon, battle them and conquer the rankings to become Pokemon master. The only catch is, at any point you may only be with a team of six pokemon. Only very little gaming franchises manage to keep such a large fanbase content over so many years of creating new and unique pokemon. Whats their secret to this success? Could it be that the game developers meticulously balanced every pokemon in such a way that it can be viable in certain usecases and team constellations? To test this hyptothesis I was tasked with finding a significantly better Pokemon team than the rest. This is not only an interesting question for many enthusiasts all over the world but also presents a rich field for computational analysis.

### 1.1 Motivation
The motivation for this particular problem stems from the personal interest in optimizing each component when gaming and the general interest for the pokemon franchise while also presenting interesting concepts in the fields of optimization problems, game theory and probability. By tackling these fields this study aims to contribute to the broader understanding of strategic game design and optimization problems with the possibility to extend that knowledge to beyond the realm of pokemon.

### 1.2 Problem Statement
Despite the many different approaches found online there remains no agreed upon standard of finding the best pokemon team. This study defines "best" as the ability of the team to adapt and succeed against a wide range of opposing teams.

### 1.3 Objectives
The primary objective of this study is to develop and apply algorithms to identify highly effective pokemon and constellations giving us ground to conclude wether a "best" pokemon team exists. Secondary objectives include measuring the effectiveness of the mentioned algorithms, analyzing the results to determine deciding factors for a "strong" team and visualizing/analyzing different data sets.

### 1.4 Methodology Overview
To achieve these goals, the study will make use of data analysis, algorithmic design and simulations. Earlier stages will involve getting familiar and preprocessing the data while later stages will involve the design and testing of various optimization algorithms, including iterative and probabilistic approaches. The criteria for evaluating the performance of an algorithmic approach will be based on simulation against a range of opponent teams. ???

---
### Todo
---

### 1.5 Thesis Structure
The remainder of the thesis is structured as follows: Chapter 2 will outline the methodology applied, Chapter 3 presents the implementation and testing phase of all algorithms used. Chapter 4 will discuss the results and findings and Chapter 5 will end the study with a conclusion and discussion of possible future work.


## 2. Methodology
### 2.1 Introduction to Methodology
This Chapter will outline the methodology employed to identify the optimal Pokemon team composition. Given the complexity an sheer amount of data caused by over 1000 pokemon with all their stats and abilities this study makes use of several algorithmic approaches such as graph theory, iterative algorithms and breaking down the problem into smaller problems. The methodology is designed to effectively and rigorously test and validate the best pokemon team against a wide range of opposing team constellations.

### 2.2 Research Design
The research follows a quantitative approach focused on measurable performance to asses the strength of a team. An experimental research design was used where strong teams found by the algorithm were tested against several thousand opponent teams and a naivly chosen "best team" which consists of the top six individually best performing pokemon. This design gave us ground to assess team performance based on measurable performance metrics such as win-probability against random teams and the baseline of the naively chosen team.

### 2.3 Data Collection and Assumptions
The Data used for this Project was provided to me by my supervisor who found a dataset on Kaggle [^1]. The data contains over 1000 pokemon, all their learnable abilities, stats and most relevant features to build a battle simulation. Although the data was far from perfectly curated it gave me a base to quickly jump right into the data analysis and development of my methodology.

---
### TODO
---

### 2.4 Data Analysis

In an initial step the data set was carefully examined and corrected where necessary to ensure proper behaviour when used for the algorithms and especially the battle simulation. Given the size of the dataset and complexity of all the connections, several inconsistencies have been identified, such as following different naming conventions, missing id's and other little things which could break the battle simulation if unnoticed. All those little inconsistencies where found and corrected iteratively in the process of developing the algorithm.

For the analysis and everything else python emerged as the programming language of choice due to its great support for datascience through libraries such as pandas, numpy, seaborn, matplotlib or network-x which enabled me to really get a feel for the data and the behavior of it.
The biggest chunk of the analysis was statistical with some venturing into graph theory in between. It was needed to uncover statistical advantages in the pokemons attributes such as types, attacks and average stats which all could influence the outcome of a battle. Visualization played a pivotal role firstly for the identification of mistakes in the process and also the intuitive understanding of data trends and distributions. Graphtheory mostely was used to identify any connections between pokemon and their peers to identify strong pokemon or more so called "team-players" which only strive in certain team constellations.

The analytical approach not only informed the initial selection of pokemon for the iterative process but also highlights underlying patterns and relations in the underlying data. The rigorous data cleaning, analysis and visualization paved the way for the developement of the algorithm and the subsequent battle simulation phase of the research.


#### 2.4.1 Assumptions
In this project, certain assumptions are made to facilitate the analysis process and manage complexity. All Pokémon in the dataset are assumed to be at level 80, with effort values (EVs) set to 85 across all attributes and all individual values (IVs) set uniformly to 16. Furthermore, the nature of all Pokémon is assumed to be hardy. All those values have been chosen to be either the mean value or assure even attribute distribution. This is contrary to the actual game where almost each attribute is chosen at random making every Pokemon unique and impossible to create reproducable results. These simplifications allow for a more manageable analysis process and prevent unnecessary complexity that could otherwise blow the project out of proportion. Experienced Pokémon players may notice that some attributes of Pokémon are still missing. These are deliberatly ommitted, as they are deemed unnecessary for battling and are therefore excluded from our research. This brings us to the next section: The Battle Simulation. 

#### 2.4.2 Battle Simulation
*Explain the development and implementation of the battle simulation. Highlight how it closely mimics Pokémon battles while simplifying certain aspects to manage complexity.*
This entire project would be impossible to carry out without the battle function, its battle simulation underpins all our simulations. It serves as the foundation for all our assumptions and is crucial for verifying the findings of our simulations. The battle simulation is mainly based on the detailed information available on Bulbapedia. These articles outline the very details of how damage is calculated and how battles are fought out in Pokémon games. Due to the scope limitations of this project, I only focused on the most relevant factors that influence the overall outcome of a battle, such a Pokémons move sets, basic stats and type advantages.

!!*maybe insert image of battling function and parts ommited*!!


To put this into perspective, it is worth noting the development of Pokémon Showdown, the main competitive platform Pokémon enthusiasts turn to, started in 2012 as an open source project is still ongoing. This highlights the complexity and depth of accurately simulating Pokémon battles taking into account all the niche cases like weather, held items, status effects ecetera. By limiting the scope to the most critical elements, the battle simulation aims to provide a realistic yet manageable representation of Pokémon battles and serves as the base for this project.



### 2.5 Algorithmic Approaches
In this Section I will go over all the different approaches I used to evaluate wether there is a significantly better team than firstly a naivly selected team and secondly a generous amount of randomly generated teams. The foundation of all my algorithmic approaches is an initial simulation where each Pokémon battles against every other Pokémon to determine which ones perform the best giving me a starting point for all my approaches.

!!!*This comprehensive performance matrix, illustrated by an image of the first 151 Pokémon from Generation 1, serves as a visual representation to help grasp the performance of each Pokémon and guides the development of subsequent algorithms.*!!!

#### 2.5.1 Graph Theory Algorithms
*Describe the initial use of graph theory algorithms to analyze Pokémon attributes and relationships. Discuss the results obtained and any challenges faced.*
In the early stages I primarily concerned myself with graph theory and ranking algorithms to get a feel for the individual pokemon. Using the network library NetworkX I quickly was set up for initial analysis of all pokemon and their relations. Using this Network which has a node for each pokemon and an edge from pokemon A to B if pokemon A beats pokemon B with probability p >= threshold. Initially I was on the lookout for Kings and Dominating Sets. Kings are defined as as Verteces which can reach any Vertex through an edge. A n-King is a Vertex which does the same but using n Edges. Using this I wanted to Rule out the exisence of clear *must Pick* pokemon. Besides that I looked into the existance of minimal Dominating Sets where the Vertex count is <= 6. A dominating Set is a Set of Verteces which reaches every other Vertex through 1 Edge. By this I investigated the existance of good teams which "dominate" the whole list of Pokemon. Next I looked into different ranking algorithms like Pagerank and others to identify differences to the very rudimentary ranking of pokemon by their average win probability. Finally I looked into Communities and if there are any noteworthy interconnection points or gaps in the graph which force teams to have certain pokemon on their roster in order to be successful.

#### 2.5.2 Iterative Methods
*Explain the use of iterative methods to iteratively improve Pokémon team configurations. Discuss the rationale behind this approach and the results achieved.*
After finishing up the Graph Theoretical approach of identifying a best Pokemon team I mainly concerned myself with an iterative approach which starts out with a randomly assembled team and tries to converge onto a *best team* by improving the randomly assembled team iteratively. Due to very similar results in performance when improving over and over again I needed to look into reducing the overall noise in the win probability of the teams which performed well. The noise in winprobabilities was assumed to exist because of many random teams battles outcomes being clear due to super weak pokemon. To distinguis the great teams from the good in this noise I either had to run many magnitudes more battles or I needed a way to remove super weak pokemon out of the random opponenets.

Generally the algorithms used to do that can be divided into two groups. Firstly Algorithms which have been used to shrink the number of pokemon which might belong into the best pokemon team, lets call this candidate pool, and secondly reducing the number of pokemons which a team can face to give battles some meaning and reduce overall noise, called opponent pool.

Generally the candidate- and opponent pool are assumed to be equal in the beginning with every pokemon being in it. The main practices used to reduce the size of the pools is based upon previous data analysis. Generally the question to answer was can this pokemon be replaced directly by one or more pokemon which are equally as good or better in all its relevant stats. For this I tried several strategies:

##### Top performing Pokemon by type
For each type combination and pokemon A, there are 171 ($\binom{18}{2} + 18$). I looked at every other same typed pokemon B and checked if this pokemon B has equal or better stats than pokemon A and beats all opposing pokemon and if so B can replace A. This reduced the size by only roughly 50\% which is not enough for the algorithm to run efficiently
##### Top n performing Pokemon by type
Using the same approach we can reduce the number even further by just picking the top n pokemon for each type combination. This in the best case gives us at minimum $< 171$ pokemon, one for each type, since not all of the 171 type combinations are used.
##### Top n performing Pokemon by type
Doing the same but scaled by the amount of pokemon in that typing
##### Coverage algorithms?
Coverage describes a teams ability to beat different types of pokemon. A high coverage means a team might win against a lot of pokemon teams with a low probability of e.g. 70\%. Coverage is constituted of the minimal nonzero value of any of the pokemon which beats all pokemon of a type group. With this metric we can define a team with high coverage to form a good team since most types are covered. While teams with low coverage might be especially effective against the eventually to be found "best team" they are not suitable to be the best team themselves as they only cover a small subset of the broad spectrum of teams.

#### 2.5.3 Incremental Team Optimization Approach
*Detail the simulation-based approach used to evaluate Pokémon team configurations. Discuss how this approach was chosen and the insights gained from the results.*
This is the final approach i used to tackle the problem. It revolves around the idea of breaking the problem down into smaller subproblems and figuring out any relations which might be helpful in concluding something about the bigger problem. In this concrete case I started with the top 20 performing pokemon. Then I formed teams of two out of those top 20 individual pokemon and simulated battles against random opponent teams of size 2. I followed this this up by forming teams of 3 of the teams of 2 and continued this process until I reached teams of size 6.
This also meant that I finally needed to take advantage the computing cluster, which I used to handle the extensive simulations and computations required.

### 2.6 Conclusion
*Summarize the methodology section, highlighting the key steps taken in the research design, data collection, and analysis. Emphasize the importance of the battle simulation and the three algorithms used to find the best Pokémon team.*
My supervisor provided me with the flexibility to explore several approaches, as there is no clear best way to tackle such a complex optimization problem. This allowed me to be dynamic and adaptive with my research, enabling me to experiment with graph theoretical methods, iterative techniques, and simulation-based evaluations, leading to a more exploratory and on the go process.




~~#### The actual Algorithms
Now I am going to introduce you to the heart of this thesis which all prior pokemon subset selection lead up to. The algorithm works by looking the individually top performing 6 pokemon and the respective team they form. This is our baseline which needs to be beaten. Over a great number of battles I tested their performance and estimated their win probability against a random team. Now we make a selection of teams from our candidate pool making sure each pokemon gets selected at least once. Then the simulation process starts and we divide the teams into two groups based on our findings. Teams who significantly performed better than our baseline are here to stay while the rest gets discarded. We perform a union over the pokemon of the teams which stay and do not adjust the opponent pool?~~

## 3. Implementation
In this implementation section, I will over the key components behind the different approaches. While I won't cover every detail here, those interested in the full implementation can have a look at the code, which is in the GitHub repository. [^2] One thing you will often see is the conversion from .csv files into dictionaries due to them being faster. Generally everything that can be precomputed is precomputed.


### 3.1 Battle Simulation
The battle simulation consists of two main parts: the Pokémon class and the Battle class. Both of these classes will be touched upon in the following subsections.


#### 3.1.1 Pokemon Class
The Pokémon class initializes each Pokémon with its base stats, top moves, and calculated stats based on fixed EVs, IVs, and nature:
- **Initialization**: Retrieves base stats, top moves, and calculates the final stats for each Pokémon.
- **Stat Calculation**: Functions to calculate stats based on the Pokémon's base stats, EVs, IVs, and nature.
- **Reset HP**: Resets the Pokémon's battle HP to its base HP. This is done so I can quickly reset a pokemon in battle to its normal HP after it faints and not create a completely new Pokémon everytime.
- **Retrieve Moves**: Retrieves the top moves for each Pokémon.
- **Print Stats**: Prints the Pokémon's stats for debugging purposes.


#### 3.1.2 Battle Class


### 3.2 Graph Theory Algorithms
### 3.3 Iterative Algorithm
### 3.4 Incremental Team Optimization


## 4. Results

- Presentation of findings

## 5. Discussion

- Interpretation of results
- Comparison with existing literature
- Implications of findings

## 6. Conclusion

- Summary of key findings
- Contributions to the field
- Recommendations for future research

## 7. References

- List of all sources cited in the thesis
[^1]: [Kaggle dataset](https://www.kaggle.com/datasets/mylesoneill/pokemon-sun-and-moon-gen-7-stats?select=moves.csv).
[^2]: [GitHub Repository](Testtest)








# Markdown Cheat Sheet

## Headers
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6

## Emphasis
*Italic* or _Italic_
**Bold** or __Bold__
**_Bold and Italic_** or *__Bold and Italic__*
~~Strikethrough~~

## Lists
- Bullet list
  - Nested bullet
    - Sub-nested bullet

1. Numbered list
2. Number two
   1. Sub-number

## Links
[Title](https://www.example.com)

## Images
![Alt text](https://www.example.com/image.jpg "Optional title")

## Code
`Inline code` with backticks


## Blockquotes
> Blockquote
>> Nested blockquote

## Tables

| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |

| Syntax | Description | Test Text |
| :--- | :---: | ---: |
| Left | Center | Right |

## Advanced Elements

### Task Lists
- [x] Task 1
- [ ] Task 2
- [ ] Task 3

### Horizontal Rule
---

### Escaping Markdown Characters
\*This text is not italicized\*
