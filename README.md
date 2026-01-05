# Reducing False Negatives in Breast Cancer Detection

## Project Overview

Early and accurate detection of breast cancer is crucial in medical diagnostics. Missing a malignant tumor (False Negative) can have serious consequences, making recall (sensitivity) more critical than overall accuracy.

This project develops a **machine learning pipeline** to classify breast masses as **Malignant** or **Benign**, leveraging the Wisconsin Breast Cancer Dataset. The focus is on building an interpretable, high-recall model that can assist clinicians in identifying high-risk cases reliably.

---

## Research Questions

* Which tumor characteristics are most predictive of malignancy?
* Can a simple, interpretable model achieve high recall while remaining clinically useful?
* How does prioritizing recall over accuracy affect overall model performance?

---

## Dataset Overview

The dataset contains **569 patient samples** with **30 numeric features** extracted from digitized images of **fine needle aspirates (FNA)** of breast tumors.

**Target Variable:**

* `diagnosis`: Malignant (`M`) or Benign (`B`)

**Key Feature Groups:**

* **Radius, Perimeter, Area:** Size and shape measurements of the cell nucleus
* **Texture, Smoothness:** Variation in pixel intensity and surface regularity
* **Compactness, Concavity, Concave Points:** Shape irregularities and indentations
* **Symmetry, Fractal Dimension:** Geometric complexity of the nucleus

Each feature is recorded as **mean, standard error (SE), and worst-case value**, resulting in 30 descriptive features per sample.

---

## Methodology

### Data Preparation

* Removed irrelevant identifiers (`id`)
* Checked for missing values and handled them appropriately
* Encoded the target variable numerically: Malignant = 1, Benign = 0

### Exploratory Data Analysis (EDA)

* Analyzed feature distributions and relationships
* Visualized correlations using heatmaps
* Identified potential top predictors of malignancy

### Modeling Pipeline

* Used **Scikit-learn Pipelines** for clean, reproducible workflows
* Applied **StandardScaler** for feature normalization
* Implemented **Logistic Regression** for interpretability
* Trained **Decision Tree Classifier** for comparison

### Model Evaluation

* Focused on **Confusion Matrices, Classification Reports, and Recall Scores**
* Prioritized minimizing **False Negatives** to ensure malignant tumors are detected

---

## Key Findings

* **Top Predictors:** Concave points, radius, and perimeter were most indicative of malignancy
* **Model Performance:**

  * Logistic Regression achieved high recall, successfully detecting most malignant cases
  * Decision Tree provided good accuracy but slightly lower recall
* **Interpretability:** Logistic Regression coefficients allowed for a clear understanding of which features drive predictions, enabling clinical insight

---

## How to Use

1. Clone the repository or download the notebook.
2. Install required Python packages:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Run the Jupyter Notebook:

   ```
   Reducing_False_Negatives_Breast_Cancer_Detection.ipynb
   ```
4. Explore visualizations of feature importance, correlation heatmaps, and classification metrics.

---

## Outcome

By focusing on **recall**, this project provides a **reliable clinical decision support tool** that reduces the risk of missing malignant breast tumors, while maintaining model interpretability for medical experts.
