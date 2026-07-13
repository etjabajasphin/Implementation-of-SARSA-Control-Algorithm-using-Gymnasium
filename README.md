# Implementation-of-SARSA-Control-Algorithm-using-Gymnasium

## Aim

To implement the **SARSA control algorithm** using the Gymnasium `FrozenLake-v1` environment and learn an action-value function that helps the agent select better actions for reaching the goal state while avoiding holes.

---

## Problem Statement

The objective of this experiment is to train an agent in the Gymnasium `FrozenLake-v1` environment using the SARSA algorithm.

The agent must learn:

1. How to interact with the FrozenLake environment.
2. How to select actions using an epsilon-greedy policy.
3. How to update the Q-table using the SARSA update rule.
4. How to derive the learned policy from the Q-table.
5. How to evaluate the performance of the learned policy.

---

## Software Requirements

```bash
pip install gymnasium numpy matplotlib
```

---

## Environment Description

This experiment uses the Gymnasium `FrozenLake-v1` environment.

FrozenLake is a grid-world environment where the agent moves across frozen tiles and tries to reach the goal without falling into holes.

For the default 4 x 4 FrozenLake map:

| Component | Description |
|---|---|
| Environment | `FrozenLake-v1` |
| Map size | 4 x 4 |
| Observation space | 16 discrete states |
| Action space | 4 discrete actions |
| Actions | 0 = Left, 1 = Down, 2 = Right, 3 = Up |
| Reward | +1 for reaching the goal, 0 otherwise |
| Terminal states | Goal and hole states |

---

## Theory

SARSA stands for:

$$
S_t, A_t, R_{t+1}, S_{t+1}, A_{t+1}
$$

It updates the Q-value using the action actually selected in the next state.

The SARSA update rule is:

$$
Q(S_t,A_t) \leftarrow Q(S_t,A_t) + \alpha
\left[
R_{t+1} + \gamma Q(S_{t+1},A_{t+1}) - Q(S_t,A_t)
\right]
$$

Where:

| Symbol | Meaning |
|---|---|
| $S_t$ | Current state |
| $A_t$ | Current action |
| $R_{t+1}$ | Reward received after taking action $A_t$ |
| $S_{t+1}$ | Next state |
| $A_{t+1}$ | Next action selected using the current policy |
| $\alpha$ | Learning rate |
| $\gamma$ | Discount factor |
| $Q(s,a)$ | Action-value function |

---

## Epsilon-Greedy Policy

SARSA uses an epsilon-greedy policy for action selection.

With probability $\epsilon$, the agent explores by selecting a random action.

With probability $1-\epsilon$, the agent exploits by selecting the action with the highest Q-value.

$$
a =
\begin{cases}
\text{random action}, & \text{with probability } \epsilon \\
\arg\max_a Q(s,a), & \text{with probability } 1-\epsilon
\end{cases}
$$

---


## Algorithm

1. Create the Gymnasium `FrozenLake-v1` environment.
2. Initialize the Q-table with zeros.
3. Set the learning rate $\alpha$, discount factor $\gamma$, and exploration rate $\epsilon$.
4. For each episode:
   - Reset the environment.
   - Select the first action using epsilon-greedy policy.
   - For each step:
     - Execute the selected action.
     - Observe the reward and next state.
     - Select the next action using epsilon-greedy policy.
     - Update the Q-value using the SARSA update rule.
     - Move to the next state and next action.
   - Reduce epsilon gradually.
5. After training, extract the learned policy using the maximum Q-value action for each state.
6. Display the Q-table, state-value function, learned policy, and learning curve.

---

## Python Program

```python

# -------------------------------------------------
# SARSA Training
# -------------------------------------------------
# Write your code here




```
---

## Output

```text
Final Q-table:





Estimated State-Value Function:





Learned Policy:




Average reward over last 1000 episodes: 


```

---

## Result
```text



```

---

## Inference
```text



```
---

