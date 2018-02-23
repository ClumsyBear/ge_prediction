# Project 1: Gene Expression Prediction using Genetic Markers

## 1. Background and Introduction

As explained in the class, the primary goal of this project is to build machine learning algorithms for predicting gene expression levels using genotypes of cis-SNPs. This is an active research area in genetics and genomics, the following papers provide necessary background on this topic.

+ [Gamazon et al. A gene-based association method for mapping traits using reference transcriptome data](https://www.nature.com/articles/ng.3367)
+ [Gusev et al. Integrative approaches for large-scale transcriptome-wide association studies](https://www.nature.com/articles/ng.3506)

## 2. Data Download

Download a single zipped tar file ```project_data.tgz``` from [here](https://goo.gl/o6hmWY). Note that the file size is about 571Mb, make sure you have enough disk space to save and operate on the downloaded file.

To decompress the file, run the following command in a UNIX/Linux/Mac terminal

```
tar zxf project_data.tgz
```

The whole data set contains text formated data files for ***68*** genes. There are *3* separate files for each gene:
1. genotype data for training samples (named as ```ENSG###.training_geno.dat```): genotype data matrix (Nxp) for a given gene. For all genes, training data sample size N=570. The number of cis-SNPs (i.e., the predictors) varies by genes. The summary of distribution of p across 68 genes is given by 

```
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max.
   2178    5200    5736    6618    7056   17060
```
Note that genotype data file contains a header of SNP names.

2. phenotype (i.e. expression level) data for training samples (named as ```ENSG###.training_pheno.dat```): gene expression data matrix (Nx1) for a given gene. 

3. genotype data for testing samples (named as ```ENSG###.testing_geno.dat```): genoype data matrix (Mxp) for a given gene. For all genes, testing data sample size M=100. This genotype data file also contains a header of SNP names.




