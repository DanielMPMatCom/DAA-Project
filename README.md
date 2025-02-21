# Energy Distribution Network Optimization. DAA-Project

<img src="logo.jpeg" alt="logo" width="400" height="400">

This repository contains the theoretical framework and algorithmic solutions for optimizing energy distribution networks, focusing on minimizing maintenance costs and ensuring continuous power supply to critical zones during emergencies.

## About the Project

Modern energy distribution networks require dynamic reorganization during failures to minimize repair costs and prioritize critical infrastructure. This project addresses two core problems:

1. **Optimal Network Partitioning**: Dividing a network into `k` independent sub-networks with minimal disconnection costs.
2. **Priority Zone Preservation**: Ensuring at least one connected component of size `t` (critical zones) remains operational with minimal edge removals.

The work combines graph theory, NP-completeness proofs, greedy algorithms, dynamic programming, and approximation techniques to solve these challenges.

## Key Problems Addressed

1. **Minimum-Cost k-Partitioning**

   - Input: Weighted graph `G`, integer `k`.
   - Goal: Split `G` into `k` connected components by removing edges with minimal total cost.
   - Complexity: Proven NP-Complete via reduction from Max-Clique.
2. **Priority Component Isolation**

   - Input: Graph `G`, integer `t`.
   - Goal: Remove the minimum number of edges to retain at least one connected component of exactly `t` nodes.
   - Solution: Dynamic programming on trees with `O(n²)` complexity.

## Methodology

### Algorithmic Approaches

- **NP-Completeness Proof**: Reduction from Max-Clique for the partitioning problem.
- **Greedy Solutions**:
  - For trees: Select `k-1` lowest-weight edges (`O(n log n)` complexity).
  - For forests: Extend the tree solution to handle disconnected graphs.
- **Dynamic Programming**: Solves priority component isolation on trees by tracking minimal edge cuts for subtree sizes.
- **Approximation Algorithms**:
  - **Efficient**: Uses Gomory-Hu trees for `(2−2/k)`-approximate k-cuts.
  - **Split**: Iteratively splits components with minimal cuts, achieving the same approximation ratio.

### Technical Contributions

- Formal proofs of NP-Hardness for optimization variants.
- Efficient greedy and dynamic programming solutions for restricted graph classes.
- Novel reductions and combinatorial arguments for approximation guarantees.
