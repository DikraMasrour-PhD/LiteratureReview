---
tags:
  - DNN
  - Technique
---
#### Motivation
Complexity of input data varies in most scenarios, and shallow networks are usually enough to correctly identify canonical inputs. Thus, it is ideal that these inputs be output early without executing deeper layers, therefore costing more computational power and time.
>**Early exiting allows to terminate the inference procedure at an intermediate layer**
#### Early exiting schemes
##### Cascading DNNs
Cascading multiple mutually independent models, and adaptively deciding to retrieve the prediction or feed it to a latter model. After each model, a decision function is trained to decide whether to exit early or not. Inference after each model is performed from scratch.
![[Pasted image 20231107144515.png|300]]
**References**
- [[Big/Little Deep Neural Network for Ultra Low Power Inference|Big-little NN]] proposes the cascading of a small low-cost NN with a bigger high consumption NN that can only be used if the little NN's prediction was deemed inaccurate by the success checker, regardless of the architecture of both NNs. 
- [[IDK Cascades-Fast Deep Learning by Learning not to Overthink|IDK Cascades]] introduces the *'I don't know'* classifier framework (need to look deeper into the IDK classifiers unit)
- [[Adaptive Neural Networks for Efficient Inference]] (not sure about what the contribution is)
##### Intermediate classifiers
In contrast to cascading DNNs, intermediate classifiers are part of ONE backbone network allowing for reuse of early propagated (learned) features in deeper layers. Adaptive early exiting in this case is typically achieved according to:
- Confidence-based criteria
	- [[(2016) BranchyNet-Fast Inference via Early Exiting from Deep Neural Networks|BranchyNet]] introduce the 'branch' notion that involves branching the main network into side branches that lead to early exits. The paper describes the branches with the classification task in mind but the concept can be extended to other tasks like image segmentation or object detection
	- [[Resource-Constrained Classification Using a Cascade of Neural Network Layers]]
- Learned functions
	- [[Adaptive Neural Networks for Efficient Inference]]
	- [[(2020) EPNet-Learning to Exit with Flexible Multi-Branch Network|EPNet]] propose a learnable exiting policy for the case of multi-branch neural networks (not sure about the 'label' and 'controller' part, does the label unit produce a label regardless of the decision)
	- [[Energy-efficient Amortized Inference with Cascaded Deep Classifiers]] 
![[Pasted image 20231107144546.png|350]]
##### Multi-scale architectures with early exits
- Multi-scale Dense Neural Networks ([[Multi-Scale Dense Networks for Resource Efficient Image Classification|MSDNets]]) as an approach to adaptive early exiting for the following reasons (added to the motivating reasons for DenseNets):
	- Lack of coarse-level features in early layers of regular CNNs > forcing early classifiers to generates task-specific features > loss of general information
	- To solve these issues, MSDNets adopt:
		- **multi-scale architecture**: allows for generation of coarse-level features in shallower layers which are essential for classification
		- **dense connectivity**: allows for reuse of already learned features
- Resolution Adaptive Networks ([[Resolution Adaptive Networks for Efficient Inference|RANets]]) exploit spatial redundancy by:
	- classifying canonical samples using early low-resolution features
	- deeper high-resolution features are conditionally used based on previous predictions
![[Pasted image 20231110110607.png|520]]
###### Training schemes for EE DNNs
- [[Improved Techniques for Training Adaptive Deep Networks]] enhance training efficacy of early exiting adaptive neural networks. The experiments are specifically conducted on MSDNet architecture. 
###### Exiting policies for EE DNNs
- [[(2017) Deciding How to Decide-Dynamic Routing in Artificial Neural Networks|Deciding how to Decide]] (understand difference between statistically routed and dynamically routed networks) propose 3 strategies for training dynamically-routed NNs:
	- Actor learning
	- Pragmatic critic learning
	- Optimistic critic learning 
- [[Anytime Recognition with Routing Convolutional Networks|Anytime Recognition]] (dig deeper)
#### Critique/Insights
- (TASE) IDK classifiers maybe introduce the 3rd choice of skipping a sample ?