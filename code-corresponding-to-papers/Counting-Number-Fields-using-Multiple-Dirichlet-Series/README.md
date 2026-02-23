## Code related to the paper "Counting Number Fields using Multiple Dirichlet Series" by Brandon Alberts and Alina Bucur

All references below are to the arxiv version of this paper, available soon.

### Files

- [code.mag](code.mag) contains all of the Magma code related to this paper.
  - This file defines several Magma functions
    - `ind`: returns the index of an element in a finite transitive permutation group.
    - `MinInd`: returns the minimum index of a nontrivial element in a finite transitive group.
    - `IsConcentrated`: returns a boolean detecting whether a finite transitive group is concentrated in the sense of [[ALOWW25]](https://arxiv.org/abs/2501.18574). Some options are included to restrict the normal subgroups being considered.
    - `IsSemiConcentrated`: returns a boolean detecting whether a finite transitive group is concentrated in the sense of Definition 1.1. Some options are included to restrict the normal subgroups being considered.
  - The file then checks the conditions of Proposition 6.4 for all transitive nilpotent groups of degree less than 24 over any base field linearly disjoint with Q(\zeta_d), where d is the least common mulitple of orders of all minimum index elements. For each group satisfying these conditions, the Magma code returns a string with the following information
    - `nTd`: the transitive group label for the group
    - `a(G)`: the minimum index of a nontrivial element of nTd
    -  `x \le b \le y`: bounds for the parameter b appear in the asymptotic in Conjecture 1, which is one more than the degree of the polynomial in Theorem 1.6
    -  `Can count nTd wr B extensions if \#\mathcal{F}_{k}(B,X) \ll`: when nTd is a 2-group, this returns a sufficient upper bound for the number of B-extensions needed to prove Conjecture 1 for the wreath product of nTd by B, veryifing the statement of Theorem 1.7.
- [output.txt](output.txt) contains a copy of the output as a string.
 
The Magma code is written to be future-proof: while the small examples produced by this code all have minimum index elements of order 2, the code is written to correctly handle any transitive nilpotent group. Generalizing Theorem 1.7 to nilpotent groups other than 2-groups will require generalizing Lemma 7.3, but is otherwise accessible.

### Future Directions

- We expect that it is possible to write Magma code to directly test Theorem 6.1 for nilpotent groups and Theorem 6.6 for groups concetrated in nilpotent subgroups, rather than relying on shortcuts like Proposition 6.4.
- It is certainly possible to include the results of this Magma code in the records produced by the Magma code associated with [[ALOWW25]](https://arxiv.org/abs/2501.18574), see the corresponding [github repository](https://github.com/lemkeoliver/lemkeoliver.github.io/tree/main/docs/code/inductivemethods)

We hope to see more work in these directions at a forthcoming [ICERM workshop](https://icerm.brown.edu/program/topical_workshop/tw-26-nfc). Should more comprehensive Magma code become available after this workshop, we will endeavor to update this readme file with links.
