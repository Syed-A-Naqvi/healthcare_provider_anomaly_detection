# Healthcare Provider Anomaly Detection: Aggregate Claim Analysis

**Developed a provider-level risk scoring system to identify statistical outliers in billing behavior, service frequency, and beneficiary concentration.**

*Author: Arham Naqvi*

*Last Updated: February 12th, 2026*

---
## Project Overview

This project develops a **provider-level risk scoring system** to identify potentially fraudulent healthcare providers by analyzing aggregate claim patterns. Using a dataset of 500,000+ Medicare claims, we build behavioral profiles for each provider and apply anomaly detection techniques to flag high-risk billing behavior.

### Key Objectives
- Aggregate claim-level data to provider-level features
- Identify statistical outliers in billing patterns
- Detect indicators of **upcoding** and **phantom billing**
- Generate interpretable risk scores for each provider

## Project Structure

```
source/
├── data/
│   ├── raw/                    # Train/Test CSV files
│   └── processed/              # Cleaned, aggregated provider-level features
├── notebooks/
│   ├── 01_data_cleaning_integration.ipynb    # Merge Claims + Beneficiary data
│   ├── 02_feature_engineering_aggregation.ipynb  # Create per-provider metrics
│   ├── 03_exploratory_analysis.ipynb         # Visualize fraud vs normal distributions
│   └── 04_model_training_evaluation.ipynb    # Autoencoder & Random Forest models
├── src/
│   ├── features.py             # Aggregation logic functions
│   └── visualization.py        # Plotting utilities
├── models/                     # Saved trained models
└── requirements.txt            # Python dependencies
```

## Methodology

### 1. Data Integration
- Merge inpatient and outpatient claims with beneficiary demographics
- Link provider identifiers with fraud labels for supervised learning

### 2. Feature Engineering
- **Volume Metrics**: Total claims, unique beneficiaries, claim frequency
- **Financial Metrics**: Average claim amount, reimbursement statistics
- **Behavioral Metrics**: Procedure diversity, diagnosis patterns
- **Risk Indicators**: Concentration ratios, upcoding signals

### 3. Anomaly Detection
- **Autoencoder**: Unsupervised approach learning "normal" provider patterns
- **Random Forest**: Supervised classification with feature importance analysis
- **Ensemble Scoring**: Combined risk scores from multiple models

## Getting Started

### Prerequisites
```bash
pip install -r source/requirements.txt
```

### Workflow
1. Place raw data files in `source/data/raw/`
2. Run notebooks in sequential order (01 → 04)
3. Trained models will be saved to `source/models/`

## Technologies

- **Languages**: Python 3.10+
- **Data Processing**: Pandas, NumPy, SciPy
- **Machine Learning**: Scikit-learn, TensorFlow/Keras
- **Visualization**: Matplotlib, Seaborn, Plotly

## Author

**Arham Naqvi**

## License

This project is licensed under the terms specified in the LICENSE file.
