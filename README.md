# Project 1: Gene Expression Prediction using Genetic Markers

## Background and Introduction

As explained in the class, the primary goal of this project is to build machine learning algorithms for predicting gene expression levels using genotypes of cis-SNPs. This is an active research area in genetics and genomics, the following papers provide necessary background on this topic.

+ [Gamazon et al. A gene-based association method for mapping traits using reference transcriptome data](https://www.nature.com/articles/ng.3367)
+ [Gusev et al. Integrative approaches for large-scale transcriptome-wide association studies](https://www.nature.com/articles/ng.3506)

## Data Downloading

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

You use/modify the following R code to test the downloaded training data by performing single SNP association analysis 

```
# load in training genotype data
d = read.table("ENSG00000211955.2.training_geno.dat",head=T)
dim(d)
# load in gene expression data
y = as.matrix(read.table("ENSG00000211955.2.training_pheno.dat"))
# get all p-values by single SNP association testing
pval = apply(d,2,function(x) summary(lm(y~x))$coef[2,4])
summary(pval)
```
## Specific Aims

You can choose one of the following two tasks to work on. 

### 1. Predicting gene expression-levels of the testing samples

This is a prediction problem. You may choose and implement any algorithm to predict the gene expression levels of the testing samples. The accuracy of the prediction will be judged by the squared rank correlation (R^2) between the predicted values and the actual values (not accessible to you)

### 2. Identify cis-SNPs that associated with gene-expressions

This is a variable selection problem. You may use any algorithm of your choice to identify potentially multiple association signals. In this case, you may choose not using the testing genotype data. But some measurement/quantification/justification of the type I errors of your identified signals is required.









