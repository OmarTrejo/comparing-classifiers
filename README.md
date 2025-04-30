# Practical Application III: Comparing Machine Learning Classifiers

## 📘 Overview

This project explores and compares the performance of four supervised machine learning classifiers—**K-Nearest Neighbors (KNN)**, **Logistic Regression**, **Decision Trees**, and **Support Vector Machines (SVM)**—using data from a Portuguese bank's telemarketing campaigns. The primary objective is to predict whether a client will subscribe to a term deposit (`y = yes | no`) based on socio-demographic, behavioral, and campaign-specific attributes.

📓 Access the complete notebook here: [prompt_III.ipynb](prompt_III.ipynb)

---

## 📊 Dataset

- **Source**: [UCI Machine Learning Repository – Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
- **File**: `bank-additional-full.csv`
- **Samples**: 41,188 rows
- **Features**: 20 input features + 1 target variable
- **Period**: May 2008 – November 2010

### Feature Categories:

- **Client Information**: `age`, `job`, `marital`, `education`, `default`, `housing`, `loan`
- **Last Contact (Campaign Related)**: `contact`, `month`, `day_of_week`, `duration`
- **Other Campaign Attributes**: `campaign`, `pdays`, `previous`, `poutcome`
- **Economic Indicators**: `emp.var.rate`, `cons.price.idx`, `cons.conf.idx`, `euribor3m`, `nr.employed`
- **Target Variable**: `y` (binary: yes/no)

📄 For full feature context, refer to the [CRISP-DM-BANK.pdf](CRISP-DM-BANK.pdf) article.

---

## 🎯 Objectives

1. **Understand the dataset**: Analyze the structure, context, and distribution of features.
2. **Preprocess the data**: Clean, encode, scale, and prepare features for model consumption.
3. **Compare classifiers**: Evaluate the performance of multiple ML models under equal conditions.
4. **Improve model performance**: Apply hyperparameter tuning, feature selection, and metric diversification.
5. **Provide business insights**: Translate model outcomes into actionable marketing recommendations.

---

## 🧪 Methodology

### 1. Data Preparation
- Load CSV into a Pandas DataFrame.
- Assess and convert data types.
- Identify and handle missing values (none found).
- Separate numerical and categorical features.

### 2. Preprocessing
- Encode categorical features (one-hot encoding where appropriate).
- Standardize numerical features using `StandardScaler`.
- Address class imbalance (`~11% 'yes'` vs. `~89% 'no'`) in evaluation strategy.

### 3. Model Training and Evaluation
- Split dataset using `train_test_split` (75% train, 25% test).
- Train the following models:
  - **KNN**: Best performance at `k = 7`
  - **Logistic Regression**: Best performance at `C = 10`
  - **Decision Tree**: Trained with default parameters; visualized top layers
  - **SVM**: Linear kernel used for performance benchmarking
- Evaluate with:
  - **Accuracy**
  - **Confusion Matrix**
  - (Optionally) F1-score, precision, recall

### 4. Visualization
- Tree structure visualized using `plot_tree` (first two levels)
- Confusion matrices displayed with `ConfusionMatrixDisplay`

---

## 📈 Results & Insights

| Model               | Accuracy (Approx.) | Notes                            |
|--------------------|--------------------|----------------------------------|
| K-Nearest Neighbors| 79.5%              | Optimal with `k = 7`             |
| Logistic Regression| 80.6%              | Best with `C = 10`               |
| Decision Tree      | ~78%               | Basic tuning, visualized         |
| SVM                | ~79%               | Linear kernel, default settings  |

---

## 💡 Marketing Recommendations

### 1. Prioritize High-Conversion Profiles
- **Long call durations** and **prior positive outcomes** (`poutcome = success`) are strong indicators.
- Track these metrics monthly for lead prioritization.

### 2. Reduce False Positives
- Avoid overpromising in scripts to minimize predicting "yes" when client doesn't subscribe.

### 3. Re-engage False Negatives
- Clients incorrectly predicted as "no" could still convert—create a secondary outreach list.

### 4. Segmentation Strategy
- **Single clients** may show higher subscription likelihood.
- Customize messaging for **married clients** to improve their conversion.

### 5. Model Maintenance
- **Retrain quarterly** to account for campaign and market shifts.
- **Drop low-importance features** (e.g., `loan`, `day_of_week`) to improve clarity and speed.

---

## 📁 Project Structure

ml-comparison-bank/
├── data/
│   └── bank-additional-full.csv         # Dataset
├── prompt_III.ipynb                     # Jupyter notebook with full analysis
├── CRISP-DM-BANK.pdf                    # Background paper on dataset and problem
├── requirements.txt                     # Minimal pip-based dependencies
├── environment.yml                      # Conda environment configuration
├── .gitignore                           # Files and folders to exclude from version control
└── README.md                            # Project documentation

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

## 🚧 Future Work
* Apply grid search to optimize hyperparameters for all models.
* Implement evaluation using ROC-AUC, F1-score, and precision/recall.
* Experiment with ensemble methods (Random Forest, Gradient Boosting).
* Automate retraining workflows with scheduled jobs or CI pipelines.
* Explore feature interactions or domain-specific transformations to improve modeling.

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