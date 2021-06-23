# Solving a New 3D Bin Packing Problem with Deep Reinforcement Learning Method

#### Intro

3D BPP: a number of cuboid-shaped items with different sizes should be packed into bins orthogonally. The size and cost of bins are fixed and known and the objective is to minimize the number of bins used, i.e., minimize the total cost.

#### Method

 find out the least surface area bin that could pack all items

约束很多，13条

cplex not ok.

In this paper, DRL is used to fin better sequence to pack the items

pointer network -> combinatorial optimization problems

seq to seq

the attention mechanism is used to blend hidden units of the encoder to a context vector in sequence-to-sequence model, but Ptr-Net use attention as a pointer to select a member of the input sequence as the output.

input sequence of size data(length, width, height.) 

output: order

Learning, use surface area for evaluating the policy 

use heuristic algorithm result as baseline value. 

很一般...