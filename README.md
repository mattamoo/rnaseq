# NR2C2 Knockdown in MCF7 and T47D Breast Cancer Cells

RNA-seq analysis of public data from [GEO: GSE299760](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE299760), investigating whether NR2C2 knockdown produces different transcriptional responses in MCF7 and T47D breast cancer cells.

The dataset includes three knockdown and three control replicates per cell line.

## Analysis

- Differential expression analysis using DESeq2, performed separately for each cell line.
- Comparison of differentially expressed genes and fold changes between cell lines.
- Interaction model to test for cell-line-specific knockdown effects.
- Gene set enrichment analysis (GO Biological Process) to compare affected pathways.

Figures, including PCA, volcano plots, fold-change comparisons, heatmaps, and enrichment plots, are available in `results/`.

## Data and citation

Data: [GSE299760](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE299760).

Plagens *et al.* (2025). [Original publication](https://aacrjournals.org/mcr/article-abstract/23/12/997/767273/Mapping-the-FOXA1-Interactome-in-ER-Breast-Cancer).
