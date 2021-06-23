# First return then explore

RL 的两个问题

**detachment**: algorithm loses track of interesting areas to explore from / forgetting how to reach previously visited states

算法虽然鼓励智能体去探索未知的状态空间，但是当前状态到被探索状态空间的边界之间隔着很多被探索过的状态，算法并不能激励智能体越过这些 IR 很小的状态走到边界上再去探索

**derailment**: exploratory mechanisms of the algorithm prevent it from returning to previously visited states, preventing exploration directly and/or forcing practitioners to make exploratory mechanisms so minimal that effective exploration does not occur 

但是现有的算法会在走到边界的半路上“边走边探索”，最后偏离的轨迹，无法到达边界，这就是 derailment 所描述的问题

三个要点

- 记录下之前访问过的状态；
- 优先考虑返回更有可能探索到新状态的状态，返回的过程中采用确定性环境，这样一定能够返回到特定的状态；非确定性欢迎用goal-conditioned policy
- 现在确定性的环境中探索出可能比较脆弱的高奖励轨迹，然后再利用该轨迹学习到鲁棒的策略。

#### The Go-Explore family of algorithms

1. Probabilistically select a state from the archive, guided by heuristics that prefer states associated with promising cells. 一些启发式的评价指标
2. Return to the selected state, such as by restoring simulator state or by running a goal-conditioned policy.
3. Explore from that state by taking random actions or sampling from a policy.做100步的随机行动采样，并且有95%的概率重复上一步的动作，然后看看能够到达什么状态
4. Map every state encountered during returning and exploring to a low-dimensional cell representation.
5. Add states that map to new cells to the archive and update other archive entries.当遇到以下两种情况之一的时候会更新存档。一种是遇到了之前没有遇到过的状态；另一种遇到了已经存在于存档中的状态，但是其走到该状态的路径更优。这里说的更优指的是获得了更多的奖励或者获得了相同的奖励但是轨迹长度更短。这样原本的状态对应的轨迹就会被更新成新的轨迹。

Previous RL algorithms do not separate returning from exploring, and instead mix
time in exploration throughout an episode, usually by adding random actions a fraction of the time or by sampling from policy a stochastic policy

![image-20210303120801686](C:\Users\weishupeng\AppData\Roaming\Typora\typora-user-images\image-20210303120801686.png)

拿到一条高奖励的轨迹之后，先把智能体放在离轨迹末端较近的位置，让智能体能够学习到如何从这个离目标很近状态走到目标，然后再逐步把智能体放在轨迹上离目标更远一些的地方。通过这种方式智能体就能逐步学习到如何从初始位置走到目标位置。

#### Learning to play Atari when returning without a policy

state to cell mapping, robustification phase - backward algorithm, 展示结果, domain knowledge -> constructing the cell representation. 

#### A hard exploration robotics environment

机械臂实验，感觉文中描述的ppo的困难和我们遇到的很像

count based intrinsic motivation algorithm failed, evidence suggests that this failure to grasp is due to the problem of derailment. 

The exploration phase significantly outperforms an intrinsic motivation control using the same cell representation.

robotics - trajectory diverse but finish the task

#### Policy-based Go-Explore

execute a policy conditioned on (i.e. told to go to) the state or cell to return to the simulation state instead of restore the simulator. 

三点优势

In policy-based Go-Explore, policy is trained to follow the best trajectory of cells that previously led to the selected state

但是policy based 没做robotics任务

## METHODS

State of the art on Atari

Domain knowledge representations

Exploration phase

Evaluation

Hyperparameters

Policy based Go explore



还没看完。