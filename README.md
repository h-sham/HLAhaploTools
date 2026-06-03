# HLAhaploTools

<!-- badges: start -->
[![R-CMD-check](https://github.com/h-sham/HLAhaploTools/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/h-sham/HLAhaploTools/actions/workflows/R-CMD-check.yaml)
[![Codecov test coverage](https://codecov.io/gh/h-sham/HLAhaploTools/graph/badge.svg)](https://app.codecov.io/gh/h-sham/HLAhaploTools)
<!-- badges: end -->

HLAhaploTools is an R package for inference and analysis of extended human leukocyte antigen (HLA) haplotypes. It supports cleaning, standardization, family-based inference, frequency estimation, and visualization across classical and non-classical HLA loci.

## Key features

- Standardize and clean HLA genotype data from multiple input formats
- Infer haplotypes using an expectation-maximization (EM) algorithm
- Calculate allele and haplotype frequencies for samples or pedigrees
- Visualize allele frequency and diversity with ggplot2-based plots
- Support classical and non-classical HLA loci, including MICA, MICB, HFE, DMA, DMB, DOA, and DOB

## Supported loci

- Classical HLA loci: A, B, C, DRB1, DRB3, DRB4, DRB5, DQA1, DQB1, DPA1, DPB1
- Non-classical loci: E, F, G, H, J, K, L, MICA, MICB, HFE, DMA, DMB, DOA, DOB

## Installation

Install the stable release from Bioconductor:

```r
if (!requireNamespace("BiocManager", quietly = TRUE))
  install.packages("BiocManager")
BiocManager::install("HLAhaploTools")
```

Install the development version from GitHub:

```r
# Using pak
# install.packages("pak")
pak::pak("fmobegi/HLAhaploTools")

# Using devtools
# install.packages("devtools")
devtools::install_github("fmobegi/HLAhaploTools")

# Using remotes
# install.packages("remotes")
remotes::install_github("fmobegi/HLAhaploTools")
```

## Quick start

```r
library(HLAhaploTools)

# Standardize input column names
cleaned <- standardize_colnames(raw_hla_data)

# Extract and organize loci
loci <- extract_loci(cleaned)

# Estimate haplotype frequencies with EM
haplotype_results <- em_algorithm(cleaned)

# Calculate allele frequencies
freqs <- calculate_hla_frequency(cleaned)

# Plot allele frequencies
plot_hla_allele_frequency(freqs)

# Plot diversity for one gene
plot_hla_diversity(freqs, gene = "E")
```

## Input data format

Input should be a tabular file (CSV/TSV/XLSX/XLS) with one row per sample or family member and columns for HLA allele calls.

### Recommended columns

- `FAMILY_ID` or another sample identifier
- `Family_Member` for pedigree data (`F`, `M`, `C1`, `C2`, ...)
- Allele calls such as `A_1`, `A_2`, `B_1`, `B_2`, `DRB1_1`, `DRB1_2`, etc.

Allele values may appear as `A*01:01`, `*01:01`, or `01:01`.

### Accepted column naming conventions

HLAhaploTools recognizes and standardizes common column formats:

- `GENE_1`, `GENE_2`
- `GENE.1`, `GENE.2`
- `GENE1`, `GENE2`
- `GENE-1`, `GENE-2`
- `GENE_ALLELE1`, `GENE_ALLELE2`

Gene names are case-insensitive.

## Supported HLA genes

- Classical: A, B, C, DRB1, DRB3, DRB4, DRB5, DQA1, DQB1, DPA1, DPB1
- Non-classical: E, F, G, H, J, K, L, MICA, MICB, HFE, DMA, DMB, DOA, DOB

## Documentation and support

- Repository: https://github.com/fmobegi/HLAhaploTools
- Issues: https://github.com/fmobegi/HLAhaploTools/issues

For full examples and detailed usage, see the package vignettes and help pages after installation.
