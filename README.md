# Genotyping pipeline

Snakemake pipeline for genotyping

## Prepare environment

```
screen -S [project_name]
git clone https://github.com/alberdilab/genomics
mv genomics [project_name]
cd [project_name]

# Download wrappers to avoid connection issues
git clone https://github.com/snakemake/snakemake-wrappers.git  workflow/wrappers
```
*Replace [project_name] by an actual project name

## Prepare input

**Reads**: add sequencing reads to the resources/reads directory
**Reference genome**: add the reference genome to the resources/reference directory

## Launch pipeline

```
snakemake --workflow-profile profile/slurm
```
