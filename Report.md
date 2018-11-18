# Report

## Agent

Here we have implemented Deep Q Agent. That means that a neural network is replacing classical Q table. 

### Neural Network architecture

We have tested frew architectures. The one that has worked best was fully connected neural network with 3 layers. 
Its structure is the following. 
1. Fully connected layer with output of dimension 64 and then Relu activation.
2. Fully connected layer with output of dimension 32 and then Relu activation.
2. Output layer of dimension equal to number of actions.

###  Agent architecture

We use the following techiques in order to improve the performance of the agent:
1. Experience Reply
2. Fixed Q Target

### Epsilon-greedy action selection

Our epsilon is dacaying from 1 to 0.01. We have tested two ways of decayin

#### Epsilon decay

With slow epsilon decay `0.995` it took `620` episodes to get average score on last 100 episodes above 13. When we made faster decay `0.95` it has droped to `317`.

However, maximum average score (within 2000 episodes) with this configuration is about `15.8` and with slower decay `16.3`.

#### Trainig with fast decay

![Alt text](https://raw.githubusercontent.com/sbartek/unity_navigation_with_deep_q_network/master/navigation13.png?raw=true "Optional Title")

#### Trainig with slow decay

In this trainig we get average score above 16.

![Alt text](https://raw.githubusercontent.com/sbartek/unity_navigation_with_deep_q_network/master/navigation16.png?raw=true "Optional Title")


## Checkpoints

`checkpoint_fast_decay_13.pth`: fast decay with average 13
`checkpoint_fast_decay_13_2.pth`: slow decay with average 16

## Further improvement

We would like to try 
1. Double DQN 
2. Dueling DQN
3. Prioritized experience replay
4. Learinig from pixels
