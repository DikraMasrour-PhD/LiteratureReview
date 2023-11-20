---
tags:
  - DNN
  - Technique
---
More flexible than EE (early exiting), Layer Skipping allows for the adaptation of network depth on the fly by strategically skipping the calculation of intermediate layers without intermediate classifiers.
#### Layer skipping schemes
![[Pasted image 20231113123040.png]]
##### Halting score
A scalar accumulated to decide whether to skip the execution of the next layer. 
- [[Iterative Adaptive Mobile Neural Network for Efficient Image Classification|IamNN]] replaces the residual units in a ResNet with custom IamNN architectures that accumulates a halting score along with a state buffer.
##### Gating function
Plug-and-play option for dynamic depth architectures involving decision gates.
- [[SkipNet: Learning Dynamic Routing in Convolutional Networks|SkipNet]] (dive deeper into 3 gates types)
- [[Convolutional Networks with Adaptive Inference Graphs|ConvNet-AIG]] are high-level similar to ResNet plus a gating mechanism that estimates on the fly, and based on the input, the relevance of the next layer (look into how the forward & backward routes work)
- [[Dynamic Recursive Neural Networks|DRNNs]] explains the dynamic recursive mechanism (look deeper)
##### Policy network
Policy networks are built to directly produce skipping decisions on the entire backbone network.
- [[(2018) BlockDrop-Dynamic Inference Paths in Residual Networks|BlockDrop]] attaches a pre-trained ResNet to a policy neural network that outputs a decision on which blocks to keep and which to drop for a specific input image. The policy network is trained to optimise the reward which itself account for block usage and prediction accuracy.