---
title: Project - 99502 Critical Paper Review
tags:
  - "#project-note"
---

# Contexts

*Neuromorphic Computing* | *Speech Processing* | *Robotic Control* | *Deep Neural Networks* | *Spiking Neural Networks* | *Artificial Intelligence* | *Machine Learning*

---

# Project - 99502 Critical Paper Review

Here the main purpose of this assignment is for you to demonstrate an ability to read, with a critical eye, the current technical literature in brain-inspired computing. You will choose a paper from recent journals (“Stochastic phase-change neurons” or “Comparing Loihi with a SpiNNaker 2 Prototype on Low-Latency Keyword Spotting and Adaptive Robotic Control”) that makes use of statistical analysis or modeling methods.

You will summarize the goals and statistics/analytical methods used in the paper you are reviewing. You should also analyze the effectiveness of these methods and make suggestions as to improvements or next steps in these methods or research that might be appropriate.

An important part of the review is to convince your audience of the valuable ideas or aspects of the paper you are reviewing, as well as to provide any insight you develop into the limitations or extension of these methods. You should also assess the overall success of the paper in achieving what you see as the authors’ intent.

Guidelines of paper review content:
a) Introduction (providing context and a framework for critique)
b) Body (consisting of your description and analysis of the methods)
c) Summary/conclusion (underscoring the main idea your review)

## To-do

* [x] What is this project about?
* [x] Add contexts
* [ ] Fill up the To-do

## References

### Permanent Notes

* [202107291348 Multiply-accumulate arrays efficiently perform matrix multiplications in DNNs](202107291348-Multiply-accumulate-arrays-efficiently-perform-matrix-multiplications-in-DNNs.md)
* [202107291603 MAC arrays, a tool for DNNs, can be used to supplement the performance of SNNs with high-dimensional inputs, while maintaining system flexibility](202107291603-MAC-arrays-a-tool-for-DNNs-can-be-used-to-supplement-the-performance-of-SNNs-with-high-dimensional-inputs-while-maintaining-system-flexibility.md)

### Literature Notes

* [yanComparingLoihiSpiNNaker2021](yanComparingLoihiSpiNNaker2021.md)

## Quick Notes

quick notes on the spinnaker 2 paper:

* are you convinced with the paper's claim that their comparison of the spiNNaker and loihi chips meaningfully add to an understanding of how best the chips work?
* they claim a need to perform a "direct comparison of both ... platforms with the same benchmarks", so question is
  * a. what's the lit review on this? is it really missing?
  * b. is their example really a decent comparison?
* for keyword spotting, spiNNaker used normal DNN with relu, but loihi used only SNN. is there a reason not to use SNN for both? if it's not possible to use the same implementation for both, then how meaningfully can we draw conclusions on the results?
* did they not actually perform an implementation of the loihi for this paper? are they just doing spinnaker only and comparing it to the loihi results from other papers?
* if yes, something to assess is:
  * since this is pretty much a combi of a review+experimental paper, it may potentially be limited in its reliance on the assumed reproducibility of the loihi implementation results from other papers
  * while the paper tries to infer the reason for difference in performance in each of the sections, these inferences are ultimately educated guesses, and do not substantially explore or attempt to truly validate them. (mostly ref pg5 content)
    * i.e. while the paper tries to give us quantitative data on the chip performance comparisons, it doesn't substantively tell us the reason for the differences, and this could be a further piece of research for another paper
* what value is created, from filling this specific gap in the literature? 
  * is it only to tell us that spinnaker is better than loihi? 
  * does it tell us which contexts spinnaker should be used in? (they seem to suggest that spinnaker is better in xxx contexts and not that great in yyy contexts, but would that be enough to conclude that spinnaker should be preferred ahead of other alternatives?)
* why in particular choose loihi to be the comparison?

## Outline

## -

Every connection between neurons in a deep neural network is assigned a weight. Inputs to the deep neural network are multiplied by these weights. Thus, in the forward pass of a deep neural network, much of the computation done consists of vector matrix multiplications. In computing, these calculations are achieved through the accumulation of products, via multiply-accumulate operations.

Multiply accumulate operations are more efficient on the MAC arrays than general purpose processors because of their ability to perform the multiply accumulate operations in parallel. General purpose processors with complex instruction set computing need to fetch both operands into the registers, perform the multiply-accumulate, write the result back, check the condition of the loop, and then compute the addresses of the data in the next iteration.

MAC arrays, on the other hand, enable Single Instruction Multiple Data (SIMD) operation: in each clock cycle, multiple values from both operands are fed into the array, with all MAC units in the same row receiving the same value from one operand and all MAC units in the same column receiving the same value from the other operand. This allows for many MAC operations to be done in parallel - one for each MAC unit. When paired with a general-purpose processor, the latter can control logic of data arranging and data transfer to the MAC array in parallel to the MAC operations. This parallelization greatly increases the efficiency of multiply-accumulate operations, and thus greatly reduces the time needed to perform a forward pass in a DNN.

## -

Neuromorphic hardware platforms like Loihi have dedicated circuits for synapses and neurons to increase the efficiency of spiking neural network models implemented on them. However, this results in less flexible systems that cannot be used to implement more diverse models, that additionally do not have specialized tools to handle specific types of computations.

In contrast to this "hard-coded" platform design, at the core of SpiNNaker 2 are general purpose processors (ARM cores) that can handle a large variety of synapse and neuron models and learning rules, increasing the flexibility of the platform. SpiNNaker 2 supplements these general purpose processors with numerical accelerators and MAC arrays that efficiently handle more specific tasks: the former can be used to perform computations like exponential function and random number generation that are found often in neuromorphic models; the latter enables highly parallelized execution of multiply-accumulate operations for matrix operations that are found often in the operations of both SNNs and DNNs ([202107291348 Multiply-accumulate arrays efficiently perform matrix multiplications in DNNs](202107291348-Multiply-accumulate-arrays-efficiently-perform-matrix-multiplications-in-DNNs.md)).

While platforms with dedicated circuits like Loihi are faster than the more generalized SpiNNaker 2 for inputs with lower dimensions due to their more integrated processing for neuron updates, this performance difference is negated for high-dimensional inputs due to the parallelized input processing enabled by the MAC arrays in SpiNNaker 2 - many slightly slower computations done at the same time will be faster than many slightly faster computations done one by one. Beyond that, SpiNNaker still maintains the flexibility needed to run DNNs instead of SNNs where the task can be more effectively done by a DNN.
