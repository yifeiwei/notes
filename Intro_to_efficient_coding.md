# Introduction to Efficient coding
This part of notes is based on a 51 min long [video lecture](https://www.youtube.com/watch?v=NJsHsUwfNb8) given by [Li Zhaoping](http://www0.cs.ucl.ac.uk/staff/Zhaoping.Li) on efficient coding. It comes with Chapter 3 of the book ["Understanding Vision: theory, model and data"](http://www0.cs.ucl.ac.uk/staff/Zhaoping.Li/VisionBook.html)

[![Introduction to efficient coding](https://img.youtube.com/vi/NJsHsUwfNb8.jpg)](https://www.youtube.com/watch?v=NJsHsUwfNb8 "Introduction to efficient coding")

#### Understanding early visual processing from visual input statistics

The three stages of vision
* encoding
    * ***Efficient coding***: like data compression
* attention selection
* decoding (recognition)

Efficient coding maximize extracted input information while limiting neural coding cost
* encoded information represented by V1 neurons and retinal ganglion cells
* receptive fields are filters

Example: Ocular coding
* ![](http://latex.codecogs.com/gif.latex?\\ S^L): image in left eye.
* `$S^R$`: image in right eye.
* eyes->LGN->V1
A  V1 neuron's response output:
```math
O = K_L S_L + K_R S_R
```
* coding transform K:`$ O_i = \sum_j K_{ij}(S_j+N_j)+(N_O)_i$`
Input signal can be measured as mutual information:
* e.g `$I(O;S)$` mutual information in both neurons
* information redundancy: `$I(O_1;S)+ I(O_2;S) \geq I(O;S)$`
* Coding cost e.g `$<O_1^2>+<O_2^2> $`
* `$E(K) \equiv \text{Coding cost}-\lambda \cdot I(O;S) $`
    * The optimal K to minimize the objective is the efficient code
    * Essential recipe to extract K
      1. Decorrelation
      2. Cain control
      3. Multiplexing
###### Decorrelation
1. Ocular summation: `$S_+ = S_L + S_R$`
2. Ocular contrast: `$S_- = S_L - S_R$`
###### Gain control
* whitening
###### Multiplexing
* does not change coding efficiency
* minimize the amount of neuron wirings in the brain
###### Summary
S+noise`$\rightarrow$` Decorrelation`$  K_O$` `$\rightarrow$`Gain control `$g$` `$\rightarrow$`Multiplexing `$U$` `$\rightarrow$` `$O=(UgK_O)S+noise'$`
* `$K=UgK_O$` K stands for kernel
* 
