
Deep Reinforcement Learning with Tetris (DQN)
=============


## Description

This project aims to create a game agent that learns Tetris through in-depth reinforcement learning.
Tetris is a typical Sparse Reward Environment. And it is one of the difficult problems in reinforcement learning.

We aim to create model-free AI through several techniques.


Demo Video : https://www.youtube.com/watch?v=rgL0GCjwG-U


## Features

### 1. Prioritized Experience Replay
![img_1](https://user-images.githubusercontent.com/26384442/54540397-496c2380-49db-11e9-85ce-c97613b8322f.JPG)
<br>
![img_2](https://user-images.githubusercontent.com/26384442/54540403-4c671400-49db-11e9-8eb9-fc8dffa609ba.JPG)

As in the above image, the deviation of the reward can be large even in the same starting state. 
So we applied PER to learn more state with large reward deviation.
In the PER, the priority value P is defined in proportion to the time difference error, 
and the memory samples are extracted with a probability proportional to this value.



![img_3](https://user-images.githubusercontent.com/26384442/54540409-4e30d780-49db-11e9-8efb-722e2761e8b1.JPG)

Difference between replay memory and PER

![img_4](https://user-images.githubusercontent.com/26384442/54540416-4ffa9b00-49db-11e9-93cc-7295b73ce818.JPG)

the priority value P is defined in proportion to the time difference error


### 2. Group action

![img_5](https://user-images.githubusercontent.com/26384442/54541557-81746600-49dd-11e9-8525-31a625bf0b51.JPG)

From the conclusion, the agent performs both the rotation and the drop in one step.
In Tetris, the probability that an agent gets a reward in a random action is extremely low.
For example, in only T-shaped Tetris games, random action alone gets rewards of less than 3% per episode.
So we made this adjustment in a way that does not hurt the game's goals.



## Requirements
tensorflow==1.12.0
pygame==1.9.3
Keras==2.1.3


## Result

![img_7](https://user-images.githubusercontent.com/26384442/54542770-c7322e00-49df-11e9-89a0-4f7ea447df04.JPG)

![img_6](https://user-images.githubusercontent.com/26384442/54542778-c9948800-49df-11e9-8cb8-c7fb99161fa4.JPG)

DQN with PER means the group action agent with PER
The results showed that when combined the methods used gave good performance.

### PS.

In DQN_feature, defined features enter to the states.
But DQN_CNN's state is a board of game, and extract the features with convolution network.
