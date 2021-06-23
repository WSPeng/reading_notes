# “Good Robot!”: Efficient Reinforcement Learning for Multi-Step Visual Tasks with Sim to Real Transfer

long-horizon tasks where time can be wasted exploring dead ends and task progress may be easily reversed

Multi step robotic tasks intertwine learning the immediate physical consequences of actions with the need to understand how these consequences affect progress towards the overall goal.

对于抓取实验，the knowledge that grasping at empty air will never snag an object is “common sense” for humans, but may take some time for a vanilla algorithm to discover.

learning a pixel-wise success likelihood map.

a simplifying assumption equating sensor observations and state.

#### Reward shaping

**base reward**: weight * indicator function indicate the action is failed or not 

**situation removal reward**: new indicator function indicates that the “task progress function” increases. * base reward

**progress reward**: proportional progress * SR reward

situation removal: design a reward function to account for actions which lead to failures at a later time step, better than discount factor. -> *block reward propagation through failed actions.* 

**SPOT trial reward**: 

关键在那个0

**关于实验细节**， 

Mask 是图像处理的结果，用来添加先验

Algorithm ablation

Saftey and domain generalization

Real world experiment



