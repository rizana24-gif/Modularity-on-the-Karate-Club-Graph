DSC212 – Graph Theory Assignment
## Name: Rizana Anzar
   Roll No: IMS24193
# Modularity-Based Community Detection on the Karate Club Graph

This project implements recursive spectral modularity partitioning to detect multiple communities in the classic Zachary’s Karate Club network. It demonstrates how mathematical concepts in network science (modularity, eigenvectors, community structure) can be translated into algorithms and visualized dynamically.
The notebook produced for this assignment executes end-to-end without manual edits and includes all required code, visualizations, and analysis.

## Modularity 
Modularity measures how well a division groups densely connected nodes compared to a random baseline.

$$ Q = \frac{1}{4m} \, s^T B s $$

Higher values indicate more meaningful communities.

## Spectral Modularity Algorithm
The method is based on the modularity matrix:

$$ B = A - \frac{k k^T}{2m} $$

Algorithm steps:
1. Compute the **largest eigenvalue** and **eigenvector** of the modularity matrix.
2. Split nodes by the **sign** of the eigenvector components.
3. Recursively apply the same procedure to each subgroup.
4. Stop when the largest eigenvalue is **non-positive**, meaning no split improves modularity.

##  Recursive Community Detection
- Begins with all 34 nodes.  
- Applies spectral bisection iteratively.  
- Visualizes the graph after each split with unique community colors.  
- Returns the final modularity-optimal set of communities.

## Node Metrics
After each split, NetworkX is used to compute:

- **Degree Centrality** – direct connectivity  
- **Betweenness Centrality** – role as a bridge  
- **Closeness Centrality** – average distance to all nodes  
- **Clustering Coefficient** – local neighborhood cohesiveness  

Plots show how these values change across iterations.

## Discussion Summary
The discussion highlights:
- Nodes that consistently remain central  
- Bridge nodes linking communities  
- Effects of recursive splitting on clustering and centrality  
- How closely detected communities match the real Karate Club split  

## References
- Newman, M. E. J. (2006). *Modularity and community structure in networks.*  
- Zachary, W. W. (1977). *An information flow model for conflict and fission in small groups.*
