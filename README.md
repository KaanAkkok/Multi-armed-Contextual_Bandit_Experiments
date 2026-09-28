# Multi-armed-Contextual_Bandit_Experiments

## Introduction
This project implements and compares several popular Multi-Armed Bandit (MAB) algorithms, including Upper Confidence Bound (UCB), Epsilon-Greedy, Linear UCB, and Linear Thompson Sampling. The goal is to simulate their performance in a multi-armed bandit environment, which can be configured as stationary or non-stationary, and visualize their average rewards and optimal action percentages over time.

## Implemented Algorithms

### 1. UCB (Upper Confidence Bound)
An exploration-exploitation algorithm that balances choosing the best-known action with exploring less-known actions. It is implemented with different Q-value update methods:
- `sample_average`
- `constant_step_size`
- `recency_weighted`
- `sliding_window`

### 2. Epsilon-Greedy
A simple yet effective algorithm that chooses the best-known action with a probability of `1 - epsilon` and a random action with a probability of `epsilon`. It also supports various Q-value update methods:
- `sample_average`
- `constant_step_size`
- `recency_weighted`
- `sliding_window`

### 3. LinUCB (Linear Upper Confidence Bound)
An algorithm designed for contextual bandits, where the rewards depend on the features of the arms. It assumes a linear relationship between features and expected rewards.

### 4. Linear Thompson Sampling
Another contextual bandit algorithm that uses a Bayesian approach to estimate the reward distribution for each arm and samples from these distributions to make decisions.

## Environment (`Environment` Class)
The `Environment` class simulates the multi-armed bandit problem. Key features include:
- **`arm`**: Number of arms in the bandit problem.
- **`stationary`**: Boolean flag indicating whether the reward distribution of the arms changes over time (`True` for stationary, `False` for non-stationary).
- **`q_mean`, `q_std_dev`**: Parameters for updating Q-values in a non-stationary environment.
- **`f_mean`, `f_std_dev`, `dim`**: Parameters for generating features for contextual bandit algorithms.
- It provides methods to initialize arm features, Q-values, update Q-values (for non-stationary settings), get rewards, and run single or multiple experiments.

## How to Run

1.  **Dependencies**: Ensure you have `numpy` and `matplotlib` installed.
2.  **Configuration**: Adjust the `env settings` and `agent` parameters in the `M3YoYjqxwh8y` cell. These parameters control the number of arms, stationarity, Q-value update methods, and agent-specific constants.
3.  **Agent Initialization**: The various agent instances (`ucb`, `epsilon_greedy`, `lin_ucb`, `thompson_sampling`) are initialized with the configured parameters.
4.  **Run Simulation**: The `Environment` class's `run_multiple_experiments` method is called to simulate the performance of all agents over a specified number of runs and steps.
5.  **Plot Results**: The `plot_multiple_experiments` method generates two plots:
    - **Average Reward Comparison**: Shows the average cumulative reward for each agent over time.
    - **Optimal Action Comparison**: Displays the percentage of times each agent chose the optimal action at each step.

Simply run all the code cells in the notebook to execute the simulation and view the results.

## Example Output
The plots generated at the end of the simulation compare the performance of the different agents based on average reward and optimal action percentage.
<img width="463" height="490" alt="resim" src="https://github.com/user-attachments/assets/a95b37f2-2426-4cc0-8968-1fb39282d01b" />
<img width="1189" height="490" alt="resim" src="https://github.com/user-attachments/assets/fcf17e0a-7c9e-45fb-9610-dec6c803be72" />
<img width="1189" height="490" alt="resim" src="https://github.com/user-attachments/assets/db88e82f-7351-4c46-a0e5-8ce52df49e8a" />

