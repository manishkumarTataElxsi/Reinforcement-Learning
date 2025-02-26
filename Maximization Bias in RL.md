#Maximization Bias
* It refers to the tendency of Q-learning algorithms to overestimate action values due to the **max** operator used in action selection. This bias arises when estimating the expected return, leading to overly optimistic Q-values and suboptimal policy learning.
* Why Does maximization bias occur?
  * Q-learning update rule:

    **Q(s,a) <--- Q(s,a) + alpha[r + gamma * max_{a'} Q(s',a') - Q(s,a)]**

    As here the next state's Q-values are approximations(often learned from limited experiences), the **max** operator tends to select actions with overestimated values due to random noise or estimation errors. Overtime , this results in a bias where Q-values become systematically overestimated, leading to poor policy decisions.
    
