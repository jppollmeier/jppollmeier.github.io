# Best Pokémon Team

## Abstract

This bachelor's thesis concerns itself with the finding of the best Pokémon Team under several given assumptions. With the Pokémon franchise now encompassing over 1000 Pokémon and additional ~100 being released every generation, each with their own set of stats and features, identifying the best team poses a very challenging question. This Study makes use of a dataset and uses different approaches to find the best pokemon team. The methodology includes simulation of battles between individual pokemon and teams and also several graph theory approaches to find the best team. We can show that the selection of our algorithm is significantly better than a more common selection technique employed by most players. This work is not only interesting for the pokemon community by providing them with a scientific approach of team selection but has its roots in many optimization problems such as ?. Future research directions could include a less restricted definition of the problem statement and including more probabilities.

## Table of Contents

- [1. Introduction](#1-introduction)
    - [1.1 Motivation](#11-motivation)
    - [1.2 Problem Statement](#12-problem-statement)
    - [1.3 Objectives](#13-objectives)
    - [1.4 Methodology Overview](#14-methodology-overview)
    - [1.5 Thesis Structure](#15-thesis-structure)
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
- [3. Implementation](#3-implementation)
- [4. Results](#4-results)
- [5. Discussion](#5-discussion)
- [6. Conclusion](#6-conclusion)
- [7. References](#7-references)


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
The Data used for this Project was provided to me by my supervisor who found a dataset on Kaggle. (footnote to dataset ~\cite{Kaggle-Link}) ????? The data contains over 1000 pokemon, all their learnable abilities, stats and most relevant features to build a battle simulation. Although the data was far from perfectly curated it gave me a base to quickly jump right into the data analysis and development of my methodology.

---
### TODO
---

### 2.4 Data Analysis

In an initial step the data set was carefully examined and corrected where necessary to ensure proper behaviour when used for the algorithms and especially the battle simulation. Given the size of the dataset and complexity of all the connections, several inconsistencies have been identified, such as following different naming conventions, missing id's and other little things which could break the battle simulation if unnoticed. All those little inconsistencies where found and corrected iteratively in the process of developing the algorithm.

For the analysis and everything else python emerged as the programming language of choice due to its great support for datascience through libraries such as pandas, numpy, seaborn, matplotlib or network-x which enabled me to really get a feel for the data and the behavior of it.
The biggest chunk of the analysis was statistical with some venturing into graph theory in between. It was needed to uncover statistical advantages in the pokemons attributes such as types, attacks and average stats which all could influence the outcome of a battle. Visualization played a pivotal role firstly for the identification of mistakes in the process and also the intuitive understanding of data trends and distributions. Graphtheory mostely was used to identify any connections between pokemon and their peers to identify strong pokemon or more so called "team-players" which only strive in certain team constellations.

The analytical approach not only informed the initial selection of pokemon for the iterative process but also highlights underlying patterns and relations in the underlying data. The rigorous data cleaning, analysis and visualization paved the way for the developement of the algorithm and the subsequent battle simulation phase of the research.


#### 2.4.1 Assumptions
Detail the assumptions made about Pokémon attributes (e.g., IVs, EVs) to streamline the analysis process and avoid unnecessary complexity.

#### 2.4.2 Battle Simulation
Explain the development and implementation of the battle simulation. Highlight how it closely mimics Pokémon battles while simplifying certain aspects to manage complexity.


### 2.5 Algorithmic Approaches
*Generally the algorithms used can be divided into two groups. Firstly Algorithms which have been used to shrink the number of pokemon which might belong into the best pokemon team, lets call this candidate pool, and reducing the number of pokemons which a team can face to give battles some meaning and reduce overall noise, opponent pool. Secondly the algorithm which based on our previous findings and assumptions finds the best pokemon team using an iterative approach.*
~~Algorithms employed can be diveded into two groups:
Firstly Algorithms which decide if a pokemon is a candidade for either the strongest pokemon team and or the opponent teams. This is done so that we can drastically reduce the amount of pokemon which we need to consider as candidates and or opponents since most of them either are indirectly or directly replaceable by stronger pokemons with similar stats. Candiate pool is what we call all the pokemon which are in consideration for the strongest team while the opponent pool describes the pokemon which give meaningful battles to the candidate pool.
Secondly we have the algorithms employed to find the best pokemon team~~

#### 2.5.1 Graph Theory Algorithms
*Describe the initial use of graph theory algorithms to analyze Pokémon attributes and relationships. Discuss the results obtained and any challenges faced.*

#### 2.5.2 Iterative Methods
*Explain the use of iterative methods to iteratively improve Pokémon team configurations. Discuss the rationale behind this approach and the results achieved.*


#### Poolsize Reduction
Generally the candidate- and opponent pool are assumed to be equal in the beginning. The main practices used to reduce the size of the pools is based upon previous data analysis. Generally the question to answer was can this pokemon be replaced directly by one or more pokemon which are equally as good or better in all its relevant stats. For this I tried several strategies:

##### Top performing Pokemon by type
For each type combination and pokemon A, there are 171 ($\binom{18}{2} + 18$). I looked at every other same typed pokemon B and checked if this pokemon B has equal or better stats than pokemon A and beats all opposing pokemon and if so B can replace A. This reduced the size by only roughly 50\% which is not enough for the algorithm to run efficiently
##### Top n performing Pokemon by type
Using the same approach we can reduce the number even further by just picking the top n pokemon for each type combination. This in the best case gives us at minimum $< 171$ pokemon, one for each type, since not all of the 171 type combinations are used.
##### Top n performing Pokemon by type
Doing the same but scaled by the amount of pokemon in that typing
##### Coverage algorithms?
Coverage describes a teams ability to beat different types of pokemon. A high coverage means a team might win against a lot of pokemon teams with a low probability of e.g. 70\%. Coverage is constituted of the minimal nonzero value of any of the pokemon which beats all pokemon of a type group. With this metric we can define a team with high coverage to form a good team since most types are covered. While teams with low coverage might be especially effective against the eventually to be found "best team" they are not suitable to be the best team themselves as they only cover a small subset of the broad spectrum of teams.


#### 2.5.3 Simulation-Based Approach
Detail the simulation-based approach used to evaluate Pokémon team configurations. Discuss how this approach was chosen and the insights gained from the results.


#### The actual Algorithms
Now I am going to introduce you to the heart of this thesis which all prior pokemon subset selection lead up to. The algorithm works by looking the individually top performing 6 pokemon and the respective team they form. This is our baseline which needs to be beaten. Over a great number of battles I tested their performance and estimated their win probability against a random team. Now we make a selection of teams from our candidate pool making sure each pokemon gets selected at least once. Then the simulation process starts and we divide the teams into two groups based on our findings. Teams who significantly performed better than our baseline are here to stay while the rest gets discarded. We perform a union over the pokemon of the teams which stay and do not adjust the opponent pool?

### 2.6 Conclusion
*Summarize the methodology section, highlighting the key steps taken in the research design, data collection, and analysis. Emphasize the importance of the battle simulation and the three algorithms used to find the best Pokémon team.*

## 3. Implementation



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

### Footnotes
Here's a sentence with a footnote. [^1]

[^1]: This is the footnote.

### Horizontal Rule
---

### Escaping Markdown Characters
\*This text is not italicized\*
