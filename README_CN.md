# **空间-时间数据挖掘经典论文汇总**

本项目整理了**空间-时间数据挖掘**领域中的经典论文、方法与框架，涵盖空间关系建模、时间依赖建模以及联合时空建模的核心技术与前沿进展，为研究人员和从业者提供全面的参考。

---

## **目录**

1. [基础前置工作](#基础前置工作)  
   1.1 [基于图卷积神经网络（GNN）的空间关系建模](#基于图卷积神经网络gnn的空间关系建模)  
   1.2 [基于深度神经网络的时间依赖建模](#基于深度神经网络的时间依赖建模)  
2. [时空建模相关代表性工作](#时空建模相关代表性工作)  
   2.1 [时序优先方法](#时序优先方法)  
   2.2 [空间优先方法](#空间优先方法)  
   2.3 [联合建模方法](#联合建模方法)  
3. [应用场景](#应用场景)  
   3.1 [交通](#交通)  
   3.2 [能源](#能源)  
   3.3 [天气预报](#天气预报)  
   3.4 [AI4Science](#ai4science)  
4. [总结](#总结)

---

## **基础前置工作**

时空数据建模涉及**空间关系**和**时间依赖**的综合建模，以下是基础的技术模块：

### **基于图卷积神经网络（GNN）的空间关系建模**

图神经网络（GNN）广泛用于空间关系建模，能够捕获图结构中节点与邻居之间的依赖关系。以下是代表性方法及其变体：

#### **1. 基于聚合方法的变体**
- **GCN (Graph Convolutional Networks)**  
  *论文: [Semi-Supervised Classification with Graph Convolutional Networks](https://arxiv.org/abs/1609.02907)*  
  基于拉普拉斯卷积实现局部图结构的空间关系建模，是 GNN 的经典模型。

- **GraphSAGE (Graph Sample and Aggregation)**  
  *论文: [Inductive Representation Learning on Large Graphs](https://arxiv.org/abs/1706.02216)*  
  引入采样和聚合方法（如均值、LSTM、最大值），支持**归纳学习**，可处理新节点。

- **GAT (Graph Attention Networks)**  
  *论文: [Graph Attention Networks](https://arxiv.org/abs/1710.10903)*  
  使用注意力机制动态调整邻居节点的权重，适合异构图和复杂网络建模。

- **GIN (Graph Isomorphism Network)**  
  *论文: [How Powerful Are Graph Neural Networks?](https://arxiv.org/abs/1810.00826)*  
  提升节点特征区分性，具有强大的图同构判别能力。

#### **2. 面向异构图的变体**
- **HAN (Heterogeneous Graph Attention Network)**  
  针对异构图设计多头注意力机制，处理多类型节点和边的关系。

- **RGCN (Relational GCN)**  
  *论文: [Modeling Relational Data with Graph Convolutional Networks](https://arxiv.org/abs/1703.06103)*  
  通过边类型的特征建模关系图，广泛应用于知识图谱。

#### **3. 面向动态图的变体**
- **Dynamic GCN**  
  动态调整图结构以捕捉随时间变化的依赖关系。

- **EvolveGCN**  
  将递归神经网络（RNN）与 GNN 结合，建模动态图中节点和边的演化。

#### **4. 基于网络深度的变体**
- **JK-Net (Jumping Knowledge Network)**  
  *论文: [Jumping Knowledge Networks](https://arxiv.org/abs/1806.03536)*  
  动态选择不同层次的节点特征，缓解过平滑问题。

- **Graph U-Nets**  
  模仿 U-Net，利用图的上下采样提取多尺度特征。

- **DropEdge**  
  随机去除部分边以提高模型的鲁棒性，缓解过拟合。

- **APPNP (Approximate Personalized Propagation of Neural Predictions)**  
  *论文: [Predict then Propagate: Graph Neural Networks Meet Personalized PageRank](https://arxiv.org/abs/1810.05997)*  
  结合 PageRank 和 GNN，提高信息传播范围和质量。

---

### **基于深度神经网络的时间依赖建模**

时间依赖建模关注于捕捉数据中的时序动态，以下是主流方法分类：

#### **1. 基于 RNN 的方法**
- **LSTM (Long Short-Term Memory)**  
  捕捉长期依赖关系，是处理时间序列的经典方法。

- **GRU (Gated Recurrent Units)**  
  简化 LSTM 的结构，计算更高效。

#### **2. 基于 CNN 的方法**
- **TCN (Temporal Convolutional Network)**  
  *论文: [An Empirical Evaluation of Generic Convolutional and Recurrent Networks for Sequence Modeling](https://arxiv.org/abs/1803.01271)*  
  使用扩展卷积和因果卷积并行处理序列数据。

- **WaveNet**  
  *论文: [WaveNet: A Generative Model for Raw Audio](https://arxiv.org/abs/1609.03499)*  
  使用扩展卷积和残差连接处理长序列。

#### **3. 基于 Attention 的方法**
- **Transformer**  
  *论文: [Attention Is All You Need](https://arxiv.org/abs/1706.03762)*  
  利用全局自注意力机制建模长序列依赖。

- **Informer**  
  *论文: [Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting](https://arxiv.org/abs/2012.07436)*  
  针对长时间序列优化稀疏注意力机制，提升预测效率。

---

## **时空建模相关代表性工作**

### **时序优先方法**
- **STGCN (Spatio-Temporal Graph Convolutional Networks)**  
  将 GCN 和 TCN 结合，联合建模时空依赖，广泛应用于交通预测。  

- **DCRNN (Diffusion Convolutional Recurrent Neural Network)**  
  通过扩散卷积捕捉空间特性，同时用 RNN 建模时间动态。

---

### **空间优先方法**
- **GC-LSTM**  
  在图卷积基础上嵌入 LSTM 单元处理时间依赖。

- **Graph WaveNet**  
  结合扩展卷积捕捉长时依赖，同时用 GCN 处理空间关系。

---

### **联合建模方法**
- **ASTGCN**  
  引入注意力机制结合 GCN 和时间卷积，联合学习时空特性。  

- **ST-MetaNet**  
  使用元学习框架，自适应建模复杂时空关系。

---

## **应用场景**

### **交通**
- **任务**：交通流量预测、路径规划。  
- **方法**：STGCN、DCRNN。

### **能源**
- **任务**：电力负荷预测、光伏发电预测。  
- **方法**：Graph WaveNet 等时空联合建模方法。

### **天气预报**
- **任务**：多区域温度和降水量预测。  
- **方法**：基于图和时间序列模型的联合方法。

### **AI4Science**
- **任务**：空气污染分析、地震预测、生物医学数据分析。  
- **方法**：结合领域知识与时空数据建模技术。

---

## **总结**

时空数据挖掘是人工智能的关键研究方向之一，涵盖了图神经网络、时间序列建模与联合学习等技术。它在交通、能源、气候科学等领域有着广泛的应用前景。本项目系统性总结了该领域的经典与最新研究，希望为科研人员提供全面的参考。

---

### **贡献指南**

欢迎贡献更多经典论文、模型和应用场景！🎉  
请通过 PR 或 issue 提交您的建议。
