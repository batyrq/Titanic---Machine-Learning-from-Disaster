# 🛳️ Titanic - Machine Learning from Disaster

This repository contains my solution to the [Titanic Kaggle competition](https://www.kaggle.com/competitions/titanic), where the goal is to predict survival of passengers based on features such as age, sex, and class.

## 📁 Files

* `Titanic.ipynb`: Jupyter notebook containing the complete training, preprocessing, and inference pipeline.
* `predictions.csv`: Submission file generated after prediction on the test set.

## 🧠 Approach

The model is trained using **Gradient Boosting Classifier** from `scikit-learn`. The pipeline includes basic preprocessing and feature encoding:

### 🔧 Preprocessing

* **Name**: Converted to numeric based on title (`Mr`, `Mrs`, etc.) using simple substring matching.
* **Sex, Ticket, Embarked**: Label encoded.
* **Cabin**: Dropped due to high missingness.
* **Age**: Missing values filled with mean.
* **Embarked**: Missing values filled and label encoded.
* **PassengerId**: Dropped from training (used only for test output).

### 🧪 Model

* Model: `GradientBoostingClassifier` (default parameters)
* Target: `Survived`
* Features: All others after preprocessing
### Score

Accuracy of 0.796

### 🧾 Inference

The same preprocessing pipeline is applied to `test.csv`. Predictions are saved in `predictions.csv` as required by Kaggle format.

## ⚠️ Notes & Limitations

* **No validation** is performed (e.g., train/val split or cross-validation).
* **Hardcoded feature engineering** (e.g., substring search in names) could fail for unexpected inputs.
* **No hyperparameter tuning** or model selection beyond one algorithm.
* **Imputation** is basic (mean fill).
* Could benefit from:

  * Cross-validation
  * More robust feature extraction (e.g., using regex for titles)
  * Ensemble of models
  * Feature importance analysis

## ✅ How to Run

1. Place `train.csv` and `test.csv` in the same directory.
2. Run the notebook `Titanic.ipynb`.
3. Submission file `predictions.csv` will be created.

## 🏁 Output Format

```csv
PassengerId,Survived
892,0
893,1
...
```

## 📌 Dependencies

* Python 3.x
* pandas
* scikit-learn

You can install required packages with:

```bash
pip install pandas scikit-learn
```

---

Let me know if you'd like to include example visualizations, feature importance plots, or split it into `.py` modules for production use.
