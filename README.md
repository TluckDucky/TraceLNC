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
* [Developer](https://github.com/TluckDucky)
* [Licença](#licença)

### Introduction
This pipeline comprises steps of:
1. RNA-Seq raw reads download using the NCBI-SRA [fasterq-dump](https://github.com/ncbi/sra-tools/wiki/HowTo:-fasterq-dump) tool;
2. Raw reads pre-processing and sequencing quality analyses using [Fastp](https://github.com/OpenGene/fastp) and [FastQC](https://github.com/s-andrews/FastQC) tools;
3. 
