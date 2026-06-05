# Quantum Support Vector Machine (QSVM) for Space Debris Risk Classification

## Overview

This project implements a Quantum Support Vector Machine (QSVM) using PennyLane and a custom quantum kernel to classify collision risk levels in a Space Debris Risk Dataset (SDRD).

The objective is to explore the application of quantum machine learning techniques for multi-class classification problems involving high-dimensional scientific data.

---

## Dataset

The dataset contains orbital and environmental features related to space debris objects.

Target Variable:

* `risk_level`

  * 0 = Low Risk
  * 1 = Moderate Risk
  * 2 = High Risk

The dataset was divided into training and test sets.

---

## Methodology

### Data Preprocessing

* Missing value handling using forward filling
* Feature standardization using StandardScaler
* Dimensionality reduction using PCA

### PCA

The original feature space was reduced to 4 principal components to match the number of available qubits and reduce quantum circuit complexity.

### Quantum Feature Map

A custom 4-qubit feature map was implemented using:

* Hadamard gates
* RZ rotations
* Entangling CNOT operations

### Quantum Kernel

A quantum kernel matrix was generated using state overlap estimation through PennyLane's quantum simulator.

### QSVM

The generated kernel matrix was used with Scikit-Learn's Support Vector Classifier using a precomputed kernel.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Scikit-Learn
* PennyLane
* PennyLane Lightning Simulator

---

## Results

Validation Performance:

* Balanced Accuracy: 0.3333
* Macro F1 Score: 0.2698

A predictions file (`predictions.csv`) is generated for the test dataset.

---

## Project Structure

```text
QSVM_Project/
│
├── qml_project.py
├── train.csv
├── test.csv
├── predictions.csv
├── requirements.txt
└── README.md
```

---

## How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Run:

```bash
python qml_project.py
```

The script will:

1. Load and preprocess data
2. Perform PCA
3. Construct the quantum kernel
4. Train the QSVM
5. Evaluate validation performance
6. Generate predictions.csv

---

## Future Improvements

* Hyperparameter tuning
* Larger quantum feature maps
* Increased qubit count
* Comparison with classical SVM baselines
* Alternative quantum kernel designs

---

## Author

Krishnandu Panda

Indian Institute of Technology Guwahati (IIT Guwahati)
