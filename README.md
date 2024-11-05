# Problem Statement:

Suppose we have an optimal alignment for two sequences  S1…n  and  T1…m  in which Si matches Tj. The key insight is that this optimal alignment is composed of an optimal alignment between  (S1,…,Si−1) and (T1,…,Ti−1) and an optimal alignment between  (Si+1,…,Sn) and  (Tj+1,…,Tm). This follows from a cut-and-paste argument: if one of these partial alignments is suboptimal, then we cut-and-paste a better alignment in place of the suboptimal one. This achieves a higher score of the overall alignment and thus contradicts the optimality of the initial global alignment. In other words, every subpath in an optimal path must also be optimal. Notice that the scores are additive, so the score of the overall alignment equals the addition of the scores of the alignments of the subsequences. This implicitly assumes that the sub-problems of computing the optimal scoring alignments of the subsequences are independent. We need to biologically motivate that such an assumption leads to meaningful results.

# Idea and approach:

The idea is central to the optimal substructure property of dynamic programming algorithms, particularly in sequence alignment problems like in Needleman-Wunsch Algorithm. In biological sequence alignment, we are generally comparing two sequences, say a pair of DNA, RNA, or protein sequences, to find regions of similarity. The goal is to identify homologous sequences that are evolutionarily related. These alignments can reveal structural or functional similarities that help us understand the biological roles of certain genes or proteins.

# Needleman-Wunsch Algorithm

1. Scoring System

+ Match score: A positive score for aligning identical characters.<br/>
+ Mismatch penalty: A negative score for aligning different characters.<br/>
+ Gap penalty: A negative score for introducing a gap (insertions or deletions).<br/>

2. Dynamic Programming Matrix
We construct a matrix D where the element D[i][j] represents the optimal score for aligning the first i characters of sequence S with the first j characters of sequence T. The size of the matrix is (n+1)×(m+1), where n is the length of S and m is the length of T.

3. Recurrence Relation
To fill in the matrix, we compute each cell D[i][j] using the following recurrence relation:<br/>

4. Traceback
Once the matrix is filled, we perform a traceback starting from D[n][m] (the bottom-right corner of the matrix).This traceback process reveals the optimal alignment by following the path that led to the optimal score.
