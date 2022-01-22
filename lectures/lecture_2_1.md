lecture_2_1

# Rational agents
_Agents that do the right thing._

## Definition
![](lecture_2_1/Screenshot%202022-01-13%20at%2014.14.05.png)
Though arbitrary, the above definition is chosen.

![](lecture_2_1/Screenshot%202022-01-13%20at%2014.16.23.png)
* A rational agents does the right thing. 
* An AI as a rational agents is a system which choses the optimal action given its knowledge of the environment. 
* If knowledge is complete, it acts optimally.
* To know which option is optimal, performance needs to be quantified in a utility measure.

## Types of environment
_The characteristics of an environment can be summarised in 6 variables._
![](lecture_2_1/Screenshot%202022-01-13%20at%2014.19.11.png)
* Fully observable or partially observable: 
	* Fully observable: in chess, the position of every piece is known to all players.
	* Partially observable: a car driving on the road can never view its whole surroundings with infinite precision, always limited by sensor resolution.
* Deterministic vs stochastic:
	* Deterministic: the next state is completely determined by the current state and the chosen action, no probability of a different next state.
	* Stochastic: given the current state and the action, there is a probability distribution for the next state.
	* Strategic: the next state is deterministic from the action, but there is another agent (with deterministic actions) who’s actions are not dependent only on the state. (chess)
* Episodic vs sequential:
	* Episodic: every state and its optimal action are completely independent of the previous states.
	* Sequential: the agent needs a memory: new optimal action is dependent on current state and previous states.
* Static vs dynamic:
	* Static: environment waits for next action of the agent to change.
	* Dynamic: environment can change while the agent hasn’t made a move yet.
* Discrete vs continuous:
	* Discrete: distinct steps (chess)
	* Continuous: time is continuous (robot moving)
* Single-agent vs multi-agent
	* Single-agent: only agent interacting with the environment.
	* Multi-agent: multiple agents interacting with the environment.

## Reflex vs planning based agents
![](lecture_2_1/Screenshot%202022-01-13%20at%2014.35.18.png)
SYSTEM 1

![](lecture_2_1/Screenshot%202022-01-13%20at%2014.36.02.png)
SYSTEM 2

## Conclusion
![](lecture_2_1/Screenshot%202022-01-13%20at%2014.37.24.png)
* Fundamental difference between environments
* Fundamental differences in agent designs




#bioinformatics/fundamentals_of_AI/summary