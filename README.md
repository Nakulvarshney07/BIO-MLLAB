# Bioinformatics ML Lab (GEO microarray & yeast cell-cycle)

1. Summary of Analysis Workflow
Downloaded and preprocessed gene expression dataset (GSE2034).

Computed correlation-based distance matrix reflecting gene expression similarity.

Applied hierarchical clustering (Ward linkage) to group genes.

Explored clusters at multiple cut heights to identify meaningful groupings.

Assessed cluster robustness through bootstrap resampling and computed Adjusted Rand Index scores.

Performed pathway enrichment analysis (GO Biological Process and KEGG) to interpret biological functions of each cluster.

2. Clustering Results and Stability
Selected k=10
k=10 clusters based on dendrogram and cluster size balance.

Cluster sizes ranged from ~300 to 2200 genes.

Cluster stability measured via bootstrap resampling showed mean ARI around 0.13, indicating moderate stability.

Per-cluster stability scores varied, highlighting some clusters as more robust.

3. Biological Interpretation of Clusters
Enrichment analyses identified key biological pathways specific to clusters, such as signal transduction, cell cycle, metabolic processes.

Representative genes in clusters mapped to known functional annotations, supporting biological validity.

Results suggest clusters capture functionally coherent gene modules relevant to the studied condition.

4. Limitations
Potential batch effects and technical noise may affect clustering accuracy.

Choice of number of clusters k
k is semi-arbitrary and impacts biological conclusions.

Annotation databases used for enrichment (GO, KEGG) have inherent biases and coverage gaps.

Bootstrap sample fraction and number of iterations are parameters that influence stability results.

5. Future Work
Validate clusters with additional datasets or experimental assays.

Incorporate multi-omics data or apply alternative clustering algorithms (e.g., spectral, graph-based).

Explore dynamic clustering on time-series or condition-specific datasets.

Extend pathway analysis with other databases (Reactome, MsigDB).

6. Visualizations and Code
Included dendrograms, cluster size distribution tables, heatmaps of correlation matrices.

Stability histograms and cluster-wise stability barplots provide insight into reproducibility.

Enrichment barplots highlight most significant pathways per cluster.

All analyses performed in modular, reproducible Jupyter notebooks using Python packages: scipy, gseapy, seaborn, matplotlib.

## Project layout
```
bio-ml-lab/
  data/
    raw/          # untouched downloads
      GEO/        # GEO cache
    processed/    # cleaned, matrices, annotations
    external/     # pathway resources if needed
  notebooks/
    01_data_download.ipynb
  src/            # python modules, utils
  reports/        # figures, tables, notes
  environment.yml # conda environment
```
