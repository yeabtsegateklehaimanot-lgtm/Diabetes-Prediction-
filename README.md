#Diabetes Prediction & Evaluation Pipeline


📌 Overview

This project implements a two-phase machine learning pipeline for diabetes prediction and evaluation using clinical and demographic data.
It is designed for biomedical decision support, focusing on:

- Robust preprocessing of real-world health data

- Probabilistic classification using Gaussian Naïve Bayes

- Fair evaluation using patient-level alignment

- Visualization of diagnostic performance

The pipeline supports situations where predictions and true labels are stored in separate files and may not cover the same number of patients.


📂 Project Workflow

Phase 1: Train & Predict

1.Load training and test datasets

2.Preprocess data (cleaning, encoding, transformation)

3.Train a Gaussian Naïve Bayes model

4.Generate predictions and probabilities

5.Save results to diabetes_predictions.csv



Phase 2: Evaluate

1.Upload true-label CSV and prediction CSV

2.Align records using patient_id

3.Compute evaluation metrics

4.Generate performance plots



📊 Dataset Requirements

Training Dataset

Must include:

- patient_id

- diabetic (target label: 1 = diabetic, 0 = non-diabetic)

- Clinical and demographic features


Test Dataset

Must include:

- patient_id

- Same feature columns as training data
(Target label is optional)


🧹 Data Preprocessing

The following preprocessing steps are applied:

- Missing Values
Filled using the median of each feature to preserve data size.


- Categorical Encoding
Binary and categorical variables (e.g., gender, family history) are label-encoded.


- Feature Engineering

1.BMI category (normal / overweight / obese)

2.Age–BMI interaction

3.Pulse pressure (systolic − diastolic)

4.High glucose indicator

- Feature Transformation
Yeo–Johnson power transformation is applied to stabilize variance and improve model assumptions.


🤖 Model

- Algorithm: Gaussian Naïve Bayes

- Why Naïve Bayes?

  Probabilistic and interpretable

  Efficient for large biomedical datasets

  Well-suited to transformed continuous features



📈 Evaluation Metrics

The following metrics are reported:

- Accuracy

-Precision

-Recall

-F1-score

-Classification Report


Visualizations

-Confusion Matrix

-ROC Curve

-Precision–Recall Curve

These plots help assess performance, especially for the minority (diabetic) class.


📁 Output Files

diabetes_predictions.csv

- patient_id

- predicted_class

- y_prob (probability of diabetes)

▶️ How to Run

1.Install dependencies:

pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn


2.Run the script:

python diabetes_pipeline.py


3.Select files when prompted:

- Training CSV

- Test CSV

- True-label CSV

- Prediction CSV


🧪 Example Use Case

This pipeline is suitable for:

Academic assignments and theses

Biomedical machine learning research

Evaluating models when test labels are released later

Clinical risk stratification studies

📜 License & Data Source

Dataset License: CC BY 4.0
Data Source: Mendeley Data
https://data.mendeley.com/datasets/m8cgwxs9s6/2

Data Source: Mendeley Data

