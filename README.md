# MUMT621 Final Project: Source Separation Results Analysis

## Overview

This code calculates the Source to Distortion Ratio (SDR) as defined by Vincent et al. (available [here](https://inria.hal.science/inria-00544230/document)).

### Demucs Separation
The notebook `demucs.ipynb` orchestrates the execution of the [demucs](https://github.com/facebookresearch/demucs) source separation algorithm on the test portion of the [MUSDBHQ](https://sigsep.github.io/datasets/musdb.html#musdb18-compressed-stems) dataset. It subsequently computes the SDR on the separated .wav files for the 'other', bass, vocals, and drums categories.

The output of `demucs.ipynb` is stored in `demucs_output.csv`, containing the calculated SDRs for each song's 'other', bass, vocals, and drum categories, along with their average and median values.

### Wave-U-Net Separation
The notebook `wave-u-net-pytorch.ipynb` facilitates the execution of the [Wave-U-Net Pytorch implementation](https://github.com/f90/Wave-U-Net-Pytorch) source separation algorithm on the test portion of the [MUSDBHQ](https://sigsep.github.io/datasets/musdb.html#musdb18-compressed-stems) dataset. It then computes the SDR on the separated .wav files for the 'other', bass, vocals, and drums categories.

The output of `wave-u-net-pytorch.ipynb` is stored in `wave-u-net-pytorch_output.csv`, containing the calculated SDRs for each song's 'other', bass, vocals, and drum categories, along with their average and median values.

## Usage

When utilizing this repository, several assumptions were made:

1. The [Wave-U-Net Pytorch](https://github.com/f90/Wave-U-Net-Pytorch) repository was cloned to this directory for usage.
2. The files of the [MUSDBHQ](https://sigsep.github.io/datasets/musdb.html#musdb18-compressed-stems) dataset test directory were installed on the local machine for separation and processing.

If the Wave-U-Net Pytorch repository and MUSDBHQ dataset are installed on your machine, set the necessary paths in both `wave-u-net-pytorch.ipynb` and `demucs.ipynb` files to reference these repositories and directories.

To utilize this repository:

1. Clone it to your machine:

```bash
git clone https://github.com/KaiMikkelsen/MUMT621-Final-Project.git
```

2. Navigate into the directory:

```bash
cd MUMT621-Final-Project
```

3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

4. Ensure that the MUSDBHQ test folder files and Wave-U-Net Pytorch repository files are installed on your machine, and update the paths in both `wave-u-net-pytorch.ipynb` and `demucs.ipynb` files accordingly.

5. Execute the various commands in `wave-u-net-pytorch.ipynb` and `demucs.ipynb` depending on whether you wish to perform separation or write results to a CSV file.

## References

- Paths to repositories and documents:
  - Wave-U-Net repository
  - Demucs repository
  - SDR calculation document
