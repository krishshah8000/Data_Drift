# Data Drift Detection Techniques in Machine Learning

## Overview

This repository demonstrates three widely used statistical techniques for detecting **data drift** in Machine Learning. Data drift occurs when the distribution of incoming data changes from the data used to train a model, which can lead to reduced model performance.

The implementations in this repository provide simple, well-documented Python examples for understanding and comparing different approaches to drift detection.

---

## Implemented Techniques

### 1. Population Stability Index (PSI)

Population Stability Index (PSI) measures the change in the distribution of a feature between a reference dataset (training data) and a new dataset (production data).

**Key Features**

* Uses histogram-based binning
* Calculates expected and actual distributions
* Computes PSI score
* Provides drift interpretation

**Typical Interpretation**

| PSI Score   | Interpretation       |
| ----------- | -------------------- |
| < 0.10      | No significant drift |
| 0.10 – 0.25 | Moderate drift       |
| > 0.25      | Significant drift    |

---

### 2. Kolmogorov–Smirnov (KS) Test

The Kolmogorov–Smirnov Test compares the cumulative distribution functions (CDFs) of two datasets to determine whether they originate from the same distribution.

**Key Features**

* Non-parametric statistical test
* No manual binning required
* Computes KS statistic
* Reports p-value for hypothesis testing

**Hypothesis**

* **Null Hypothesis (H₀):** Both datasets come from the same distribution.
* **Alternative Hypothesis (H₁):** The datasets come from different distributions.

**Decision Rule**

* p-value > 0.05 → No statistically significant drift
* p-value ≤ 0.05 → Statistically significant drift detected

---

### 3. Jensen–Shannon Distance (JSD)

Jensen–Shannon Distance measures the similarity between two probability distributions. Unlike KL Divergence, it is symmetric and always produces a finite value, making it suitable for distribution comparison.

**Key Features**

* Symmetric distance measure
* Probability distribution based
* Suitable for monitoring feature distribution changes

**Typical Interpretation**

| JSD         | Interpretation           |
| ----------- | ------------------------ |
| 0.00        | Identical distributions  |
| 0.00 – 0.10 | Very similar             |
| 0.10 – 0.20 | Small shift              |
| 0.20 – 0.40 | Moderate shift           |
| > 0.40      | Large distribution shift |

---

## Project Structure

```text
.
├── psi.py                  # Population Stability Index implementation
├── ks_test.py              # Kolmogorov–Smirnov Test implementation
├── jensen_shannon.py       # Jensen–Shannon Distance implementation
└── README.md
```

---

## Technologies Used

* Python 3.x
* NumPy
* Pandas
* SciPy

---

## Installation

Clone the repository:

```bash
git clone https://github.com/krishshah/Data_Drift.git
```

Navigate to the project directory:

```bash
cd your-repository
```

---

## Running the Programs

Run the Population Stability Index implementation:

```bash
python psi.py
```

Run the Kolmogorov–Smirnov Test:

```bash
python ks_test.py
```

Run the Jensen–Shannon Distance implementation:

```bash
python jensen_shannon.py
```

---

## Learning Objectives

This repository helps you understand:

* Data drift detection concepts
* Distribution comparison techniques
* Statistical hypothesis testing
* Practical implementation of drift monitoring
* Comparison of multiple drift detection methods

---

## Applications

These techniques are commonly used in:

* Predictive Maintenance
* Credit Risk Modeling
* Fraud Detection
* Recommendation Systems
* Healthcare Analytics
* Production Machine Learning Monitoring
* Model Performance Monitoring
* MLOps Pipelines

---

## Future Improvements

Potential extensions to this repository include:

* Wasserstein Distance
* KL Divergence
* Anderson–Darling Test
* Chi-Square Test
* Feature-wise drift dashboards
* Automated drift monitoring pipeline
* Visualization of distribution changes
* Integration with real-world datasets

---

## License

This project is intended for educational and research purposes. Feel free to use, modify, and extend the implementations with appropriate attribution.

---

## Author

**Krish Shah**

If you found this repository helpful, consider giving it a ⭐ on GitHub.
