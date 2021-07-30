---
title: 202107291348 Multiply-accumulate arrays efficiently perform matrix multiplications in DNNs
date: 20210729
aliases:
  - "202107291348"
tags:
  - "#permanent-note"
---

# Contexts

*Deep Neural Networks* | *Computing Hardware* | *Artificial Intelligence* | *Machine Learning*

---

# 202107291348 Multiply-accumulate arrays efficiently perform matrix multiplications in DNNs

Every connection between neurons in a deep neural network is assigned a weight. Inputs to the deep neural network are multiplied by these weights. Thus, in the forward pass of a deep neural network, much of the computation done consists of vector matrix multiplications. In computing, these calculations are achieved through the accumulation of products, via multiply-accumulate operations.

Multiply accumulate operations are more efficient on the MAC arrays than general purpose processors because of their ability to perform the multiply accumulate operations in parallel. General purpose processors with complex instruction set computing need to fetch both operands into the registers, perform the multiply-accumulate, write the result back, check the condition of the loop, and then compute the addresses of the data in the next iteration.

MAC arrays, on the other hand, enable Single Instruction Multiple Data (SIMD) operation: in each clock cycle, multiple values from both operands are fed into the array, with all MAC units in the same row receiving the same value from one operand and all MAC units in the same column receiving the same value from the other operand. This allows for many MAC operations to be done in parallel - one for each MAC unit. When paired with a general-purpose processor, the latter can control logic of data arranging and data transfer to the MAC array in parallel to the MAC operations. This parallelization greatly increases the efficiency of multiply-accumulate operations, and thus greatly reduces the time needed to perform a forward pass in a DNN.

## Reference

[yanComparingLoihiSpiNNaker2021](../3.-Literature-Notes/yanComparingLoihiSpiNNaker2021.md)

## To-do

* [x] Add contexts
* [ ] Link to other permanent notes
