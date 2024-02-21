<h1 align="center"> Human Transcriptome Construction, Novel Human lncRNA Annotation and Downstream Analyses </h1>

## Description:
This document provides a description of a pipeline to build a new human transcriptome, to annotate novel human lncRNAs and to perform further downstream analyses.

<p align="center">
<img loading="lazy" src="http://img.shields.io/static/v1?label=status&message=developing&color=blue"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=updated&message=february&color=GREEN"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=language&message=bash&color=red"/>
</p>

# Summary  
* [Introduction](#Introduction)
* [Algorithms](#Algorithms)
* [Developer](https://github.com/TluckDucky)
* [License](https://github.com/TluckDucky/bash/blob/main/LICENSE)

### Introduction
This pipeline comprises steps of:
1. RNA-Seq raw reads [download](https://github.com/TluckDucky/bash/blob/main/sraSamplesDownload) using the NCBI-SRA [fasterq-dump](https://github.com/ncbi/sra-tools/wiki/HowTo:-fasterq-dump) tool;
2. Raw reads [pre-processing and sequencing quality analyses](https://github.com/TluckDucky/bash/blob/main/sequencingQualityAnalyses) using [fastp](https://github.com/OpenGene/fastp) and [FastQC](https://github.com/s-andrews/FastQC) tools;
3. 


### Algorithms

![Badge algorithm](http://img.shields.io/static/v1?label=fasterq-dump&message=v3.0.2&color=brightgreen)
![Badge algorithm](http://img.shields.io/static/v1?label=FastQC&message=v0.11.9&color=brightgreen)
![Badge algorithm](http://img.shields.io/static/v1?label=fastp&message=v0.20.0&color=brightgreen)
![Badge algorithm](http://img.shields.io/static/v1?label=STAR&message=v2.3.7a&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=samtools&message=v1.10&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=geneBody_coverage.py&message=v3.0.1&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=nfer_experiment.py&message=v3.0.1&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=tin.py&message=v3.0.1&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=Scallop&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=bedToGenePred&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=genePredToGtf&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=bedtools&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=FEELnc&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=CPC2&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=CPAT&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=liftOver&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=Gffcompare&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=featureCounts&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=edgeR&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=WGCNA&message=v0.10.4&color=GREEN)
![Badge algorithm](http://img.shields.io/static/v1?label=clusterProfiler&message=v0.10.4&color=GREEN)










