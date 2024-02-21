<h1 align="center"> Human Transcriptome Construction, Novel Human lncRNA Annotation and Downstream Analyses </h1>

## Description:
This document provides a description of a pipeline to build a new human transcriptome, to annotate novel human lncRNAs and to perform further downstream analyses.

<p align="center">
<img loading="lazy" src="http://img.shields.io/static/v1?label=status&message=developing&color=blue"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=updated&message=february2024&color=GREEN"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=language&message=bash&color=red"/>
</p>

# Summary  
* [Introduction](#Introduction)
* [Developer](https://github.com/TluckDucky)
* [License](https://github.com/TluckDucky/bash/blob/main/LICENSE)

### Introduction
This pipeline comprises the following steps and the respective algorithms:
1. RNA-Seq raw reads [download](https://github.com/TluckDucky/bash/blob/main/sraSamplesDownload) using the NCBI-SRA [fasterq-dump](https://github.com/ncbi/sra-tools/wiki/HowTo:-fasterq-dump) tool;
[![Badge algorithm](http://img.shields.io/static/v1?label=fasterq-dump&message=v3.0.2&color=yellow)](https://github.com/ncbi/sra-tools/wiki/HowTo:-fasterq-dump)


2. Raw reads [pre-processing and sequencing quality analyses](https://github.com/TluckDucky/bash/blob/main/sequencingQualityAnalyses) using [fastp](https://github.com/OpenGene/fastp) and [FastQC](https://github.com/s-andrews/FastQC) tools;
3. Mapping of trimmed reads to the human reference transcriptome and mapping quality analyses;
4. Assembly of human transcripts and new human transcriptome;
5. Mapping of trimmed reads to the new human transcriptome assembly;
6. Coding potential analyses and transcript annotation;
7. Reads counting and differential expression analysis;
8. Gene co-expression network and gene ontology analyses.


### Algorithms
List of algorithms used in this pipeline respective to each of the aforementioned pipeline steps:

1. RNA-Seq raw reads download <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=fasterq-dump&message=v3.0.2&color=yellow)

2. Raw reads pre-processing and sequencing quality analyses <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=FastQC&message=v0.11.9&color=brightgreen)
![Badge algorithm](http://img.shields.io/static/v1?label=fastp&message=v0.20.0&color=brightgreen)

3. Mapping of trimmed reads to the human reference transcriptome and mapping quality analyses <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=STAR&message=v2.3.7a&color=green)
![Badge algorithm](http://img.shields.io/static/v1?label=samtools&message=v1.10&color=green)
![Badge algorithm](http://img.shields.io/static/v1?label=geneBody_coverage.py&message=v3.0.1&color=green)
![Badge algorithm](http://img.shields.io/static/v1?label=nfer_experiment.py&message=v3.0.1&color=green)
![Badge algorithm](http://img.shields.io/static/v1?label=tin.py&message=v3.0.1&color=green)

4. Assembly of human transcripts and new human transcriptome <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=Scallop&message=v0.10.4&color=007fff)
![Badge algorithm](http://img.shields.io/static/v1?label=Taco_run&message=v0.6.2&color=007fff)
![Badge algorithm](http://img.shields.io/static/v1?label=bedToGenePred&message=v0.0.4&color=007fff)
![Badge algorithm](http://img.shields.io/static/v1?label=genePredToGtf&message=v0.0.4&color=007fff)

5. Mapping of trimmed reads to the new human transcriptome assembly <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=STAR&message=v2.3.7a&color=9cf)

6. Coding potential analyses and transcript annotation <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=bedtools&message=v2.26.0&color=red)
![Badge algorithm](http://img.shields.io/static/v1?label=FEELnc&message=v0.01&color=red)
![Badge algorithm](http://img.shields.io/static/v1?label=CPC2&message=v0.1&color=red)
![Badge algorithm](http://img.shields.io/static/v1?label=CPAT&message=v3.0.4&color=red)
![Badge algorithm](http://img.shields.io/static/v1?label=liftOver&message=v0.1&color=red)
![Badge algorithm](http://img.shields.io/static/v1?label=Gffcompare&message=v0.11.6&color=red)

7. Reads counting and differential expression analysis <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=featureCounts&message=v2.14.2&color=orange)
![Badge algorithm](http://img.shields.io/static/v1?label=edgeR&message=v3.42.4&color=orange)

8. Gene co-expression network and gene ontology analyses <br/><br/>
![Badge algorithm](http://img.shields.io/static/v1?label=WGCNA&message=v0.10.4&color=lightgray)
![Badge algorithm](http://img.shields.io/static/v1?label=clusterProfiler&message=v4.8.1&color=lightgray)










