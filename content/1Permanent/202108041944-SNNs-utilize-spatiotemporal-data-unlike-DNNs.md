---
title: "202108041944 SNNs utilize spatiotemporal data, unlike DNNs"
date: 20210804
aliases:
  - "202108041944"
  - "202108041944 SNNs utilize spatiotemporal data, unlike DNNs"
tags:
  - "#permanent-note"
---

# Contexts

*Neuromorphic Computing* | *Spiking Neural Networks* | *Artificial Intelligence* | *Machine Learning*

---

# 202108041944 SNNs utilize spatiotemporal data, unlike DNNs

## <!-- - -->

SNNs incorporate the concept of time and space in their operating model. Unlike DNNs, where every neuron sends a continuous output at every time cycle to every neuron in the next layer, neurons in SNNs only transmit single-bit impulses (or spikes) to neighbors through directed connections known as synapses, when a membrane potential reaches a certain threshold. Each neuron in an SNN has local state variables that govern its evolution and timing of spike generation.

This output approach means that SNNs utilize:

* spatial information by having neurons connect only to nearby neurons so that input blocks are processed separately;
* temporal information because not all neurons are activated at every time step, allowing spike timing to add time information.

## References

[2Literature/daviesLoihiNeuromorphicManycore2018 > 1 Permanent Notes 202108041944 SNNs utilize spatiotemporal data unlike DNNs 202108041944 SNNs utilize spatiotemporal data unlike DNNs](2Literature/daviesLoihiNeuromorphicManycore2018.md#1-permanent-notes-202108041944-snns-utilize-spatiotemporal-data-unlike-dnns-202108041944-snns-utilize-spatiotemporal-data-unlike-dnns)

## To-do

* [x] Add contexts
* [ ] Link to other permanent notes
