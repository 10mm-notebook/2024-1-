# Report
## Introduction
This report details the methodologies and technologies employed to analyze and classify the Blood-Brain Barrier Penetration (BBBP) dataset. The project involved converting molecular data from SMILES strings to graph representations, extracting meaningful features, performing classification, and visualizing the results.

## Graph Construction and Technology
### Technology Used
- RDKit: Used for handling and converting SMILES strings to molecular graphs.
- NetworkX: Utilized for graph representation and manipulation.
- Pandas: For data manipulation and analysis.
- Scikit-learn: Used for classification and visualization (SVM, T-SNE, PCA).
- Matplotlib: For plotting the visualizations.

### Process
1. SMILES Conversion: SMILES strings were converted to molecular graphs using RDKit.
2. Graph Creation: Each molecule was represented as a graph where nodes correspond to atoms and edges to bonds using NetworkX.
3. Feature Extraction: Extracted features like clustering coefficient, Jaccard coefficient, and modularity for each graph to be used in classification.

## Classification Result
### Technology Used
- Support Vector Machine (SVM): Selected for its robustness and effectiveness in high-dimensional spaces.

### Process
1. Data Preprocessing: SMILES strings were sanitized and converted to molecular graphs.
2. Feature Extraction: Features such as clustering coefficient, Jaccard coefficient, and modularity were computed for each graph.
3. Model Training: An SVM classifier was trained on the extracted features.

### Result Explanation
The SVM classifier was chosen for the following reasons:

1. High-Dimensional Feature Space: SVM effectively handles high-dimensional data, which is common in molecular feature spaces.
2. Binary Classification: The BBBP dataset involves binary classification (penetrating vs. non-penetrating the blood-brain barrier), for which SVM is well-suited.
3. Complex Data Relationships: SVM can manage complex data relationships, ensuring robust classification performance.


## Feature Selection
The features selected were clustering coefficient, Jaccard index, and modularity. These were chosen based on their ability to capture the structural and relational properties of molecular graphs, critical for understanding their behavior in blood-brain barrier penetration:

### Clustering Coefficient:

- Connectivity Insight: Measures the degree to which nodes in a graph cluster together. This helps in understanding how connected the atoms within a molecule are, providing insight into the molecular structure.
- Functional Group Identification: Indicates the presence of functional groups within a molecule. High clustering coefficient values often correspond to tightly connected functional groups, which can be crucial in determining the molecule's ability to penetrate the blood-brain barrier.
- Local Density: Reflects the local density of the graph, which can influence the molecule's interaction with the biological environment. Molecules with higher local density might have more stable and specific interactions with the blood-brain barrier.
- Chemical Properties: High clustering can be associated with specific chemical properties like hydrophobicity and polarity, which are important for BBB penetration.

### Jaccard Index:

- Similarity Measure: Measures the similarity between the neighborhoods of two nodes. For molecular graphs, it helps in comparing the similarity of different regions within the molecule, which is important for understanding the molecule's overall behavior.
- Interaction Patterns: Can reveal patterns of interactions within the molecule, indicating how different parts of the molecule might interact with the blood-brain barrier.
- Substructural Similarity: Helps in identifying similar substructures within different molecules. This is useful for classifying molecules based on common functional groups that influence BBB penetration.
- Diversity and Uniqueness: A low Jaccard index may indicate diverse and unique structural elements within a molecule, while a high index shows repetitive and similar structures, both of which can have different implications for BBB penetration.


### Modularity:

- Community Structure: Quantifies the strength of division of a graph into modules (clusters or communities). High modularity indicates a well-defined community structure, suggesting distinct functional regions within the molecule.
- Functional Segregation: Molecules with high modularity have regions that function semi-independently. This can be crucial for understanding how different parts of the molecule contribute to its ability to penetrate the blood-brain barrier.
- Structural Organization: Reflects the overall structural organization of the molecule. Molecules with high modularity might have more organized and efficient structures for interacting with biological membranes.
- Biological Activity Correlation: High modularity might correlate with specific biological activities and properties relevant to BBB penetration, helping in predicting the molecule's behavior based on its structural organization.


## Visualization
### Technology Used

- T-SNE and PCA: For dimensionality reduction and visualization in 3D space.
- Matplotlib: For plotting the reduced dimensions.
### Process
1. **T-SNE Visualization**: Reduced the feature space to three dimensions using T-SNE to visualize data structure and cluster separations.
2. **PCA Visualization**: Employed PCA to compare and contrast clustering patterns observed with T-SNE.

### Visualization Analysis
The T-SNE 3D visualization demonstrates a distinct clustering pattern, indicating that the features extracted from the molecular graphs effectively separate the classes (0 and 1). The clear separation suggests that the chosen features (clustering coefficient, Jaccard index, and modularity) are meaningful and relevant for classifying molecules based on their ability to penetrate the blood-brain barrier. In contrast, the PCA 3D visualization shows a more compressed clustering, indicating that while PCA captures some variance, it is less effective in clearly separating the classes compared to T-SNE. This highlights the complex, non-linear relationships in the data that T-SNE can capture

## Conclusion
The project successfully converted SMILES strings to molecular graphs, extracted relevant features, and classified the data using an SVM classifier. The chosen features effectively captured the structural properties of the molecules, and the SVM provided robust classification performance. The visualizations supported the classification outcomes, showing clear separation of classes in reduced dimensions. The methods and technologies used were well-aligned with the dataset's characteristics, providing a comprehensive understanding of the relationship between molecular structures and blood-brain barrier penetration.
