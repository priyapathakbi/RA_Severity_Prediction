# 🧠 Machine Learning-Based Prediction of Rheumatoid Arthritis (RA) Severity Using GWAS Data

## 📌 Objective

The goal of this project is to develop a machine learning model capable of predicting the severity of Rheumatoid Arthritis (RA)—categorized as mild, moderate or severe based on Single Nucleotide Polymorphisms (SNPs) derived from publicly available Genome-Wide Association Studies (GWAS) datasets.

### 🧬 Methodology

## 1. Data Collection
Publicly available GWAS datasets relevant to RA will be sourced from established repositories, including:
- [GWAS Catalog](https://www.ebi.ac.uk/gwas/)
- [UK Biobank](https://www.ukbiobank.ac.uk/)
- [dbGaP (Database of Genotypes and Phenotypes)](https://www.ncbi.nlm.nih.gov/gap)
- [FinnGen](https://www.finngen.fi/en)

## 2. Preprocessing
- Filter SNPs significantly associated with RA severity using appropriate statistical thresholds (e.g., p-value).
- Remove low-quality or missing genotype data.
- Normalize the input dataset for machine learning compatibility.

## 3. Feature Engineering
- Genotype encoding: Convert SNP data into numerical representations (e.g., 0, 1, 2 for homozygous reference, heterozygous, homozygous alternate).
- Class labeling: Assign severity labels (mild/moderate/severe) to samples based on available clinical metadata.

## 4. Model Training
- Implement and train classification models such as:
- Random Forest
- XGBoost (Extreme Gradient Boosting)
- Hyperparameter tuning using cross-validation to optimize performance.

## 5. Technologies Used
- Python 3.9
- Pandas, NumPy
- scikit-learn
- XGBoost
- Jupyter Notebook

### 6. Validation and Evaluation
- Assess model accuracy, precision, recall, and F1-score on a test dataset.
- Analyze feature importance to identify influential SNPs.
- Visualize performance using confusion matrix and ROC curves.

## 🎯 Expected Outcomes

- A machine learning pipeline capable of predicting RA severity based on SNP data.
- Identification of critical genetic markers associated with disease progression.
- Foundational insights to support the development of personalized treatment strategies and precision medicine in RA.
