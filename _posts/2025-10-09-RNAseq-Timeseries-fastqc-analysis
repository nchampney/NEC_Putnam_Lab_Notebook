---
layout: post
title: 2025-10-09 Time Series Test RNAseq fastqc analysis
date: '2025-10-09'
categories: bioinformatics
tags: [RNA, Time Series]
---

## Fastqc results and analysis from test libraries for the Time Series expeiment

RNA libraries created using 5 uL of the poly A reagent and 3 uL of the poly A reagent for 3 different *P. acuta* samples were sent out for sequencing. These test sequences were recieved and analyzed using fast qc and multiqc.

## Running fastqc and multiqc

1. Download `fastqc/0.12.1` onto computer
2. Create script under `nano script1.sh`
    a. Script:
    ``` #!/usr/bin/env bash
    #SBATCH --export=NONE
    #SBATCH --nodes=1 --ntasks-per-node=20
    #SBATCH --signal=2
    #SBATCH --no-requeue
    #SBATCH --mem=200GB
    #SBATCH -t 12:00:00
    #SBATCH --mail-type=BEGIN,END,FAIL #email you when job starts, stops and/or fails
    #SBATCH --error=../scripts/outs_errs/"%x_error.%j" #if your job fails, the error report will be put in this file
    #SBATCH --output=../scripts/outs_errs/"%x_output.%j" #once your job is completed, any final job report comments will be put in this file
    ```
3. Download multiqc `module load uri/main
module load all/MultiQC/1.12-foss-2021b
#Compile MultiQC report from FastQC files
multiqc ../outputs/rawqc/`
4. Run script using the command `sbatch script1.sh`

## Results from the fastqc files

R1 files

| File name | Per base sequence quality | Per tile sequence quality | Per sequence quality scores | Per base sequence content | Per sequence GC content | Per base N content | Sequence length distribution| Sequence Duplication levels | Overrepresented sequences | Adapter content |
|-----------|---------------------------|---------------------------|-----------------------------|---------------------------|-------------------------|--------------------|-----------------------------|-----------------------------|---------------------------|-----------------|
| 1_12C3_5uL|           \u2705          |          \u2705           |          \u2705             |           \u274c          |          \u274c         |        \u2705      |             \u2705          |            \u274c           |            !              |     \u274c      |
| 4_12C3_3uL|         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |        \u274c             |       !         |
| 2_1H1_5uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |            !              |       !         |
| 5_1H1_3uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |            !              |       !         |
| 3_3C3_5uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |            !              |       !         |
| 6_3C3_3uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |            !              |      \u2705     |


R2 files

| File name | Per base sequence quality | Per tile sequence quality | Per sequence quality scores | Per base sequence content | Per sequence GC content | Per base N content | Sequence length distribution| Sequence Duplication levels | Overrepresented sequences | Adapter content |
|-----------|---------------------------|---------------------------|-----------------------------|---------------------------|-------------------------|--------------------|-----------------------------|-----------------------------|---------------------------|-----------------|
| 1_12C3_5uL|           \u2705          |          \u2705           |          \u2705             |           \u274c          |          \u274c         |        \u2705      |             \u2705          |            \u274c           |         \u274c            |     \u274c      |
| 4_12C3_3uL|         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |        \u274c             |       !         |
| 2_1H1_5uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |         \u274c            |       !         |
| 5_1H1_3uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |         \u274c            |       !         |
| 3_3C3_5uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |         \u274c            |      \u274c     |
| 6_3C3_3uL |         \u2705            |          \u2705           |          \u2705             |           \u274c          |         \u274c          |        \u2705      |             \u2705          |            \u274c           |         \u274c            |      \u2705     |

Sequence lengths across all files is 151 bp, and there were no sequences flagged for poor quality with any of them. 

Poor quality in the per sequence GC content, sequence duplication levels, and overrepresented sequences is most likely a result of the primers used to sequence the RNA. I am hoping that trimming the sequences to cut out the primer sequence will improve the scores in these areas. 