lecture_3

# Lecture 3: uninformed search part 2
## Graph search
![](lecture_3/Screenshot%202022-01-16%20at%2015.51.16.png)
* A naive algorithm for search in graphs
* No loop detection

## Loop detection
![](lecture_3/Screenshot%202022-01-16%20at%2015.58.41.png)
* Check wether a node is not yet visited

## Depth-first search
![](lecture_3/Screenshot%202022-01-16%20at%2016.01.00.png)
* Order: last in, first out
* Longest routes get extended first

### Complexity
![](lecture_3/Screenshot%202022-01-16%20at%2016.04.16.png)

![](lecture_3/Screenshot%202022-01-16%20at%2016.07.16.png)
* Pro’s
	* Complete if loop breaking
	* Low space complexity
* Cons
	* Finds left-most solution
	* Time complexity O(b^m)


## Breadth first search
### Principle
First in-first out -> expand the shallowest node first.
![](lecture_3/Screenshot%202022-01-16%20at%2016.31.16.png)

![](lecture_3/Screenshot%202022-01-16%20at%2016.31.59.png)
* Pro’s:
	* Depth of shallowest solution s -> time complexity O(b^s)
	* If costs are 1, optimal
* Con’s:
	* High space complexity, O(b^s) -> size of the last tier

## Iterative deepening
![](lecture_3/Screenshot%202022-01-16%20at%2016.38.28.png)


![](lecture_3/Screenshot%202022-01-16%20at%2016.39.35.png)

### Comparison
![](lecture_3/Screenshot%202022-01-16%20at%2016.43.32.png)

## Bidirectional search
![](lecture_3/Screenshot%202022-01-16%20at%2016.44.59.png)
* Good for very long paths

## Cost sensitive search
![](lecture_3/Screenshot%202022-01-16%20at%2016.50.15.png)
* Always select path with the lowest cost
* Late goal check -> guaranteed optimal path

![](lecture_3/Screenshot%202022-01-16%20at%2020.43.02.png)
* c*/e: optimal solution length divided by the minimal cost of an arc

![](lecture_3/Screenshot%202022-01-16%20at%2016.52.02.png)
* Breadth-first: 
	* time complexity: O(b^d), where d is the depth of the correct solution and b the branching factor.
	* Space-complexity: O(b^d), which might exceed memory
	* Optimal
* Depth-first:
	* Time complexity: O(b^m), where m is the maximum depth of the search space. If search space is infinite, it is not complete.
	* Space complexity: O(bm), branching factor multiplied by the maximum depth of the search tree. All side branches of the main branch are on the frontier.
	* Not optimal, only complete if search space is finite
* Bidirectional:
	* Time complexity: O(b^s/2)
	* Space complexity: O(b^s/2)
	* Optimal and complete
* Iterative deepening:
	* Same time complexity as breadth search: O(d^s), but 
	* Space complexity also the 





#bioinformatics/fundamentals_of_AI/summary