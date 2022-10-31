# CS50's Introduction to Computer Science
## HarvardX - CS50x
### Week 4 Problem Set - Tideman.c
<hr>


### Assignment and Requirements:
Write and execute the program that takes candidates and number of voters as command-line arguments, prompts user for votes and print out the winner of the election.

Program should behave per the example below:

```
./tideman Alice Bob Charlie
Number of voters: 5
Rank 1: Alice
Rank 2: Charlie
Rank 3: Bob

Rank 1: Alice
Rank 2: Charlie
Rank 3: Bob

Rank 1: Bob
Rank 2: Charlie
Rank 3: Alice

Rank 1: Bob
Rank 2: Charlie
Rank 3: Alice

Rank 1: Charlie
Rank 2: Alice
Rank 3: Bob

Charlie
```

#### Tideman Voting Method:

In voting system known as a ranked-choice voting system, voters can vote for more than one candidate. Instead of just voting for their top choice, they can rank the candidates in order of preference.

In this election system, winnwe is called “Condorcet winner”: the person who would have won any head-to-head matchup against another candidate.

The Tideman voting method (also known as “ranked pairs”) is a ranked-choice voting method that’s guaranteed to produce the Condorcet winner of the election if one exists.

Tideman method works by constructing a “graph” of candidates, where an arrow (i.e. edge) from candidate A to candidate B indicates that candidate A wins against candidate B in a head-to-head matchup. Looking at graph, the Tideman method says the winner of the election should be the “source” of the graph (i.e. the candidate that has no arrow pointing at them).

The Tideman algorithm specifies that matchup edges should be “locked in” to the graph one at a time, based on the “strength” of the victory (the more people who prefer a candidate over their opponent, the stronger the victory). So long as the edge can be locked into the graph without creating a cycle, the edge is added; otherwise, the edge is ignored.

#### Compiling And Execution:

Before execution of the program, it must be compiled with a compiler, translating it from source code into machine code.\
Execute the command below in the Command Line to do that:

```C
make tideman
```

Execute the program by executing the below:
```C
./tideman *args
```
substitute valid candidates in place of ```*args```
