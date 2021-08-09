---
type: article
title: Comparing Loihi with a SpiNNaker 2 Prototype on Low-Latency Keyword Spotting and Adaptive Robotic Control
authors:
  - "Yan, Yexin"
  - "Stewart, Terrence"
  - "Choo, Xuan"
  - "Vogginger, Bernhard"
  - "Partzsch, Johannes"
  - "Hoeppner, Sebastian"
  - "Kelber, Florian"
  - "Eliasmith, Chris"
  - "Furber, Steve"
  - "Mayr, Christian"
year: 2021
container: Neuromorphic Computing and Engineering
external_URL: "https://iopscience.iop.org/article/10.1088/2634-4386/abf150"
DOI: 10.1088/2634-4386/abf150
citekey: yanComparingLoihiSpiNNaker2021
aliases:
  - Comparing Loihi with a SpiNNaker 2 Prototype on Low-Latency Keyword Spotting and Adaptive Robotic Control
tags:
  - "#literature-note"
---

# Contexts

*Neuromorphic Computing* | *Speech Processing* | *Robotic Control* | *Deep Neural Networks* | *Spiking Neural Networks* | *Artificial Intelligence* | *Machine Learning* | *Computing Hardware*

---

# [Comparing Loihi with a SpiNNaker 2 Prototype on Low-Latency Keyword Spotting and Adaptive Robotic Control](zotero://select/items/@yanComparingLoihiSpiNNaker2021)

We implemented two neural network based benchmark tasks on a prototype chip of the second-generation SpiNNaker (SpiNNaker 2) neuromorphic system: keyword spotting and adaptive robotic control. Keyword spotting is commonly used in smart speakers to listen for wake words, and adaptive control is used in robotic applications to adapt to unknown dynamics in an online fashion. We highlight the benefit of a multiply accumulate (MAC) array in the SpiNNaker 2 prototype which is ordinarily used in rate-based machine learning networks when employed in a neuromorphic, spiking context. In addition, the same benchmark tasks have been implemented on the Loihi neuromorphic chip, giving a side-by-side comparison regarding power consumption and computation time. While Loihi shows better efficiency when less complicated vector-matrix multiplication is involved, with the MAC array, the SpiNNaker 2 prototype shows better efficiency when high dimensional vector-matrix multiplication is involved.

## Authors

*Yan, Yexin*, *Stewart, Terrence*, *Choo, Xuan*, *Vogginger, Bernhard*, *Partzsch, Johannes*, *Hoeppner, Sebastian*, *Kelber, Florian*, *Eliasmith, Chris*, *Furber, Steve*, *Mayr, Christian*

## Notes

### Questions

* Is Loihi the industry standard for SNN architectures? Are there better things to compare SpiNNaker 2 to?
* Why do SNNs use more computation time and energy consumption than DNNs regarding keyword spotting? The main comparison explained was between SpiNNaker 2 with MAC array vs SpiNNaker 2 with no MAC array, which is self-evident.
* It is not very clearly established that the main purpose of the benchmarks chosen to compare Loihi and SpiNNaker 2 is to showcase the flexibility of the SpiNNaker 2 architecture compared to Loihi. In keyword spotting, they are trying to show that there are certain use cases where DNNs will always beat out current implementations of SNNs, while in adaptive control, they are trying to show that in use cases where SNNs are useful, inspiration from DNNs (i.e. the MAC arrays) can be used to improve the performance of the SNN design.
* The paper explicitly claims to establish new benchmarks by which architectures can be compared, but does not actually 
* Did they re-implement the Loihi benchmark for keyword spotting, or did the authors just reference the results of P. Blouw et al., “Benchmarking keyword spotting efficiency on neuromorphic hardware”? Either way, not made clear.
* 

### [202107291348 Multiply-accumulate arrays efficiently perform matrix multiplications in DNNs](1Permanent/202107291348-Multiply-accumulate-arrays-efficiently-perform-matrix-multiplications-in-DNNs.md)

 > 
 > "A substantial amount of computation in DNNs is caused by the multiply-accumulate (MAC) operations" ([Yan et al 2021:2](zotero://open-pdf/library/items/S4TD4XET?page=2))

 > 
 > "Arm core needs to: 1. fetch the operand A and operand B into the registers, 2. do the multiply-accumulate, 3. write the result back, 4. check the condition of the loop, 5. compute the addresses of the data in the next iteration." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

 > 
 > "1. 64 MAC operations can be done in one clock cycle in parallel. 2. 16 x 8 bits of data of operand A and 4 x 8 bits of data of operand B can be fetched in one clock cycle in parallel 3. control logic and data transfer in parallel to MAC operations, hiding the overhead of data transfer for the next iteration." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

 > 
 > "While the MAC array essentially does the same, it is more efficient due to the Single Instruction Multiple Data (SIMD) operation." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

### [202107291603 MAC arrays, a tool for DNNs, can be used to supplement the performance of SNNs with high-dimensional inputs, while maintaining system flexibility](1Permanent/202107291603-MAC-arrays-a-tool-for-DNNs-can-be-used-to-supplement-the-performance-of-SNNs-with-high-dimensional-inputs-while-maintaining-system-flexibility.md)

 > 
 > "While Loihi has dedicated circuits for synapses and neurons, which increases the efficiency for the implemented models, and a programmable learning engine for more flexibility for various learning rules, SpiNNaker 2 uses general purpose processors (Arm cores) connected with numerical accelerators. While the processor increases the flexibility of the synapse and neuron models and learning rules, the accelerators increase the efficiency for certain computations like exponential function and random number generation which are often required in neuromorphic applications. Besides the neuromorphic accelerators, SpiNNaker2 also contains MAC arrays for efficient matrix operations and is thus able to merge SNN and DNN operation." ([Yan et al 2021:2](zotero://open-pdf/library/items/S4TD4XET?page=2))

 > 
 > "However, a direct comparison of both neuromorphic hardware platforms with the same benchmarks has been missing." ([Yan et al 2021:2](zotero://open-pdf/library/items/S4TD4XET?page=2))

 > 
 > "he main benefit of MAC array is reflected in the reduction of 7:07N Din in Eq. (14) to 0:13N Din in Eq. (13), which is made possible by the SIMD operation of the MAC array." ([Yan et al 2021:7](zotero://open-pdf/library/items/S4TD4XET?page=7))

 > 
 > "From the comparison it is clear that for small number of input dimensions, Loihi is faster than the SpiNNaker 2 prototype, and for large number of input dimensions, the SpiNNaker 2 prototype is faster than Loihi." ([Yan et al 2021:8](zotero://open-pdf/library/items/S4TD4XET?page=8))

 > 
 > "Because of the MAC array, the computation time of the SpiNNaker 2 prototype increases less rapidly with the number of input dimensions, so that the SpiNNaker 2 prototype could catch up with Loihi in terms of computation time for higher input dimensions." ([Yan et al 2021:8](zotero://open-pdf/library/items/S4TD4XET?page=8))

 > 
 > "For small number of input dimensions, Loihi is more energy efficient than the SpiNNaker 2 prototype, and for large number of input dimensions, the SpiNNaker 2 prototype is more energy" ([Yan et al 2021:8](zotero://open-pdf/library/items/S4TD4XET?page=8))

 > 
 > "Similar to the computation time comparison, we see the benefit of MAC array especially for high input dimensions, when the MAC array is more extensively used" ([Yan et al 2021:9](zotero://open-pdf/library/items/S4TD4XET?page=9))

 > 
 > "Here, it is clear how the input processing energy increases with the input dimensions for the same number of neurons and output dimensions, how the neuron update energy increases with the number of neurons for the same input dimensions and output dimensions, and how the output processing and weight update energy increases with the number of output dimensions for the same input dimensions and number of neurons." ([Yan et al 2021:9](zotero://open-pdf/library/items/S4TD4XET?page=9))

 > 
 > "highlight the benefit of the MAC array in neuromorphic applications" ([Yan et al 2021:11](zotero://open-pdf/library/items/S4TD4XET?page=11))

 > 
 > "By trying to mix DNN and SNN on the algorithm and hardware levels, we attempt to increase exchange between different disciplines and contribute to different communities" ([Yan et al 2021:11](zotero://open-pdf/library/items/S4TD4XET?page=11))

### Keyword spotting is more efficiently done on a DNN rather than an SNN

Keyword spotting is more efficiently done on a DNN rather than an SNN

When trying to identify specific keywords in speech, 2 types of computations are needed: vector matrix multiplication for the 

 > 
 > "Keyword spotting is a speech processing problem which deals with identifying keywords in utterances." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

 > 
 > "no training is involved and only inference is considered." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

 > 
 > "The difference to the implementation on Loihi is that on the SpiNNaker 2 prototype, we implement the network with normal DNN with ReLU activations, whereas on Loihi, the SNN version was implemented since Loihi only supports SNNs." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

 > 
 > "The keyword spotting network consists of 2 computational steps: vector-matrix multiplication which is done with the MAC array and ReLU update which is done with the Arm core." ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))

 > 
 > "We compare the computation time and active energy consumption of the benchmark tasks with Loihi, and highlight the benefit of the MAC array. Specifically, for keyword spotting, because the original DNN version is implemented on the SpiNNaker 2 prototype with the MAC array, and the SNN version is implemented on Loihi because it only supports SNN, the SpiNNaker 2 prototype shows better efficiency regarding computation time and energy consumption." ([Yan et al 2021:2](zotero://open-pdf/library/items/S4TD4XET?page=2))

### Adaptive robotic control TODO

Why was a DNN version of the adaptive robotic control model not implemented on SpiNNaker?

 > 
 > "This benchmark consists of a single-hidden-layer neural network, where the input is the sensory state of the system to be controlled (such as a robot arm) and the output is the extra force that should be applied to compensate for the intrinsic dynamics and forces on the arm (gravity, friction, etc.)" ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

 > 
 > "There are mainly 4 computational steps: input processing, neuron update, output processing and weight update." ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))

 > 
 > "The vector-matrix multiplication with only Arm core and without MAC array is also implemented and serves as reference." ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))

 > 
 > "In neuron update, the neuron dynamics is updated according to the input current. The Leaky-Integrate-and-Fire (LIF) neuron model is used in the hidden layer to allow for event based processing of the spikes in the following steps" ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))

 > 
 > "In output processing, the outputs of the neurons are multiplied with the output weight matrix. In the case of nonspiking neuron models like ReLU, this process is a vectormatrix multiplication. In the case of spiking neuron models, a connection is only activated when there is a spike, so this output processing step corresponds to adding the weights associated with the neuron which has spiked to the output of the network." ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))

 > 
 > "In weight update, the output weight matrix is updated according to the neuron activity and error signal. In order to do weight update in an event based manner, the low pass filter mentioned in section III-B has been removed, similar to \[30\]." ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))

 > 
 > "For adaptive control, SNN is implemented on both hardwares and Loihi shows better efficiency when low dimensional vector-matrix multiplication is involved, and the SpiNNaker 2 prototype shows better efficiency when high dimensional vector-matrix multiplication is involved." ([Yan et al 2021:3](zotero://open-pdf/library/items/S4TD4XET?page=3))

### Scalability for NEF TODO

````ad-quote
> "While this benchmark was originally proposed for its simplicity and applicability across a wide range of neuromorphic hardware and controlled devices, there is one further important reason for us to choose this benchmark. The core network that it requires has a single hidden layer non-linearity, and the inputs and outputs are generally of much lower dimensionality than the number of neurons in the hidden layer. This is exactly the sort of network that forms the core component of the Neural Engineering Framework (NEF) [27]. The NEF has been used to create large-scale biologically-based neural models [28] by chaining these smaller networks together. By sending the output from one of these networks to the inputs of another network, we are effectively factoring the weight matrix between the hidden layers of the two networks. This has been shown to be a highly efficient method for implementing neural models on the original SpiNNaker 1 hardware [29], and we expect the same to be the case on SpiNNaker 2." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

> "In this work, we focus on the adaptive control network implemented on a single PE. The implementation is done with scalability in mind." ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))

> "Eq. (13) is very similar to Eq. (5), because the main computation is in both cases done by the MAC array. The difference is caused by the different data types" ([Yan et al 2021:7](zotero://open-pdf/library/items/S4TD4XET?page=7))

> ". In keyword spotting, the inputs are assumed to be 8 bit integers, but in adaptive control, each input is assumed to be floating point. This is necessary because in general, the same implementation can be used as a building block for NEF implementation on SpiNNaker 2 to construct largescale cognitive models as mentioned in Section III-B, so that the input data type needs to be the same as the output data type. Since the output weights are floating point, and their values change dynamically due to learning, an extra range check is performed for each input value, and an extra data type conversion is performed. This is reflected in 35:79Din and the constant 131:21. T" ([Yan et al 2021:7](zotero://open-pdf/library/items/S4TD4XET?page=7))

````

### SpiNNaker 2 configuration TODO

````ad-quote
> "Arm Cortex-M4F core, 128 KBytes local SRAM, hardware accelerators for exponential functions [14] [15] and trueand pseudo random numbers [10], [16] and multiplyaccumulate (MAC) accelerators." ([Yan et al 2021:3](zotero://open-pdf/library/items/S4TD4XET?page=3))

> "This FDSOI technology allows the application of adaptive body biasing (ABB) for low-power operation at ultra-low supply voltages in both forward [20] and reverse bias schemes [21]. For maximum energy efficiency and reasonable clock frequencies," ([Yan et al 2021:3](zotero://open-pdf/library/items/S4TD4XET?page=3))

> "The rest of the computation is implemented on the Arm core which allows event based processing." ([Yan et al 2021:5](zotero://open-pdf/library/items/S4TD4XET?page=5))
````

### Future work can be done to benchmark data movement between PEs in SpiNNaker 2

In this paper demonstrating the effectiveness of SpiNNaker 2 over Loihi as neuromorphic hardware platform, the authors neglect to implement a benchmark that would increase data movement between PEs, 

````ad-quote
> "Since for the benchmarks in this work, there is not much data movement between the PEs, the throughput of the NoC is not a bottleneck." ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))
````

*Future work can benchmark the throughput of the NoC. ([note on p.6](zotero://open-pdf/library/items/S4TD4XET?page=6))*

### 

````ad-quote

````

 > 
 > "mean squared error between actual and desired trajectories in the case of adaptive control are negligibly small, so that this will not be further discussed in this section." ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))
 >  

 > 
 > "The total memory for a neural network on a PE is Mtotal = Mw + Mi" ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "In the keyword spotting benchmark, the computation times for the vector-matrix multiplication (Tmm) and the ReLU update (Trelu ) are measured" ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "Since the parameters are limited by the hardware constraints such as SRAM memory anyways, adopting more complicated models doesn't seem to be necessary for our benchmarks" ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "The time for the vector-matrix multiplication is mostly reflected in 0:13N D. Before the vector-matrix multiplication starts, the inputs to the network needs to be prepared for the MAC array. This pre-processing step is mostly reflected in 24:0D. After the vector-matrix multiplication, a post-processing step is necessary for the resulting neuron input current. The computation time depends on both D and N , and this is reflected in 24:0D and 5:38N . For each of the computational steps, there is a constant overhead, which is reflected in the constant 74:0" ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "1000 inferences per second. In \[5\], 296 inferences per second has been reported for Loihi" ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "One reason for the reduced speed of Loihi might be that the inputs to the neural network are coming from an FPGA which could cause some latency, while the SpiNNaker 2 prototype is using inputs generated by one of the PEs of the same chip." ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "This could be the reason that the SpiNNaker 2 prototype consumes less energy for each inference in the keyword spotting benchmark" ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "a 70 mW overhead presumably caused by the x86 processor on Loihi" ([Yan et al 2021:6](zotero://open-pdf/library/items/S4TD4XET?page=6))

 > 
 > "In this work the overhead has been removed which results in 37 J per inference" ([Yan et al 2021:7](zotero://open-pdf/library/items/S4TD4XET?page=7))

 > 
 > "The total memory for a neural network on a PE is Mtotal = Mib + Mo + Mic + Mn" ([Yan et al 2021:7](zotero://open-pdf/library/items/S4TD4XET?page=7))

 > 
 > "Unlike in keyword spotting, where the ReLU neuron model is used, in adaptive control, the LIF neuron model is used, which is the same as in Loihi." ([Yan et al 2021:7](zotero://open-pdf/library/items/S4TD4XET?page=7))

 > 
 > ". The minus sign in 26:9N P is because during the refractory period, the compu" ([Yan et al 2021:7](zotero://open-pdf/library/items/S4TD4XET?page=7))

 > 
 > "tation needed is reduced. Since this is event based, it depends on P ." ([Yan et al 2021:8](zotero://open-pdf/library/items/S4TD4XET?page=8))

 > 
 > "Since output processing and weight update are event based, the firing rate of 130 Hz corresponding to a firing probability P of 0.13, which is used for comparing the SpiNNaker 2 prototype with Loihi, would reduce the computation time by 87% compared to a non-event-based implementation" ([Yan et al 2021:8](zotero://open-pdf/library/items/S4TD4XET?page=8))

 > 
 > "So the maximum implementable size of a network on a single PE in this benchmark is constrained by memory rather than computation" ([Yan et al 2021:8](zotero://open-pdf/library/items/S4TD4XET?page=8))

### Neural networks can produce the I value in a PID controller for greater adaptivity

Neural networks can produce the I value in a PID controller for greater adaptivity

A proportional integral derivative (PID) controller uses feedback from a system to continuously modulate control. By calculating the difference between a desired setpoint and a measured process variable, it then derives the proportional, integral, and derivative terms from the continuous measurement of this error value. A correction based on a weighted sum of these three values is then applied to a control variable, to try to minimize the error over time.

I, or the integral term, is derived by integrating the past error values over time. While P, the proportional term, decreases as the error value decreases, I grows as the 

````ad-quote
> "One way to think of this is that the neural network is acting somewhat like the I term in a PID-controller, but since the I value is being produced by the neural network, it can be different for different parts of the sensory space. It can thus learn to, for example, apply extra positive torque when a robot arm is leaning far to one side, and extra negative torque when the arm is leaning far to the other side." ([Yan et al 2021:4](zotero://open-pdf/library/items/S4TD4XET?page=4))

> "In the normal case, both controllers perform equally well, but in the simulated aging case, the PID controller cannot adapt itself to the new situation, while the adaptive controller can learn from the error feedback and adapt its parameters to improve the performance" ([Yan et al 2021:9](zotero://open-pdf/library/items/S4TD4XET?page=9))
````

 > 
 > "We assume that the same benchmarks in this work could also be implemented on SpiNNaker 1. However, since in SpiNNaker 1 there is no MAC array, the vector-matrix multiplication would be much slower and therefore consume much more energy than the SpiNNaker 2 prototype." ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "3 categories" ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "Neuromorphic platforms with static synapses" ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "Neuromorphic platforms with configurable (but not programmable) plasticity" ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "Neuromorphic platforms with programmable plasticity" ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "DNNs can not be directly implemented on these platforms since they only support SNNs (except Tianjic, which also supports DNNs). Solutions similar to the SNN version implemented on Loihi would be an option" ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "For adaptive control, since learning is involved, we assume the neuromorphic platforms in group 1 can not support this benchmark. It would be still possible to have an external host PC to reprogram the synaptic weights, but that would not be suitable for embedded applications" ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "involves multiplying an external error signal with the activity of the presynaptic neuron in every time step, which is quite different from the learning rules normally supported in the neuromorphic community, like Spike-Timing Dependent Plasticity (STDP) \[45\] or Spike-Driven Synaptic Plasticity (SDSP) \[46\]. Therefore we assume the neuromorphic platforms in group 2 could not implement the adaptive control benchmark." ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "BrainScales 2 system in group 3 comes with programmable plasticity, but since the neural network runs in accelerated time, it is unclear whether the neural activity of each time step can be used for the weight update. Also it is unclear how to interface robotic applications which require real time response with a neural network running in accelerated time." ([Yan et al 2021:10](zotero://open-pdf/library/items/S4TD4XET?page=10))

 > 
 > "PE of the SpiNNaker 2 prototype consists of a general purpose processor plus highly efficient accelerators, while Loihi employs dedicated circuits for neuron and synapse models plus a flexible learning engine" ([Yan et al 2021:11](zotero://open-pdf/library/items/S4TD4XET?page=11))

 > 
 > "For keyword spotting, because of the MAC array used for vector-matrix multiplication and Arm core used for ReLU activation, the DNN version of keyword spotting network can be directly implemented on the SpiNNaker 2 prototype, while on Loihi the SNN version is implemented for the same task. The result of this is faster inference and higher energy efficiency of the SpiNNaker 2 prototype." ([Yan et al 2021:11](zotero://open-pdf/library/items/S4TD4XET?page=11))

 > 
 > "For adaptive control both the SpiNNaker 2 prototype and Loihi are efficient in specific parameter regions. The SpiNNaker 2 prototype is more efficient than Loihi both regarding the computation time and active energy, when the number of input dimensions is high, because that is where the vectormatrix multiplication is more complicated and the MAC array is more dominant. On the other hand, the SpiNNaker 2 prototype is less efficient than Loihi when the number of input dimensions is low, because that is where the vector-matrix multiplication is less complicated and the Arm core is more dominant." ([Yan et al 2021:11](zotero://open-pdf/library/items/S4TD4XET?page=11))

 

 > 
 > "The comparison regarding other benchmarks would be out of scope of this work and is left for future work." ([Yan et al 2021:11](zotero://open-pdf/library/items/S4TD4XET?page=11))

## Notable References

* [ ] M. Davies et al., "Loihi: A neuromorphic many-core processor with on-chip learning," IEEE Micro, vol. 38, no. 1, pp. 82-99, January 2018.

* [ ] T. C. Stewart et al., "Closed-loop neuromorphic benchmarks," Frontiers in Neuroscience, vol. 9, p. 464, 2015. \[Online\]. Available: https://www.frontiersin.org/article/10.3389/fnins.2015.00464

## To-do

* [x] Add contexts
* [x] Add notes
* [ ] Convert notes
