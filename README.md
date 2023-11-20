# R-CQ
Reverse-CQ (R-CQ) is an algorithm that uses read-alignment depth information from separate male and female sequencing datasets in order to detect sex chromosomes in an assembly using the Male-depth/Female-depth ratio.
It is based on the copy-number difference of sex chromosomes between the two sexes, that corresponds to respective difference in the depth of sequencing reads. 
Therefore, for N sequencing depth of diploid autosomes, the respective depth for X will be N in XX female and N/2 in XY males. 
The detection of Y regions is amenable due to the absence of actual genomic data in female datasets from the male-limited Y chromosome.
Each assembly region is assessed for the Male-depth/Female-depth ration on a sequence window based manner, where the window size is determined by the user (default is 100 bp). 

R-CQ algorithm takes as input two .bw coverage files from the independent alignment of male and female DNA reads on the query genome. 
Users are highly recommended to either use the GSNAP alignment algorithm for aligning reads, and then feeding R-CQ with the concordant unique reads, or use other tools (eg. samtools) to filter repetitive and halfmapping reads. 
The algorithm also requires the ID of an autosomal contig for normalizing depth differences between male and female datasets. 
Users have the option to use an automatic repeat cutoff filter that excludes windows with repetitive sequences from the analysis, manually set the repeat cutoff or deactivate the function. 

Run the R-CQ.pl script to see a full list of options. 
