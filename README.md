# 🌟 Transmission Line Analysis – Neural Network Model 🌟

Welcome! This project provides a robust and interactive workflow for analyzing transmission lines using both classical analytical methods and modern machine learning (Neural Network/MLPRegressor). Dive into the comprehensive Jupyter Notebook (`EMT_Assignment (1).ipynb`) and explore data generation, model training, evaluation, and a visualization-rich analysis window.

---

## 🚀 Features

- **💡 Synthetic Data Generation:** Realistic transmission line parameters via a custom `TransmissionLine` class.
- **🛠️ Data Preparation:** Train/test split, feature scaling, and target scaling for optimal ML performance.
- **🤖 Neural Network Training:** Multi-layer MLPRegressor predicts key transmission line metrics from physical parameters.
- **📊 Model Evaluation:** R² accuracy for every metric and overall performance summary.
- **🔍 Analysis Window:** Interactive comparison of analytical vs ML results, with beautiful standing wave plots.
- **📝 Exportable Dataset:** Save synthetic data to CSV for future research.

---

## 🧭 Workflow Overview

### 1. Data Generation & Preparation

- Define the `TransmissionLine` class for all analytical calculations.
- Randomly generate realistic line parameters (`R`, `L`, `G`, `C`, `freq`, `length`, `ZL`).
- Calculate targets: `Z0_real`, `Z0_imag`, `alpha`, `beta`, `SWR`.
- Organize data into a DataFrame.
- Split into train/test sets and scale features/targets.

### 2. Model Training

- Train an MLPRegressor neural network using scaled training data.
- Architecture: 3 hidden layers (128, 128, 64 neurons).
- Includes regularization and early stopping for best results.

### 3. Model Evaluation

- Predict on the test set, inverse-transform the results.
- Calculate R² accuracy for each metric and average accuracy.
- Typical accuracy: ~97% (may vary).

### 4. Analysis Window

- `analysis_window` function accepts input parameters and compares:
    - Analytical calculations (ground truth).
    - ML predictions from the trained model.
    - Plots voltage/current standing wave patterns with beautiful Matplotlib visuals.

### 5. Example Usage

```python
# Sample usage
sample_params = {
    'R': 0.1,
    'L': 250e-9,
    'G': 1e-6,
    'C': 100e-12,
    'freq': 150e6,
    'length': 10,
    'ZL': 75 + 30j,
    'ZL_real': 75,
    'ZL_imag': 30,
}
analysis_window(sample_params, model, scaler_X, scaler_y)
```

---

## 🎨 Visual Output

- **Accuracy:** Prints average R² accuracy, per-target results.
- **Comparison:** Analytical vs ML model predictions for custom inputs.
- **Plots:** Standing wave patterns for voltage and current, with color and style options.

---

## 🗂️ File Structure

- `EMT_Assignment (1).ipynb` – Main notebook; full workflow, rich visuals
- `transmission_line_data.csv` – Exported synthetic dataset (created by notebook)
- `README.md` – This documentation

---

## ⚡ How to Run

1. Open the notebook in Jupyter or Colab.
2. Run all cells to generate data, train, and evaluate the model.
3. Use `analysis_window()` to analyze custom transmission line parameters.
4. Save the dataset using the provided code block if desired.

---

## 🛠️ Requirements

- Python (Jupyter Notebook)
- numpy, pandas
- scikit-learn
- matplotlib

```bash
pip install numpy pandas scikit-learn matplotlib
```

---

## 📈 Example Output

```
1. Generating synthetic training data...
   Generated 10000 data points.

2. Preparing and scaling data...
   Data scaling complete.

3. Training the Neural Network (MLPRegressor) model...
   Model training complete.

4. Evaluating model performance...
--- NEURAL NETWORK MODEL EVALUATION RESULTS ---
Accuracy:  (97.12%)
---------------------------------------------
```

---

## 👤 Author

pra48-cyber

---

_✨ Tweak parameters, explore transmission line physics, and unleash the power of neural networks in engineering analysis! ✨_
