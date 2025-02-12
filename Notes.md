#  About Reinforcement Learning
## 1 The Reinforcement Learning Problem
* Learning from interaction
* Learn by interacting with our environment
* a computational approach to learning from interaction
* how people or animals learn?
* An approach, called reinforcement learning, is much more focused on goal-directed learning from interaction than are other approaches to machine learning.

### 1.1 Reinforcement Learning 
* Reinforcement learning problems involve learning what to do — how to map situations to actions — so as to maximize a numerical reward signal.
* RL Problems are are closed-loop problems because the learning system’s actions influence its later inputs:
* The learner is not told which actions to take, as in many forms of machine learning, but instead must discover which actions yield the most reward by trying them out.
* In RL, actions may affect not only the immediate reward but also the next situation and, through that, all subsequent rewards.
* Three characteristics, not having direct instructions as to what actions to take, and where the consequences of actions,including reward signals, play out over extended time periods—are the three most important distinguishing features of reinforcement learning problems.
* RL problems in terms of optimal control of Markov decision processes 
### 1.2 Examples 
### 1.3 Elements of Reinforcement Learning
* Main elements : Agent and Environment
* Subelements : a policy, a reward signal, a value function, and a model of the environment.
* A policy defines the learning agent’s way of behaving at a given time i.e. a policy is a mapping from perceived states of the environment to actions to be taken when in those states. Policy may be a simple function or lookup table, it may involve extensive computation such as a search process. policies may deterministic  or may be stochastic.
* A reward signal defines the goal in a reinforcement learning problem. On each time step, the environment sends to the reinforcement learning agent a single number, a reward.
* The agent’s sole objective is to maximize the total reward it receives over the long run. The reward signal thus defines what are the good and bad events for the agent. They are the immediate and defining features of the problem faced by the agent.
* The reward sent to the agent at any time depends on the agent’s current action and the current state of the agent’s environment. The agent cannot alter the
process that does this. The only way the agent can influence the reward signal is through its actions, which can have a direct effect on reward, or an indirect effect through changing the environment’s state.
* In example of Phil eating breakfast, the reinforcement learning agent directing his behavior might receive different reward signals when he eats his breakfast depending on how hungry he is, what mood he is in, and other features of his of his body, which is part of his internal reinforcement learning agent’s environment.
* The reward signal is the primary basis for altering the policy. If an action selected by the policy is followed by low reward, then the policy may be changed to select
some other action in that situation in the future.
* In general, reward signals may be stochastic functions of the state of the environment and the actions taken. Whereas the reward signal indicates what is good in an immediate sense
* A value function specifies what is good in the long run. Roughly, the value of a state is the total amount of reward an agent can expect to accumulate over the future, starting from that state. Whereas rewards determine the immediate, intrinsic desirability of environmental states, values indicate the long-term desirability of states after taking into account the states that are likely to follow, and the rewards available in those states.
* For example, a state might always yield a low immediate reward but still have a high value because it is regularly followed by other states that yield high rewards. Or the reverse
could be true.
* To make a human analogy, rewards are somewhat like pleasure (if high) and pain (if low), whereas values correspond to a more refined and farsighted judgment of how pleased or displeased we are that our environment is in a particular state.
* Rewards are in a sense primary, whereas values, as predictions of rewards,
are secondary. Without rewards there could be no values, and the only purpose
of estimating values is to achieve more reward. Nevertheless, it is values with
which we are most concerned when making and evaluating decisions. Action
choices are made based on value judgments. We seek actions that bring about
states of highest value, not highest reward, because these actions obtain the
greatest amount of reward for us over the long run. In decision-making and
planning, the derived quantity called value is the one with which we are most
concerned. Unfortunately, it is much harder to determine values than it is to
determine rewards. Rewards are basically given directly by the environment,
but values must be estimated and re-estimated from the sequences of observations an agent makes over its entire lifetime. In fact, the most important
component of almost all reinforcement learning algorithms we consider is a
method for efficiently estimating values. The central role of value estimation
is arguably the most important thing we have learned about reinforcement
learning over the last few decades.


### 1.4 Limitations and Scope 
* Most of the reinforcement learning methods are structured around estimating value functions, but it is not strictly necessary to do this to solve reinforcement learning problems. 
For example, methods such as genetic algorithms, genetic programming, simulated annealing, and other optimization methods have been used to approach reinforcement learning problems
without ever appealing to value functions. These methods evaluate the “lifetime” behavior of many non-learning agents, each using a different policy for interacting with its environment, and select those that are able to obtain the most reward. We call these evolutionary methods because their operation is analogous to the way biological evolution produces organisms with skilled behavior even when they do not learn during their individual lifetimes. If the
space of policies is sufficiently small, or can be structured so that good policies are common or easy to find—or if a lot of time is available for the search—thencevolutionary methods can be effective. In addition, evolutionary methods have advantages on problems in which the learning agent cannot accurately sense the state of its environment.
* The focus  on reinforcement learning methods is that involve learning while interacting with the environment, which evolutionary methods do not do (unless they evolve learning algorithms, as in some of the approaches that have been studied). It is our belief that methods able to take advantage of the details of individual behavioral interactions can be much more efficient than evolutionary methods in many cases. Evolutionary methods ignore much of the useful structure of the reinforcement learning problem: they do not use
the fact that the policy they are searching for is a function from states to actions; they do not notice which states an individual passes through during its lifetime, or which actions it selects. In some cases this information can be misleading (e.g., when states are misperceived), but more often it should enable more efficient search. Although evolution and learning share many features and naturally work together, we do not consider evolutionary methods
by themselves to be especially well suited to reinforcement learning problems.


* However, we do include some methods that, like evolutionary methods,
do not appeal to value functions. These methods search in spaces of policies
defined by a collection of numerical parameters. They estimate the directions
the parameters should be adjusted in order to most rapidly improve a policy’s
performance. Unlike evolutionary methods, however, they produce these estimates while the agent is interacting with its environment and so can take
advantage of the details of individual behavioral interactions. Methods like
this, called policy gradient methods, have proven useful in many problems, and
some of the simplest reinforcement learning methods fall into this category. In
fact, some of these methods take advantage of value function estimates to improve their gradient estimates. Overall, the distinction between policy gradient
methods and other methods we include as reinforcement learning methods is
not sharply defined.
* Reinforcement learning’s connection to optimization methods deserves some
additional comment because it is a source of a common misunderstanding.
When we say that a reinforcement learning agent’s goal is to maximize a numerical reward signal, we of course are not insisting that the agent has to
actually achieve the goal of maximum reward. Trying to maximize a quantity
does not mean that that quantity is ever maximized. The point is that a reinforcement learning agent is always trying to increase the amount of reward
it receives. Many factors can prevent it from achieving the maximum, even if
one exists. In other words, optimization is not the same a optimality.

### 1.5 An Extended Example: Tic-Tac-Toe 
### 1.6 Summary   
* Reinforcement learning is a computational approach to understanding and automating goal-directed learning and decision-making.
* It is distinguished from other computational approaches by its emphasis on learning by an agent from direct interaction with its environment, without relying on exemplary supervision or complete models of the environment.
* Reinforcement learning is the first field to seriously address the computational issues that arise when learning from interaction with an environment in order to achieve long-term goals.
* Reinforcement learning uses a formal framework defining the interaction between a learning agent and its environment in terms of states, actions, and rewards. This framework is intended to be a simple way of representing essential features of the artificial intelligence problem. These features include a sense of cause and effect, a sense of uncertainty and nondeterminism, and the existence of explicit goals.
* The concepts of value and value functions are the key features of most of the reinforcement learning methods. The value functions are important for efficient search in the space
of policies. Their use of value functions distinguishes reinforcement learning methods from evolutionary methods that search directly in policy space guidedby scalar evaluations of entire policies.


# I Tabular Solution Methods 
## 2 Multi-arm Bandits 
### 2.1 An n-Armed Bandit Problem 
### 2.2 Action-Value Methods 
### 2.3 Incremental Implementation
### 2.4 Tracking a Nonstationary Problem
### 2.5 Optimistic Initial Values 
### 2.6 Upper-Confidence-Bound Action Selection
### 2.7 Gradient Bandits
### 2.8 Associative Search (Contextual Bandits)
### 2.9 Summary

## 3 Finite Markov Decision Processes (RL problems in terms of optimal control of Markov decision processes)

### 3.1 The Agent–Environment Interface 
###  3.2 Goals and Rewards
### 3.3 Returns 
### 3.4 Unified Notation for Episodic and Continuing Tasks 
### 3.5 The Markov Property 
### 3.6 Markov Decision Processes 
### 3.7 Value Functions 
### 3.8 Optimal Value Functions 
### 3.9 Optimality and Approximation 
### 3.10 Summary 

## 4 Dynamic Programming 
### 4.1 Policy Evaluation 
### 4.2 Policy Improvement 
### 4.3 Policy Iteration 
### 4.4 Value Iteration 
### 4.5 Asynchronous Dynamic Programming
### 4.6 Generalized Policy Iteration 
### 4.7 Efficiency of Dynamic Programming 
### 4.8 Summary 

## 5 Monte Carlo Methods 
### 5.1 Monte Carlo Prediction
### 5.2 Monte Carlo Estimation of Action Values 
### 5.3 Monte Carlo Control 
### 5.4 Monte Carlo Control without Exploring Starts 
### 5.5 Off-policy Prediction via Importance Sampling
### 5.6 Incremental Implementation 
### 5.7 Off-Policy Monte Carlo Control
### 5.8 Importance Sampling on Truncated Returns
### 5.9 Summary

## 6 Temporal-Difference Learning 
### 6.1 TD Prediction 
### 6.2 Advantages of TD Prediction Methods 
### 6.3 Optimality of TD(0) 
### 6.4 Sarsa: On-Policy TD Control 
### 6.5 Q-Learning: Off-Policy TD Control 
### 6.6 Games, Afterstates, and Other Special Cases
### 6.7 Summary

## 7 Eligibility Traces 
### 7.1 n-Step TD Prediction
### 7.2 The Forward View of TD(λ) 
### 7.3 The Backward View of TD(λ) 
### 7.4 Equivalences of Forward and Backward Views 
### 7.5 Sarsa(λ) 
### 7.6 Watkins’s Q(λ) 
### 7.7 Off-policy Eligibility Traces using Importance Sampling 
### 7.8 Implementation Issues 
### 7.9 Variable λ 
### 7.10 Conclusions 

## 8 Planning and Learning with Tabular Methods 195
### 8.1 Models and Planning 
### 8.2 Integrating Planning, Acting, and Learning 
### 8.3 When the Model Is Wrong 

### 8.4 Prioritized Sweeping 
### 8.5 Full vs. Sample Backups 
### 8.6 Trajectory Sampling 
### 8.7 Heuristic Search 
### 8.8 Monte Carlo Tree Search 
### 8.9 Summary 

# II Approximate Solution Methods 

## 9 On-policy Approximation of Action Values
### 9.1 Value Prediction with Function Approximation 
### 9.2 Gradient-Descent Methods
### 9.3 Linear Methods 
### 9.4 Control with Function Approximation 
### 9.5 Should We Bootstrap? 
### 9.6 Summary 

## 10 Off-policy Approximation of Action Values 

## 11 Policy Approximation 
### 11.1 Actor–Critic Methods 
### 11.2 Eligibility Traces for Actor–Critic Methods
### 11.3 R-Learning and the Average-Reward Setting 
