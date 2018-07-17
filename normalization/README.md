## Normalization of Hi-C data

- `HiCNorm` - removing biases in Hi-C data via Poisson regression, http://www.people.fas.harvard.edu/~junliu/HiCNorm/

- `caICB` - chromosome-adjusted iterative correction of biases method. Review of Hi-C data biases and methods to remove them. CNV bias cannot be removed after within-chromosome iterative correction bias methods. The distance-dependent decay of interaction frequencies is modeled by splines. The caICB method aims to minimize the differences across count-distance curves of different chromosomes, chr1 as the reference. A priori knowledge of CNVs is not required. The between- and within-chromosome bias is removed, minimizing the number of significant contacts due to CNVs. https://bitbucket.org/mthjwu/hicapp
    - Wu, Hua-Jun, and Franziska Michor. “A Computational Strategy to Adjust for Copy Number in Tumor Hi-C Data.” Bioinformatics (Oxford, England) 32, no. 24 (15 2016): 3695–3701. https://doi.org/10.1093/bioinformatics/btw540.

- `OneD` - CNV bias-correction method, addresses the problem of partial aneuploidy. Bin-centric counts are modeled using negative binomial distribution, and its parameters are estimated using splines. A hidden Markov model is fit to infer copy number for each bin. Each Hi-C matrix entry is corrected by dividing its value by square root of the product of CNVs for the corresponding bins. Reproducibility score (eigenvector decomposition and comparison) to measure improvement in the similarity between replicated Hi-C data. https://github.com/qenvio/dryhic
    - Vidal, Enrique, François le Dily, Javier Quilez, Ralph Stadhouders, Yasmina Cuartero, Thomas Graf, Marc A Marti-Renom, Miguel Beato, and Guillaume J Filion. “OneD: Increasing Reproducibility of Hi-C Samples with Abnormal Karyotypes.” Nucleic Acids Research, January 31, 2018. https://doi.org/10.1093/nar/gky064.