# Domain-Independent Dynamic Programming (DIDP)

Domain-Independent Dynamic Programming (DIDP) is a novel model-based paradigm for combinatorial optimization based on dynamic programming (DP).
In DIDP, once you formulate your problem as a DP model, you can use generic solvers to solve the model, just as in mixed-integer programming (MIP) and constraint programming (CP).
DIDP shows superior performance to MIP and CP in a number of combinatorial optimization problems including vehicle routing problems (VRPs), packing problems, and scheduling problems (see our [papers](#papers) for detailed evaluations).

## Software

Our framework is publicly available as open-source software under the MIT/Apache-2.0 license (**free for commercial use!**).
To get started, we recommend using [DIDPPy](https://didppy.rtfd.io).

- [DIDPPy](https://didppy.rtfd.io): Python interface for DIDP. You can formulate DP models and solve them with generic solvers using Python. You do not need to install the other libraries individually.
- [didp-yaml](https://crates.io/crates/didp-yaml): Command line executable for DIDP taking YAML files as input. You can formulate DP models and write configurations of a solver in the YAML data format and pass them to the executable. You do not need to install the other libraries individually.
- [dypdl](https://crates.io/crates/dypdl): Rust library for DP modeling.
- [dypdl-heuristic-search](https://crates.io/crates/dypdl-heuristic-search): Rust library for heuristic search based generic DP solvers.

All of the above software are managed on [our GitHub repository](https://github.com/domain-independent-dp/didp-rs).

## Modeling in DIDP

We use Dynamic Programming Description Language (DyPDL) as a modeling formalism for DIDP, which is based on state transition systems.
While it is named "Language", DyPDL is independent from particular programming languages or data formats, and we provide [Python](https://didppy.rtfd.io), [Rust](https://crates.io/crates/dypdl), and [YAML](https://crates.io/crates/didp-yaml) interfaces for it.

We provide Python and YAML models used by our papers in a [repository](https://github.com/Kurorororo/didp-models/tree/main).

## Solvers for DIDP

Currently, [our generic DIDP solvers](https://crates.io/crates/dypdl-heuristic-search) are based on heuristic search such as A* and beam search, inspired by AI planning.

## Papers

- Ryo Kuroiwa and J. Christopher Beck. [Domain-Independent Dynamic Programming: Generic State Space Search for Combinatorial Optimization.](https://ojs.aaai.org/index.php/ICAPS/article/view/27200/26973) In Proceedings of the 33rd International Conference on Automated Planning and Scheduling (ICAPS). 2023. [supplement](https://tidel.mie.utoronto.ca/pubs/Appendix_CAASDy_ICAPS23.pdf) [slides](./pdfs/didp_icaps2023.pdf) [poster](./pdfs/didp_poster_icaps2023.pdf)
  - This paper introduces the notion of DIDP with the modeling language DyPDL and the generic solver CAASDy with the experimental evaluation using 6 combinatorial optimization problems.
- Ryo Kuroiwa and J. Christopher Beck. [Solving Domain-Independent Dynamic Programming Problems with Anytime Heuristic Search.](https://ojs.aaai.org/index.php/ICAPS/article/view/27201/26974) In Proceedings of the 33rd International Conference on Automated Planning and Scheduling (ICAPS). 2023. [supplement](https://tidel.mie.utoronto.ca/pubs/Appendix_Anytime_ICAPS23.pdf) [slides](./pdfs/anytime_icaps2023.pdf)
  - This paper proposes 6 anytime solvers for DIDP with the experimental evaluation using 9 combinatorial optimization problems.
- Ryo Kuroiwa and J. Christopher Beck. [Large Neighborhood Beam Search for Domain-Independent Dynamic Programming.](https://drops.dagstuhl.de/opus/volltexte/2023/19060/pdf/LIPIcs-CP-2023-23.pdf) In Proceedings of the 29th International Conference on Principles and Practice of Constraint Programming (CP). 2023. [slides](./pdfs/lnbs_cp2023.pdf) [poster](./pdfs/lnbs_poster_cp2023.pdf)
  - This paper proposes a large neighborhood search framework for DIDP based on beam search.
- Ryo Kuroiwa and J. Christopher Beck. [Parallel Beam Search Algorithms for Domain-Independent Dynamic Programming.](https://ojs.aaai.org/index.php/AAAI/article/view/30062/31869) In Proceedings of the 38th Annual AAAI Conference on Artificial Intelligence (AAAI). 2024. [supplement](https://tidel.mie.utoronto.ca/pubs/Appendix_Parallel_AAAI24.pdf) [slides](./pdfs/parallel_aaai2024.pdf) [poster](./pdfs/parallel_poster_aaai2024.pdf)
  - This paper develops multi-thread DIDP solvers based on parallel beam search algorithms.
  - Errata: In Algorithm 8, `|L| < k` should be added in the while loop condition. This condition is used in the implementation but was forgotten in the pseudo-code.  
- Ryo Kuroiwa and J. Christopher Beck. [Domain-Independent Dynamic Programming](https://arxiv.org/abs/2401.13883)
  - This paper formally defines and theoretically analyzes DyPDL and heuristic search solvers for DIDP, extending the two ICAPS papers. The experimental evaluation uses 11 combinatorial optimization problems.

### Papers using DIDP

- Arnoosh Golestanian, Giovanni Lo Bianco, Chengyu Tao, and J. Christopher Beck. [Optimization Models for Pickup and Delivery Problems with Reconfigurable Capacities.](https://tidel.mie.utoronto.ca/pubs/Golestanian_CP2023.pdf) In Proceedings of the 29th International Conference on Principles and Practice of Constraint Programming (CP). 2023.
  - DIDP beats MIP and CP in a pickup and delivery problem with complicated capacity constraints inspired by a real-world application.
- Jiacheng Zhang and J. Christopher Beck. [Solving LBBD Master Problems with Constraint Programming and Domain-Independent Dynamic Programming](https://drops.dagstuhl.de/storage/00lipics/lipics-vol307-cp2024/LIPIcs.CP.2024.32/LIPIcs.CP.2024.32.pdf). In Proceedings of the 30th International COnference on Principles and Practice of Constraint Programming (CP). 2024.
  - This paper proposes a Bender's decomposition method using DIDP as a master problem formulation.
- Jiacheng Zhang and J. Christopher Beck. [Domain-Independent Dynamic Programming and Constraint Programming Approaches for Assembly Line Balancing Problems with Setups](https://pubsonline.informs.org/doi/full/10.1287/ijoc.2024.0603). INFORMS Journal on Computing 2024. [post-print](https://tidel.mie.utoronto.ca/pubs/sualbp_ijoc_postprint.pdf)
  - DIDP models for SUALBP-1 and SUALBP-2, variants of assembly line balancing problems, are proposed, and they outperform MIP and CP models.


## Presentations

- [Introduction to DIDP](./pdfs/didp_dpsolve2023.pdf) presented at the [DPSOLVE](https://sites.google.com/view/dpsolve2023/) workshop at CP 2023

## Contact Information

Ryo Kuroiwa (kuroiwa [at] nii.ac.jp)
