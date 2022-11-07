# uCDL

[![Stable](https://img.shields.io/badge/docs-stable-blue.svg)](https://kchu25.github.io/uCDL.jl/stable/)
[![Dev](https://img.shields.io/badge/docs-dev-blue.svg)](https://kchu25.github.io/uCDL.jl/dev/)
[![Build Status](https://github.com/kchu25/uCDL.jl/actions/workflows/CI.yml/badge.svg?branch=main)](https://github.com/kchu25/uCDL.jl/actions/workflows/CI.yml?query=branch%3Amain)
[![Coverage](https://codecov.io/gh/kchu25/uCDL.jl/branch/main/graph/badge.svg)](https://codecov.io/gh/kchu25/uCDL.jl)

# What is uCDL?
uCDL (Unfolded Convolutional Dictionary Learning for Motif discovery) is a method for motif discovery. We first formulate a convolutional dictionary learning problem and then "unfold" its optimization algorithm into a neural network. The network is fully interpretable, fast to train, and outputs a sparse representation of the dataset. The sparse representation allows us to carry out efficient inference to discover motifs.

## Why use uCDL for motif discovery?
Many methods can find statistically significant motifs, but characterizing the binding modes of the motifs is harder. The motifs may have multiple modes: each mode may share similar patterns (multimeric binding, alternate structural conformations), have different "parts" (variable spacing), or have multiple motifs that look entirely dissimilar to each other (multiple DNA binding domains). Some traditional motif discovery method uses heuristic such as substring-masking to deal with the above scenario, which leads to a sequential motif discovery method, and results in some secondary motif being masked and not revealed. The inference on the motifs using other black-box deep learning approaches is challenging.

The sparse representation we obtained from uCDL is fully interpretable, and we seek to use such representation to discover all the motifs simultaneously.


# How to Install
We are currently adding this package to the Julia registry. Once it's added, the user can simply install our package via the Julia's package manager:
```
pkg> add uCDL
```

## Software requirements
 This package requires [Weblogo](http://weblogo.threeplusone.com/manual.html#download). You need python3 and install Weblogo with following command:
 ```bash
 pip3 install weblogo
 ```
You can check if you have weblogo installed by typing:
```bash
weblogo -h
```

## Hardware requirements
We require the user to have an Nvidia GPU; we plan to implement a CPU version in the future.

# How to Use

In Julia, import the uCDL package first:
````julia
using uCDL-motif
````
<br>


To do motif discovery on a single fasta file, execute
````
find_motif(<fasta-path>, <output-folder>)
````
- Perform motif discovery on the fasta file `<fasta-path>`, and 
- Output the result in a pre-specified folder `<output-folder>`. <br><br>



To do motif discovery on a batch of fasta files, execute
````
find_motif_fasta_folder(<fasta-folder-path>, <output-folder>)
````
- Perform motif discovery on all the fasta files in the `<fasta-folder-path>`, and 
- Output each of the results in a pre-specified folder `<output-folder>`.<br><br>

# Citing uCDL

If you use `uCDL` in your work, please cite
```
Shane K. Chu, Gary D. Stormo, Deep unfolded convolutional dictionary learning for motif discovery, bioRxiv 2022.11.06.515322; doi: https://doi.org/10.1101/2022.11.06.515322
```