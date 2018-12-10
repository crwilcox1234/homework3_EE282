##code for all of Summarize an annotation file portion of HW3

##cut column 3 with the all of the features and placing them in features.txt

````bash

cut -f 3 dmel-all-r6.24.gtf > features.txt

````

##sort and counts the unique elements in features.txt

````bash

sort features.txt | uniq -c > sorted_counted_features.txt

````

##to pull out all of the genes in column 3

````bash

awk '{ if ($3 == "gene") { print } }' ../../dmel-all-r6.24.gtf > dmel-genes-r6.24.gtf

````

##to cut the first column in dmel-genes-r6.24.gtf and place it in a new file chromosomes.txt

````bash

cut -f 1 dmel-genes-r6.24.gtf > chromosomes.txt

````

##to sort and counts the unique elements in chromosomes.txt, this counts the number of genes on each chromosome, and counts the number of other non-chromosomal genes that are named in the gtf file 

````bash

sort chromosomes.txt | uniq -c > total_gene_chromosome.txt

````
