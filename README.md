# MapReduce-GENSEG
The following explanation is the details for executing The algorithm GenSeg and MR-GenSeg on sample NA12878 on chromosome 22 of human DNA sequences. The same procedure is followed for the other samples and other chromosomes. 

Software requirements:

1. Ubuntu 
2. Samtools
3. Python
4. R
5. Java
4. A Hadoop real distributed cluster, with minimum 1 master and 1 slave. Atleast 16 GB RAM. 



Step 1> The desired samples in .bam format is not included here, due to its large size. You can download the .bam files from the following url. 
ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/technical/
    
Chromosome 22 and chromosome 14 of both low coverage and high coverage data for the below mentioned samples are downloaded.
NA12878,NA12891,NA12892,NA19238,NA19239,NA19240

Step 2>
Samtools is used to process the .bam file and the sorted .bam files are prepared and provided as input to the next step.
Step 3>
Go to to the tobegiven-12878-22.zip file and then go to creating-coverage-quantification.zip. There execute the sortedcsv.py file to generate the base coverage and base quantification. The output of this is then provided to the next step.
Step 4>
Go to preprocessing-missingvalues-zscore.zip . This contains the file mrscore.py used for preprocessing , filling missingvalues with 0 and generating the zscores. Output of this is provided to the next step.
Step 5>
Go to traditional.zip. This contains a file SegVar.py file which is the segmentation algorith GenSeg used to generate the segments of the genome. 
Step 6>
Go to mapreduce.zip and considering the output of step 4 execute the MapReduce programs map1lakh.py and red1lakh.py to generate the segments.
