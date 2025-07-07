# Genotyping pipeline

Snakemake pipeline for genotyping. The pipeline trims and QC-filters Illumina reads, aligns them to a single reference genome, cleans and indexes the alignments, learns an error model from an initial bcftools call, recalibrates base qualities, then calls high-quality joint genotypes for all samples—scaling to large genomes by sharding per chromosome and wrapping every third-party tool in reproducible conda environments.

## 1. Prepare environment

Clone this repository and rename the main directory as wished. Replace [project_name] by an actual project name

```
screen -S [project_name]
git clone https://github.com/alberdilab/genotyping
mv genomics [project_name]
cd [project_name]
```

Download Snakemake wrappers to avoid connection issues.

```
git clone --depth 1 --branch v7.2.0 https://github.com/snakemake/snakemake-wrappers.git  workflow/wrappers/v7.2.0
```

## 2. Prepare input

Prepare sequencing reads and reference genome.

- **Reads**: add sequencing reads to the resources/reads directory.
- **Reference genome**: add the reference genome to the resources/reference directory.

## Launch pipeline

```
snakemake --workflow-profile profile/slurm
```
