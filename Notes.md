#  About Reinforcement Learning
## 1 The Reinforcement Learning Problem
### 1.1 Reinforcement Learning 
### 1.2 Examples 
### 1.3 Elements of Reinforcement Learning
### 1.4 Limitations and Scope 
### 1.5 An Extended Example: Tic-Tac-Toe 
### 1.6 Summary  
### 1.7 History of Reinforcement Learning 
### 1.8 Bibliographical Remarks 

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

## 3 Finite Markov Decision Processes 53
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

## 7 Eligibility Traces 167
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
###9.1 Value Prediction with Function Approximation 
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
