# Enzymatic Targeted Methylation Sequencing Bioinformatics Workflow: Best Practices
This repository contains scripts and environment used for DNA methylation analysis. The pipeline covers trimming, quality control, alignment, deduplication, and methylation calling for bisulfite/enzymatic sequencing data. 

This best practices was compiled aiming to develop a more user-friendly workflow, enhancing clarity, modularity, and reproducibility in the analysis of Twist-based Panels for DNA methylation data. Our approach refines and extends the existing TNMDW by integrating additional QC steps with differential and statistical analyses that could be conducted. The proposed workflow is customizable and reproducible, ensuring compatibility with a range of experimental contexts.

The original TNMDW protocol can be found at: https://www.twistbioscience.com/resources/protocol/twist-targeted-methylation-sequencing-protocol

The pipeline was designed for high-throughput methylation analysis and is fully compatible with the human genome reference GRCh38. It integrates standard bioinformatics tools and provides reproducible results while maintaining a clear structure for easy use.

## Pipeline Overview

The pipeline processes bisulfite/enzymatic sequencing data to generate methylation calls at CpG sites. The main steps are:

- **Trimming and Quality Control:** Adapter removal and read quality assessment using Trim Galore and FastQC, summarized with MultiQC.  
- **Read Alignment:** Mapping reads to the reference genome using BWA and Bwa-meth followed by sorting with Samtools.  
- **Duplicate Marking:** Identification and removal of PCR duplicates using Java and Picard.  
- **Methylation Calling:** Extraction of methylation metrics using MethylDackel for downstream analysis.

## Pipeline Structure
The repository is organized as follows:

```bash
├── README.md
├── meth_analysis_bash.yml        # Conda environment
├── pipeline_part1_bash           # Bash script for steps of preprocessing and methylation calling
├── pipeline_part2_R              # R script for downstream methylation analysis          

```

## Installation
The pipeline uses a pre-configured Conda environment to simplify setup. To create the environment:

```bash
# Clone the repository
git clone https://github.com/PGT-Lab/TNMDW-best-practices
cd TNMDW-best-practices

# Create Conda environment
conda env create -f envs/meth_analysis_bash.yml

# Activate environment
conda activate meth_analysis_bash
```
