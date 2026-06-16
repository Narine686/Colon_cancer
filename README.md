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

As the number of tumoral samples is much higher than the number of healthy samples, two types of analysis have been carried out:

All tumoral samples against all healthy samples, for which the workflow to follow would be:

1. `colon_DEA.Rmd`

   * Downloads and preprocesses TCGA-COAD data
   * Performs differential expression analysis

2. `Colon_FEA.Rmd`

   * Performs functional enrichment analysis using the differential expression results
   * Performs location enrichment analysis using the differential expression results

And making random groups that have the same number of tumoral samples as healthy samples, for later carrying out the DEA with that group. Multiple groups are created randomly, and a DEA is performed per group. The workflow to follow would be:


1. `colon_DEA_groups.Rmd`

   * Downloads and preprocesses TCGA-COAD data
   * Generates 1000 random groups of 41 tumour samples and 41 healthy samples
   * Performs differential expression analyses
   * Corrects for multiple testing

2. `Colon_FEA_group.Rmd`

   * Performs functional enrichment analysis using the differential expression results
   * Performs location enrichment analysis using the differential expression results

## Output

The workflow generates tables and visualizations describing differentially expressed genes and enriched biological functions associated with colon cancer samples.

## License

This project is licensed under the MIT License.
