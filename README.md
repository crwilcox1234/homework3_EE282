# Homework4
# Homework4
#homework3_EE282

Due November 5th, 12pm. I downloaded the Drosophila melanogaster genome from flybase.org by going to the most current download genomes section and downloading the fasta file for all chromosomes for the first part of the homework (Summarize a genome assembly) and the annotation file for the second part (Summarize an annotation file)

##Summarize a genome assembly

###the genome_assembly directory

This directory includes two directories a File_integrity directory and a genome_calcs directory. The File_integrity directory includes the check.txt which is the checksum output for 

```bash
md5sum filename > check.txt

```

###the genome_calcs directory

This directory includes the README.md file that explains the files in the genome_calcs directory. The code is included in the answer or output files for each part (countnumberofNs.txt, faSize_FileIntegrity.txt, numberofnucleotides.txt).


##Summarize an annotation file

##annotation_file directory

Includes the File_integrity directory and summary_report directory

####the File_integrity directory

the File_integrity directory includes the check.txt and md5sum.txt files.  The chect.txt file was generated by:

```bash
md5sum filename > check.txt

```
####the summary_report directory

the summary_report directory includes the code_explanation.txt and code_explanation.md files that are copies of eachother.  I was experimenting using different file types in github and how they would look.  These files explain the code I used to answer question 1 & 2 in this section of the homework (the answer files for each part are in their respective directories (Q1 and Q2) in this directory.  The README file in this directory gives a brief explanation of what I did to answer each question in this section.

#####Q1 directory

includes the features.txt file which contains just the features column (generated using cut) of the annotation file.  The sorted_counted_features.txt file includes the answer to question 1. I used the following code to create features.txt and sorted_counted_features.txt files:

```bash

cut -f 3 dmel-all-r6.24.gtf > features.txt
sort features.txt | uniq -c 

```

#####Q2 directory

includes the chromosomes.txt, dmel-genes-r6.24.gtf, and total_gene_chromosome.txt files.  The code_explanation.md and .txt files in the previous directory explain the code used to generate these files:

````bash

awk '{ if ($3 == "gene") { print } }' ../../dmel-all-r6.24.gtf > dmel-genes-r6.24.gtf
cut -f 1 dmel-genes-r6.24.gtf > chromosomes.txt
sort chromosomes.txt | uniq -c > total_gene_chromosome.txt

```

