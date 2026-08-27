# Q-Learning CliffWalking Reinforcement Learning

## Overview

This project implements the Q-Learning reinforcement learning algorithm using the CliffWalking-v1 environment from Gymnasium.

The goal is to train an agent to learn an optimal path from the starting position to the goal while avoiding the cliff and maximizing the total reward.

## Algorithm

Q-Learning is an off-policy Temporal Difference reinforcement learning algorithm.

The Q-value is updated using the following equation:

Q(s,a) ← Q(s,a) + α[r + γ max Q(s',a') - Q(s,a)]

The algorithm learns the expected value of taking an action in a particular state and uses the maximum Q-value of the next state during the update.

## Environment

The project uses the Gymnasium CliffWalking-v1 environment.

The environment contains:

- 48 states
- 4 possible actions
- A starting state
- A goal state
- A cliff area with negative rewards

The agent learns to reach the goal while avoiding the cliff.

## Q-Table

The agent maintains a Q-table with 48 states and 4 possible actions.

Each row represents a state and each column represents an action.

The Q-table is initialized with zeros and updated during training.

## Exploration Strategy

An epsilon-greedy policy is used to balance exploration and exploitation.

With probability epsilon, the agent selects a random action for exploration.

Otherwise, the agent selects the action with the highest Q-value.

## Hyperparameters

| Parameter | Value |
|---|---:|
| Learning Rate (α) | 0.5 |
| Discount Factor (γ) | 0.99 |
| Exploration Rate (ε) | 0.1 |
| Training Episodes | 500 |
| States | 48 |
| Actions | 4 |

## Training

The agent is trained for 500 episodes.

During each episode:

1. The environment is reset.
2. The current state is obtained.
3. An action is selected using the epsilon-greedy policy.
4. The agent performs the action.
5. The reward and next state are obtained.
6. The Q-table is updated using the Q-Learning update rule.
7. The process continues until the episode ends.

The environment is rendered every 50 episodes during training.

## Results

After training for 500 episodes, the learned policy is evaluated by selecting the action with the highest Q-value for each state.

The final evaluation achieved:

- Total Reward: -13
- Episode Length: 13 steps

This indicates that the learned policy successfully reaches the goal using a short path through the environment.

## Q-Table Examples

The notebook also examines the learned Q-values for individual states.

For example, the Q-values for state 36 and state 35 are inspected after training to understand the actions preferred by the learned policy.

## Technologies Used

- Python
- NumPy
- Gymnasium
- Jupyter Notebook

## Project Structure

Q-Learning-CliffWalking-Reinforcement-Learning/

- Q_Learning_CliffWalking.ipynb - Q-Learning implementation
- README.md - Project documentation
- .gitignore - Git ignored files

## How to Run

Install the required libraries:

pip install gymnasium numpy jupyter

Open the notebook:

Q_Learning_CliffWalking.ipynb

Run the notebook cells from top to bottom.

## Key Concepts

This project demonstrates:

- Reinforcement Learning
- Q-Learning
- Off-policy learning
- Temporal Difference learning
- Q-Tables
- Epsilon-greedy policy
- Exploration vs exploitation
- State-action values
- Reward-based learning
- Gymnasium environments

## Future Improvements

Possible improvements include:

- Implement epsilon decay
- Compare Q-Learning with SARSA
- Plot reward versus episode
- Plot episode length versus episode
- Experiment with different learning rates
- Experiment with different discount factors
- Experiment with different exploration rates
- Save and load the trained Q-table

## Author

Devansh Singh