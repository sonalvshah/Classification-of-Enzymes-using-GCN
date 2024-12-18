# classification-of-enzymes-using-GCN
Classification of ENZYMES using GCN

The ENZYMES dataset is used in this project to construct a graph classification model. Classifying graph-structured data is the problem at hand. Each graph represents a molecule, and the classifications match those of different enzymes. Graph Convolutional Networks (GCNs) with different layers are used to build models, and their performance is assessed. 

**Dataset**

Upload dataset using:
dataset = TUDataset(root='data/ENZYMES', name='ENZYMES', transform=NormalizeFeatures())

num_classes = dataset.num_classes

- Dataset Name: ENZYMES
- Total Samples: 600 graphs
- Nodes: Represent individual atoms in the enzyme's molecular chain.
- Edges: Represent atomic contacts within the enzyme.
- Node Features: Computed parameters for each atom (3 features per node).
- Classes: 6 enzyme categories.

**Data Split**

- Training: 70%
- Validation: 15%
- Testing: 15%

**Preprocessing Steps**

Normalization: Node features are normalized using NormalizeFeatures() from torch_geometric.transforms to standardize input values, improving model training.

**Models Implemented**
GCN with 1, 2, and 3 layers 

**Key Techniques and Parameters**

1. Loss Function:
Cross-Entropy Loss: Suitable for multi-class classification problems like graph classification.
2. Optimizer:
Adam Optimizer: Efficient and robust for graph-based models with large parameter spaces.
3. Learning Rates:
Multiple learning rates were tested: 0.1, 0.01, 0.001.

Best results achieved with learning rate 0.01 for the 3-layer GCN model.

**Summary of the Results**

With an accuracy of 53.88% and an F1 score of 0.5667, the 3-layer GCN model performed the best. The model's accuracy and F1 scores increased as the number of layers increased because it was better able to identify intricate patterns in the graph-structured data.
