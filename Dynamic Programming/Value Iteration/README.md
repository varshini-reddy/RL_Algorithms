The aim of this exercise is to find the optimal policy that gives the maximum reward given an environment. For this, we will be using a pre-defined environment by OpenAI Gym. We will be using an environment called FrozenLake-v0.There are many environments defined by OpenAI Gym, that you can see here.



## Environment Description:

Winter is here. You and your friends were tossing around a frisbee at the park when you made a wild throw that left the frisbee out in the middle of the lake. The water is mostly frozen, but there are a few holes where the ice has melted. If you step into one of those holes, you'll fall into the freezing water. At this time, there's an international frisbee shortage, so it's absolutely imperative that you navigate across the lake and retrieve the disc.

The agent controls the movement of a character in a grid world. Some tiles of the grid are walkable, and others lead to the agent falling into the water. Additionally, the movement direction of the agent is uncertain and only partially depends on the chosen direction. The agent is rewarded for finding a walkable path to a goal tile.

The surface is described using a grid-like the following:

![img](frozen_lake.png)

Possible actions are Left(0), Right(1), Down(2), Up(3).



NOTE - Here we are slightly altering the value iteration algorithm. Instead of computing the optimal value function first, we compute the optimal policy and then find the value function associated with it.

## **Instructions**

- Initialize an environment using a pre-defined environment from OpenAI Gym.
- Set parameters gamma and theta.
- Define a function policy_improvement that returns the action which takes us to a higher valued state. This function updates the policy to the optimal policy.
- Define a function policy_evaluation that updates the state value of the environment given a policy.
- Define a function value_iteration that calls the above-defined functions to get an optimal policy, action sequence governed by the policy and the state value function.
- Now test the policy by checking how many episodes (with a fixed number of steps) in the 100 episode loop does the agent reach the final goal.
  - First, try the environment with a random policy, by taking random actions at each state.
  - Next, take actions based on the optimal policy.

## **Hints**

Equation to compute the value function:

\pi(s)= \sum_{\{s',r\}} p(\{s',r\}\ |\ s,a)\ [r+\gamma v(s')]

Equation to computer Delta:

\triangle\gets\max(\triangle,|v-v(s)|)

gym.make(environment-name)

Access a pre-defined environment

Env.action_space.n

Returns the number of discrete actions

Env.observation_space.n

Returns the number of discrete states

np.zeros()

Return a new array of given shape and type, filled with zeros.

environment_object.env.P[s][a]

Returns the probability of reaching successor state (s’) and its reward (r)

np.argmax()

Returns the indices of the maximum values along an axis.

max()

Returns the largest item in an iterable or the largest of two or more arguments.

abs()

Returns the absolute value of a number.