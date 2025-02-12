Exercise 1.1: Self-Play Suppose, instead of playing against a random
opponent, the reinforcement learning algorithm described above played against
itself. What do you think would happen in this case? Would it learn a different
way of playing?

Exercise 1.2: Symmetries Many tic-tac-toe positions appear different but
are really the same because of symmetries. How might we amend the reinforcement learning algorithm described above to take advantage of this? In what
ways would this improve it? Now think again. Suppose the opponent did not
take advantage of symmetries. In that case, should we? Is it true, then, that
symmetrically equivalent positions should necessarily have the same value?

Exercise 1.3: Greedy Play Suppose the reinforcement learning player was
greedy, that is, it always played the move that brought it to the position that
it rated the best. Would it learn to play better, or worse, than a nongreedy
player? What problems might occur?

Exercise 1.4: Learning from Exploration Suppose learning updates occurred
after all moves, including exploratory moves. If the step-size parameter is
appropriately reduced over time, then the state values would converge to a
set of probabilities. What are the two sets of probabilities computed when we
do, and when we do not, learn from exploratory moves? Assuming that we
do continue to make exploratory moves, which set of probabilities might be
better to learn? Which would result in more wins?

Exercise 1.5: Other Improvements Can you think of other ways to improve
the reinforcement learning player? Can you think of any better way to solve
the tic-tac-toe problem as posed?
