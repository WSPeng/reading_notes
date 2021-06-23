# Online 3D Bin Packing with Constrained Deep Reinforcement Learning

The agent first *predicts* a feasibility mask for the placement actions as an auxiliary task and then uses the mask to modulate the action probabilities output by the actor during training. --- prediction and projection. (so called)

state = Height map + dimension of items incoming. 

feasibility mask: add priori of stability. --> constrained Markov decision processes

Kronecker- Factored Trust Region (ACKTR)

Result : on policy better than sac?

Network: CNN first encode the raw state input. lwh三个数据被拉宽成三个矩阵了。

mask to small quantity like 1e-3 works better. 

##### K bins:  用遍历树

condition the placement of the current item on that of the next k-1 ones. 但是要满足constraint. better: MCTS

-





另一篇垃圾paper：

## A Generalized Reinforcement Learning Algorithm for Online 3D Bin-Packing

The key obstacle to effective learning was the fact that the optimality of a chosen location and orientation varies sharply (almost discontinuously) with small changes in the inputs.

1. selection of feasible location/orientation combinations using basic rules, and 

2. a value-based RL algorithm for choosing one of the suggested options

很垃圾的先验+DQN

