# transcriptome_annotation
Assignment to get statistics about a genome assembly using stats from O'Neil and Emrich

O'Neil and Emrich (BMC Genomics 2013) investigate a number of statistics that can be used to assess a transcriptome.
[Click here to read the paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3733778/)

Some statistics use only the transcriptome itelf:

* Total number of basepairs
* Number of transcripts
* Number of "unigenes" 
* Mean and median transcript length
* N50 [explanation here](https://en.wikipedia.org/wiki/N50,_L50,_and_related_statistics)

In Trinity the sequences have IDs like comp18781_c1_g1_i1 and the following would all be members of the same unigene:
comp18781_c1_g1_i1
comp18781_c1_g1_i2
comp18781_c1_g1_i3
comp18781_c1_g1_i4

Thes isoforms may actually be splice forms of the same gene, or they may be different parts of the same gene, or they could be paralogs of a gene as a result of gene or genome duplication. The only way to figure that out is with annotation-based statistics.

The O'Neil & Emrich claims that statistics based on annotations to reference genomes are more consistent. These stats include:

* Number of transcripts with BLAST hits in a reference proteome
* Number of transcripts with a recriprocal blast result (proteome-to-transcriptome and transcriptome-to-proteome)
* Collapse factor (average number of transcripts that match the same protein sequence)

Finally, the annotation statistics may be different when all transcripts are considered versus the 

Phase 1: Use the transcripome sequence to calculate the within-transcriptome statistics.
Phase 2: Use the BLAST results files to also calculate the annotation-based statistics.
Phase 3: Separate statistics based on whether all transcripts are considered or are summarized for each unigene.
