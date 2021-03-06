# PHYLIP2NEXUS

THIS SHELL script, ```PHYLIP2NEXUS.sh```, converts a single PHYLIP-formatted DNA sequence alignment file present in the current working directory, and passed to the program as stdin, into NEXUS format. The starting file must have the extension ".phy", and the first line of this file must contain the  number of taxa, followed by one space, followed by the number of characters in the  alignment. Some actions are echoed to screen. The output is a single NEXUS file with the name, "BASENAME.nex", where "BASENAME" is the base or root name of the original PHYLIP file. For example, in a starting file named "Smerianae_ND4.phy," BASENAME would  be "Smerianae_ND4" and the resulting output file would be named "Smerianae_ND4.nex". 

I have not had time to add help texts yet, but I recently added two new options--one for specifying a partitions file (-p), and another related option for specifying the format of the partitions file (-f). If the partitions file is given, then the script expects partitions file format to be of either RAxML format  (specified with 'raxml') or NEXUS format ('NEX' or 'nex'). The RAxML format is the same format used in RAxML (e.g. v8+, Stamatakis 2014) and output by PartitionFinder 1 and 2 (Lanfear et al. 2012, 2014), and both this format and the more traditional NEXUS charset format (i.e. ```begin sets; ... charset 1 = 1-xxx;```) will be  familiar to most users.

## USAGE

Usage example:

```
$ ./PHYLIP2NEXUS.sh -p balf_clade_simData.partitions -f raxml ./balf_clade_simData.phy

##########################################################################################
#                             PHYLIP2NEXUS v1.1, March 2018                              #
##########################################################################################

INFO      | Thu Mar 15 15:35:32 EDT 2018 |          Setting user-specified path to: 
/path/to/balf_clade/folder 
INFO      | Thu Mar 15 15:35:32 EDT 2018 |          Input PHYLIP file: ./balf_clade_simData.phy 
INFO      | Thu Mar 15 15:35:32 EDT 2018 |          Examining current directory, setting variables... 
INFO      | Thu Mar 15 15:35:32 EDT 2018 |          Making NEXUS-formatted file... 
INFO      | Thu Mar 15 15:35:32 EDT 2018 |          Read RAxML-style partitions file. Adding partition information to final NEXUS file... 
INFO      | Thu Mar 15 15:35:32 EDT 2018 |          Removing temporary files... 
INFO      | Thu Mar 15 15:35:32 EDT 2018 |          Done converting PHYLIP-formatted DNA sequence alignment to NEXUS format using PHYLIP2NEXUS.sh.
Bye.

$
```

## REFERENCES

- Lanfear R, Calcott B, Ho SYW, Guindon S (2012) PartitionFinder: combined selection of partitioning schemes and substitution models for phylogenetic analyses. Molecular Biology and Evolution, 29,1695-1701.
- Lanfear R, Frandsen PB, Wright AM, Senfeld T, Calcott B (2016) PartitionFinder 2: new methods for selecting partitioned models of evolution for molecular and morphological phylogenetic analyses. Molecular Biology and Evolution.
- Stamatakis A (2014) RAxML version 8: a tool for phylogenetic analysis and post-analysis of large phylogenies. Bioinformatics, 30, 1312-1313.

March 15, 2018
Justin C. Bagley, Richmond, VA
