The aim of this repo is to solve the openAI Taxi-v2 environment using Q-learning.

**Environment:**

There are 4 locations (labeled by different letters) and the agent's job is to pick up the passenger at one location and drop him off in another.
The agent can then perform 6 different actions at any point in time:
1-move south
2-move north
3-move west
4-move east
5-pickup the passenger
6-dropoff the passenger

The agent receives +20 points for a successful dropoff, and loses 1 point for every timestep it takes.
There is also a 10 point penalty for illegal pick-up and drop-off actions.

<p align="center">
  <img width="116" height="264" src="https://cdn-images-1.medium.com/max/1600/1*FJJ9bOOt1cUXkEH6Y0r63g.gif">
</p>

**Algorithm:**
