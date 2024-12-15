# Q-Learning-in-a-Hybrid-Approach

# Q-Learning in Gridworld and MountainCar-v0

This repository implements Q-learning for two environments:
1. A custom Gridworld environment.
2. The `MountainCar-v0` environment from the `gym` library.

The project includes custom implementations of the Q-learning algorithm, training, and testing scripts, as well as reward visualizations and video recording for the `MountainCar-v0` environment.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Gridworld Environment](#gridworld-environment)
  - [Environment Details](#environment-details)
  - [Q-Learning in Gridworld](#q-learning-in-gridworld)
- [MountainCar-v0 Environment](#mountaincar-v0-environment)
  - [Q-Learning in MountainCar-v0](#q-learning-in-mountaincar-v0)
  - [Video Recording](#video-recording)
- [Results](#results)
- [License](#license)

## Installation

### Prerequisites
- Python 3.x
- Required libraries: 
  - `numpy`
  - `matplotlib`
  - `gym`
  - `gymnasium[box2d]` (if using newer versions of OpenAI Gym)
  - `moviepy` (for video processing)

### Clone the Repository
```bash
git clone https://github.com/yourusername/q-learning-gridworld-mountaincar.git
cd q-learning-gridworld-mountaincar
```

### Install Dependencies
```bash
pip install numpy matplotlib gym moviepy
```

## Usage

### Running the Gridworld Environment
1. Run the `gridworld_qlearning.py` file to train the agent in the custom Gridworld environment.
   ```bash
   python gridworld_qlearning.py
   ```

2. After training, the learned policy and the agent's path will be visualized in the console, and a plot of total rewards over episodes will be shown.

### Running the MountainCar-v0 Environment
1. Run the `mountaincar_qlearning.py` file to train the agent in the `MountainCar-v0` environment.
   ```bash
   python mountaincar_qlearning.py
   ```

2. After training, a video of the final test episode will be recorded in the `./video` directory, and a plot of total rewards over episodes will be displayed.

## Gridworld Environment

### Environment Details
- **Grid Size**: 5x5
- **Start State**: (0, 0)
- **Goal State**: (4, 4)
- **Obstacles**: Two obstacles at positions (2, 2) and (3, 3).
- **Rewards**:
  - `+100` for reaching the goal.
  - `-10` for hitting obstacles.
  - `-1` penalty for every step.

### Q-Learning in Gridworld
- The agent is trained using the Q-learning algorithm to navigate from the start state to the goal state, avoiding obstacles.
- The Q-learning parameters include:
  - Learning rate (`alpha`)
  - Discount factor (`gamma`)
  - Exploration rate (`epsilon`)
- The agent's policy is learned through exploration and exploitation of actions (up, down, left, right) within the grid.

## MountainCar-v0 Environment

The MountainCar environment is a continuous-state environment where the goal is to drive a car up a steep hill. The agent uses Q-learning to learn how to reach the goal by discretizing the continuous state space.

### Q-Learning in MountainCar-v0
- The agent learns using a discretized state space.
- Actions include accelerating left, right, or doing nothing.
- The Q-table is updated based on the agent's interaction with the environment to maximize cumulative reward.

### Video Recording
- The final test run is recorded using the `gym.wrappers.RecordVideo` feature and saved in the `./video` folder.
- The video shows the agent's performance after training.

## Results

### Gridworld
- The agent learns an optimal policy to navigate from the start to the goal while avoiding obstacles. Convergence is checked, and rewards per episode are plotted.

### MountainCar-v0
- The agent learns to drive the car up the mountain over several episodes.
- A video of the agent's performance in the final test is saved in the `./video` folder.

