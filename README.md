# TP_Snakemake


The main objective of this project is to use a workflow language and its interest compared to building a rudimentary workflow built in bash ; then adopt the FAIR principle for a reproducible science and finaly handling the ressources of the infrastructure to optimize your codes. The project will use the resources of the Biosphere Cloud of the French Institute of Bioinformatics. In this context, I have build a workflow in Snakemake allowing me to reproduce the analysis conducted in the ATACseq project from the quality control of the fastq.gz sequences to the identification of regions of accessibility to the DNA in the 2 biological conditions.

In the previous project, we re-analyzing, on a UCA Mesocenter computational cluster, the ATAC-seq data produced in the publication: "STATegra, a comprehensive multi-omics dataset of B-cell differentiation in mouse" David Gomez-Cabrero et al. 2019 https://doi.org/10.1038/s41597-019-0202-7. One of the goals of this study was to identify regions of the genome accessible to transcription as DNA opens and detaches from the nucleosome complex. For this, the analysis was conducted on a mouse B3 cell line. Please go to https://github.com/arzonon/Projet_HPC2022 for more details. 

## Dataset collection 

Datasets were collected from European Nucleotide Archive (ENA) https://www.ebi.ac.uk/ena on 2021-07-26 by Nadia Goué with enaDataGet tool https://www.ebi.ac.uk/about/news/service-news/new-tools-download-data-ena included in inhouse script ena_array_atac.slurm

In this project, we work on these following subsets : 

ss_50k_0h_R1_1.fastq.gz  
ss_50k_0h_R1_2.fastq.gz  
ss_50k_0h_R2_1.fastq.gz  
ss_50k_0h_R2_2.fastq.gz  
ss_50k_0h_R3_1.fastq.gz  
ss_50k_0h_R3_2.fastq.gz  
ss_50k_24h_R1_1.fastq.gz  
ss_50k_24h_R1_2.fastq.gz  
ss_50k_24h_R2_1.fastq.gz  
ss_50k_24h_R2_2.fastq.gz  
ss_50k_24h_R3_1.fastq.gz  
ss_50k_24h_R3_2.fastq.gz  

## Code usage
### 1) Essential files

The Snakemake worflow will need some special files to work. Use the following files (that you can find in this github project) to execute properly the workflow :  
scripts/envs/fastqc.yaml  
scripts/envs/trim.yaml  
scripts/envs/bowtie2.yaml  
scripts/envs/picard.yaml  
scripts/envs/deeptools.yaml  
scripts/envs/mac2.yaml  
scripts/envs/bedtools.yaml  
scripts/config/config.yaml  
scripts/Snakefile  

### 2) How to run the workflow 

To run the snakemake workflow use the command : snakemake --cores all --use-conda --snakefile scripts/Snakefile
