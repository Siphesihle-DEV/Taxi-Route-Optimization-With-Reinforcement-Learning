# Taxi-Route-Optimization-With-Reinforcement-Learning

An implementation of a **Q-Learning Reinforcement Learning agent** that learns to solve the **Taxi-v3** environment from Gymnasium. The agent learns an optimal policy for picking up passengers and dropping them off at their destinations while minimizing unnecessary movements and maximizing rewards.

A trained policy is then used to generate a GIF demonstrating the taxi's learned behavior.

---

## Project Overview

Urban transportation requires efficient route planning to reduce travel time, improve passenger satisfaction, and minimize unnecessary costs.

This project simulates that challenge using the **Taxi-v3** environment, where an autonomous taxi learns through **reinforcement learning** instead of being explicitly programmed with routes.

The agent improves over thousands of training episodes using the **Q-Learning** algorithm with an **epsilon-greedy exploration strategy**.

---

## Features

- Q-Learning implementation from scratch
- Epsilon-greedy action selection
- Q-table learning
- Reward optimization
- Policy extraction after training
- GIF visualization of the trained agent
- Reproducible results using random seeds

---

## Technologies Used

- Python
- NumPy
- Gymnasium
- ImageIO
- IPython Display

---

## Project Structure

```
.
├── city-1265055_1280.jpg
├── Taxi_Route_Optimization.ipynb
├── taxi_agent_behavior.gif
└── Taxi_snap.png
```

---

## Environment

The project uses the **Taxi-v3** environment provided by Gymnasium.

### Environment Details

- Grid Size: **5 × 5**
- Observation Space: **500 discrete states**
- Action Space: **6 actions**

### Available Actions

| Action | Description |
|---------|-------------|
| 0 | Move South |
| 1 | Move North |
| 2 | Move East |
| 3 | Move West |
| 4 | Pick Up Passenger |
| 5 | Drop Off Passenger |

---

## Reward System

| Event | Reward |
|--------|--------|
| Each time step | -1 |
| Successful passenger drop-off | +20 |
| Illegal pickup/drop-off | -10 |

The objective is to maximize cumulative reward by learning the shortest valid routes.

---

## Reinforcement Learning Algorithm

The agent uses the **Q-Learning** algorithm.

### Q-Learning Update Rule

```
Q(s, a) = (1 − α)Q(s, a) + α(R + γ max Q(s', a'))
```

Where:

- **α (alpha)** = Learning rate
- **γ (gamma)** = Discount factor
- **ε (epsilon)** = Exploration rate

---

## Hyperparameters

| Parameter | Value |
|-----------|-------|
| Learning Rate (α) | 0.1 |
| Discount Factor (γ) | 0.95 |
| Initial Epsilon | 0.20 |
| Epsilon Decay | 0.995 |
| Minimum Epsilon | 0.01 |
| Episodes | 2000 |
| Max Actions per Episode | 100 |

---

## Installation

Clone the repository

```bash
git clone https://github.com/Siphesihle-DEV/Taxi-Route-Optimization-With-Reinforcement-Learning.git
```

Navigate into the project

```bash
cd Taxi_Route_Optimization
```

## Running the Project

This project is implemented as a **Jupyter Notebook**.

1. Navigate to the project folder:

```bash
cd Taxi_Route_Optimization
```

2. Launch Jupyter Notebook:

```bash
jupyter notebook
```

After training, the project generates:

```
taxi_agent_behavior.gif
```

which visualizes the learned policy.

---

## Learning Process

During training the agent:

1. Initializes an empty Q-table.
2. Chooses actions using an epsilon-greedy strategy.
3. Receives rewards from the environment.
4. Updates Q-values.
5. Gradually reduces exploration.
6. Extracts the optimal policy from the learned Q-table.

---

## Results

After approximately **2,000 training episodes**, the agent learns a policy that efficiently:

- Navigates the grid
- Picks up passengers
- Delivers them successfully
- Avoids illegal actions
- Maximizes cumulative reward

The learned behavior is saved as an animated GIF for visualization.

---

## Learning Outcomes

This project demonstrates practical understanding of:

- Reinforcement Learning
- Q-Learning
- Markov Decision Processes (MDPs)
- Exploration vs Exploitation
- Policy Learning
- Reward Optimization
- Sequential Decision Making

---

## Future Improvements

Potential enhancements include:

- Deep Q-Networks (DQN)
- Double DQN
- Prioritized Experience Replay
- Reward shaping
- Hyperparameter tuning
- Performance evaluation metrics
- Interactive visualization dashboard

---

## References

- Gymnasium Taxi-v3 Environment
- Sutton & Barto, *Reinforcement Learning: An Introduction*
- NumPy Documentation

---

## License

This project is intended for educational and learning purposes.
