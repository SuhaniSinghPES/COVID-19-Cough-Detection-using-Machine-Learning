# COVID-19 Cough Detection using Machine Learning


## Overview
This project aims to detect COVID-19 from cough audio recordings using machine learning. Cough sounds contain unique respiratory patterns, which can provide a non-invasive and rapid pre-screening tool for COVID-19 detection.

We used a Convolutional Neural Network (CNN) trained on audio features extracted from cough recordings.

---

## Dataset
- **Source:** [Coswara Dataset](https://github.com/iiscleap/Coswara-Data)  
- **Classes:** COVID-19 positive and healthy  
- **Format:** Audio files (.wav) with metadata CSV  
- **Preprocessing:** Filtered to include only COVID-positive and healthy samples  

---

## Features Extracted
Using [Librosa](https://librosa.org/), we extracted the following audio features from each cough sample:  
- MFCC (Mel-Frequency Cepstral Coefficients)  
- Mel-Spectrogram  
- Spectral Contrast  
- Spectral Centroid & Bandwidth  
- Energy (RMS)  
- Zero-Crossing Rate  
- Pitch (Fundamental Frequency)  

All features were normalized to [0,1] and standardized for consistent input size for the CNN.

---

## Model
- **Architecture:** Convolutional Neural Network (CNN) with multiple Conv2D and MaxPooling2D layers, followed by Dense layers with Dropout  
- **Loss Function:** Binary Cross-Entropy  
- **Optimizer:** Adam  
- **Training:** 80% train, 20% test stratified split  

---

## Evaluation Metrics
- Accuracy  
- Precision  
- Recall (Sensitivity)  
- Specificity  
- F1-Score  
- Confusion Matrix  
- AUC-ROC Curve  

**Performance on Test Set:**  
- Accuracy: ~65–66%  
- AUC-ROC: ~0.687  

---

## How to Run
 Clone this repository:  
```bash
git clone <https://github.com/SuhaniSinghPES/COVID-19-Cough-Detection-using-Machine-Learning.git>
