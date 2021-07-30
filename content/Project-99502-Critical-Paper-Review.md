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

[yanComparingLoihiSpiNNaker2021](yanComparingLoihiSpiNNaker2021.md)

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


