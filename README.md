# Essential Gene Prediction from Protein-Protein Interaction Networks

## Overview
Essential genes are critical for organism survival and are 
key targets in drug discovery. Experimental identification 
is expensive and time-consuming — this project predicts 
gene essentiality computationally using network-based 
machine learning.

## Organism Studied
*Actinomyces coleocanis* — a bacterium with a well-annotated
protein interaction network, suitable for computational 
essentiality prediction.

## Dataset
- **PPI Network:** STRING Database v11.5
  (525245.protein.links.v11.5.txt)
- **Essential Gene Labels:** NetGenes Database
  (Actinomyces coleocanis Essential Genes)

## Approach

### 1. Network Construction
Built a weighted protein-protein interaction graph 
using NetworkX from STRING database edges.

### 2. Network Analysis
- Computed graph properties: nodes, edges, 
  average degree, density
- Visualised degree distribution
- Extracted largest connected component

### 3. Feature Engineering (Network Centralities)
Extracted 11 network topology features per protein:
- Closeness centrality
- Betweenness centrality
- Degree centrality
- Eigenvector centrality
- Subgraph centrality
- Load centrality
- Harmonic centrality
- Local reaching centrality
- PageRank
- Clustering coefficient
- Average neighbour degree

### 4. Data Preparation
- Scaled features using StandardScaler
- Removed highly correlated features (r > 0.9)
  using annotated heatmap analysis
- Final features: betweenness, harmonic, 
  eigenvector, clustering, average neighbour degree

### 5. Classification
- Model: Logistic Regression (scikit-learn)
- Train/Test Split: 75/25
- Target: Binary — Essential (1) / Non-Essential (0)

## Results
**F1 Score: 0.97**

## Tools & Libraries
Python · NetworkX · scikit-learn · pandas · 
numpy · seaborn · matplotlib

## Why This Matters
Computational prediction of essential genes reduces 
wet lab costs and accelerates drug target identification
— directly applicable to pharma R&D and 
antimicrobial drug discovery pipelines.
