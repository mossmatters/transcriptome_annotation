# transcriptome_annotation
Assignment to get statistics about a genome assembly using stats from O'Neil and Emrich

[Click here to get the input data.](https://texastechuniversity-my.sharepoint.com/:u:/g/personal/matt_johnson_ttu_edu/ESUmMoaX-y5PtpAd-9Orus8BB7fghDVhIwrF4vRRki8eUQ?e=wcbgS0)

O'Neil and Emrich (BMC Genomics 2013) investigate a number of statistics that can be used to assess a transcriptome.
[Click here to read the paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3733778/)

Some statistics use only the transcriptome itself:

* Total number of basepairs
* Number of transcripts
* Number of "unigenes" 
* Mean and median transcript length
* N50 [explanation here](https://en.wikipedia.org/wiki/N50,_L50,_and_related_statistics)

In Trinity the sequences have IDs like c1_g1_i1 and the following would all be members of the same unigene:

- c1_g1_i1
- c1_g1_i2
- c1_g1_i3
- c1_g1_i4

Unigenes are identified by the first two fields (c1_g1) and the other transcripts are isoforms. The isoforms may actually be splice forms of the same gene, or they may be different parts of the same gene, or they could be paralogs of a gene as a result of gene or genome duplication. The only way to figure that out is with annotation-based statistics.

The O'Neil & Emrich claims that statistics based on annotations to reference genomes are more consistent. These stats include:

* Number of transcripts with BLAST hits in a reference proteome
* Number of unique proteins in the reference proteome with a BLAST hit
* Collapse factor (average number of transcripts that match the same protein sequence)

Finally, the annotation statistics may be different when all transcripts are considered versus summarizing them for each unigene separately. Statistics could include:

* Number of unigenes with more than 1 (or 5 or 10) isoforms
* Percentage of cases where each isoform has the same best BLAST hit
* Annotation statistics for only the *longest isoform* of each unigene

**Phase 1**: Use the transcripome sequence to calculate the within-transcriptome statistics.

**Phase 2**: Use the BLAST results files to also calculate the annotation-based statistics.

**Phase 3**: Separate statistics based on whether all transcripts are considered or are summarized for each unigene.

Input files:

`NW-1.Trinity.fasta`: Assembled transcriptome sequence. Sequence ids are as explained above.

`NW-1.Physco.blastx`: Results of a BLASTx search of the NW-1 transcriptome against a reference proteome.

