---
title: 202108092218 SNNs use less arithmetic operations for certain sparse coding optimization problems
date: 20210809
aliases:
  - "202108092218"
  - 202108092218 SNNs use less arithmetic operations for certain sparse coding optimization problems
tags:
  - "#permanent-note"
---

# Contexts

*Neuromorphic Computing* | *Spiking Neural Networks* | *Statistics* | *Machine Learning* | *Regression Analysis* | *Representation Learning* | *Optimization* | *Unsupervised Learning*

---

# 202108092218 SNNs use less arithmetic operations for certain sparse coding optimization problems

## <!-- - -->

Sparse coding refers to unsupervised methods of learning how to represent data efficiently using a linear combination of a relatively small number of elements from a feature dictionary. One such method is the Least Absolute Shrinkage and Selection Operator (LASSO), which finds an estimate of the representation by minimizing the least square error subject to a ℓ1-norm constraint in the solution vector. SNNs solve this ℓ1-minimizing sparse coding problem differently from traditional matrix arithmetic-based solutions, using the interacting dynamics of neuron states in the network to converge the neurons' average spike rates to a fixed point that is the solution of the optimization problem.

As [computations in SNNs utilize the temporal ordering of spikes](202108041944-SNNs-utilize-spatiotemporal-data-unlike-DNNs.md), this means that in SNNs applied to LASSO, the neuron with the largest external input is more likely to spike earlier, immediately inhibiting the activities of the other neurons through a single one-to-many interaction. This is unlike traditional matrix arithmetic-based solvers that require all-to-all state exchanges, resulting in far faster convergence speed due to the lower number of arithmetic operations needed to estimate a close representation. However, FISTA, a conventional solver, still finds a much more precise solution quicker, after the SNN approach slows in convergence speed.

## References

[2Literature/daviesLoihiNeuromorphicManycore2018 > 1 Permanent Notes 202108092218 SNNs use less arithmetic operations for certain sparse coding optimization problems 202108092218 SNNs use less arithmetic operations for certain sparse coding optimization problems](2Literature/daviesLoihiNeuromorphicManycore2018.md#1-permanent-notes-202108092218-snns-use-less-arithmetic-operations-for-certain-sparse-coding-optimization-problems-202108092218-snns-use-less-arithmetic-operations-for-certain-sparse-coding-optimization-problems)

## To-do

* [x] Add contexts
* [x] Link to other permanent notes
* [ ] Link to notes about Sparse Coding, LASSO, ℓ1-norm Regularization, FISTA
