# Best Pokémon Team

## Abstract

This bachelor's thesis concerns itself with the finding of the best Pokémon Team under several given assumptions. With the Pokémon franchise now encompassing over 1000 Pokémon and additional ~100 being released every generation, each with their own set of stats and features, identifying the best team poses a very challenging question. This Study makes use of a dataset and uses different approaches to find the best pokemon team. The methodology includes simulation of battles between individual pokemon and teams and also several graph theory approaches to find the best team. We can show that the selection of our algorithm is significantly better than a more common selection technique employed by most players. This work is not only interesting for the pokemon community by providing them with a scientific approach of team selection but has its roots in many optimization problems such as ?. Future research directions could include a less restricted definition of the problem statement and including more probabilities.


## Table of Contents

- [1. Introduction](#1-introduction)
- [2. Literature Review](#2-literature-review)
- [3. Methodology](#3-methodology)
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
The primary objective of this study is to develop and apply algorithms to identify highly effective pokemon and constellations giving us ground to conclude wether a "best" pokemon team exists. Secondary objectives include measuring the effectiveness of the mentioned algorithms, analyzing the results to determine deciding factors for a "strong" team and visualizing different data sets.

### 1.4 Methodology Overview
To achieve these goals, the study will make use of data analysis, algorithmic design and simulations. Earlier stages will involve getting familiar and preprocessing the data while later stages will involve the design and testing of various optimization algorithms, including iterative and probabilistic approaches. The criteria for evaluating the performance of an algorithmic approach will be based on simulation against a range of opponent teams.

### 1.5 Thesis Structure
The remainder of the thesis is structured as follows: Chapter 2 will outline the methodology applied, Chapter 3 presents the implementation and testing phase of all algorithms used. Chapter 4 will discuss the results and findings and Chapter 5 will end the study with a conclusion and discussion of possible future work.



## 2. Literature Review

- Overview of relevant literature
- Theoretical framework
- Previous research findings

## 3. Methodology

- Research design
- Data collection methods
- Data analysis techniques

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
