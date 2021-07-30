---
title: "202107291603 MAC arrays, a tool for DNNs, can be used to supplement the performance of SNNs with high-dimensional inputs, while maintaining system flexibility"
date: 20210729
aliases:
  - "202107291603"
tags:
  - "#permanent-note"
---

# Contexts

*Neuromorphic Computing* | *Computing Hardware* | *Deep Neural Networks* | *Spiking Neural Networks* | *Artificial Intelligence* | *Machine Learning*

---

# 202107291603 MAC arrays, a tool for DNNs, can be used to supplement the performance of SNNs with high-dimensional inputs, while maintaining system flexibility

Neuromorphic hardware platforms like Loihi have dedicated circuits for synapses and neurons to increase the efficiency of spiking neural network models implemented on them. However, this results in less flexible systems that cannot be used to implement more diverse models, that additionally do not have specialized tools to handle specific types of computations.

In contrast to this "hard-coded" platform design, at the core of SpiNNaker 2 are general purpose processors (ARM cores) that can handle a large variety of synapse and neuron models and learning rules, increasing the flexibility of the platform. SpiNNaker 2 supplements these general purpose processors with numerical accelerators and MAC arrays that efficiently handle more specific tasks: the former can be used to perform computations like exponential function and random number generation that are found often in neuromorphic models; the latter enables highly parallelized execution of multiply-accumulate operations for matrix operations that are found often in the operations of both SNNs and DNNs ([202107291348 Multiply-accumulate arrays efficiently perform matrix multiplications in DNNs](202107291348-Multiply-accumulate-arrays-efficiently-perform-matrix-multiplications-in-DNNs.md)).

While platforms with dedicated circuits like Loihi are faster than the more generalized SpiNNaker 2 for inputs with lower dimensions due to their more integrated processing for neuron updates, this performance difference is negated for high-dimensional inputs due to the parallelized input processing enabled by the MAC arrays in SpiNNaker 2 - many slightly slower computations done at the same time will be faster than many slightly faster computations done one by one. Beyond that, SpiNNaker still maintains the flexibility needed to run DNNs instead of SNNs where the task can be more effectively done by a DNN.

## Reference

[yanComparingLoihiSpiNNaker2021](../3.-Literature-Notes/yanComparingLoihiSpiNNaker2021.md)

## To-do

* [ ] Add contexts
* [ ] Link to other permanent notes
