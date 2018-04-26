# SplitFusion - a fast pipeline for detection of gene fusion based on fusion-supporting split alignment.

Gene fusion is a hallmark of cancer. Many gene fusions are effective therapeutic targets such as the BCL-ABL in chronic myeloid leukemia, EML4-ALK in lung cancer, and various partners-ROS1 in lung cancer. Thus, accurate detection of gene fusion plays a pivotal role in precision medicine by matching the right drugs to the right patients.

Challenges in the diagnosis of gene fusions include poor sample quality, limited amount of available clinical specimens, and complicated gene rearrangements. The anchored multiplex PCR (AMP) is a clinically proven technology designed for robust detection of gene fusion across clinical samples of different types and varied quality, including RNA extracted from FFPE samples.

**SplitFusion** is a companion data pipeline for AMP for detection of gene fusion based on split alignments, i.e. reads cross the fusion breakpoints, with the ability to accurately infer in-frame or out-of-frame of fusion candidates. SplitFusion outputs example seqeunces (in FASTA format) supporting detected fusions.

## Reference publication
[Zheng Z, et al. Anchored multiplex PCR for targeted next-generation sequencing. Nat Med. 2014](http://www.nature.com/nm/journal/v20/n12/full/nm.3729.html)

## How does SplitFusion work?  


The analysis consists of ## computational steps:

1. Retrival of all alignments that have secondaly alignments (SA tag in SAM format) from the BWA MEM mapped bam file.

2. Remove alignments with low mapping quality (default 20).

3. ...

4. ...


Lastly, output summary table.

## Installation

Required software, libraries and data dependency

- R
- samtools
- bedtools
- AnnoVar


The dependency data (e.g. in 'scripts') should contain:

| Filename    | Content |
| :---------: |:-------:|
| panel-name.target.genes   | Contains the list of targets (gene name, e.g. ALK, ROS1, etc.)
| fusion.filter.breakpointID   | Contains recurrent breakpoints identified as data accumulates, but are not of interest.
| fusion.forced.txt   | Contains known breakpoints that are clinically relevant, e.g. "MET_exon13---MET_exon15" which is a exon skipping event that forms an important theraputic target. Many exons skipping/alternative splicings are of unknown clinical relevance and thus not output by default.

The above two files could be updated periodically as supporting database that facilitates automatcial filtering and outputing of fusion candidates.

## Usage examples

