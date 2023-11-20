---
Paper Title: Dynamic Neural Networks - A Survey
Reference: "Han, Y., Huang, G., Song, S., Yang, L., Wang, H., & Wang, Y. (2021). Dynamic Neural Networks: A Survey (arXiv:2102.04906). arXiv. https://doi.org/10.48550/arXiv.2102.04906"
tags:
  - Survey
  - Paper
  - DNN
---
![[Pasted image 20231107123303.png]]Survey Overview
#### DNNs categories in survey:
1. Sample wise dynamic models: data-dependent architectures
2. Spatial wise dynamic models: adaptive computation depending on *spatial locations of image data*
3. Temporal wise dynamic models: adaptive inference for sequential data (e.g. text, video data)
#### Pros of dynamic computation in DL:
1. **Computational efficiency**: on-demand computation at test time allocation by selectively activating model components conditioned by the input > avoiding canonical (easy to recognise) & less informative spatial/temporal locations of an input.
2. **Representation** power: data-dependent architecture/parameters > DNNs have enlarged parameter space > representation power. E.g. Application of feature-conditioned attention weights boosts model capacity.
3. **Adaptiveness**: dealing with computational budgets on-the-fly > achieve accuracy/efficiency trade-off > DNNs model adaptable to hardware/platform environments
4. Interpretability: possibility of observing which components are accountable for which inference + bridging the gap between deep models and brains.
### Survey
#### Overview
**Category** | **Subcategory** | **Content** | **Linked reference** 
---|---|---|---
Sample-wise dynamic NNs|Dynamic architectures|Dynamic depth|[[Early exiting]]<br>[[Layer skipping]]
Sample-wise dynamic NNs|Dynamic architectures|Dynamic width|[[Skipping Neurons (in FC layers)]]<br>[[Skipping branches in MoE]]<br>[[Skipping channels in CNN]]

#### Insights/Critique
- Dynamic architecture > dynamic width > skipping channels in CNNs could be relevant to HS and MS images.
#### ==(references to explore)== 
##### Perf. improvement techniques
- Lightweight models (Andrew G Howard, Menglong Zhu, Bo Chen, Dmitry Kalenichenko, Weijun Wang, Tobias Weyand, Marco Andreetto, and Hartwig Adam. Mobilenets: Efficient convolutional neural networks for mobile vision applications. arXiv preprint arXiv:1704.04861, 2017)
- NAS approaches (9. Barret Zoph and Quoc V Le. Neural architecture search with reinforcement learning. In ICLR, 2017. 10. Hanxiao Liu, Karen Simonyan, and Yiming Yang. DARTS: Differentiable Architecture Search. In ICLR, 2018.)
- Static models acceleration methods:
	- network pruning (Gao Huang, Shichen Liu, Laurens Van der Maaten, and Kilian Q Weinberger. Condensenet: An efficient densenet using learned group convolutions. In CVPR, 2018.)
	- weight quantisation (Itay Hubara, Matthieu Courbariaux, Daniel Soudry, Ran El-Yaniv, and Yoshua Bengio. Binarized neural networks. In NeurIPS, 2016.)
	- knowledge distillation (Geoffrey Hinton, Oriol Vinyals, and Jeff Dean. Distilling the knowledge in a neural network. In NeurIPS Workshop, 2014.)
	- low-rank approximation (Max Jaderberg, Andrea Vedaldi, and Andrew Zisserman. Speeding up convolutional neural networks with low rank expansions. In BMVC, 2014.)
##### DNN applications
- image classification (Gao Huang, Danlu Chen, Tianhong Li, Felix Wu, Laurens van der Maaten, and Kilian Weinberger. Multi-scale dense networks for resource efficient image classification. In ICLR, 2018 / Le Yang, Yizeng Han, Xi Chen, Shiji Song, Jifeng Dai, and Gao Huang. Resolution Adaptive Networks for Efficient Inference. In CVPR, 2020)
- object detection (Michael Figurnov, Maxwell D Collins, Yukun Zhu, Li Zhang, Jonathan Huang, Dmitry Vetrov, and Ruslan Salakhutdinov. Spatially adaptive computation time for residual networks. In CVPR, 2017)
- semantic segmentation (Xiaoxiao Li, Ziwei Liu, Ping Luo, Chen Change Loy, and Xiaoou Tang. Not all pixels are equal: Difficulty-aware semantic segmentation via deep layer cascade. In CVPR, 2017)

 