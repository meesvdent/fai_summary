lecture_2_2

# Lecture 2: state spaces
## Goal based search
![](lecture_2_2/Screenshot%202022-01-13%20at%2014.46.43.png)
* You have a current state and a goal
* Which sequence of actions should be selected to reach the goal?

## State space representation
![](lecture_2_2/Screenshot%202022-01-13%20at%2014.50.28.png)
* A search graph represents alle possible states and how you can travel from one state to another with single actions
	* Every state is represented only once.
	* Even in a moderately small problem, the number of possible states will be huge. Therefore this is not useful.
* In a search tree, nodes also represent states, but a node in a tree also defines the path you took to get there.
	* States are repeated throughout the tree if there exist multiple paths to get there
* Both constructed on demand.

## Search direction
![](lecture_2_2/Screenshot%202022-01-13%20at%2014.54.07.png)
* Forward search starts at the start-node
* Backward search starts at the goal.
* If the branching factor at the start of the problem is different from the branching factor at the end of the problem, there might be a difference in what is useful.

## Summary 
* An agent needs a goal to formulate the search problem before it can start searching.
* A search problem can consists of 5 aspects:
	* An initial state
	* State space definition
	* A goal test
	* A set of possible actions
	* Action costs


#bioinformatics/fundamentals_of_AI/summary