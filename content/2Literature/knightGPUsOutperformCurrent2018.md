---
type: article
title: GPUs Outperform Current HPC and Neuromorphic Solutions in Terms of Speed and Energy When Simulating a Highly-Connected Cortical Model
authors:
  - "Knight, James C."
  - "Nowotny, Thomas"
year: 2018
container: Frontiers in Neuroscience
external_URL: "https://www.frontiersin.org/articles/10.3389/fnins.2018.00941/full"
DOI: 10.3389/fnins.2018.00941
citekey: knightGPUsOutperformCurrent2018
aliases:
  - GPUs Outperform Current HPC and Neuromorphic Solutions in Terms of Speed and Energy When Simulating a Highly-Connected Cortical Model
  - knightGPUsOutperformCurrent2018
tags:
  - "#literature-note"
---

# Contexts

\[\[\]\]

---

# [GPUs Outperform Current HPC and Neuromorphic Solutions in Terms of Speed and Energy When Simulating a Highly-Connected Cortical Model](zotero://select/items/@knightGPUsOutperformCurrent2018)

While neuromorphic systems may be the ultimate platform for deploying spiking neural networks (SNNs), their distributed nature and optimisation for specific types of models makes them unwieldy tools for developing them. Instead, SNN models tend to be developed and simulated on computers or clusters of computers with standard Von Neumann CPU architectures. Over the last decade, as well as becoming a common fixture in many workstations, NVIDIA GPU accelerators have entered the High Performance Computing field and are now used in 50 of the Top 10 super computing sites worldwide. In this paper we use our GeNN code generator to re-implement two neo-cortex-inspired, circuit-scale, point neuron network models on GPU hardware. We verify the correctness of our GPU simulations against prior results obtained with NEST running on traditional HPC hardware and compare the performance with respect to speed and energy consumption against published data from CPU-based HPC and neuromorphic hardware. A full-scale model of a cortical column can be simulated at speeds approaching real-time using a single NVIDIA Tesla V100 accelerator - faster than is currently possible using a CPU based cluster or the SpiNNaker neuromorphic system. In addition, we find that, across a range of GPU systems, the energy to solution as well as the energy per synaptic event of the microcircuit simulation is as much as lower than either on SpiNNaker or in CPU-based simulations. Besides performance in terms of speed and energy consumption of the simulation, efficient initialisation of models is also a crucial concern, particularly in a research context where repeated runs and parameter-space exploration are required. Therefore, we also introduce in this paper some of the novel parallel initialisation methods implemented in the latest version of GeNN and demonstrate how they can enable further speed and energy advantages.

## Authors

*Knight, James C.*, *Nowotny, Thomas*

## Notes

## Notable References

## To-do

* [ ] Add contexts
* [ ] Add notes
* [ ] Convert notes
