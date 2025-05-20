## 🧠 RA Severity Prediction Using Gene Expression Data

This project uses publicly available gene expression data (from GEO dataset GSE93272) and machine learning to classify rheumatoid arthritis (RA) patients into severity levels based on their DAS28 scores.

### 📂 Project Structure

📁 RA-Severity-Prediction
│
├── data/                      # Raw and processed data files
├── notebooks/                 # Jupyter notebooks for EDA, preprocessing, modeling
├── src/                       # Scripts for loading, preprocessing, training
├── results/                   # Model performance metrics, plots, reports
├── expression_cleaned.csv     # Final normalized expression data
├── metadata_cleaned.csv       # Cleaned clinical metadata (including DAS28)
├── README.md                  # Project overview and instructions
└── requirements.txt           # Python dependencies

### 📊 Dataset

* Source: [GSE93272](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE93272)
* Platform: GPL570 (Affymetrix Human Genome U133 Plus 2.0 Array)
* Samples: Whole blood gene expression profiles from RA patients.
* Clinical Metadata: Includes DAS28 scores, gender, treatment response, etc.

### 🧪 Objective

Classify RA patients into mild, moderate, or severe groups based on DAS28 scores using:

* Gene expression profiles (microarray)
* Optional clinical metadata

### 🎯 Classification Labels (Target Variable)

* `Mild`: DAS28 < 3.2
* `Moderate`: 3.2 ≤ DAS28 ≤ 5.1
* `Severe`: DAS28 > 5.1

### 🛠️ Methods

1. Data Preprocessing:

   * Normalize expression data (log2 if needed)
   * Clean and map metadata
   * Map probe IDs to gene symbols using GPL570 annotations

2. Feature Selection:

   * Differential expression analysis (optional)
   * Clinical variables like age, gender, etc. (optional)

3. Machine Learning Models:

   * Random Forest
   * XGBoost
   * Logistic Regression
   * Support Vector Machine (SVM)

4. Model Evaluation:

   * Accuracy, Precision, Recall, F1-Score
   * Confusion matrix
   * ROC curves

### 📈 Results (Example)

| Model         | Accuracy | F1 Score |
| ------------- | -------- | -------- |
| Random Forest | 0.82     | 0.79     |
| XGBoost       | 0.85     | 0.81     |

### 📌 Requirements

Create a virtual environment and install the required packages:

```bash
pip install -r requirements.txt
```

Main libraries:

* `pandas`, `numpy`, `scikit-learn`, `xgboost`, `matplotlib`, `seaborn`, `GEOparse`

---

### 🚀 Run the Project

```bash
# Clone repository
git clone https://github.com/yourusername/RA-Severity-Prediction.git
cd RA-Severity-Prediction

# Run preprocessing
python src/preprocess.py

# Train and evaluate model
python src/train_model.py
```

Or explore via Jupyter notebooks in the `notebooks/` directory.

---

### 📚 Resources

* [GEO Accession Viewer: GSE93272](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE93272)
* [Affymetrix GPL570 Annotation File](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GPL570)

---

### 📌 TODO

* [ ] Add hyperparameter tuning (GridSearchCV)
* [ ] Explore multi-omics integration
* [ ] Improve feature selection with LASSO or PCA
* [ ] Add Streamlit demo (optional)

---






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
