[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

## Introduction

This project is the first one in Udacity's Deep Reinforcement Learning Nanodegree. The task was to train an agent to navigate and collect bananas in a large square world.

<p align="center">
  <img src="https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif" alt="Trained Agent" width="600"/>
</p>

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

- **`0`** - move forward
- **`1`** - move backward
- **`2`** - turn left
- **`3`** - turn right

The task is episodic. In order to solve the environment, the agent must get an average score of at least +13 over 100 consecutive episodes.

### Agent

To solve the enviroment the Agent uses a Deep Q-Network with the following techniques:

1. **Experience Replay**: Storing and sampling experiences from a replay buffer to break correlation and enable efficient learning.
2. **Fixed Q-Targets**: Using a separate target network to provide stable targets during learning.
3. **Double DQN**: Decoupling the selection of the action from the evaluation to reduce overestimation bias.
4. **Dueling DQN**: Separating the estimation of state value and advantage for better policy evaluation.

## Possible Improvements

Implementing these techniques could potentially improve performance:

1. **Prioritized Experience Replay**: Sampling more important transitions more frequently, which can improve learning efficiency.
2. **Learning from Multi-Step Bootstrap Targets**: Using n-step returns to provide more informative updates.
3. **Distributional DQN**: Learning a distribution over Q-values instead of just the expectation.
4. **Noisy DQN**: Incorporating noisy linear layers for exploration, which can lead to better performance in environments with high uncertainty.

## Get Started!

1. Create the environment using the `environment.yml` file:

    ```bash
    conda env create -f environment.yml
    conda activate mlagents
    ```

    or alternatively using the way superior micromamba:

    ```bash
    micromamba env create -f environment.yml
    micromamba activate mlagents
    ```

2. Start working with `Navigation.ipynb`.
