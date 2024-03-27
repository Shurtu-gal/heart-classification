## Heart Signal Classification using STFT

This project is part of the Computer Vision Lab 2024, and aims to classify heart signals using the Short Time Fourier Transform (STFT) and a Convolutional Neural Network (CNN). The dataset used is the [Paediatric Heart Sound Database](https://pubmed.ncbi.nlm.nih.gov/38194403/). 

### Dataset Description

This Dataset comprises Paediatric heart sound recordings stored in .wav format collected from 941 individuals. These recordings include 533 instances of normal heart sounds and 408 instances of abnormal heart sounds. The dataset is sampled at a rate of 4000Hz.

### Feature Extraction

The features are extracted using four different methods:
1. **Short Time Fourier Transform (STFT)**
2. **Mel-Frequency Cepstral Coefficients (MFCC)**: It is based on **STFT** and is a representation of the short-term power spectrum of a sound, based on a linear cosine transform of a log power spectrum on a nonlinear mel scale of frequency.
3. **Mel Spectrogram**
4. **Chromagram**: Based on the **STFT** and classifies sound based on pitch class.
 
### Preprocessing

The features thus extracted are preprocessed using **Standard Scaler** and **MinMax Scaler**.

### Model Architecture

 
### Setup

```bash 
    ./setup.sh
```
