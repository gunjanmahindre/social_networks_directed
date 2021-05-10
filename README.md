# Social network codes: directed networks

This has all the codes used in Social Network paper.
Working with directed networks. **D** is not symmetric.
Missing entries in the matrix are recovered using Low-rank Matrix Completion (LMC). Results are compared for the two different sampling schemes as shown below.
1. **Random sampling**: random entries are sampled from the complete distance matrix **D**. LMC is used to recover the missing entries.
2. **Anchor based sampling**: M anchors are selected from N nodes in the network, M<<N. These M nodes know their shortest distance to all the other nodes in the network. Intermittent path lengths are also known, i.e., If node A is an anchor and distance of A-C is known and the path is A-B-C, then the distance from A-B and B-C is also known.


## Approach
**D** >> **P** >> delete a percentage of entries >> Recover **D**    
Where     
**P**: Sampled distance matrix    
**VC**: Virtual coordinate matrix = Only a few columns are selected from the NxN distance matrix    
Percentage deletion: 20, 40, 60, 80, 90% of entries are deleted from the **D** matrix    
We use Low-rank Matrix Completion integrated with bounds for missing entries to estimate missing node pair distances.    


## Performance evaluation metrics:
1. Absolute hop distance error
2. Mean error
We also compare distance distribution and degree distributions of original and recovered distance matrices.
(File distribution_plots.py)

More excution details are provided in (how_to_run.pdf) file.



## Data used
The following directed social networks were used:    
1. Twitter 
2. US election blog 
3. Linux files 
Distance matrices of these networks are given in this repository in data.zip.
