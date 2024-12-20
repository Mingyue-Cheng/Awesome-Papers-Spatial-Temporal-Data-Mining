[中文](./README_CN.md)    [English](./README.md)

# **Awesome Papers: Spatial-Temporal Data Mining**

A curated list of key papers, methods, and frameworks in **spatial-temporal data mining**, focusing on spatial relationship modeling, temporal dependency modeling, and joint spatiotemporal modeling. This repository serves as a comprehensive resource for researchers and practitioners in the field.

---

## **Table of Contents**

1. [Getting Started](#getting-started)  
   1.1 [Spatial Relationship Modeling with Graph Neural Networks (GNN)](#spatial-relationship-modeling-with-graph-neural-networks-gnn)  
   1.2 [Temporal Dependency Modeling with Deep Learning](#temporal-dependency-modeling-with-deep-learning)  
2. [Representative Works in Spatiotemporal Modeling](#representative-works-in-spatiotemporal-modeling)  
   2.1 [Temporal-First Methods](#temporal-first-methods)  
   2.2 [Spatial-First Methods](#spatial-first-methods)  
   2.3 [Joint Spatiotemporal Methods](#joint-spatiotemporal-methods)  
3. [Applications](#applications)  
   3.1 [Traffic](#traffic)  
   3.2 [Energy](#energy)  
   3.3 [Weather Forecasting](#weather-forecasting)  
   3.4 [AI4Science](#ai4science)  
4. [Conclusion](#conclusion)

---

## **Getting Started**

### **Spatial Relationship Modeling with Graph Neural Networks (GNN)**

Graph Neural Networks (GNN) are widely used for spatial modeling, effectively capturing dependencies between nodes and their neighbors. Below are representative methods and their variants:

#### **Aggregation-Based Variants**
- **GCN (Graph Convolutional Networks)**  
  *Paper: [Semi-Supervised Classification with Graph Convolutional Networks](https://arxiv.org/abs/1609.02907)*  
  The foundational GNN model that captures local graph structure via Laplacian convolution.

- **GraphSAGE (Graph Sample and Aggregation)**  
  *Paper: [Inductive Representation Learning on Large Graphs](https://arxiv.org/abs/1706.02216)*  
  Introduces different aggregation methods (mean, LSTM, max) to learn node representations. Supports inductive learning.

- **GAT (Graph Attention Networks)**  
  *Paper: [Graph Attention Networks](https://arxiv.org/abs/1710.10903)*  
  Uses attention mechanisms to dynamically assign weights to neighbors, particularly effective for heterogeneous graphs.

- **GIN (Graph Isomorphism Network)**  
  *Paper: [How Powerful Are Graph Neural Networks?](https://arxiv.org/abs/1810.00826)*  
  Aims to improve expressiveness and achieve strong isomorphism testing capabilities by emphasizing unique node features.

#### **Heterogeneous Graph Variants**
- **HAN (Heterogeneous Graph Attention Network)**  
  Designed to handle multi-type nodes and edges with multi-head attention mechanisms.

- **RGCN (Relational GCN)**  
  *Paper: [Modeling Relational Data with Graph Convolutional Networks](https://arxiv.org/abs/1703.06103)*  
  Models relational graphs by incorporating edge type-specific transformations, widely used in knowledge graphs.

#### **Dynamic Graph Variants**
- **Dynamic GCN**  
  Adapts graph structures dynamically to capture temporal changes in graphs.

- **EvolveGCN**  
  Combines RNNs with GNNs to model the evolution of nodes and edges in dynamic graphs.

#### **Depth-Based Variants**
- **JK-Net (Jumping Knowledge Network)**  
  *Paper: [Jumping Knowledge Networks](https://arxiv.org/abs/1806.03536)*  
  Dynamically selects features from different layers to avoid over-smoothing.

- **Graph U-Nets**  
  Mimics U-Net by applying graph down-sampling and up-sampling to extract multi-scale features.

- **DropEdge**  
  Randomly removes edges during training to improve generalization and robustness.

- **APPNP (Approximate Personalized Propagation of Neural Predictions)**  
  *Paper: [Predict then Propagate: Graph Neural Networks Meet Personalized PageRank](https://arxiv.org/abs/1810.05997)*  
  Combines PageRank with GNNs to improve information propagation.

---

### **Temporal Dependency Modeling with Deep Learning**

Temporal dependency modeling focuses on capturing dependencies in sequential data and is a core aspect of spatiotemporal modeling.

#### **RNN-Based Methods**
- **LSTM (Long Short-Term Memory)**  
  Captures long-term dependencies, widely used for sequential data modeling.

- **GRU (Gated Recurrent Units)**  
  Simplifies LSTM while maintaining high performance and computational efficiency.

#### **CNN-Based Methods**
- **TCN (Temporal Convolutional Network)**  
  *Paper: [An Empirical Evaluation of Generic Convolutional and Recurrent Networks for Sequence Modeling](https://arxiv.org/abs/1803.01271)*  
  Uses causal convolutions and dilations to process sequential data, enabling parallelism.

- **WaveNet**  
  *Paper: [WaveNet: A Generative Model for Raw Audio](https://arxiv.org/abs/1609.03499)*  
  Employs dilated convolutions and residual connections for long-sequence modeling.

#### **Attention-Based Methods**
- **Transformer**  
  *Paper: [Attention Is All You Need](https://arxiv.org/abs/1706.03762)*  
  Leverages global self-attention mechanisms to capture dependencies over long sequences.

- **Informer**  
  *Paper: [Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting](https://arxiv.org/abs/2012.07436)*  
  Optimizes Transformers for long time-series forecasting using sparse attention.

---

## **Representative Works in Spatiotemporal Modeling**

### **Temporal-First Methods**
Focus primarily on temporal dependencies while incorporating spatial modeling as a secondary factor:
- **STGCN (Spatio-Temporal Graph Convolutional Networks)**  
  Combines GCN and TCN to model spatiotemporal dependencies, widely used in traffic prediction.  

- **DCRNN (Diffusion Convolutional Recurrent Neural Network)**  
  Models spatial properties using diffusion convolution and temporal dependencies via RNN.

### **Spatial-First Methods**
Focus primarily on spatial dependencies with temporal modeling as a secondary factor:
- **GC-LSTM**  
  Incorporates LSTM into graph convolution layers to handle temporal dependencies.

- **Graph WaveNet**  
  Combines dilated convolutions for long-term temporal dependencies with GCN for spatial relations.

### **Joint Spatiotemporal Methods**
Simultaneously model spatial and temporal dependencies:
- **ASTGCN**  
  Combines attention mechanisms, GCN, and temporal convolution for unified spatiotemporal learning.

- **ST-MetaNet**  
  Uses meta-learning approaches to adaptively capture spatiotemporal dependencies.

---

## **Applications**

### **Traffic**
- **Tasks**: Traffic flow prediction, vehicle route planning.  
- **Methods**: STGCN, DCRNN.

### **Energy**
- **Tasks**: Power load forecasting, photovoltaic generation prediction.  
- **Methods**: Hybrid spatiotemporal models like Graph WaveNet.

### **Weather Forecasting**
- **Tasks**: Multi-region temperature and precipitation prediction.  
- **Methods**: Graph-based models combined with time-series forecasting.

### **AI4Science**
- **Tasks**: Atmospheric pollution analysis, earthquake prediction, and biomedical spatiotemporal data analysis.  
- **Methods**: Integrate domain knowledge with spatiotemporal modeling techniques.

---

## **Conclusion**

Spatiotemporal data mining is a critical area in artificial intelligence, encompassing techniques from graph neural networks to deep sequential models and joint learning paradigms. With broad applications in transportation, energy, climate science, and beyond, it remains an exciting and impactful research field.

---

### **Contributions**

Feel free to contribute! Open a pull request to add new papers, methods, or applications. 🎉
