# TOAST benchmark dataset for SARS-CoV-2 sequencing

## Author
Technical Outreach and Assistance for States Team (TOAST)

## Purpose
TOAST decided to work on generating a benchmark dataset for SARS-CoV-2 sequencing per multiple states’ requests. Our benchmark dataset is designed for users at different stages of building sequencing capacity. 
It consists of six subsets summarized in the below table.

## Summary Table
| Dataset  | Datatype | Platform | Primer | Size | Application |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| Outbreak  | fastq,consensus  | Illumina  | random primer (metagenomics)  | 70 samples  | This dataset is an outbreak with three introductions. It’s suitable for labs to understand the features of virus transmission during the real outbreak. [Dataset1](https://github.com/globalmicrobialidentifier-WG3/datasets/blob/master/datasets/sarscov2-SNF-A.tsv) is generated from [Lemieux et al., 2020](https://science.sciencemag.org/content/371/6529/eabe3261) .       |
| Rapid-18 hr | fastq,consensus  | Illumina, MinIon  | ARTIC | 44 samples*3 (CoronaHiT-ONT, ARTIC LoCost, CoronaHiT-Illumina)| This dataset is consisted of Illumina and MinIon sequencing data using 18 hr wet lab protocol (ARTIC LoCost or CoronaHiT). It is suitable for labs to understand the effect of wet lab protocols on the sequencing data and downstream analysis. Due to shorter processing time, they are suitable for being applied under the outbreak setting. Also suitable for labs who consider about automation. [Dataset2](https://github.com/globalmicrobialidentifier-WG3/datasets/blob/master/datasets/sars-cov-2-coronahit-rapid.tsv) is generated from [Baker et al.,2021](https://genomemedicine.biomedcentral.com/articles/10.1186/s13073-021-00839-5).   |
| Routine-30 hr  |  fastq,consensus  | Illumina, MinIon | ARTIC  | 72 samples*3 (CoronaHiT-ONT, ARTIC LoCost, CoronaHiT-Illumina)  | This dataset is consisted of Illumina and MinIon sequencing data using 30 hr wet lab protocol (ARTIC LoCost or CoronaHiT). It is suitable for labs to understand the effect of wet lab protocols on the sequencing data and downstream analysis. Due to longer processing time, they are suitable for being applied under the weekly surveillance setting. Also suitable for labs who consider about automation. [Dataset3](https://github.com/globalmicrobialidentifier-WG3/datasets/blob/master/datasets/sars-cov-2-coronahit-routine.tsv) is generated from [Baker et al.,2021](https://genomemedicine.biomedcentral.com/articles/10.1186/s13073-021-00839-5).  |
| CDC defined VOC/VOI  | fastq | Illumina  | Most are  ARTIC  | 19 samples | This dataset is consisted of representative genomes from 11 VOI/VOC lineages (B.1.1.7, B.1.351, B.1.427, B.1.429, P.1, B.1.525, B.1.526, B.1.526.1, P.2, B.1.617.1, B.1.617.2) with the CDC define spike protein mutations (till 05/30/2021). They are suitable for labs to compare different bioinformatics pipelines or validate any analysis parameter change. [Dataset4](https://github.com/daisy0223/misc/blob/main/Dataset4.tsv) is generated from data mining of publicly available data. |
| Non-VOI/VOC  | fastq, complete genome  | Illumina | ARTIC V3: 33, ARTIC V1: 2, NA:12  |  47 samples  | This dataset is consisted of 47 samples from unique non-VOI/VOC lineages. Due to the existence of close genomes, they are suitable for all labs to evaluate the quality of consensus, comparing different bioinformatics pipelines or validating any analysis parameter change. [Dataset5](https://github.com/daisy0223/misc/blob/main/Dataset5.tsv) is generated from data mining of publicly available data.|
| Bad genomes  | fastq | Illumina   | Some are ARTIC  | 17 samples  | This dataset is consisted of bad sequencing data. They are suitable for new labs to understand possible scenarios of sequencing failures, therefore establish necessary quality management and control system. It covers frameshifts which would always fail VADR, low breadth of coverage, human contamination, 100 Ns in a row of a consensus, amplicon dropout, and non-template control. [Dataset6] is generated by CDC internal collaborators.|

## Downloading script
- Please refer to this [site](https://github.com/WGS-standards-and-analysis/datasets) for more details of installing the downloading script.
## Prerequisites
- `edirct, sratoolkit,Perl, Make, wget, sha256sum`

## Data downloading
-download the dataset.tsv
```Shell
$> Example 1: wget https://raw.githubusercontent.com/globalmicrobialidentifier-WG3/datasets/master/datasets/sarscov2-SNF-A.tsv
$> Example 2: wget https://raw.githubusercontent.com/daisy0223/misc/main/Dataset4.tsv
```
-download the raw reads for each dataset
```Shell
$> perl GenFSGopher.pl -o /path/to/target/directory /path/to/dataset/tsv
```
