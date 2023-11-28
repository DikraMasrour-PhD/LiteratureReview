---
tags:
  - SideQuest
  - Technique
---
### Resources
[Mixture-of-Experts Course: by Geoffrey Hinton](https://www.youtube.com/watch?v=FxrTtRvYQWk|)
[Machine Learning Mastery article](https://machinelearningmastery.com/mixture-of-experts/)
![Hu-po stream: From Sparse to Soft Mixture of of Experts](https://www.youtube.com/watch?v=_epq9VsViJc)
### Mixture of experts: what is it?
MoE is an ensemble learning approach that involves dividing the main task (which is often complex) into sub-tasks that 'expert models' specialise in, a 'gating model' then decides which expert model's prediction to trust more based on the input values. Finally, all/some expert models' predictions are combined into one final prediction. 
### MoE concepts
The MoE approach involves 4 elements
- Divide tasks into sub-tasks
- Develop / Train a specialised expert for each substask
- Develop a gating model (manager/decision-maker) to decide which expert to use
- Pool predictions based on the gating model's decision
#### Sub-tasks

#### Expert models
![[Pasted image 20231128162913.png|400]]
#### Gating model
This model decides on-the-fly the weights to give each expert model's prediction based on the input values.
![[Pasted image 20231128162729.png]]
#### Pooling method(s)
To make a final prediction, the experts' predictions weighted by the gating model's decision are pooled or aggregated:
- Some methods suggest to choose the prediction with the highest confidence score according to the gating model
- Alternatively, a weighted sum of the predictions and the weights given by the gating model can be computed
#### Genealogy of Soft MoEs
#### Cons of MoE
> [!failure] Cons
> For MoEs to perform well, large data is required

