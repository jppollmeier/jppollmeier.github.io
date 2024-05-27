# Best Pokémon Team
# Colored Text Example

<p style="color: red;">This is red text.</p>
<p style="color: green;">This is green text.</p>
<p style="color: blue;">This is blue text.</p>

<details>
  <summary>Click to expand</summary>
  
  <!-- Content goes here -->
  This is the collapsible content.
</details>

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
        - [2.5.3 Incremental Team Optimization Approach](#253-incremental-team-optimization-approach)
    - [2.6 Conclusion](#26-conclusion)
- [3. Implementation](#3-implementation)
    - [3.1 Battle Simulation](#31-battle-simulation)
        - [3.1.1 Pokemon Class](#311-pokemon-class)
        - [3.1.2 Team Class](#312-team-class)
        - [3.1.3 Battle Class](#313-battle-class)
    - [3.2 Graph Theory Algorithms](#32-graph-theory-algorithms)
        - [3.2.1 Directed Graph Functions](#321-directed-graph-functions)
        - [3.2.2 Dominating Sets](#322-dominating-sets)
        - [3.2.3 Finding Kings](#323-finding-kings)
        - [3.2.4 Ranking Metrics](#324-ranking-metrics)
        - [3.2.5 Community Detection](#325-community-detection)
    - [3.3 Iterative Algorithm](#33-iterative-algorithm)
    - [3.4 Incremental Team Optimization](#34-incremental-team-optimization)
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


## 3. Implementation
In this implementation section, I will over the key components behind the different approaches. While I won't cover every detail here, those interested in the full implementation can have a look at the code, which is in the GitHub repository. [^2] One thing you will often see is the conversion from .csv files into dictionaries due to them being faster. Generally everything that can be precomputed is precomputed.


### 3.1 Battle Simulation
The battle simulation consists of three main parts: the Pokémon class, Team class and the Battle class. Both of these classes will be touched upon in the following subsections.


#### 3.1.1 Pokemon Class
The Pokémon class initializes each Pokémon with its base stats, top moves, and calculated stats based on fixed EVs, IVs, and nature:
- **Initialization**: Retrieves base stats, top moves, and calculates the final stats for each Pokémon.
- **Stat Calculation**: Functions to calculate stats based on the Pokémon's base stats, EVs, IVs, and nature.
- **Reset HP**: Resets the Pokémon's battle HP to its base HP. This is done so I can quickly reset a pokemon in battle to its normal HP after it faints and not create a completely new Pokémon everytime.
- **Retrieve Moves**: Retrieves the top moves for each Pokémon.
- **Print Stats**: Prints the Pokémon's stats for debugging purposes.

<details>
  <summary>Code Pokemon Class</summary>
    
```Python
class Pokemon:
    def __init__(self, id, moves=None, level=None, hp_ev=None, attack_ev=None, defense_ev=None, special_attack_ev=None, special_defense_ev=None, speed_ev=None, hp_iv=None, attack_iv=None, defense_iv=None, special_attack_iv=None, special_defense_iv=None, speed_iv=None, nature=None):
        self.id = id

        # Retrieve the base stats for the Pokémon using the preprocessed dictionary
        base_stats = base_stats_dict[self.id]

        self.name = base_stats['forme']
        self.species = base_stats['species']
        self.ndex = base_stats['ndex']

        self.type1 = base_stats['type1'].lower()
        self.type2 = base_stats['type2'].lower() if isinstance(base_stats['type2'], str) else ''

        self.level = 80  # Assuming a fixed level

        # Retrieve top moves using the preprocessed dictionary
        self.moves = self.get_top_moves()

        # Set EVs and IVs
        self.hp_ev = self.attack_ev = self.defense_ev = self.special_attack_ev = self.special_defense_ev = self.speed_ev = 85
        self.hp_iv = self.attack_iv = self.defense_iv = self.special_attack_iv = self.special_defense_iv = self.speed_iv = 16

        # Set nature and retrieve nature modifiers using the preprocessed dictionary
        self.nature = "Hardy"  # Assuming a fixed nature
        nature_modifiers = nature_modifiers_dict[self.nature]

        # Function to calculate each stat
        def calc_stat(base, iv, ev, nature_mod):
            return ((2 * base + iv + ev // 4) * self.level) // 100 + 5 * nature_mod

        # Function to calculate HP
        def calc_hp(base, iv, ev):
            if base == 1:  # For special cases like Shedinja
                return 1
            return ((2 * base + iv + ev // 4) * self.level) // 100 + self.level + 10

        # Calculate stats
        self.hp = calc_hp(base_stats['hp'], self.hp_iv, self.hp_ev)
        self.bhp = self.hp
        self.attack = calc_stat(base_stats['attack'], self.attack_iv, self.attack_ev, nature_modifiers['attack'])
        self.defense = calc_stat(base_stats['defense'], self.defense_iv, self.defense_ev, nature_modifiers['defense'])
        self.special_attack = calc_stat(base_stats['spattack'], self.special_attack_iv, self.special_attack_ev, nature_modifiers['spattack'])
        self.special_defense = calc_stat(base_stats['spdefense'], self.special_defense_iv, self.special_defense_ev, nature_modifiers['spdefense'])
        self.speed = calc_stat(base_stats['speed'], self.speed_iv, self.speed_ev, nature_modifiers['speed'])




        # Generate EVs and IVs if all respective values are None
        '''
        if all(v is None for v in [hp_ev, attack_ev, defense_ev, special_attack_ev, special_defense_ev, speed_ev]):
            self.generate_legal_evs()
        if all(v is None for v in [hp_iv, attack_iv, defense_iv, special_attack_iv, special_defense_iv, speed_iv]):
            self.generate_ivs()
        '''
        #removed due to already being set
    
    def reset_hp(self):
        self.bhp = self.hp


    def generate_legal_evs(self):
        MAX_EV_PER_STAT = 252
        MAX_TOTAL_EVs = 510

        ev_attributes = {
            "hp_ev": "HP",
            "attack_ev": "Attack",
            "defense_ev": "Defense",
            "special_attack_ev": "Special Attack",
            "special_defense_ev": "Special Defense",
            "speed_ev": "Speed"
        }

        total_evs = sum([getattr(self, attr) for attr in ev_attributes])

        while total_evs < MAX_TOTAL_EVs:
            # Randomly select an EV attribute
            ev_attr_index = int(pop_random() * len(ev_attributes))
            ev_attr = list(ev_attributes.keys())[ev_attr_index]

            max_possible_ev = min(MAX_EV_PER_STAT - getattr(self, ev_attr), MAX_TOTAL_EVs - total_evs)

            if max_possible_ev <= 0:
                break

            # Determine EV to add
            ev_to_add = int(pop_random() * max_possible_ev) + 1
            setattr(self, ev_attr, getattr(self, ev_attr) + ev_to_add)
            total_evs += ev_to_add


    def generate_ivs(self):
        iv_attributes = [
            "hp_iv", 
            "attack_iv", 
            "defense_iv", 
            "special_attack_iv", 
            "special_defense_iv", 
            "speed_iv"
        ]
        for iv_attr in iv_attributes:
            iv_value = int(pop_random() * 32)
            setattr(self, iv_attr, iv_value)


    def get_top_moves(self):
        # Retrieve top moves for the given Pokémon
        moves = top_moves_dict.get(self.name, {})
        if moves == {}:
            #print(f"Failed to fetch moves with \"{self.name}\" now trying \"{self.species}\"")
            moves = top_moves_dict.get(self.species, {})
        return moves



    def sample_moves(moves):
        sampled_moves = set()
        moves_list = list(moves)

        while len(sampled_moves) < min(4, len(moves_list)):
            move_index = int(pop_random() * len(moves_list))
            sampled_moves.add(moves_list[move_index])
        
        return list(sampled_moves)


    def print_stats(self):
        print(f"Pokemon ID: {self.id}")
        print(f"Name: {self.name}")
        print(f"(Types: {self.type1, self.type2}")
        print(f"Level: {self.level}")
        print(f"Nature: {self.nature}")
        print(f"Stats: HP: {self.hp}, Attack: {self.attack}, Defense: {self.defense}, Special Attack: {self.special_attack}, Special Defense: {self.special_defense}, Speed: {self.speed}")
        print(f"EVs: HP: {self.hp_ev}, Attack: {self.attack_ev}, Defense: {self.defense_ev}, Special Attack: {self.special_attack_ev}, Special Defense: {self.special_defense_ev}, Speed: {self.speed_ev}")
        print(f"IVs: HP: {self.hp_iv}, Attack: {self.attack_iv}, Defense: {self.defense_iv}, Special Attack: {self.special_attack_iv}, Special Defense: {self.special_defense_iv}, Speed: {self.speed_iv}")
        print(f"Moves: {self.moves}")
```

</details>


#### 3.1.2 Team Class
The Team class initializes a team of Pokémon, ensuring unique Pokédex numbers and filling the team to the required size if necessary:
- **Initialization**: 
  - Takes a variable number of Pokémon IDs and a team size. Which is especially important for the Incremental Team Optimization Approach.
  - Ensures that the team consists of unique Pokémon based on their Pokédex numbers.
  - Fills the rest of the team with random, unique Pokémon if the provided IDs are insufficient to meet the team size.
- **Reset**: 
  - Resets the HP of all Pokémon in the team to their base HP.
- **String Representation**: 
  - Provides a string representation of the team, listing each Pokémon and their base HP for debugging purposes.

<details>
  <summary>Code Team Class</summary>
    
```Python
class Team:
    def __init__(self, *pokemon_ids, team_size):
        self.max_team_size = team_size
        self.pokemon_ids = []
        self.pokedex_numbers = set()  # To track unique Pokédex numbers
        self.pokemon_team = []
        
        # Process the provided Pokémon IDs, ensuring they are unique by Pokédex number
        for pid in pokemon_ids:
            pokemon = scripts.Pokemon.Pokemon(pid)
            if pokemon.ndex not in self.pokedex_numbers:
                self.pokemon_ids.append(pid)
                self.pokemon_team.append(pokemon)
                self.pokedex_numbers.add(pokemon.ndex)
        
        # Fill the rest of the team with random, unique Pokémon, if necessary
        while len(self.pokemon_team) < self.max_team_size:
            random_id = random.randint(1, 151)
            random_pokemon = scripts.Pokemon.Pokemon(random_id)
            if random_pokemon.ndex not in self.pokedex_numbers:
                self.pokemon_ids.append(random_id)
                self.pokemon_team.append(random_pokemon)
                self.pokedex_numbers.add(random_pokemon.ndex)

    def reset(self):
        for pok in self.pokemon_team:
            pok.reset_hp()
            
    def __str__(self):
        return "Team: " + ', '.join((str(pokemon.name) + " " + str(pokemon.bhp)) for pokemon in self.pokemon_team)
```

</details>

#### 3.1.3 Battle Class

The Battle class manages battles between two teams of Pokémon, handling individual battles and determining the overall winner:

- **Initialization and Data Loading**: 
  - CSV files are read and converted into dictionaries for faster access during battles.
  - Type chart data is preprocessed into a nested dictionary for quick lookups.

- **Battle Functions**:
  - `teamBattle(team1, team2, verbose=True)`: 
    - Manages a full battle between two teams of Pokémon.
    - Determines the winner based on which team's Pokémon faint first.
  - `battle(pokemon1, pokemon2, verbose=True)`:
    - Conducts a battle between two individual Pokémon.
    - Determines the first attacker based on speed and alternates attacks until one Pokémon faints.
  - `attack(pokemon1, pokemon2, verbose)`:
    - Handles the logic for one Pokémon attacking another.
    - Chooses a random move, calculates damage, and updates the defending Pokémon's HP.

### 3.2 Graph Theory Algorithms

This will be the most uninteresting implementation-section since most of the graph theory algorithms were implemented using the NetworkX library and only little adjustements or loops have been employed. Key algorithms and methods used include:

#### 3.2.1 Directed Graph Functions:
  - Created directed graphs (`G`) from Pokémon battle outcomes, adding edges between Pokémon A and B if A beats B with a probability \( p \geq 0.9 \).

#### 3.2.2 Dominating Sets:
  - Utilized `nx.dominating_set(G)` to find dominating sets. (The problem of finding smallest dominating sets is NP-Hard and only bruteforcable for smaller subsets of all pokemon.)

#### 3.2.3 Finding Kings:
  - Implemented a custom function to find "kings" in the tournament graph, defined as Pokémon from which every other Pokémon is reachable within two steps:
    ```python
    def is_king(tournament, vertex):
        shortest_paths = nx.single_source_shortest_path_length(tournament, vertex, cutoff=2)
        return len(shortest_paths) == len(tournament.nodes)

    def find_kings(tournament):
        kings = []
        for vertex in tournament.nodes:
            if is_king(tournament, vertex):
                kings.append(vertex)
        return (kings, len(kings))

    find_kings(G)
    ```

#### 3.2.4 Ranking Metrics:
  - Evaluated various centrality and ranking metrics to identify better metrics than win probability for ranking Pokémon in the created DiGraph \( G \):
    - `in_degree = nx.in_degree_centrality(G)`
    - `out_degree = nx.out_degree_centrality(G)`
    - `page_rank = nx.pagerank(G)`
    - `hubs, authorities = nx.hits(G)`
    - `betweenness = nx.betweenness_centrality(G)`
    - `closeness = nx.closeness_centrality(G)`

#### 3.2.5 Community Detection:
  - Detected communities within the undirected graph using `communities = nx.algorithms.community.louvain_communities(G_undirected)` to explore relationships among Pokémon.


### 3.3 Iterative Algorithm
The following algorithm iteratively identifies top-performing Pokémon teams by simulating battles and refining the selection of Pokémon IDs over multiple iterations.

1. **Initialization**:
    - Start with a random sample of Pokémon IDs (`subset_size`).
    - Set parameters for the number of iterations, the number of top teams to consider, the number of battles to start with, and the number of battles to end with.

2. **Iterative Process**:
    - For each iteration:
        - **Generate Opponent Teams**: Create a set of fixed opponent teams by randomly sampling Pokémon IDs and adding any custom teams provided.
        - **Simulate Battles**: Use the `run_battle_simulation` function to simulate battles between the generated teams and record win counts for each team.
        - **Identify Top Performers**: Sort teams by their win counts to identify the top teams and extract the most frequently occurring Pokémon.
        - **Update Pokémon IDs**: Update the current set of Pokémon IDs with the top-performing Pokémon IDs and introduce new IDs to maintain diversity.
        - **Check Specific Team Performance**: Calculate the win rate of a specific team and track better-performing teams if the specific team is not the best or does not have a 100% win rate.

3. **Output**:
    - The algorithm returns the top Pokémon IDs after the final iteration.


```python
from scripts.Team import Team
from collections import Counter
from scripts.Battle import teamBattle

def run_battle_simulation(team_combinations, number_of_opponents, id_set, custom_opponent_teams=None):
    win_counts = {}
    if custom_opponent_teams is None:
        custom_opponent_teams = []
    fixed_opponent_teams = [Team(*random.sample(id_set, 6)) for _ in range(number_of_opponents)] + custom_opponent_teams
    for team_combo in team_combinations:
        win_counts[team_combo] = 0
        team1 = Team(*team_combo)
        for opponent_team in fixed_opponent_teams:
            opponent_team.reset()
            team1.reset()
            result = teamBattle(team1, opponent_team)
            if result == 1:
                win_counts[team_combo] += 1
    return win_counts

def find_top_performers(win_counts, top_n):
    sorted_teams = sorted(win_counts.items(), key=lambda x: x[1], reverse=True)
    top_teams = sorted_teams[:top_n]
    top_pokemon = [pokemon for team, _ in top_teams for pokemon in team]
    return Counter(top_pokemon), top_teams

def iterative_best(iterations=100, id_set=list(range(1, 803)), subset_size=12, top_teams_to_consider=10, start_battles=100, end_battles=200, print_teams=False):
    current_ids = random.sample(id_set, subset_size)
    for iteration in range(iterations):
        number_of_opponents = int((start_battles + ((end_battles - start_battles) * (iteration / (iterations-1)))))
        team_combinations = list(itertools.combinations(current_ids, 6))
        custom_opponent_teams = [Team(*random.sample(current_ids, 6)) for _ in range(number_of_opponents)]
        win_counts = run_battle_simulation(team_combinations, number_of_opponents, id_set, custom_opponent_teams)
        top_pokemon_counter, top_teams = find_top_performers(win_counts, top_teams_to_consider)
        top_ids = [id for id, _ in top_pokemon_counter.most_common(6)]
        new_pokemon_ids = []
        unique_current_ids = set(top_ids[:6])
        while len(unique_current_ids) < subset_size:
            new_id = random.choice(id_set)
            if new_id not in unique_current_ids:
                unique_current_ids.add(new_id)
                new_pokemon_ids.append(new_id)
                id_set.remove(new_id)
        current_ids = list(unique_current_ids)
        if print_teams:
            print(f"\nTop 10 Teams from Iteration {iteration + 1}:")
            for team, win_count in top_teams[:10]:
                team_win_rate = (win_count / (number_of_opponents + len(custom_opponent_teams))) * 100
                print(f"Team {team}: {win_count} wins ({team_win_rate:.2f}%)")
    return top_ids
```



### 3.4 Incremental Team Optimization

Given the computational complexity of simulating battles for full 6v6 teams, we started with smaller subproblems. The main idea is to:

1. Identify the top 20 individually performing Pokémon.
2. Create all possible pairs (combinations) from these 20 Pokémon.
3. Simulate battles between these pairs and random teams to evaluate their performance.
4. Incrementally build larger teams by fusing smaller teams, adding one Pokémon at a time, based on shared members and predicted performance.

#### Process Summary

1. **Create Initial Teams**: Form all `20 choose 2` pairs from the top 20 Pokémon.
2. **Simulate Battles**: Evaluate the performance of these pairs against random teams.
3. **Fuse Teams**: Combine smaller teams into larger teams (triples, quadruples, etc.) if they share `team_size-1` Pokémon.
4. **Predict Performance**: Use the performance of smaller teams to predict the performance of the newly formed larger teams.
5. **Simulate and Compare**: Simulate battles for the larger teams and compare the results with the predictions.
6. **Repeat**: Continue the process, increasing the team size by one each iteration until reaching teams of size 6.

<details>
  <summary> <p style="color: red;"> Code Incermental Team Optimization </p> </summary>
    
---
Since showing all examples would be a bit much I will just use the case from teams of size 3 to teams of size 4 as an example:
#### Prediction from triples to Quadruples
    
        ```Python
        def fuse_to_quadruples(ranked_results_df):
            ranked_results = {tuple(sorted(map(int, row[:3]))): row[3] for row in ranked_results_df.to_numpy()}
            tuple_set = set(ranked_results.keys())
            quadruples = {}
            counts = {}
            
            # Check each pair of triples
            for idx1, avg_score1 in ranked_results.items():
                for idx2, avg_score2 in ranked_results.items():
                    if idx1 != idx2:
                        shared_ids = tuple(set(idx1).intersection(idx2))
                        if len(shared_ids) == 2:  # Two IDs shared between the triples
                            all_ids = sorted(set(idx1).union(set(idx2)))
                            if len(all_ids) == 4:  # We're forming a quadruple
                                # Create all combinations of triples from the four IDs
                                all_triples = list(combinations(all_ids, 3))
                                # Verify all necessary triples exist
                                if all(triple in tuple_set for triple in all_triples):
                                    quad_key = tuple(all_ids)
                                    total_score = avg_score1 + avg_score2
                                    # Add scores for the other two triples
                                    for triple in all_triples:
                                        if triple not in (idx1, idx2):
                                            total_score += ranked_results.get(triple, 0)
                                    quadruples[quad_key] = quadruples.get(quad_key, 0) + total_score
                                    counts[quad_key] = counts.get(quad_key, 0) + 1
        
            # Average the scores for each quadruple
            for quad_key in quadruples:
                quadruples[quad_key] /= counts[quad_key]
        
            if quadruples:
                sorted_quadruples = sorted(quadruples.items(), key=lambda item: item[1], reverse=True)
                quadruples_df = pd.DataFrame(sorted_quadruples, columns=['IDs', 'Average'])
                quadruples_df[['ID1', 'ID2', 'ID3', 'ID4']] = pd.DataFrame(quadruples_df['IDs'].tolist(), index=quadruples_df.index)
                quadruples_df.drop('IDs', axis=1, inplace=True)
                quadruples_df = quadruples_df[['ID1', 'ID2', 'ID3', 'ID4', 'Average']]
            else:
                # Create an empty DataFrame with the correct columns if no quadruples exist
                quadruples_df = pd.DataFrame(columns=['ID1', 'ID2', 'ID3', 'ID4', 'Average'])
        
            return quadruples_df
        
        def main():
            triples_sorted = pd.read_csv('./tuples/triples_sorted.csv')
            quadruples_df = fuse_to_quadruples(triples_sorted)
            if not quadruples_df.empty:
                quadruples_df['ID1'] = quadruples_df['ID1'].astype(int)
                quadruples_df['ID2'] = quadruples_df['ID2'].astype(int)
                quadruples_df['ID3'] = quadruples_df['ID3'].astype(int)
                quadruples_df['ID4'] = quadruples_df['ID4'].astype(int)
            quadruples_df.to_csv('./tuples/quadruples_predict.csv', index=False)
            print(f"Saved sorted fused quadruples to './tuples/quadruples_predict.csv', total count: {len(quadruples_df)}")
        
        if __name__ == "__main__":
            main()
        ```
        
        #### Simulation of Quadruples
        
        ```Python
        def generate_random_teams(num_teams, team_size=4):
            teams = []
            for _ in range(num_teams):
                team = Team.Team(team_size=team_size)
                teams.append(team)
            return teams
        
        def main():
            # Load the quadruples data from CSV
            quadruples_df = pd.read_csv('./tuples/quadruples_predict.csv')
        
            num_battles = 10
            num_opps = 100  # Total number of random opponents
        
            job_index = int(sys.argv[1])  # Job array index from command line argument
            chunk_size = 10  # Number of teams each job should process
            start_index = (job_index - 1) * chunk_size
            end_index = min(job_index * chunk_size, num_opps)
        
            random_teams = generate_random_teams(num_opps, team_size=4)
        
            # Create an empty results matrix
            results_matrix = np.zeros((len(quadruples_df), end_index - start_index))
        
            # Directory to save the matrices
            output_dir = './output/quadruples_results'
            if not os.path.exists(output_dir):
                os.makedirs(output_dir)
        
            # Save the partial results matrix for this chunk
            file_path = os.path.join(output_dir, f"results_matrix_chunk_{job_index}.csv")
        
            for i, row in enumerate(quadruples_df.itertuples()):
                team1 = Team.Team(row.ID1, row.ID2, row.ID3, row.ID4, team_size=4)
                for j, team2 in enumerate(random_teams[start_index:end_index], start=start_index):
                    total_score = 0
                    for _ in range(num_battles):
                        result = Battle.teamBattle(team1, team2)
                        total_score += result
                        team1.reset()
                        team2.reset()
                    results_matrix[i, j - start_index] = total_score / num_battles
        
            # Constructing the DataFrame for the results with ID1, ID2, ID3, ID4, and corresponding team results
            ids_and_results_df = pd.concat([quadruples_df[['ID1', 'ID2', 'ID3', 'ID4']], pd.DataFrame(results_matrix, columns=[f"team_{j}" for j in range(start_index, end_index)])], axis=1)
            ids_and_results_df.to_csv(file_path, index=False, index_label='ID')
        
        if __name__ == "__main__":
            main()
        ```

</details>

---
###TODO
---
## 4. Results


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
