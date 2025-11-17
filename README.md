# dsc212-assignment-
# Karate Modularity Assignment

## **Author:** Shipra Meena 
## **Roll No.:** IMS24226

## Overview
This repository provides a complete Jupyter notebook implementing **recursive spectral modularity partitioning** on **Zachary’s Karate Club** graph.  
It automatically computes modularity-based community splits, records community labels at each accepted split, and tracks node-level metrics (degree, betweenness, closeness, clustering coefficient) across all iterations.

## Scientific Motivation
Community detection is a key topic in network science. **Modularity** measures how well edges cluster within groups compared to a random baseline.  
The **leading-eigenvector spectral method** finds bipartitions that improve modularity, and recursively applying these splits yields a clear hierarchical decomposition.  
Tracking centrality values during this process helps identify core, peripheral, and bridge nodes.

## Features Implemented in the Notebook
- Construction of the **modularity matrix** for any candidate node group.
- Calculation of the **principal eigenvector** and splitting nodes by its sign.
- Modularity gain calculation:  
  \[
  \Delta Q = \frac{1}{4m} \, s^T B s
  \]
- Recursive splitting only when ΔQ > 0 and both partitions are non-empty.
- Automatic recording of:
  - Community assignments per iteration  
  - Degree, betweenness, closeness, clustering coefficient
- Visual network plots after each accepted split.


How to Reproduce the Results


1 . Open a terminal in the project directory.


2 . Set up a Python environment and install required packages:


```python -m venv .venv```


```source .venv/bin/activate (macOS / Linux)```


```.venv\Scripts\activate (Windows)```


```pip install -r requirements.txt```




3 . Launch the notebook:


```jupyter lab DSC212_Karate_Modularity.ipynb```


```or```


```jupyter notebook DSC212_Karate_Modularity.ipynb```




4 . Run all cells in sequence. The notebook will compute the partitions, generate all plots, and export any CSV summaries automatically.


Notes on Interpretation


1 . The algorithm only accepts splits with positive modularity gain, yielding a greedy hierarchical decomposition.


2 . Nodes with consistently high centrality values across iterations typically represent structural hubs or cores.


3 . Nodes whose betweenness rises sharply before a split often act as bridges between emerging communities.


4 . The recursive spectral method works best for small/medium-sized networks and pedagogical demonstrations; larger graphs may require faster or more robust algorithms.


Parameters You May Tune


1 . Minimum community size before a split is attempted ```(stop_min_size).```


2 . Minimum ΔQ threshold to avoid trivial improvements.


3 . Random seed for graph layout to keep visualizations consistent.


Reproducibility


1 . Recommended Python version: 3.9 or newer.


2 . Dependencies listed in ```requirements.txt``` ensure consistent execution.


3 . For full reproducibility, also include the ```pip freeze``` output or an environment file when submitting.


Submission Instructions


1 . The notebook is designed to be grade-ready and self-contained.


2 . If additional deliverables are required (plots, CSVs, diagrams), simply run the notebook and include the generated files according to your instructor’s submission format.


Reference


1 . Newman, M. E. J. (2006). Modularity and community structure in networks. Proceedings of the National Academy of Sciences.


