Malware Analysis Dataset
Behaviour-Based Malware Pattern Classification using Machine Learning

This project focuses on analysing malware behaviour patterns using a machine-learning pipeline.
The goal is to classify malware behaviour based on extracted features and identify potential malicious patterns using text-based feature engineering (TF-IDF) and Naive Bayes classification.

📌 Project Overview

This repository contains:

A malware behaviour dataset (cleaned and structured)

A Python ML pipeline for preprocessing, vectorizing, and classification

Performance metrics such as:

Accuracy

Confusion Matrix

Class distribution

ROC curve (if binary)

The project demonstrates end-to-end processing from raw data → cleaned form → modelling → evaluation.

📂 Dataset Details

The dataset used is:
PROJECTFILE.xlsx

It contains malware behaviour attributes such as:

System calls

Registry modifications

File operations

Network behaviours

Frequency & pattern indicators

A target column: t_4 (Malware Behaviour Class)

The target label is handled as:

Numeric class if >90% values are numeric

Categorical class otherwise

Rare classes with <2 samples are merged into "_OTHER_" to maintain stratified sampling consistency.

🧹 Data Preprocessing Steps

Load dataset from Excel

Inspect shape, missing values, and target distribution

Check whether target column is numeric or string

Drop missing or invalid rows

Merge rare classes (<2 occurrences)

Feature conversion

All columns → strings

Row-wise concatenation

Train/test split (Stratified)

🔠 Feature Engineering
TF-IDF Vectorization

All collected behavioural attributes are converted into a single text string per row:

X_text = X.astype(str).agg(' '.join, axis=1)


Then TF-IDF is applied to transform text into feature vectors.

🤖 Machine Learning Model

Algorithm used:

✅ Multinomial Naive Bayes (best for text classification)

Pipeline:

TF-IDF Vectorizer

Label Encoding

Naive Bayes Classifier

Performance Evaluation

📊 Evaluation Metrics

The following metrics are generated:

✔ Accuracy
✔ Confusion Matrix
✔ Class distribution plot
✔ ROC Curve (only if binary classes exist)

These visualizations help understand:

Classification strength

Error distribution

Class-wise prediction efficiency

🧪 Results (Sample Output)

Accuracy: (Varies based on cleaned dataset)

Confusion Matrix: Displays true vs predicted classes

ROC Curve: Plotted automatically for binary cases

📦 Installation & Usage
1. Clone the repository
git clone https://github.com/menakag878-lgtm/ML-data-cleaning
cd ML-data-cleaning

2. Install dependencies
pip install -r requirements.txt

3. Run the script
python malware_analysis.py

📁 Repository Structure
├── PROJECTFILE.xlsx          # Dataset  
├── malware_analysis.py       # Full ML analysis code  
├── README.md                 # Documentation  
└── /plots                    # Generated visual plots (optional)

🚀 Future Enhancements

Add more malware behaviour features

Use advanced models (Random Forest, XGBoost, SVM)

Integrate SHAP for behaviour explainability

Build a web dashboard for real-time malware classification

Convert pipeline into a deployable API

👩‍💻 Author

Menaka G
DATA SCIENCE STUDENT
Project completed as part of an external training program.

⭐ Support

If you find this project useful, please star ⭐ the repository!
