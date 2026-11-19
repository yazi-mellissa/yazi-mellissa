# Lynda Mellissa Yazi

M2 student in Artificial Intelligence, Systems and Data (IASD) at Université Paris Dauphine-PSL.

I work on making machine-generated programs verifiable. A language model proposes a rewrite, a
compiler transformation or a search move far faster than a person can read one. That proposal is
worth nothing until something checks it. Most of what I build sits at that junction: a generative
component that explores, and a formal or empirical procedure that decides what survives.

## Research: LLM-driven compiler optimization

Author of a paper submitted to **PLDI 2027**, with Khaled Benmachiche, supervised by
Prof. Riyadh Baghdadi at NYU Abu Dhabi. The work extends
[CHEHAB](https://github.com/Modern-Compilers-Lab/CHEHAB-LLM), a compiler for fully homomorphic
encryption (BFV, Microsoft SEAL).

FHE computes on encrypted data. A wrong rewrite there does not produce a slow program, it produces
a wrong answer, and no test on ciphertext will tell you. The transformation has to be *proved*
sound. That constraint is what makes the problem interesting: the generator can be as creative as
you like, provided the gate behind it is exact.

**FHE-Evolve**, the main contribution. An island-model evolutionary search in which an LLM proposes
rewrites, selection is multi-objective over execution cost and multiplicative depth under an
adaptive controller, and a candidate enters the population only after an SMT equivalence proof.

**FHE-Agentic.** An agent drives the compiler through a typed MCP server, with no shell access, and
proposes unrestricted source-level rewrites. Each one passes a three-stage equivalence check that
ends in a Z3 proof.

**SFT-GRPO.** An earlier exploration: post-training a small policy by supervised fine-tuning, then
GRPO, against a reward designed so that optimizing the cost proxy cannot be mistaken for optimizing
the real objective. Not part of the submitted paper.

*Code and results stay closed until the review process allows their release.*

## Engineering

**[SkillGPT](https://github.com/yazi-mellissa/SkillGPT)**, built during professional work. A
FastAPI service that extracts skills from free text through three interchangeable backends: vector
search over Milvus/Zilliz, OpenAI, and Google Gemini, with response caching. Dockerised, with a
layered `api` / `services` / `core` structure and configuration kept entirely in the environment.

## Projects

| Repository | What it is |
|---|---|
| [3d-heat-diffusion](https://github.com/yazi-mellissa/3d-heat-diffusion) | A 3D heat diffusion solver (7-point Jacobi stencil, Dirichlet boundaries) written six times over: serial C, Pthreads, OpenMP, MPI, MPI+OpenMP hybrid, and CUDA in a naive and an optimized version. With a scaling study across all six. |
| [gan-precision-recall](https://github.com/yazi-mellissa/gan-precision-recall) | Where a capacity-constrained GAN loses fidelity, where it loses mode coverage, and which intervention fixes which. 235 configurations evaluated under a frozen architecture. |
| [collaborative-filtering-bfm](https://github.com/yazi-mellissa/collaborative-filtering-bfm) | Six method families compared under a protocol fixed before the first experiment. The final model is a Bayesian factorization machine with side information. |
| [Intelligent_Irrigation_System](https://github.com/yazi-mellissa/Intelligent_Irrigation_System) | A DQN irrigation policy with an economic reward, trained against DSSAT crop simulations, with LSTM forecasters of soil moisture and yield (Algerian Sahara). |
| [graph-coloring-hyperheuristics](https://github.com/yazi-mellissa/graph-coloring-hyperheuristics) | Learned GNN vertex orderings against a genetic algorithm evolving heuristics, on DIMACS instances. |
| [Breast_Cancer_Data_Analysis](https://github.com/yazi-mellissa/Breast_Cancer_Data_Analysis) | A clinical-data study on 4,026 breast cancer patients: PCA and MCA, patient clustering by survival risk, and which variables actually predict mortality. |
| [open5gs-k8s](https://github.com/yazi-mellissa/open5gs-k8s) | A private 5G core on Kubernetes, with UPF placement for low-latency services. |

## Background

Computer Science engineering degree from ESI Algiers (École nationale Supérieure d'Informatique),
with the engineering thesis carried out at NYU Abu Dhabi.

## Tools

**HPC and clusters.** Slurm (`sbatch`, array jobs, `sacct`, resuming from checkpoints), multi-GPU
A100 nodes, CUDA, MPI, OpenMP, Pthreads, CMake, C and C++. Long jobs run on the MesoNET cluster.

**Training and post-training.** PyTorch, TRL, Unsloth, PEFT and LoRA, bitsandbytes 4-bit, vLLM,
Accelerate, Ray, Weights & Biases.

**Search and tuning.** Optuna for hyperparameter studies; genetic algorithms, simulated annealing,
tabu search and hyper-heuristics; MAP-Elites style quality-diversity search.

**Formal methods and compilers.** Z3 and SMT-based equivalence checking, e-graphs and equality
saturation, Microsoft SEAL (BFV), MCP tool servers.

**Systems.** FastAPI, Docker and Docker Compose, Kubernetes and Helm, Milvus/Zilliz, Redis,
Elasticsearch, MongoDB.

**Also.** Python, Jupyter, LaTeX, Qiskit.

## Contact

lynda.yazi@dauphine.eu
