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

## Solvers for DIDP

Currently, [our generic DIDP solvers](https://crates.io/crates/dypdl-heuristic-search) are based on heuristic search such as A* and beam search, inspired by AI planning.

## Papers

- Ryo Kuroiwa and J. Christopher Beck. [Domain-Independent Dynamic Programming: Generic State Space Search for Combinatorial Optimization.](https://tidel.mie.utoronto.ca/pubs/Domain%20Independent%20Dynamic%20Programming%20Generic%20State%20Space%20Search%20for%20Combinatorial%20Optimization.pdf) In Proceedings of the 33rd International Conference on Automated Planning and Scheduling (ICAPS). 2023.
  - This paper introduces the notion of DIDP with the modeling language DyPDL and the generic solver CAASDy with the experimental evaluation using 6 combinatorial optimization problems.
- Ryo Kuroiwa and J. Christopher Beck. [Solving domain-independent dynamic programming problems with anytime heuristic search.](https://tidel.mie.utoronto.ca/pubs/Solving%20Domain%20Independent%20Dynamic%20Programming%20Problems%20with%20Anytime%20Heuristic%20Search.pdf) In Proceedings of the 33rd International Conference on Automated Planning and Scheduling (ICAPS). 2023.
  - This paper proposes 6 anytime solvers for DIDP with the experimental evaluation using 9 combinatorial optimization problems.

## Contact Information

Ryo Kuroiwa (ryo.kuroiwa [at] mail.utoronto.ca)
