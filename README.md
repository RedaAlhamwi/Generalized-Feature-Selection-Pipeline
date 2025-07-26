# Generalized-Feature-Selection-Pipeline
A reusable feature selection pipeline for regression problems that combines: Robust Pearson correlation analysis for numerical features One-way ANOVA and Tukey's HSD post-hoc tests for categorical features ✅ Automatically identifies which variables (numeric or categorical) have statistically significant relationships with the target.


This project provides a reusable Python pipeline for selecting important features when working on **regression problems**. It combines:

* ✔ Robust **Pearson correlation** for numerical features
* ✔ **ANOVA (Analysis of Variance)** for categorical features
* ✔ **Tukey's HSD** post-hoc test to identify influential categorical levels

## Use Cases

This pipeline is ideal for:

* Real estate price prediction (e.g., Ames, Dubai datasets)
* Marketing spend analysis
* Customer segmentation based on sales
* Educational performance analysis
* Any regression dataset with **mixed numerical and categorical** features

## ⚙️ Features

* Works on **almost any dataset** with a numerical target
* Automatically detects and analyzes numerical/categorical features
* Provides detailed plots and significance summaries
* Helps reduce dimensionality for modeling


## 📚 How It Works

1. **Numerical Features:**

   * Computes Pearson correlation between each feature and the target
   * Selects those with ⬆️ strong correlation

2. **Categorical Features:**

   * Runs one-way ANOVA to assess if feature significantly affects target
   * If significant (α=0.05), runs Tukey HSD to compare group means
   * Identifies most impactful categories

3. **Result:**

   * Prints selected features
   * Saves plots and significance tables


## 💡 Example

```python
from feature_selector import FeatureSelector

selector = FeatureSelector(df, target='SalePrice')
selector.run_all()
```


## ♻️ Reusability

Just change:

```python
df = pd.read_csv("your_dataset.csv")
target = "YourTargetVariable"
```


## 📄 Output Includes:

* List of selected numerical features (based on correlation)
* List of significant categorical features
* ANOVA F-statistics
* Tukey HSD summary tables
* Optional matplotlib boxplots

## 📝 Requirements

```bash
pandas
scipy
statsmodels
matplotlib
seaborn
```

Install via:

```bash
pip install -r requirements.txt
```

---


