# Practical Application III: Comparing Machine Learning Classifiers

## 📘 Overview

This project presents a comparative analysis of several popular machine learning classifiers—**K-Nearest Neighbors (KNN)**, **Logistic Regression**, **Decision Trees**, and **Support Vector Machines (SVM)**—applied to a real-world dataset related to **telemarketing for banking products**. The goal is to predict whether a client will subscribe to a term deposit based on historical campaign data.

➡️ Access the full analysis in the Jupyter notebook: [prompt_III.ipynb](prompt_III.ipynb)

---

## 📊 Dataset

- **Source**: [UCI Machine Learning Repository – Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)
- **Description**: The data originates from direct marketing campaigns by a Portuguese bank, conducted via phone calls. Each record indicates whether the contacted client subscribed to a term deposit (`yes` or `no`).
- **File Used**: `bank-additional-full.csv`
  - Contains **41,188 instances** and **20 input features**.

---

## 🎯 Objectives

- **Understand the data**: Explore and analyze the dataset structure and features.
- **Preprocess**: Clean data, encode categorical variables, and address class imbalance.
- **Compare classifiers**: Evaluate the predictive performance of KNN, Logistic Regression, Decision Trees, and SVM.
- **Model tuning**: Optimize hyperparameters for better accuracy.
- **Assess results**: Use metrics like **accuracy** and **confusion matrix** to evaluate models.

---

## 🔄 Key Steps

### 📥 1. Data Loading
- Dataset imported using `pandas`
- Initial data exploration for structure and distribution

### 🛠️ 2. Preprocessing and Feature Engineering
- Drop irrelevant columns
- Encode categorical variables using suitable methods
- Balance the dataset (original distribution: ~89% "no" vs. ~11% "yes")

### 🤖 3. Model Training & Evaluation
- **KNN**: Tuned `k` parameter (best results with `k = 7`)
- **Logistic Regression**: Tested different regularization strengths (`C` values)
- **Decision Tree & SVM**: Included for comparison (not fully detailed in the notebook)

### 📈 4. Performance Metrics
- Accuracy
- Confusion matrix

---

## ✅ Results Summary

| Classifier           | Best Accuracy |
|----------------------|----------------|
| K-Nearest Neighbors  | ~79.5%         |
| Logistic Regression  | ~80.6% (`C=10`)|
| Decision Tree / SVM  | Included, not optimized in notebook |

---

## 🧰 Dependencies

- Python 3.x
- Libraries:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `scikit-learn`

---

## 🚀 How to Run

1. Clone this repository or download the notebook.
2. Place `bank-additional-full.csv` inside the `data/` directory.
3. Open and run `prompt_III.ipynb` sequentially in Jupyter or your preferred environment.

---

## 📄 License

This project is open-source under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- Dataset provided by the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing).
- Inspired by applied machine learning coursework and practical scenarios.

---

## 💬 Feedback

Feel free to open an issue for questions, suggestions, or feedback.

---