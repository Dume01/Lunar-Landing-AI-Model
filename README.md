# Deep Q-Learning for Lunar Landing

This code demonstrates how to train an AI agent using Deep Q-Learning to solve the Lunar Landing environment from the Gymnasium library (formerly OpenAI Gym).

## Part 0 - Installing Packages and Importing Libraries

The first part of the code installs the required packages, including Gymnasium, and imports the necessary libraries such as NumPy, PyTorch, and collections.

## Part 1 - Building the AI

In this part, the code defines the architecture of the Neural Network using PyTorch. The `Network` class creates a simple feed-forward neural network with two hidden layers of 64 units each, and an output layer with the number of units equal to the number of actions in the environment.

## Part 2 - Training the AI

### Setting up the Environment

The code initializes the Lunar Landing environment from Gymnasium and retrieves the state and action space sizes.

### Initializing Hyperparameters

Several hyperparameters are defined, including the learning rate, mini-batch size, discount factor, replay buffer size, and interpolation parameter.

### Implementing Experience Replay

The `ReplayMemory` class is defined to store and sample experiences (state, action, reward, next state, done) for training the agent.

### Implementing the DQN Class

The `Agent` class implements the Deep Q-Network (DQN) algorithm. It initializes the local and target Q-networks, the optimizer, and the replay memory. The `step` method stores experiences in the replay memory and periodically samples a mini-batch to update the Q-networks using the `learn` method. The `act` method selects an action based on an epsilon-greedy policy.

### Initializing the DQN Agent

An instance of the `Agent` class is created with the state and action sizes.

### Training the DQN Agent

The training loop runs for a specified number of episodes. In each episode, the agent interacts with the environment, selects actions, stores experiences, and updates the Q-networks. The epsilon value for the epsilon-greedy policy is decayed over time. The average score over the last 100 episodes is monitored, and training stops when the average score reaches a target value (200 in this case). The final weights of the local Q-network are saved to a file.

## Part 3 - Visualizing the Results

The last part of the code provides functionality to visualize the trained agent's performance in the environment by rendering and saving a video.
