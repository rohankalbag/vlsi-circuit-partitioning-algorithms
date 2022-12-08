# Implementation and Analysis of Various Circuit Partitioning Algorithms

## Course Project - EE 677 - Foundations of VLSI CAD
### Instructor - Prof. Virendra Singh

## Contributors
- Rohan Rajesh Kalbag
- Anubhav Bhatla

## *Abstract: Often the VLSI design schematic of a system cannot be emulated/verified on a single FPGA, due to the finite number of programmable logic elements present in the FPGA. A interconnections between circuit elements can be conveniently represented using graphs, Logic gates, LUTs, FFs and other entities present in the design can be modelled as graph nodes and the interconnections are modelled as edges, if there are multiple parallel interconnects between two entities, we can represent the same using weighted graphs. Suppose we wish to computerize dividing the design among 2 FPGAs using CAD, we can model the problem as a graph partitioning problem.*

## Some more Ideas
Suppose we partition the graph into sets $P_1$ and $P_2$, the sum of weights of interconnections between the two partitions is called **cut size**

Thus splitting the components among two FPGAs so as to minimize the cost of interconnects (which can be represented by the quantity **cut size**) denoted by $C_1$ which should be minimized and also the equitable balancing of components on both FPGAS (if components are equitably balanced among both the FPGAs, we can represent this quantity by $C_2 = N(P_1) * N(P_2)$ where $N(.)$ represents the cardinality (number of nodes) of the partition) which should be maximized.

Thus, one can use the simple metric **ratio cut** $C_1/C_2$ to ascertain and compare the quality of partitioning performed by various computer aided design partitioning algorithms. Typically a smaller value of **ratio cut** denotes a better partition.

A much better cost function can be modelled using co-optimization as well to get the minimization problem $min(\alpha C_1 + (1-\alpha)/C_2)$ where $0 < \alpha < 1$ is a co-optimization metric.

## Goals of Project

We try to implement graph partitioning algorithms and heuristics like the **Kernighan-Lin Algorithm**, **Clustering Based Heuristic**, **Hagen Kahng EIG Algorithm** and compare their analyse their capability in partitioning a given graph network into two partitions using `Python 3.x`.

## For Setting up Python

> Create a virtual environment (only the first time **if the folder `./ee677` is absent**) using `python3 -m venv ee677`

> To setup the virtual environment open a terminal in the directory and do the following command `source ee677/bin/activate` to activate it.

> Then setup pip in the following way `pip install -r requirements.txt`.
