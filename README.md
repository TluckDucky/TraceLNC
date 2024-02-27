<h1 align="center"> Pipeline for Human Transcriptome Construction, Novel Human lncRNA Annotation and Downstream Analyses </h1>

## Description:
This document provides a description of a pipeline to build a new human transcriptome, to annotate novel human lncRNAs and to perform further downstream analyses.

<p align="center">
<img loading="lazy" src="http://img.shields.io/static/v1?label=status&message=developing&color=blue"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=updated&message=february2024&color=GREEN"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=language&message=bash&color=red"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=language&message=R&color=yellow"/>
</p>

# Summary  
* [Introduction](#Introduction)
* [Details](#Details)
* [Developer](https://github.com/TluckDucky)
* [License](#License)

### Introduction
This pipeline comprises the following steps and the respective algorithms:

(Click over the badge of the desired algorithm to check its GitHub repository or similar).

1. RNA-Seq raw reads [download](https://github.com/TluckDucky/bash/blob/main/sraSamplesDownload) using the NCBI-SRA fasterq-dump tool; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=fasterq-dump&message=v3.0.2&color=yellow)](https://github.com/ncbi/sra-tools/wiki/HowTo:-fasterq-dump) <br/><br/>
2. Raw reads [pre-processing and sequencing quality analyses](https://github.com/TluckDucky/bash/blob/main/sequencingQualityAnalyses) using fastp and FastQC tools; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=FastQC&message=v0.11.9&color=brightgreen)](https://github.com/s-andrews/FastQC)
[![Badge algorithm](http://img.shields.io/static/v1?label=fastp&message=v0.20.0&color=brightgreen)](https://github.com/OpenGene/fastp)<br/><br/>
3. [Mapping of trimmed reads to the human reference transcriptome](https://github.com/TluckDucky/bash/blob/main/STARmapping) and mapping quality analyses; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=STAR&message=v2.3.7a&color=green)](https://github.com/alexdobin/STAR)
[![Badge algorithm](http://img.shields.io/static/v1?label=samtools&message=v1.10&color=green)](https://github.com/samtools/samtools)
[![Badge algorithm](http://img.shields.io/static/v1?label=geneBody_coverage.py&message=v3.0.1&color=green)](https://github.com/MonashBioinformaticsPlatform/RSeQC/blob/master/rseqc/modules/geneBody_coverage.py)
[![Badge algorithm](http://img.shields.io/static/v1?label=infer_experiment.py&message=v3.0.1&color=green)](https://github.com/MonashBioinformaticsPlatform/RSeQC/blob/master/rseqc/modules/infer_experiment.py)
[![Badge algorithm](http://img.shields.io/static/v1?label=tin.py&message=v3.0.1&color=green)](https://github.com/MonashBioinformaticsPlatform/RSeQC/blob/master/rseqc/modules/tin.py)<br/><br/>
4. Assembly of human transcripts and new human transcriptome; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=Scallop&message=v0.10.4&color=007fff)](https://github.com/Kingsford-Group/scallop)
[![Badge algorithm](http://img.shields.io/static/v1?label=Taco_run&message=v0.6.2&color=007fff)](https://tacorna.github.io/)
[![Badge algorithm](http://img.shields.io/static/v1?label=bedToGenePred&message=v0.0.4&color=007fff)](https://github.com/ENCODE-DCC/kentUtils/tree/master/src/utils/bedToGenePred)
[![Badge algorithm](http://img.shields.io/static/v1?label=genePredToGtf&message=v0.0.4&color=007fff)](https://github.com/ENCODE-DCC/kentUtils/tree/master/src/hg/genePredToGtf)<br/><br/>
5. Mapping of trimmed reads to the new human transcriptome assembly; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=STAR&message=v2.3.7a&color=9cf)](https://github.com/alexdobin/STAR)<br/><br/>
6. Coding potential analyses and transcript annotation; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=bedtools&message=v2.26.0&color=red)](https://github.com/arq5x/bedtools2)
[![Badge algorithm](http://img.shields.io/static/v1?label=FEELnc&message=v0.01&color=red)](https://github.com/tderrien/FEELnc)
[![Badge algorithm](http://img.shields.io/static/v1?label=CPC2&message=v0.1&color=red)](https://github.com/gao-lab/CPC2_standalone)
[![Badge algorithm](http://img.shields.io/static/v1?label=CPAT&message=v3.0.4&color=red)](https://github.com/liguowang/cpat)
[![Badge algorithm](http://img.shields.io/static/v1?label=liftOver&message=v0.1&color=red)](https://github.com/jeremymcrae/liftover)
[![Badge algorithm](http://img.shields.io/static/v1?label=Gffcompare&message=v0.11.6&color=red)](https://github.com/gpertea/gffcompare)<br/><br/>
7. Reads counting and differential expression analysis; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=featureCounts&message=v2.14.2&color=orange)](https://rnnh.github.io/bioinfo-notebook/docs/featureCounts.html)
[![Badge algorithm](http://img.shields.io/static/v1?label=edgeR&message=v3.42.4&color=orange)](https://bioconductor.org/packages/release/bioc/html/edgeR.html)<br/><br/>
8. Gene co-expression network and gene ontology analyses <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=WGCNA&message=v0.10.4&color=lightgray)](https://github.com/cran/WGCNA/tree/master)
[![Badge algorithm](http://img.shields.io/static/v1?label=clusterProfiler&message=v4.8.1&color=lightgray)](https://github.com/YuLab-SMU/clusterProfiler/tree/devel/vignettes)<br/><br/>


### Details
Steps 1 to 6 were run using bash programming  language. Steps 7 and 8, using R programming language.

* Step 1 <br/>
The fasterq-dump algorithm was run using the default parameters. <br/>

* Step 2 <br/>
If you use sharp trimming tools or approaches, you may encounter low rates of uniquely mapped reads (steps 3 & 5), which may impair downstream analysis. [Check it up.](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-016-0956-2) For that, fastp was run with default parameters. <br/>

* Steps 3 & 5 <br/>
After performing the second mapping, verify the percentage of uniquely mapped reads (recommended for gene expression analyses). <br/>
Low mapping rate | < 50% - indicative of a problem with library preparations or data processing. <br/>
Good mapping rate | 80 to 90%. <br/>
Very good mapping rate | superior to 90%.


### License
* [GNU General Public License v3.0](https://github.com/TluckDucky/bash/blob/main/LICENSE)

### Comments and Suggestions?
All comments and suggestions are appreciated. Please, submit them to [thalleslopes.github@gmail.com](thalleslopes.github@gmail.com).

Thank you!







