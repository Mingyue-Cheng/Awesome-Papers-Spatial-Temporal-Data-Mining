# Awesome-Papers-Spatial-Temporal-Data-Mining

## 基础前置工作

### 基于图卷积神经网络（GNN）的空间关系建模
最代表方法之一——GCN：Semi-Supervised Classification with Graph Convolutional Networks
- 基于聚合方法的变体
	•	GraphSAGE (Graph Sample and Aggregation)
	•	引入了不同的聚合函数（如均值、LSTM、最大值等）。
	•	支持归纳学习，可以在测试时处理新节点。
	•	GAT (Graph Attention Networks)
	•	使用注意力机制动态调整邻居节点对目标节点的贡献。
	•	能够处理图中不同边的重要性（异构图）。
	•	GIN (Graph Isomorphism Network)
	•	理论上具有最强的区分性（与 Weisfeiler-Lehman 图同构测试同等能力）。
	•	通过聚合邻居节点特征后加上自身特征，强调节点的唯一性。
- 面向异构图的变体
	•	HAN (Heterogeneous Graph Attention Network)
	•	针对异构图设计的多头注意力机制，能处理多种关系和类型的节点。
	•	RGCN (Relational GCN)
	•	引入边类型的特征表征，适合在知识图谱中建模多种关系。
- 面向动态图的变体
 	•	Dynamic GCN
	•	通过捕捉时间变化中的图结构调整 GCN 的权重。
	•	EvolveGCN
	•	在动态图中使用递归神经网络（RNN）来更新 GCN 权重。
- 基于网络深度的变体
	•	JK-Net (Jumping Knowledge Network)
	•	动态选择不同层的节点表征（或融合所有层的特征），解决层数选择问题。
	•	Graph U-Nets
	•	借鉴 U-Net 结构，通过下采样和上采样机制提取多尺度图结构信息。
	•	DropEdge
	•	在训练过程中随机去掉部分边，减轻图的过平滑和过拟合问题。
	•	APPNP (Approximate Personalized Propagation of Neural Predictions)
	•	结合 PageRank 算法和 GCN，改进信息传播的范围和质量。


### 基于深度神经网络的序列关系建模
