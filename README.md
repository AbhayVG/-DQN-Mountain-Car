# -DQN-Mountain-Car

Overview
This project demonstrates the application of Deep Q-Learning (DQN) to solve the "MountainCar-v0" environment from OpenAI's Gymnasium. In this classic reinforcement learning problem, an underpowered car must build up enough momentum to reach the top of a steep hill.

Objective
The main objective is to train an agent using a DQN to effectively navigate the "MountainCar-v0" environment. The agent learns to drive the car up the hill by using Q-Learning with a neural network to approximate the Q-values, which represent the expected future rewards for taking certain actions in given states.

Deep Q-Learning (DQN) Overview
Deep Q-Learning combines Q-Learning with deep neural networks to handle high-dimensional state spaces. The key components include:

Q-Learning: A model-free reinforcement learning algorithm that learns the value of actions taken in particular states.
Neural Network: Used to approximate the Q-value function, allowing the agent to handle complex environments with large state spaces.
Experience Replay: Stores past experiences and samples them randomly to break the correlation between consecutive learning samples.
Target Network: A separate network used to stabilize training by periodically copying the weights from the primary network.
Implementation
The implementation involves the following steps:

Environment Setup: The "MountainCar-v0" environment is created using Gymnasium, which provides a standard API for reinforcement learning environments.

Replay Buffer: A replay buffer is used to store experiences (state, action, reward, next_state, done) and sample minibatches for training. This helps in stabilizing learning by breaking the temporal correlations.

Neural Network Architecture:

Input Layer: Takes the state of the environment.
Hidden Layers: Two fully connected layers with 36 and 48 neurons respectively, using ReLU activation functions.
Output Layer: Outputs the Q-values for each possible action.
DQN Agent:

Initialization: The agent initializes with a primary network and a target network. The target network’s weights are periodically updated to match the primary network to stabilize training.
Action Selection: Actions are chosen using an epsilon-greedy policy, balancing exploration and exploitation.
Training: The agent trains by sampling minibatches from the replay buffer and updating the Q-values using the loss between predicted Q-values and target Q-values.
Training Loop: For each episode, the agent interacts with the environment, stores experiences, and updates the network.
Model Saving: After training, the model’s weights are saved to a file, allowing for future use or evaluation.

Testing and Evaluation: The trained model is tested to evaluate its performance. Metrics such as cumulative reward, success rate, and failure rate are collected to assess how well the agent performs.

Key Features
GPU Support: The implementation supports running on GPU if available, enhancing training performance.
Random Seed Initialization: To ensure reproducibility, random seeds are set for numpy, random, and PyTorch operations.
This project illustrates the practical application of DQN in a well-known reinforcement learning problem and demonstrates the process of training, evaluating, and saving a deep reinforcement learning model.
