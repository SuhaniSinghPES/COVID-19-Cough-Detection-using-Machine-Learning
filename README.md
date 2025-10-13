# COVID-19-Cough-Detection-using-Machine-Learning
## Problem Statement
This project develops an **audio-based screening tool** to detect COVID-19 from cough sounds. The system analyzes acoustic features of coughs to identify potential COVID-19 cases, providing a **non-invasive, rapid screening method**.

---

## Dataset
We used the **Coswara Dataset** ([GitHub Link](https://github.com/iiscleap/Coswara-Data)):

- Crowdsourced respiratory sounds
- Each participant may have multiple cough recordings
- Only COVID-positive and healthy labels were used

---

## Features Extracted
- **Mel-spectrograms** (used as CNN input)

> **Note:** Other features like MFCC, pitch, energy, zero-crossing rate were planned but not implemented yet.

---

## Preprocessing
- Audio loading and trimming
- Padding/truncation of spectrograms to a fixed width
- Min-max scaling to [0,1]
- Each cough recording treated as a separate sample

---

## Model
### Convolutional Neural Network (CNN)
- Input: Mel-spectrogram images `(128, width, 1)`
- Architecture:
 ⁠

Conv2D -> MaxPooling
Conv2D -> MaxPooling
Conv2D -> MaxPooling
Flatten -> Dense(128) -> Dropout(0.5) -> Dense(1, sigmoid)


- Loss: Binary Cross-Entropy
- Optimizer: Adam
- Training epochs: 20
- Batch size: 32

---

## Results
- Test Accuracy: **~65%**
- Confusion Matrix:


[[376 197]
[188 337]]


- Classification Report:



            precision    recall  f1-score   support

       0       0.67      0.66      0.66       573
       1       0.63      0.64      0.64       525

accuracy                           0.65      1098


macro avg       0.65      0.65      0.65      1098
weighted avg       0.65      0.65      0.65      1098

⁠ `

> **Note:** Sensitivity (recall), specificity, and AUC-ROC were not computed in this implementation.

---

## How to Use
1. Clone this repository.
2. Download the Coswara dataset and place files in the `Extracted_data/` folder, structured by participant.
3. Install dependencies:

 ⁠bash
pip install numpy pandas librosa tensorflow scikit-learn matplotlib tqdm
⁠ `

4. Run preprocessing and feature extraction scripts.
5. Train the CNN using the provided training script.
6. Evaluate using the test script.

---

## References

* [Coswara Dataset](https://github.com/iiscleap/Coswara-Data)
* Librosa: [https://librosa.org/](https://librosa.org/)
* TensorFlow/Keras: [https://www.tensorflow.org/](https://www.tensorflow.org/)

