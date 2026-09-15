<img align="center" width="877" height="678" alt="traceLNC_3" src="https://github.com/user-attachments/assets/8efa9c91-22d4-477b-b30f-7d933a1022d9" />

## Description:
This documentation provides a description of a pipeline to assemble a new human transcriptome, to annotate novel lncRNAs and to perform further downstream analyses. The "Core Evaluation of lncRNAs" is related to the part of the pipeline that transforms the identification of an RNA sequence into functional and biological knowledge.

<p align="center">
<img loading="lazy" src="http://img.shields.io/static/v1?label=status&message=developing&color=blue"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=updated&message=september2026&color=GREEN"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=language&message=bash&color=red"/>
<img loading="lazy" src="https://img.shields.io/static/v1?label=language&message=R&color=yellow"/>
</p>

# Pipeline Steps
## [STEP 1] Assembly of the first version of the new human hiPSC-TB transcriptome
<img width="794" height="1123" alt="pipeline_1" src="https://github.com/user-attachments/assets/e37e9dd8-0e3b-4712-9633-c2861cc26537" />

## [STEP 2] Annotation of the first version of the new human hiPSC-TB transcriptome to obtain the final version
<img width="794" height="1123" alt="pipeline_2" src="https://github.com/user-attachments/assets/4dfd5c14-9081-4460-b723-c3e2fe0538cd" />

## [STEP 3] Downstream analyses using the final version of the new human hiPSC-TB transcriptome
<img width="794" height="1123" alt="pipeline_3" src="https://github.com/user-attachments/assets/922157ea-5dd9-49c2-9f64-54a9878f5932" />

# Summary  
* [Introduction](#Introduction)
* [Details](#Details)
* [Contributors](#Contributors)
* [Citation](#Citation)
* [License](#License)
* [Developer](https://github.com/TluckDucky)

### Introduction
This pipeline comprises the following steps and the respective algorithms:

(Click over the badge of the desired algorithm to check its GitHub repository or similar).

1. RNA-Seq raw reads [download](https://github.com/TluckDucky/bash/blob/main/sraSamplesDownload) using the NCBI-SRA fasterq-dump tool; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=fasterq-dump&message=v3.0.2&color=yellow)](https://github.com/ncbi/sra-tools/wiki/HowTo:-fasterq-dump) <br/><br/>
2. Raw reads [pre-processing and sequencing quality analyses](https://github.com/TluckDucky/bash/blob/main/sequencingQualityAnalyses) using fastp and FastQC tools; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=FastQC&message=v0.11.9&color=brightgreen)](https://github.com/s-andrews/FastQC)
[![Badge algorithm](http://img.shields.io/static/v1?label=fastp&message=v0.20.0&color=brightgreen)](https://github.com/OpenGene/fastp)<br/><br/>
3. [Mapping of trimmed reads to the human reference transcriptome](https://github.com/TluckDucky/transcriptomeAssemblyAndFurther/blob/main/indexesAndMapping) and [mapping quality analyses](https://github.com/TluckDucky/transcriptomeAssemblyAndFurther/blob/main/mappingQualityAnalyses); <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=STAR&message=v2.3.7a&color=green)](https://github.com/alexdobin/STAR)
[![Badge algorithm](http://img.shields.io/static/v1?label=samtools&message=v1.10&color=green)](https://github.com/samtools/samtools)
[![Badge algorithm](http://img.shields.io/static/v1?label=tin.py&message=v3.0.1&color=green)](https://github.com/MonashBioinformaticsPlatform/RSeQC/blob/master/rseqc/modules/tin.py)
[![Badge algorithm](http://img.shields.io/static/v1?label=geneBody_coverage.py&message=v3.0.1&color=green)](https://github.com/MonashBioinformaticsPlatform/RSeQC/blob/master/rseqc/modules/geneBody_coverage.py)
[![Badge algorithm](http://img.shields.io/static/v1?label=infer_experiment.py&message=v3.0.1&color=green)](https://github.com/MonashBioinformaticsPlatform/RSeQC/blob/master/rseqc/modules/infer_experiment.py)<br/><br/>
5. Assembly of human transcripts and new human transcriptome; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=Scallop&message=v0.10.4&color=007fff)](https://github.com/Kingsford-Group/scallop)
[![Badge algorithm](http://img.shields.io/static/v1?label=Taco_run&message=v0.6.2&color=007fff)](https://tacorna.github.io/)
[![Badge algorithm](http://img.shields.io/static/v1?label=bedToGenePred&message=v0.0.4&color=007fff)](https://github.com/ENCODE-DCC/kentUtils/tree/master/src/utils/bedToGenePred)
[![Badge algorithm](http://img.shields.io/static/v1?label=genePredToGtf&message=v0.0.4&color=007fff)](https://github.com/ENCODE-DCC/kentUtils/tree/master/src/hg/genePredToGtf)<br/><br/>
6. Mapping of trimmed reads to the new human transcriptome assembly; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=STAR&message=v2.3.7a&color=9cf)](https://github.com/alexdobin/STAR)<br/><br/>
7. Coding potential analyses and transcript annotation; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=bedtools&message=v2.26.0&color=red)](https://github.com/arq5x/bedtools2)
[![Badge algorithm](http://img.shields.io/static/v1?label=FEELnc&message=v0.01&color=red)](https://github.com/tderrien/FEELnc)
[![Badge algorithm](http://img.shields.io/static/v1?label=CPC2&message=v0.1&color=red)](https://github.com/gao-lab/CPC2_standalone)
[![Badge algorithm](http://img.shields.io/static/v1?label=CPAT&message=v3.0.4&color=red)](https://github.com/liguowang/cpat)
[![Badge algorithm](http://img.shields.io/static/v1?label=liftOver&message=v0.1&color=red)](https://github.com/jeremymcrae/liftover)
[![Badge algorithm](http://img.shields.io/static/v1?label=Gffcompare&message=v0.11.6&color=red)](https://github.com/gpertea/gffcompare)<br/><br/>
8. Reads counting and differential expression analysis; <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=featureCounts&message=v2.14.2&color=orange)](https://rnnh.github.io/bioinfo-notebook/docs/featureCounts.html)
[![Badge algorithm](http://img.shields.io/static/v1?label=edgeR&message=v3.42.4&color=orange)](https://bioconductor.org/packages/release/bioc/html/edgeR.html)<br/><br/>
9. Gene co-expression network and gene ontology analyses <br/><br/>
[![Badge algorithm](http://img.shields.io/static/v1?label=WGCNA&message=v0.10.4&color=lightgray)](https://github.com/cran/WGCNA/tree/master)
[![Badge algorithm](http://img.shields.io/static/v1?label=clusterProfiler&message=v4.8.1&color=lightgray)](https://github.com/YuLab-SMU/clusterProfiler/tree/devel/vignettes)<br/><br/>


### Details
Steps 1 to 6 were run using bash programming  language. Steps 7 and 8, using R programming language.

* Step 1 <br/>
The fasterq-dump algorithm was run using the default parameters. <br/>

* Step 2 <br/>
If you use sharp trimming tools or approaches, you may encounter low rates of uniquely mapped reads (steps 3 & 5), which may impair downstream analysis. [Check it up.](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-016-0956-2) For that, fastp was run with default parameters. <br/>

* Steps 3 & 5 <br/>
STAR indexes generation and mapping were performed using the ENCODE standard options as described in this STAR manual and as described by [Maciel, L.F. and Verjovski-Almeida, S. (2020)](doi.org/10.1007/978-1-0716-0635-3_10). <br/><br/>
After performing the second mapping, verify the percentage of uniquely mapped reads (recommended for gene expression analyses). <br/><br/>
[Mapping rates:](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4631051/)<br/>
Low mapping rate | < 50% - indicative of a problem with library preparations or data processing. <br/>
Good mapping rate | 80 to 90%. <br/>
Very good mapping rate | superior to 90%. <br/><br/>
To run the RSeQC modules tin.py and geneBody_coverage.py you will need to index the sorted bam files from the 2nd mapping beforehand. To do so you may use the index command of samtools. The bai files are not declared in the code but they must be stored in the directory for a succesfull run of these modules. <br/><br/>
It is recommended to build one superdirectory for each PRJNA Project, bearing directories for each analyses and using symbolic links to needed files (star/index; star/1stMapping and star/2ndMapping).

### Contributors
In alphabetical order:
* Ana Carolina Tahira
* Caio Felipe Freire de Sousa
* Sergio Verjovski-Almeida
* Thalles Souza-Lopes

### Citation
Please, when using this pipeline use the following reference:

Souza-Lopes T, Fischer-Carvalho A, Freire CF, et al. Co-Expression Network Analyses Reveal Long Non-Coding RNA Programs Associated with Trophoblast Development and Response to Zika Virus Infection in Twins Discordant for Congenital Zika Syndrome. Int J Mol Sci. 2026;27(16):7281, [10.3390/ijms27167281](https://www.mdpi.com/1422-0067/27/16/7281).

### Zenodo
[Our Zenodo repository](https://doi.org/10.5281/zenodo.20399848).
### License
* [GNU General Public License v3.0](https://github.com/TluckDucky/bash/blob/main/LICENSE)

### Comments and Suggestions?
All comments and suggestions are appreciated. Please, submit them to [thalleslopes.github@gmail.com](thalleslopes.github@gmail.com).

Thank you!







