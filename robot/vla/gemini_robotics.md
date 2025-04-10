# 都 propose 了什么
- benchmark: ERQA
- 两个模型：
 - gemini robotics ER (embodied reasoning) VLM
 - gemini robotics: low level control, VLA, 对 ER的 finetune 版本，直接输出 action
提到multiple capabilities critical for understanding the physical world：
- 3D perception
- detailed pointing
- robot state estimation
- affordance prediction via code
还有: 


什么是 ER的关键能力：
to ground objects and spatial concepts in the real world, and the ability to synthesize those signals for downstream robotics applications.
举例就是：
2d detection, 3d detection, 2d pointing, 3d affordance (multi-view)
trajectory prediction, grasp prediction, 3d bounding box detection

提到的其他 benchmark: 
- paco-LVIS
- pixmo-point
- where2place

chapter2 主要在描述 ER的能力
chapter3 

backbone 在 cloud，decoder 在本地
backbone 也是一个蒸馏版本，感觉是更小一点？
加起来是 250ms latency，多个 action的话可以做到 50Hz

关于数据：采了一年的数据，1000+ hours
有一个点：Pi0 re implement 是比 openpi 效果好的，主要是吃了他们的数据


chapter4 in the future
finetune model 去完成更难的任务，看看和直接部署有多大提升
- for each task, 2000 to 5000条数据
还有就是language encoder 很重要，但是如果只有 languange encoder 也不行，也要 in addition to the high-capacity model architecture, the representation, or the physical common sense, learned from diverse robot action datasets

4.1 enhanced reasoning and generalization 
re-label 了 data
需要 one step reasoning, semantic generalization, spatial understanding, 
但是问题：到底是怎么做的这个 re label 呢？


