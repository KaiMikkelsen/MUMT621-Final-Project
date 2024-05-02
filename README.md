
# MUMT621 Final Project: Source Separation Results Analysis

## Overview

This project focuses on the analysis of source separation results using the Source to Distortion Ratio (SDR) metric, as defined by [here](https://ieeexplore.ieee.org/document/1643671). The goal is to evaluate the performance of two different source separation algorithms: Demucs and Wave-U-Net, on the MUSDBHQ dataset.

### Demucs Separation
The Demucs algorithm, developed by Facebook AI Research, is a deep learning-based source separation method known for its effectiveness in isolating individual sound sources from a mixture. In this project, we utilize Demucs to separate the audio sources (such as vocals, bass, drums, and others) from the music mixtures present in the MUSDBHQ dataset's test portion.

The notebook [`demucs.ipynb`](demucs.ipynb) orchestrates the execution of the Demucs algorithm on the test dataset. It carries out the necessary preprocessing steps, applies the separation algorithm, and then evaluates the quality of separation using the SDR metric. The SDR is computed for each individual source category (e.g., vocals, bass, drums) as well as for the overall mixture. The resulting SDR values are aggregated and analyzed to assess the performance of Demucs across different source types.

### Wave-U-Net Separation
Wave-U-Net is another deep learning-based source separation model, known for its ability to perform waveform-based audio source separation. Unlike traditional methods that operate in the spectral domain, Wave-U-Net operates directly on raw audio waveforms, enabling more accurate separation of sources. In this project, we employ the [Wave-U-Net Pytorch implementation](https://github.com/f90/Wave-U-Net-Pytorch) to perform source separation on the MUSDBHQ dataset.

The notebook [`wave-u-net-pytorch.ipynb`](wave-u-net-pytorch.ipynb) facilitates the execution of the Wave-U-Net algorithm on the test dataset. Similar to the Demucs workflow, it preprocesses the audio data, applies the separation model, and evaluates the quality of separation using the SDR metric. The SDR values are computed for each source category and aggregated to provide insights into the performance of Wave-U-Net across different types of audio sources.

By comparing the results obtained from Demucs and Wave-U-Net, this project aims to provide a comprehensive analysis of the strengths and weaknesses of each algorithm in the context of source separation tasks. Additionally, it seeks to contribute to the broader understanding of deep learning-based audio processing techniques and their applicability in real-world scenarios.

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

## Results

You can find the calculated SDR values for each song in the demucs_output.csv and wave-u-net-pytorch_output.csv files. These files display the SDR values for vocals, bass, and drums categories, along with their respective median and average values.


## References

Other important repositories utilized here include:

- [Demucs Source Separation](https://github.com/facebookresearch/demucs?tab=readme-ov-file)
- [Wave-U-Net PyTorch Implementation](https://github.com/f90/Wave-U-Net-Pytorch)
- [mir_eval Package](https://github.com/craffel/mir_eval)

