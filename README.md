# 🧠 RA Severity Prediction Using Gene Expression and Machine Learning

This project aims to predict rheumatoid arthritis (RA) disease severity based on gene expression profiles using machine learning techniques. The project utilizes publicly available datasets (such as GSE93272) from the NCBI Gene Expression Omnibus (GEO) and integrates clinical data like DAS28 scores to classify patients into severity levels.

## 📌 Objective

To build a supervised machine learning model that can classify RA patients into Mild, Moderate, or Severe disease groups based on their gene expression data and clinical features.

## 📊 Dataset Overview

* Dataset: [GSE93272](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE93272)
* Platform: GPL570 (Affymetrix Human Genome U133 Plus 2.0 Array)
* Sample Size: \~200 RA patients
* Data Types:
  * Whole blood microarray expression data
  * Clinical metadata including DAS28 scores, gender, age, treatment response

## 🧪 Methodology

### Step 1: Data Collection & Inspection

* Downloaded GSE93272 dataset using GEOparse or manual GEO tools.
* Extracted:
  * expression_matrix: Microarray expression values
  * metadata: Clinical data with DAS28 and patient characteristics

### Step 2: Preprocessing

* Expression Data:
  * Log2 transformation (if not already normalized)
  * Removed low-variance probes
  * Mapped Affymetrix probe IDs to gene symbols using GPL570 annotation

* Metadata:
  * Extracted DAS28 scores
  * Labeled samples:
    * Mild if DAS28 < 3.2
    * Moderate if 3.2 ≤ DAS28 ≤ 5.1
    * Severe if DAS28 > 5.1
  * Merged expression and metadata using sample IDs

### Step 3: Feature Selection

* Filtered highly variable genes across samples
* Optionally performed differential expression analysis to select discriminative genes
* Included optional clinical variables (e.g., sex, treatment)

### Step 4: Model Development

* Models used:

  * Random Forest
  * XGBoost
  * Logistic Regression
  * SVM

* Data split: 70% training, 30% test
* Cross-validation: 5-fold CV
* Hyperparameter tuning with GridSearchCV

### Step 5: Evaluation

* Classification metrics:
  * Accuracy
  * F1 Score
  * Precision & Recall
  * Confusion Matrix
* Visualizations:
  * ROC curves
  * Feature importance plots
  * Heatmaps of expression

## 🎯 Expected Output

* Cleaned gene expression matrix: expression_cleaned.csv
* Processed metadata with labels: metadata_cleaned.csv
* Trained classification models (e.g., random_forest_model.pkl)
* Performance reports for each model
* Plots:
  * Confusion matrices
  * Top 20 gene feature importance
  * ROC-AUC curves for each class

## 📁 Project Structure

📦 RA-Severity-Prediction/
├── data/                     # Raw and intermediate datasets
├── notebooks/                # Exploratory analysis and model building
├── src/                      # Scripts for processing, modeling
├── results/                  # Output figures, metrics, reports
├── expression_cleaned.csv    # Final gene expression data
├── metadata_cleaned.csv      # Final clinical metadata
├── README.md                 # Project documentation
└── requirements.txt          # Python environment


## 📌 Requirements

pandas
numpy
scikit-learn
xgboost
matplotlib
seaborn
GEOparse
