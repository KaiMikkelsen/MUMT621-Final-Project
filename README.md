# MUMT621 Final Project, Source Separation Results Analysis

## Overview

This code computes the Source to Distortion Ration (SDR) as defined by Vincent et al. available [here](https://inria.hal.science/inria-00544230/document). 

demucs.ipynb performs the necessary steps to run the [demucs](https://github.com/facebookresearch/demucs) source separation algorithm on the [MUSDBHQ](https://sigsep.github.io/datasets/musdb.html#musdb18-compressed-stems) dataset, and then calculates the SDR on the separated .wav files for the other, bass, vocals and drums categories.

wave-u-net-pytorch.ipynb performs the necessary steps to run the [Wave-U-Net Pytorch implementation ](https://github.com/f90/Wave-U-Net-Pytorch) source separation algorithm on the [MUSDBHQ](https://sigsep.github.io/datasets/musdb.html#musdb18-compressed-stems) dataset, and then calculates the SDR on the separated .wav files for the other, bass, vocals and drums categories.



## Installation

## References
