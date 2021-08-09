---
type: article
title: "Loihi: A Neuromorphic Manycore Processor with On-Chip Learning"
authors:
  - "Davies, Mike"
  - "Srinivasa, Narayan"
  - "Lin, Tsung-Han"
  - "Chinya, Gautham"
  - "Joshi, Prasad"
  - "Lines, Andrew"
  - "Wild, Andreas"
  - "Wang, Hong"
  - "Mathaikutty, Deepak"
year: 2018
container: IEEE Micro
DOI: 10.1109/MM.2018.112130359
citekey: daviesLoihiNeuromorphicManycore2018
aliases:
  - "Loihi: A Neuromorphic Manycore Processor with On-Chip Learning"
tags:
  - "#literature-note"
---

# Contexts

*Spiking Neural Networks* | *Neuromorphic Computing* | *Artificial Intelligence* | *Machine Learning* | *Computing Hardware* | *Computing Methodologies*

---

# [Loihi: A Neuromorphic Manycore Processor with On-Chip Learning](zotero://select/items/@daviesLoihiNeuromorphicManycore2018)

Loihi is a 60 mm2 chip fabricated in Intels 14nm process that advances the state-of-the-art modeling of spiking neural networks in silicon. It integrates a wide range of novel features for the field, such as hierarchical connectivity, dendritic compartments, synaptic delays, and most importantly programmable synaptic learning rules. Running a spiking convolutional form of the Locally Competitive Algorithm, Loihi can solve LASSO optimization problems with over three orders of magnitude superior energy-delay-product compared to conventional solvers running on a CPU iso-process/voltage/area. This provides an unambiguous example of spike-based computation outperforming all known conventional solutions.

## Authors

*Davies, Mike*, *Srinivasa, Narayan*, *Lin, Tsung-Han*, *Chinya, Gautham*, *Joshi, Prasad*, *Lines, Andrew*, *Wild, Andreas*, *Wang, Hong*, *Mathaikutty, Deepak*

## Notes

### SNNs will need different computing architectures from DNNs

 > 
 > "Artificial neural networks (ANNs) are reasonably well served by today's von Neumann CPU architectures and GPU variants, especially when assisted by coprocessors optimized for streaming matrix arithmetic. Spiking neural network models, on the other hand, are exceedingly poorly served by conventional architectures. Just as the value of ANNs was not fully appreciated until the advent of sufficiently fast CPUs and GPUs, the same could be the case for spiking models—except different computing architectures will be required." ([Davies et al 2018:2](zotero://open-pdf/library/items/N2JH3C2X?page=2))

### [202108041944 SNNs utilize spatiotemporal data, unlike DNNs](1Permanent/202108041944-SNNs-utilize-spatiotemporal-data-unlike-DNNs.md)

 > 
 > "Different from artificial neural networks, SNNs incorporate time as an explicit dependency in their computations. At some instant in time, one or more neurons may send out single-bit impulses, the spike, to neighbors through directed connections known as synapses, with a potentially nonzero traveling time. Neurons have local state variables with rules governing their evolution and timing of spike generation. Hence the network is a dynamical system where individual neurons interact through spikes." ([Davies et al 2018:2](zotero://open-pdf/library/items/N2JH3C2X?page=2))

### Loihi approximates the continuous time dynamics of spiking neurons through discrete timesteps

 > 
 > "A spiking neuron integrates its spike train input in some fashion, usually by low pass filter, and fires once a state variable exceeds a threshold." ([Davies et al 2018:3](zotero://open-pdf/library/items/N2JH3C2X?page=3))

 > 
 > "We adopt a variation of the well-known CUBA leakyintegrate-and-fire model" ([Davies et al 2018:3](zotero://open-pdf/library/items/N2JH3C2X?page=3))

 > 
 > "Loihi, a fully digital architecture, approximates the above continuous time dynamics using a fixed-size discrete timestep model. In this model, all neurons need to maintain a consistent understanding of time so their distributed dynamics can evolve in a well-defined, synchronized manner. It is worth clarifying that these fixed-size, synchronized time steps relate to the algorithmic time of the computation, and need not have a direct relationship to the hardware execution time." ([Davies et al 2018:3](zotero://open-pdf/library/items/N2JH3C2X?page=3))

### [202108092218 SNNs use less arithmetic operations for certain sparse coding optimization problems](1Permanent/202108092218-SNNs-use-less-arithmetic-operations-for-certain-sparse-coding-optimization-problems.md)

 > 
 > "Computations in SNNs are carried out through the interacting dynamics of neuron states. An instructive example is the ℓ1-minimizing sparse coding problem, also known as LASSO, which we can solve with the SNN in Figure 1a using the Spiking Locally Competitive Algorithm \[2\]. The objective of this problem is to determine a sparse set of coefficients that best represents a given input as the linear combination of features from a feature dictionary. The coefficients can be viewed as the activities of the spiking neurons in Figure 1a that are competing to form an accurate representation of the data. By properly configuring the network, it can be established that as the network dynamics evolve, the average spike rates of the neurons will converge to a fixed point, and this fixed point is identical to the solution of the optimization problem. Such computation exhibits completely different characteristics from conventional linear algebra based approaches." ([Davies et al 2018:3](zotero://open-pdf/library/items/N2JH3C2X?page=3))

 > 
 > "The SNN approach (labelled S-LCA) gives a rapid initial drop in error and obtains a good approximate solution faster than FISTA. After this, the S-LCA convergence speed significantly slows down, and FISTA instead finds a much more precise solution quicker." ([Davies et al 2018:3](zotero://open-pdf/library/items/N2JH3C2X?page=3))

 > 
 > "The remarkable algorithmic efficiency of S-LCA can be attributed to its ability to exploit the temporal ordering of spikes, a general property of the SNN computational model. In Figure 1a, the neuron that has the largest external input to win the competition is more likely to spike at the earliest time, causing immediate inhibition of the other neurons. This inhibition happens with only a single one-to-many spike communication, in contrast to the usual need for all-to-all state exchanges with matrix arithmetic based solutions such as FISTA and other conventional solvers." ([Davies et al 2018:3](zotero://open-pdf/library/items/N2JH3C2X?page=3))

### Current implementations of SNNs do not fully utilize the inherent parallelism of neuron updates

### 

## Notable References

## To-do

* [x] Add contexts
* [ ] Add notes
* [ ] Convert notes
