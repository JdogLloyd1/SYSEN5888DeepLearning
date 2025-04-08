# Graph Neural Networks (GNN)

Graph Neural Networks (GNNs) are specialized deep learning models designed to learn from graph-structured data. This repository provides detailed tutorials and code examples on building, training, and evaluating GNN models using PyTorch and PyTorch Geometric (PyG). In addition to classical tasks like vertex classification and graph classification, we emphasize AI for Materials applications where GNNs are used for material property prediction and analysis.

---

## Tutorials Overview

GNNs excel at modeling complex relationships by representing data as graphs, where nodes represent entities and edges represent relationships. These models have found applications in a wide variety of fields, including:
- **Social Networks:** Understanding user behavior and predicting social connections.
- **Recommendation Systems:** Learning user-item interactions.
- **Traffic Networks:** Predicting congestion and optimizing routes.
- **Materials Science (AI for Materials):** Predicting material properties such as formation energy, band gap, dipole moments, and more.

**AI for Materials Topics Covered:**
- **Material Property Prediction:** Leveraging GNNs to forecast key properties (e.g., formation energy, band gap, dipole moments) critical for materials design.
- **Dataset Utilization:** Utilizing benchmarks like the QM9 dataset to train models on molecular graphs tailored to materials science.
- **Graph-Based Materials Analysis:** Applying graph machine learning techniques to interpret and analyze the underlying structure of materials.

This guide walks you through:
- Building GNN models from scratch (GCN, GraphSAGE, GIN, etc.).
- Efficiently loading and processing graph data using PyG.
- Training models for vertex classification, graph classification, and regression.
- Applying GNNs to the materials domain via property prediction on datasets such as QM9.



### 1. GNN Fundamentals with PyTorch Geometric
- **Framework:** PyTorch with PyTorch Geometric.
- **Key Concepts:**
  - **Graph Representation:** Learn how graphs are represented in PyG, using node features, edge indices, and edge features.
  - **Message Passing:** Understand how GNNs aggregate and update node representations through message passing.
  - **Layer Implementations:** See implementations of popular layers such as Graph Convolutional Networks (GCNConv), GraphSAGE, and Graph Isomorphism Networks (GINConv).
- **Labs:**
  - **Vertex Classification:** Apply GCN and your own implementation of GraphSAGE on the Cora dataset.
  - **Graph Classification:** Implement GIN with various aggregation functions (SUM/MEAN/MAX) for tasks like classifying IMDB graphs.

### 2. AI for Materials: Graph Neural Networks for Material Property Prediction
- **Application Focus:**
  - Use GNNs to predict material properties such as dipole moments, formation energy, or band gap.
  - Leverage the QM9 dataset, a common molecular graph benchmark in materials science.
- **Tutorial Highlights:**
  - **Dataset Loading:** How to load and preprocess the QM9 dataset using PyG’s built-in utilities.
  - **Model Building:** Design a Graph Convolutional Network (GCN) that computes node embeddings and aggregates them into graph-level representations with global mean pooling.
  - **Regression Task:** Train the GCN model to predict a target material property (e.g., dipole moment) using mean squared error (MSE) loss.
  - **Training and Evaluation:** A tailored training loop with evaluation on validation and test splits, demonstrating how GNNs can effectively regress material properties.

---

## Environment

To run these tutorials, you will need:
- **Libraries:** PyTorch (>=1.10), PyTorch Geometric, and supporting packages.
- **Hardware:** GPU support is strongly recommended to accelerate model training.
