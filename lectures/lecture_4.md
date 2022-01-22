lecture_4

# Lecture 4: Informed search
_There is a heuristic, which gives more information about which node to expand._

## Greedy search
![](lecture_4/Screenshot%202022-01-16%20at%2020.54.48.png)
* Choose the node with the best heuristic.
* Does not look at total length of the route.

## Combining UCS and greedy
![](lecture_4/Screenshot%202022-01-16%20at%2021.03.37.png)
* Not optimal
* Short term best step might not be the long term best step
* If the heuristic needs to be admissible.

![](lecture_4/Screenshot%202022-01-16%20at%2021.09.44.png)
* Admissible heuristics underestimate the cost of each node -> they’re relaxed cost calculations.

![](lecture_4/Screenshot%202022-01-16%20at%2021.08.32.png)
* Often, admissible heuristics are a relaxation of the problem, by adding actions or calculating cost in a more relaxed way.
* If the heuristic is much lower than the actual cost from that node, it is very uninformed. 
* The closer it is to the actual cost, the more informed the heuristic is.

![](lecture_4/Screenshot%202022-01-16%20at%2021.32.08.png)
Therefore, when a heuristic is closer to the actual cost of a node for each node, it dominates the other heuristic.

## Working towards A*
![](lecture_4/Screenshot%202022-01-22%20at%2016.39.26.png)

![](lecture_4/Screenshot%202022-01-22%20at%2016.42.47.png)
* Combining UCS and greedy search is already complete (if heuristic is admissible)
* Complexity depends very much on the quality of the heuristic: if heuristic is very bad, it approaches UCS.

![](lecture_4/Screenshot%202022-01-22%20at%2016.44.43.png)
UCS + greedy adds guidance to the cost front search of UCS.

### Proof of UCG+G optimality
![](lecture_4/Screenshot%202022-01-22%20at%2016.50.53.png)
* The heuristic of a goal is always zero
* A is a better solution than B, therefore has lower cost
-> A is chosen before B, if they’re both in the frontier.


![](lecture_4/Screenshot%202022-01-22%20at%2016.48.36.png)
* Ancestor has lower cost and lower cost + heuristic than B (cost + heuristic can never be higher than the cost of A, definition of admissability).
-> N will be chosen before B
-> A will be chosen before B

## Late check vs early check
![](lecture_4/Screenshot%202022-01-22%20at%2017.04.19.png)
If you return at the first found goal, before evaluating all elements in the frontier, it is not sure that the node in the frontier is actually the best.

![](lecture_4/Screenshot%202022-01-22%20at%2017.05.09.png)
If you first expand all and then do goal check in order, optimality is guaranteed. 

![](lecture_4/Screenshot%202022-01-22%20at%2017.11.20.png)
This algorithm only stops when all of the costs in the frontier are higher than the cost of the found goal.

## Comparison
![](lecture_4/Screenshot%202022-01-22%20at%2017.13.37.png)

## Redundant path elimination
![](lecture_4/Screenshot%202022-01-22%20at%2017.25.25.png)
* If a node has already been visited, do not expand it again.

![](lecture_4/Screenshot%202022-01-22%20at%2017.27.13.png)
* This example shows a situation in which A* would not find the optimal path
* This is because the heuristic of b seemed better, but the cost of the path from a was actually better.
* The heuristic was inconsistent!

## Consistency of heuristics
![](lecture_4/Screenshot%202022-01-22%20at%2017.29.22.png)
* Difference between heuristics of two neighbouring nodes is lower than the difference between the actual costs.
* If this is the case, the heuristic is always also admissible.
* Because of this, you always find nodes in their optimal order -> you need this to be able to perform redundant path elimination!


![](lecture_4/Screenshot%202022-01-22%20at%2017.32.24.png)
Can get a very large frontier though, therefore 
![](lecture_4/Screenshot%202022-01-22%20at%2018.36.32.png)


![](lecture_4/Screenshot%202022-01-22%20at%2018.44.48.png)




#bioinformatics/fundamentals_of_AI/summary