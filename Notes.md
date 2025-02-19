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
* A **policy** defines the learning agent’s way of behaving at a given time i.e. a policy is a mapping from perceived states of the environment to actions to be taken when in those states. Policy may be a simple function or lookup table, it may involve extensive computation such as a search process. policies may deterministic  or may be stochastic.
* A **reward** signal defines the goal in a reinforcement learning problem. On each time step, the environment sends to the reinforcement learning agent a single number, a reward.
* The agent’s sole objective is to maximize the total reward it receives over the long run. The reward signal thus defines what are the good and bad events for the agent. They are the immediate and defining features of the problem faced by the agent.
* The reward sent to the agent at any time depends on the agent’s current action and the current state of the agent’s environment. The agent cannot alter the
process that does this. The only way the agent can influence the reward signal is through its actions, which can have a direct effect on reward, or an indirect effect through changing the environment’s state.
* In example of Phil eating breakfast, the reinforcement learning agent directing his behavior might receive different reward signals when he eats his breakfast depending on how hungry he is, what mood he is in, and other features of his of his body, which is part of his internal reinforcement learning agent’s environment.
* The reward signal is the primary basis for altering the policy. If an action selected by the policy is followed by low reward, then the policy may be changed to select
some other action in that situation in the future.
* In general, reward signals may be stochastic functions of the state of the environment and the actions taken. Whereas the reward signal indicates what is good in an immediate sense
* A **value function** specifies what is good in the long run. Roughly, the value of a state is the total amount of reward an agent can expect to accumulate over the future, starting from that state. Whereas rewards determine the immediate, intrinsic desirability of environmental states, values indicate the long-term desirability of states after taking into account the states that are likely to follow, and the rewards available in those states.
* For example, a state might always yield a low immediate reward but still have a high value because it is regularly followed by other states that yield high rewards. Or the reverse
could be true.
* To make a human analogy, rewards are somewhat like pleasure (if high) and pain (if low), whereas values correspond to a more refined and farsighted judgment of how pleased or displeased we are that our environment is in a particular state.
* Rewards are in a sense primary, whereas values, as predictions of rewards, are secondary. Without rewards there could be no values, and the only purpose of estimating values is to achieve more reward. Nevertheless, it is values with which we are most concerned when making and evaluating decisions.
* Action choices are made based on value judgments. We seek actions that bring about states of highest value, not highest reward, because these actions obtain the greatest amount of reward for us over the long run.
* In decision-making and planning, the derived quantity called value is the one with which we are most concerned. Unfortunately, it is much harder to determine values than it is to
determine rewards.
* Rewards are basically given directly by the environment, but values must be estimated and re-estimated from the sequences of observations an agent makes over its entire lifetime.
* In fact, the most important component of almost all reinforcement learning algorithms we consider is a method for efficiently estimating values.
* The central role of value estimation is arguably the most important thing in reinforcement learning.
* A **model of the environment** is something that mimics the behavior of the environment, or more generally, that allows inferences to be made about how the environment will behave.
* For example, given a state and action, the model might predict the resultant next state and next reward.
* Models are used for planning, by which we mean any way of deciding on a course of action by considering possible future situations before they are actually experienced.
* Methods for solving reinforcement learning problems that use models and planning are called model-based methods, as opposed to simpler model free methods that are explicitly trial-and-error learners—viewed as almost the opposite of planning.
* In Chapter 9 we explore reinforcement learning systems that simultaneously learn by trial and error, learn a model of the environment, and use the model for planning.
* Modern reinforcement learning spans the spectrum from low-level, trial-and-error learning to high-level, deliberative planning.
  
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
* The core ideas of reinforcement learning algorithms in their simplest forms, that in which the **state and action spaces are small enough** for the approximate action-value function to be represented as **an array, or table**.
* These methods can often find **exact solutions**, that is, they can often find exactly the optimal value function and the optimal policy.
* 
## 2 Multi-arm Bandits 
*  Solution methods for the special of the reinforcement learning problem in which there is only a single state, called bandit problems
*  Reinforcement learning is different from other types of learning because it uses training information that evaluates the actions taken rather than instructs by giving correct actions. That's why we need for active exploration, for an explicit trial-and-error search for good behavior.
*  Purely **evaluative feedback** indicates how good the action taken is, but not whether it is the best or the worst action possible. Evaluative feedback is the basis of methods for function optimization, including evolutionary methods.
*  Purely **instructive feedback**, on the other hand, indicates the correct action to take, independently of the action actually taken. This kind of feedback is the basis of supervised learning, which includes large parts of pattern classification, artificial neural networks, and system identification.
*  In their pure forms, these two kinds of feedback are quite distinct: evaluative feedback depends entirely on the action taken, whereas instructive feedback is
independent of the action taken.
* There are also interesting intermediate cases in which evaluation and instruction blend together.
* We will learn evaluative aspect of reinforcement learning in a simplified setting, one that does not involve learning to act in more than one situation. This **nonassociative** setting is the one in which most prior work involving evaluative feedback has been done, and it avoids much of the complexity of the full reinforcement learning problem. This case will
enable us to see most clearly how evaluative feedback differs from, and yet can be combined with, instructive feedback.
* The particular **nonassociative, evaluative feedback problem** that we explore is a **simple version of the n-armed bandit problem**. We use this problem to introduce a number of basic learning methods which we extend to the **full reinforcement learning problem**.
* What happens when the bandit problem becomes associative, that is, when actions are taken in more than one situation?

### 2.1 An n-Armed Bandit Problem 
### 2.2 Action-Value Methods 
#### Methods for estimating the values of actions and for using the estimates to make action selection decisions.
* Let true (actual) value of action a = **q(a)**,
  
   and the estimated value on the t-th time step = **Q<sub>t</sub>(a)**
  
   As the true value of an action is the **mean reward received when that action is selected**. One natural way to estimate this is by **averaging the rewards actually received when the action was selected**.
  
   In other words, if by the t-th time step action a has been chosen **N<sub>t</sub>(a)** times prior to **t**, yielding rewards **R1, R2, . . . , R<sub>N <sub>t</sub> (a)</sub>**, then its value is estimated to be **Q<sub>t</sub>(a) = R1 + R2 + · · · +  R<sub>N <sub>t</sub> (a)</sub> /N<sub>t</sub>(a)**.
* If **N<sub>t</sub>(a) = 0**, then we define Q<sub>t</sub>(a) instead as some default value, such as **Q<sub>1</sub>(a) = 0**. As **N<sub>t</sub>(a) → ∞**, by the law of large numbers, Q<sub>t</sub>(a) converges to q(a).
* We call this the **sample-average method** for estimating action values because each estimate is a **simple average** of the sample of relevant rewards.**(not necessarily the best method)**.
* Nevertheless, for now let us stay with this simple estimation method and turn to the question of **how the estimates might be used to select actions?**.
* The simplest **action selection rule** is to select the action (or one of the actions) with **highest estimated action value**, that is, to select at step t one of the greedy actions, **A<sup>*</sup><sub>t</sub>**, for which
  
  <div align="center"> 
    Q<sub>t</sub>(A<sup>∗</sup><sub>t</sub>) = max<sub>a</sub> Q<sub>t</sub>(a).
  </div>

  This **greedy action selection method** can be written as
  <div align="center"> 
    A<sub>t</sub> = argmax<sub>a</sub> Q<sub>t</sub>(a)
  </div>

* **Greedy action selection** always exploits current knowledge to maximize immediate reward; it spends no time at all sampling apparently inferior actions to see if they might really be better.
* A simple alternative is to behave greedily most of the time, but every once in a while, say with small probability **ε**, instead to select randomly from amongst all the actions with equal probability independently of the action value estimates. We call methods using this near-greedy action selection rule **ε-greedy methods**. An advantage of these methods is that, in the limit as the number of plays increases, every action will be sampled an infinite number of times, guaranteeing that N<sub>t</sub>(a) → ∞ for all a, and thus ensuring that all the Q<sub>t</sub>(a) converge to q(a). This of course implies that the probability of selecting the optimal action converges to greater than **1 − ε** , that is, to near certainty. (These are just asymptotic guarantees),
#### **The practical effectiveness of these methods**:
* To roughly assess the relative effectiveness of the **greedy and ε-greedy methods**, we compared them numerically on a suite of test problems.
* This was a set of **2000 randomly generated n-armed bandit tasks** with **n = 10**.
* For each bandit, the action values, **q(a), a = 1, . . . , 10**, were selected according to a **normal (Gaussian) distribution with mean 0 and variance 1**.
* On t-th time step with a given bandit, the actual reward **R<sub>t</sub>** was the **q(A<sub>t</sub>)** for the bandit **(where A<sub>t</sub> was the action selected)** plus a **normally distributed** noise term that was **mean 0** and **variance 1**.
* Averaging over bandits, we can plot the performance and behavior of various methods as they improve with experience over 1000 steps, as in Figure. We call this suite of test tasks the **10-armed testbed**.

* figure: Average performance of ε-greedy action-value methods on the 10-armed testbed. These data are averages over 2000 tasks. All methods used sample averages as their action-value estimates. The detailed structure at the beginning of these curves depends on how actions are selected when multiple actions have the same maximal action value. Here such ties were
broken randomly. An alternative that has a similar effect is to add a verysmall amount of randomness to each of the initial action values, so that ties effectively never happen.



* This figure **compares a greedy method with two ε-greedy methods (ε = 0.01 and ε = 0.1)**, as described above, on the 10-armed testbed.
* Both methods formed their action-value estimates using the sample-average technique.
* The **upper graph shows the increase in expected reward with experience**.
* The **greedy method improved slightly faster** than the other methods **at the very beginning**, but then **leveled off at a lower level**. It achieved **a reward per step of only 
  about 1**, compared with the **best possible of about 1.55** on this testbed.
* The **greedy method performs significantly worse in the long run** because it often gets stuck performing suboptimal actions.
* The **lower graph shows that the greedy method found the optimal action in only approximately one-third of the tasks**. In the other two-thirds, its initial samples of the optimal action were disappointing, and it never returned to it.
* The **ε-greedy methods eventually perform better** because they **continue to explore**, and to improve their chances of recognizing the optimal action.
* The ε = 0.1 method explores more, and usually finds the optimal action earlier, but never selects it more than 91% of the time.
* The ε = 0.01 method improves more slowly, but eventually performs better than the ε = 0.1 method on both performance measures.
*   It is also possible to reduce ε over time to try to get the best of both high and low values.
* The advantage of ε-greedy over greedy methods depends on the task.
* For example, suppose the **reward variance** had been **larger**, say **10** instead of 1. With noisier rewards it takes **more exploration** to find the optimal action, and ε-greedy 
  methods should fare even better relative to the greedy method.
* On the other hand, if the **reward variances were zero**, then the greedy method would know the true value of each action after trying it once. In this case the greedy method might 
  actually perform best because it would soon find the optimal action and then never explore.
* But even in the deterministic case, there is a large advantage to exploring if we weaken some of the other assumptions.
* For example, suppose the bandit task were nonstationary, that is, that the true values of the actions changed over time. In this case exploration is needed even in the deterministic case to make sure one of the nongreedy actions has not changed to become better than the greedy one. As we will see in the next few chapters, **effective nonstationarity is the case most commonly encountered in reinforcement learning**. Even if the underlying task is stationary and deterministic, the learner faces a set of banditlike decision tasks each of which changes over time due to the learning process itself. Reinforcement learning requires a balance between exploration and exploitation.
  
### 2.3 Incremental Implementation
* As all estimate action values are sample averages of observed rewards. 
* The obvious implementation is to maintain  for each action a, a record of all the rewards that have followed the selection of that action.
*  Then, when the estimate of the value of action a is needed at time t, it can be computed according to (2.1), which we repeat here:

### 2.4 Tracking a Nonstationary Problem
### 2.5 Optimistic Initial Values 
### 2.6 Upper-Confidence-Bound Action Selection
* Exploration is needed because the estimates of the action values are uncertain.
  * Uncertainty in Action Value Estimates:
  * Initially, the agent has no knowledge of the environment and therefore has uncertain estimates of the action values.
  * This uncertainty arises from two main sources:
    * Limited data: The agent has only observed a limited number of state-action transitions and their corresponding rewards. As a result, its estimates of the action values are based on a small sample of data and are therefore uncertain.
    * Stochasticity of the environment: The environment may be inherently stochastic, meaning that the same action in the same state can lead to different outcomes. This stochasticity introduces further uncertainty into the action value estimates.
    
* The greedy actions are those that look best at present, but some of the other actions may actually be better. ε-greedy action selection forces the non-greedy actions to be tried, but indiscriminately, with no preference for those that are
nearly greedy or particularly uncertain. It would be better to select among
the non-greedy actions according to their potential for actually being optimal,
taking into account both how close their estimates are to being maximal and
the uncertainties in those estimates. One effective way of doing this is to select
actions as

<div align="center">
action = argmax(Q(a) + c * sqrt(ln(t) / N(a)))
<div>
  
where ln t denotes the natural logarithm of t (the number that e ≈ 2.71828
would have to be raised to in order to equal t), and the number c > 0 controls
the degree of exploration. If Nt(a) = 0, then a is considered to be a maximizing
action.
The idea of this upper confidence bound (UCB) action selection is that the
square-root term is a measure of the uncertainty or variance in the estimate
of a’s value. The quantity being max’ed over is thus a sort of upper bound
on the possible true value of action a, with the c parameter determining the
confidence level. Each time a is selected the uncertainty is presumably reduced;
Nt(a) is incremented and, as it appears in the denominator of the uncertainty
term, the term is decreased. On the other hand, each time an action other a is
selected t is increased; as it appears in the numerator the uncertainty estimate
is increased. The use of the natural logarithm means that the increase gets
smaller over time, but is unbounded; all actions will eventually be selected, but
42 CHAPTER 2. MULTI-ARM BANDITS
�-greedy � = 0.1
UCB c = 2
Average
reward
Steps
Figure 2.3: Average performance of UCB action selection on the 10-armed
testbed. As shown, UCB generally performs better that ε-greedy action selection, except in the first n plays, when it selects randomly among the as-yetunplayed actions. UCB with c = 1 would perform even better but would not
show the prominent spike in performance on the 11th play. Can you think of
an explanation of this spike?
as time goes by it will be a longer wait, and thus a lower selection frequency,
for actions with a lower value estimate or that have already been selected more
times.
Results with UCB on the 10-armed testbed are shown in Figure 2.3. UCB
will often perform well, as shown here, but is more difficult than ε-greedy
to extend beyond bandits to the more general reinforcement learning settings
considered in the rest of this book. One difficulty is in dealing with nonstationary problems; something more complex than the methods presented in
Section 2.4 would be needed. Another difficulty is dealing with large state
spaces, particularly function approximation as developed in Part III of this
book. In these more advanced settings there is currently no known practical
way of utilizing the idea of UCB action selection.
### 2.7 Gradient Bandits
* We have seen methods that estimate action values and use those estimates to select actions.(a good approach, but it is not the only one possible.)
* Now, we consider learning a numerical preference **H<sub>t</sub>(a)** for each action a.

  The larger the preference, the more often that action is taken, but the preference has no interpretation in terms of reward.

  Only the relative preference of one action over another is important; if we add 1000 to all the preferences there is no affect on the action probabilities, which are determined 
  according to a soft-max distribution (i.e., Gibbs or Boltzmann distribution) as follows:


### 2.8 Associative Search (Contextual Bandits)
* Nonassociative tasks, in which there is no need to associate different actions with different situations. In these tasks the learner either tries to find a single best action when the task is stationary, or tries to track the best action as it changes over time when the task is nonstationary.
* In a general reinforcement learning task there is more than one situation, and the goal is to learn a policy: a mapping from situations to the actions that are best in those situations.
* To extend nonassociative tasks into the associative setting:
  
  Example:

  Suppose there are several different n-armed bandit tasks, and that on each play you confront one of these chosen at random. Thus, the bandit task changes randomly from play 
  to play. This would appear to us as a single, nonstationary n-armed bandit task whose true action values change randomly from play to play. We could try using one of the methods 
  that can handle nonstationarity, but unless the true action values change slowly, these methods will not work very well.

  Now suppose, however, that when a bandit task is selected for us, we are given some distinctive clue about its identity (but not its action values). Maybe we are facing an actual 
  slot machine that changes the color of its display as it changes its action values. Now you can learn a policy associating each task, signaled by the color you see, with the best 
  action to take when facing that task—for instance, if red, play arm 1; if green, play arm 2. With the right policy we can usually do much better than we could in the absence of any 
  information distinguishing one bandit task from another.

* This is **an example of an associative search task**, so called because **it involves both trial-and-error learning in the form of search for the best actions and association of these actions with the situations in which they are best**(Associative search tasks are often now termed contextual bandits in the literature).
* Associative search tasks are intermediate between the n-armed bandit problem and the full reinforcement learning problem. They are like the full reinforcement learning problem in that they involve learning a policy, but like our version of the n-armed bandit problem in that each action affects only the immediate reward. If actions are allowed to affect the next situation as well as the reward, then we have the full reinforcement learning problem.
* 
  
  
### 2.9 Summary

## 3 Finite Markov Decision Processes (RL problems in terms of optimal control of Markov decision processes)
* The general problem formulation that is—**finite markov decision processes**—and its main ideas including Bellman equations and value functions.
* 
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
* The elements of the reinforcement learning problem:
* Reinforcement learning is about learning from interaction how to behave in order to achieve a goal.
* The reinforcement learning agent and its environment interact over a sequence of discrete time steps.
* The specification of their interface defines a particular task:
  * the actions are the choices made by the agent;
  * the states are the basis for making the choices;
  * and the rewards are the basis for evaluating the choices.
* Everything inside the agent is completely known and controllable by the agent; everything outside is incompletely controllable but may or may not be completely known.
* A policy is a stochastic rule by which the agent selects actions as a function of states.
* The agent’s objective is to maximize the amount of reward it receives over time.
* The return is the function of future rewards that the agent seeks to maximize. It has several different definitions depending upon the nature of the task and whether one wishes to discount delayed reward.
* The undiscounted formulation is appropriate for episodic tasks, in which the agent–environment interaction breaks naturally into episodes; the discounted formulation is appropriate for continuing tasks, in which the interaction does not naturally break into episodes but continues without limit.
* An environment satisfies the Markov property if its state signal compactly summarizes the past without degrading the ability to predict the future. This is rarely exactly true, but often nearly so; the state signal should be chosen or constructed so that the Markov property holds as nearly as possible. We assume that this has already been done and focus on the decision making problem: how to decide what to do as a function of whatever state signal is available.
* If the Markov property does hold, then the environment is called a **Markov decision process (MDP)**.
* A finite MDP is an MDP with finite state and action sets. Most of the current theory of reinforcement learning is restricted to finite MDPs, but the methods and ideas apply more
generally.
* A policy’s value functions assign to each state, or state–action pair, the expected return from that state, or state–action pair, given that the agent uses the policy.
* The optimal value functions assign to each state, or state–action pair, the largest expected return achievable by any policy.
* A policy whose value functions are optimal is an **optimal policy**. Whereas the **optimal value functions for states and state–action pairs are unique for a given MDP**, there can be many optimal policies.
* Any policy that is greedy with respect to the optimal value functions **must be an optimal policy**.
* The **Bellman optimality equations are special consistency condition** that the optimal value functions must satisfy and that can, in principle, be solved for the optimal value functions, from which an optimal policy can be determined with relative ease.
* A reinforcement learning problem can be posed in a variety of different ways depending on assumptions about the level of knowledge initially available to the agent.
* In problems of complete knowledge, the agent has a complete and accurate model of the environment’s dynamics. If the environment is an MDP, then such a model consists of the one-step transition probabilities and expected rewards for all states and their allowable actions.
* In problems of incomplete knowledge, a complete and perfect model of the environment is not available.
* Even if the agent has a complete and accurate environment model, the agent is typically unable to perform enough computation per time step to fully use it.
* The memory available is also an important constraint. Memory may be required to build up accurate approximations of value functions, policies, and models. In most cases of practical interest there are far more states than could possibly be entries in a table, and approximations must be made.
* A well-defined notion of optimality organizes the approach to learning and provides a way to understand the theoretical properties of various learning algorithms, but it is an ideal that reinforcement learning agents can only approximate to varying degrees.
* In reinforcement learning we are very much concerned with cases in which optimal solutions cannot be found but must be approximated in some way.

## 4 Dynamic Programming 
* method for solving finite Markov decision problems
* Dynamic programming methods are well developed mathematically, but **require a complete and accurate model of the environment**.
* 
### 4.1 Policy Evaluation 
### 4.2 Policy Improvement 
### 4.3 Policy Iteration 
### 4.4 Value Iteration 
### 4.5 Asynchronous Dynamic Programming
### 4.6 Generalized Policy Iteration 
### 4.7 Efficiency of Dynamic Programming 
### 4.8 Summary 
* The basic ideas and algorithms of **dynamic programming** as they relate **to solving finite MDPs**.
* **Policy evaluation** refers to the (typically) **iterative computation of the value functions for a given policy**.
* **Policy improvement** refers to the **computation of an improved policy given the value function for that policy**.
* **Policy iteration/Value iteration  = Policy evaluation + Policy improvement**  (two most popular DP methods)
*  **Policy iteration/Value iteration** can be used to reliably **compute optimal policies and value functions for finite MDPs** given complete knowledge of the MDP.
* **Classical DP** methods operate in **sweeps through the state set**, performing a full backup operation on each state.
  * Each backup updates the value of one state based on the values of all possible successor states and their probabilities of occurring.
  * Full backups are closely related to Bellman equations: they are little more than these equations turned into assignment statements.
  * When the backups no longer result in any changes in value, convergence has occurred to values that satisfy the corresponding Bellman equation.
  * Just as there are four primary value functions (vπ, v∗, qπ, and q∗), there are four corresponding Bellman equations and four corresponding full backups.
  * An intuitive view of the operation of backups is given by backup diagrams.
* DP methods and almost all reinforcement learning methods, can be gained by viewing them as **generalized policy iteration (GPI)**.
* **GPI** is the general idea of two interacting processes revolving around an approximate policy and an approximate value function.
  * One process takes the policy as given and performs some form of policy evaluation, changing the value function to be more like the true value function for the policy.
  * The other process takes the value function as given and performs some form of policy improvement, changing the policy to make it better, assuming that the value function is its 
    value function.
* Although each process changes the basis for the other, overall they work together to find a joint solution: **a policy and value function that are unchanged by either process and, 
consequently, are optimal.**
* In some cases, GPI can be proved to converge, most notably for the classical DP methods.
* In other cases convergence has not been proved, but still the idea of GPI improves our understanding of the methods.
* It is not necessary to perform DP methods in complete sweeps through the state set.
* Asynchronous DP methods are in-place iterative methods that back up states in an arbitrary order, perhaps stochastically determined and using out-of-date information. Many of these methods can be viewed as fine-grained forms of GPI.
* Special property of DP methods: All of them update estimates of the values of states based on estimates of the values of successor states. That is, they update estimates on the basis of other estimates **(bootstrapping)**.
* Many reinforcement learning methods perform bootstrapping, even those that do not require, as DP requires, a complete and accurate model of the environment.
* In the next chapter we explore reinforcement learning methods that do not require a model and do not bootstrap. In the chapter after that we explore methods that do not require
a model but do bootstrap.

## 5 Monte Carlo Methods 
* method for solving finite Markov decision problems.
* Monte Carlo methods don’t require a model **(no model)** and are conceptually simple, but are not suited for step-by-step incremental computation **(not incremental)**.
* methods that do not require a model and do not bootstrap.
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
* method for solving finite Markov decision problems
* Temporal-difference methods require **no model** and are **fully incremental**, but are more **complex** to analyze.
* methods that do not require a model but do bootstrap.
### 6.1 TD Prediction 
### 6.2 Advantages of TD Prediction Methods 
### 6.3 Optimality of TD(0) 
### 6.4 Sarsa: On-Policy TD Control 
### 6.5 Q-Learning: Off-Policy TD Control 
### 6.6 Games, Afterstates, and Other Special Cases
### 6.7 Summary

##### NOTE : DP, MC, TD methods are differ swith respect to their efficiency and speed of convergence.

## 7 Eligibility Traces 
* Describe how DP, MC, TD methods can be combined to obtain the best features of each of them.
* Describe how the strengths of Monte Carlo methods can be combined with the strengths of temporal-difference methods via the use of eligibility traces. 
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

## 8 Planning and Learning with Tabular Methods 
* Describe how DP, MC, TD methods can be combined to obtain the best features of each of them.
* We will see how MC, TD learning methods can be combined with model learning and planning methods (such as dynamic programming) for a complete and unified solution to the tabular reinforcement learning problem.
* 
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
*  The approximate methods only find approximate solutions, but which in return can be applied effectively to much larger problems.
*  
## 9 On-policy Approximation of Action Values(reinforcement learning systems that simultaneously learn by trial and error, learn a model of the environment, and use the model for planning)

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
