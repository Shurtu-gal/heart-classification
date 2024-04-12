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

The features thus extracted are preprocessed using **Standard Scaler**.

### Model Architecture

#### Using Classifiers

This approach involves comparing the performance of different machine learning classifiers on the preprocessed data. We trained and evaluated various classifiers and reported the accuracy achieved by each on the heart sound classification task. Additionally, we utilised Grid Search to optimise the hyperparameters of these classifiers for improved performance.

We used the following classifiers:


- RandomForestClassifier	
- SVC	
- AdaBoostClassifier	
- DecisionTreeClassifier	
- KNeighborsClassifier	
- SVC RBF kernel	
- QuadraticDiscriminantAnalysis	
- GaussianNB

#### Using a Convolutional Neural Network 

The second method leverages a 1D Convolutional Neural Network (CNN) architecture specifically designed for processing sequential data like audio signals.
	
The CNN has the following architecture:

**Conv1D Layer**: Extracts local features using a variable number of filters (32 to 256) with a kernel size of 2, followed by a ReLU activation.
**MaxPooling1D Layer**: Downsamples the data while preserving important features.
**Flatten Layer**: Reshapes the output into a 1D vector for dense layers.
**Dense Layer 1**: Introduces non-linearity with ReLU activation and learns higher-level features with a variable number of units (32 to 256).
**Dropout Layer**: Prevents overfitting by randomly dropping out 50% of neurons during training.
**Output Layer:** Predicts the probability of a heart sound belonging to the abnormal class (sigmoid activation).

Hyperparameter tuning optimises the number of filters and dense layer units for best performance.


### Setup

```bash 
    ./setup.sh
```
