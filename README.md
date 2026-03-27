# Exoplanet Detection from Kepler Light Curves

This project applies machine learning to classify stars as exoplanet‑hosting or not, using light curve data from the Kepler space telescope.

## Dataset
- **exoTrain.csv**: 5,087 light curves (3,197 time points each) – 37 exoplanets, 5,050 non‑exoplanets.
- **exoTest.csv**: 570 light curves – 5 exoplanets, 565 non‑exoplanets.
- Source: [Kepler Exoplanet Search Dataset](https://www.kaggle.com/keplersmachines/kepler-labelled-time-series-data)

## Models
1. **Support Vector Machine (SVM)** with RBF kernel – hyperparameter tuned via grid search.
2. **Neural Network** with two hidden layers – trained on SMOTE‑balanced data.

## Preprocessing
- Fourier transform (magnitude)
- L2 normalization
- Gaussian smoothing (σ=10)
- Standardization

## Results

| Model       | Precision | Recall | F1-score |
|-------------|-----------|--------|----------|
| SVM (RBF)   | 0.714     | 1.000  | 0.833    |
| Neural Net  | **1.000** | **1.000** | **1.000** |

> *Note: The neural network achieved perfect test set scores, but the test set is small (5 exoplanets). Further validation is recommended.*

## How to Run
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
