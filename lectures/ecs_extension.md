ecs_extension

# ECS extension: Logic and automated reasoning
## Goal of automated reasoning
![](ecs_extension/Screenshot%202022-01-12%20at%2014.11.15.png)
* A set of formula’s can have certain models: a set of proposed values for each atomic formula for which each formula in the set is true.
* A new formula is logically entailed by the model if all formula’s of S are also formula’s off the new formula.
* To prove that a formula is logically entailed by the knowledge base is the goal.

## Proving logical entailment
* Forward resolution tries to prove this by evaluating every model of S in F and checking whether they’re also models.
* _Backwards resolution_ tries to combine the negation of the new formula with the knowledge base, until you arrive at a contradiction.
![](ecs_extension/Screenshot%202022-01-12%20at%2014.21.48.png)

## Overview of needed steps
![](ecs_extension/Screenshot%202022-01-12%20at%2014.23.44.png)


## Ground horn clause logic 
* consists of horn clauses: formula’s of the form `x <- a V b V … V c`
* There are only predicates with constants, _no_ variables.
* You can apply generalised modus ponens to this in a linear way to come to a resolution.

![](ecs_extension/Screenshot%202022-01-12%20at%2014.37.42.png)
* A knowledge base and the negation of the theory which we’re trying to prove.
![](ecs_extension/Screenshot%202022-01-12%20at%2015.24.44.png)
* applying generalised modus ponens wil eventually lead to an empty body on the right side, which is saying you have reached false <- true, which can never be true, therefore the negation of the formula is false, therefore the formula is true.
![](ecs_extension/Screenshot%202022-01-12%20at%2014.41.33.png)
* This can also be done when formula’s are of the form above, this is called generalised modus ponens.


## Horn clause logic
_In ground horn logic, only horn clauses with constants are allowed. The more general form, with variables, is called horn clause logic. To be able to perform backwards reasoning on these clauses, we need unification by substitution._

### Substitutions
![](ecs_extension/Screenshot%202022-01-12%20at%2015.36.40.png)
* To be able to draw conclusions from general formulas in the knowledge base, they need to be unified with the variables in the theory which needs to be proved.
* 
![](ecs_extension/Screenshot%202022-01-12%20at%2015.53.00.png)
* Formula to prove is: there exist any u and v for which u is the ancestor of v, these variables are existential.

![](ecs_extension/Screenshot%202022-01-12%20at%2015.55.11.png)
* Important to rename variables in different formula’s. This 
* This method is complete, but semi-deciding, which means that it might never complete if the statement is true, which is the halting problem.
* Not all predicate logic can be written as horn clauses, this is why we need more advanced forms of logic, like clausal logic.

## Clausal logic
![](ecs_extension/Screenshot%202022-01-12%20at%2016.12.14.png)
* Horn clauses, but there can be multiple disjunctions in the head.

### Disjunction versus negation
![](ecs_extension/Screenshot%202022-01-12%20at%2016.15.54.png)
* Important: A <- B is equivalent to A V ~B <- true
* a v b v c <- d <- -> a <- d ^ ~b ^ ~c

### Resolution principle
![](ecs_extension/Screenshot%202022-01-12%20at%2016.19.18.png)
* Because of this relation, we can apply the resolution principle
```
A v B v C	<- E ^ F ^ G
H v F 	<- I ^ J

H v F <- I ^ J <-> H <- I ^ J ^ ~F

A V B V H <- E ^ G
```
![](ecs_extension/Screenshot%202022-01-12%20at%2016.42.49.png)
* Using these tools, we can solve knowledge bases with formulas in causal form.

## Normalisation
Full predicate logic is used to translate natural language to formal logic. It has rich semantics. However, you can _not_ apply automated reasoning to full predicate logic -> it first needs to be normalised.
Full predicate logic is redundant. Everything in full predicate logic can also be expressed in clausal logic.

To make the step from full predicate logic to clausal logic, the knowledge base needs to be normalised, for which the following procedure exists.
![](ecs_extension/Screenshot%202022-01-12%20at%2021.10.35.png)

### Normalisation example
![](ecs_extension/Screenshot%202022-01-12%20at%2021.18.29.png)
1. Eliminate <- and <—>:
	1. <—> is replaced by ^ and parentheses around both sides.
	2. a <- b is replaced by a V ~b
![](ecs_extension/Screenshot%202022-01-12%20at%2021.22.05.png)
2. Move the negations inside:
	1. ~(~p) = p
	2. ~(p v q) = ~p ^ ~q
	3. ~any(x) = all(x) ~
	4. ~ all(x) = any(x) ~

6. Move disjunction inside:
	1. A V (B ^ C) = (A V B) ^ (A V C)

![](ecs_extension/Screenshot%202022-01-12%20at%2021.34.19.png)
7. eliminate ^
	1. a V b V c ^ d V e V f = a V b V c ; d V e V f
8. Drop any quantifiers

![](ecs_extension/Screenshot%202022-01-12%20at%2021.36.50.png)
9. Move ~atoms to the other side as conjunct positives

 

#bioinformatics/fundamentals_of_AI/summary









