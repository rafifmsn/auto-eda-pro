# Auto Exploratory Data Analysis (EDA) Pro

![Thumbnail](/assets/og.png)

## ✨ Overview

Auto EDA Pro is a ready-to-use Google Colab / Jupyter notebook that performs a complete workflow:
- Data ingestion and validation
- Automated cleaning (missing values, duplicates, invalid types)
- Rich exploratory visualizations (numerical + categorical)
- Correlation and feature behavior insights
- Auto-model selection for quick performance verification
- Rule-based insight engine (data quality + modeling risks)
- Optional AI-powered summary (OpenAI / Gemini)

> Perfect for analysts, students, and ML practitioners who want **fast and reliable** dataset understanding.

## 🚀 Quick Start

**1️⃣ Clone the repository**

```bash
git clone https://github.com/rafifmsn/auto-eda-pro.git
cd auto-eda-pro
pip install -r requirements.txt
```

**2️⃣ Install dependencies**

```bash
pip install -r requirements.txt
```

**3️⃣ Run in Jupyter / Colab**
- Open the notebook here: notebooks/auto_eda.ipynb
- Upload your CSV dataset when prompted
- Choose (optional) AI provider for insight summarization

## 🔧 Configuration Notes

You may configure AI settings at the top of the notebook:
```python
AI_PROVIDER = "openai"      # "openai", "gemini", or None
AI_API_KEY = "YOUR_KEY_HERE"
AI_MODEL = None             # Default model if left None
```

AI is optional — if disabled:
- The notebook still runs 100%
- Insight summary will fall back to rule-based only

## 📊 CSV Requirements

| Requirement                 | Default     | How to change                               |
| --------------------------- | ----------- | ------------------------------------------- |
| Delimiter                   | , comma     | In upload cell → pd.read_csv(file, sep=';') |
| First row contains headers  | Required    | Rename columns in notebook if needed        |
| Mixed numeric + categorical | Recommended | Numeric-only still works                    |
| Missing values              | Supported   | Will be automatically imputed               |
| Duplicates                  | Supported   | Will be automatically removed               |

## 🧠 What the Notebook Detects

- Missing values and how they were handled ✅
- Duplicate pattern detection ✅
- Outlier warnings and data skewness analysis ✅
- Categorical invalid value detection ✅
- Correlation anomalies ✅
- Target interaction and modeling suitability ✅
- High-risk data quality issues flagged automatically ✅

All insights are scored with severity:
- error → needs immediate fix
- warning → important issue
- info → normal behavior but highlighted

## 🤖 Model Training Behavior

- Automatically detects the target column (last column by default)
- Chooses:
    - Regression if numeric target
    - Classification if categorical target
- Trains baseline models and reports metrics
> Intended to help you evaluate if data is ready for modeling.

## 🔑 License & citation

- Repository code: MIT
- Sample dataset: [Jakki Seshapanpu](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams/data), [Royce Kimmons](http://roycekimmons.com/tools/generated_data/exams)