# NR2C2 knockdown in MCF7 and T47D breast cancer cells: RNA-seq cell-line comparison

An analysis of public RNA-seq data (GEO: [GSE299760](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE299760)).
NR2C2 was knocked down by siRNA in two breast cancer cell lines, MCF7 and T47D (3 knockdown + 3 control replicates each).

**Main question:** does the transcriptional response to NR2C2 knockdown differ between the two cell lines, and do the same pathways respond in both?

## Workflow

1. Raw counts for each cell line were combined and low-count genes removed (≥10 counts in ≥3 samples).
2. Differential expression with DESeq2, run **separately in each line** (`~ condition`, Knockdown vs Control).
3. Cell-line comparison: overlap of significant genes (padj < 0.05, |log2FC| > 1) and agreement of fold changes.
4. Formal test for line-specific effects with an **interaction model** (`~ cell_line + condition + cell_line:condition`).
5. Gene set enrichment (GSEA, GO Biological Process) per line, genes ranked by the DESeq2 Wald statistic; redundant terms collapsed with `simplify()`.

Figures are in `results/` (PCA, volcano plots, log2FC comparison, heatmap, GSEA dotplots).

## Data and credits

Data: GEO accession [GSE299760](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE299760). Citation: [Plagens *et al*. (2025)](https://aacrjournals.org/mcr/article-abstract/23/12/997/767273/Mapping-the-FOXA1-Interactome-in-ER-Breast-Cancer).
