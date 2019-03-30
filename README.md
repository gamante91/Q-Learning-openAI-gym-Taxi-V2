The aim of this repo is to solve **openAI Taxi-v2** environment using **Q-learning**.

**Environment:**

There are 4 locations (labeled by different letters) and the agent's job is to pick up the passenger at one location and drop him off in another.

```
+---------+
|R: | : :G|   R, G, B, Y are locations on this map
| : : : : |   The pipe symbol (|) represent walls
| : : : : |   The colon symbol (:) represent open spaces
| | : | : |
|Y| : |B: |
+---------+ 
```

**State space and action space**:

The state space is finite and has 25x5x4 = 300 possible values:
- 25 is the number of possible taxi positions in a 5x5 grid
- 5 is the number of possible passenger positions (R, G, B, Y and inside the taxi)
- 4 is the number of possible target positions (where the passenger wants to go)

The action space is finite and has 6 possible values, as the agent can perform 6 different actions:
- move south
- move north
- move west
- move east
- pickup the passenger
- dropoff the passenger

**Reward signal**

The agent receives +20 points for a successful dropoff, and loses 1 point for every timestep it takes.
There is also a 10 point penalty for illegal pick-up and drop-off actions.
An optimal algorithm will then [...]

**Algorithm:**

The algorithm used to train the agent is the popular **Q-learning** (also known as SARSA-max), which makes used of a lookup table of size n_states x n_actions, called the Q-table.

Each Q-table entry Q[s][a] contains a so called Q-value, which represents the expected cumulated reward if the agent takes action a from state s.

These entries are learned by the agent while exploring the environment using the followig update formula:

<p align="center">
  <img src="docs/Q_table_update_rule.png">
</p>

<p align="center">
  <img width="116" height="264" src="docs/random_play.gif">
</p>
