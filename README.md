# Colon Cancer Transcriptomic Analysis

This repository contains the RMarkdown code used to perform:

* Differential Expression Analysis (DEA)
* Functional Enrichment Analysis (FEA)
* Location Enrichment Analysis

using colon cancer samples and healthy colon tissue samples.

## Data

The analysis uses open-access data from the TCGA-COAD project available through the Genomic Data Commons (GDC) Data Portal.

Data download requires the GDC Data Transfer Tool (`gdc-client`).

## Requirements

### Software

* R / RStudio
* GDC Data Transfer Tool (`gdc-client`)

### R packages

* TCGAbiolinks
* edgeR
* geneplotter
* limma
* sva
* dplyr
* ggplot2
* tidyr
* rlist
* openxlsx
* SummarizedExperiment
* AnnotationDbi
* org.Hs.eg.db
* GOstats

## Workflow

The analysis should be performed in the following order:

1. `breast_DEA.Rmd`

   * Downloads and preprocesses TCGA-BRCA data
   * Performs differential expression analysis

2. `Breast_FEA.Rmd`

   * Performs functional enrichment analysis
   * Performs location enrichment analysis using the differential expression results

## Output

The workflow generates tables and visualizations describing differentially expressed genes and enriched biological functions associated with breast cancer samples.

## Notes

This repository was developed as a research analysis workflow and is not intended as a production-ready software package.
