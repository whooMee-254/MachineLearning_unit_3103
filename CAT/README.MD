# Student Exam Performance Prediction

# Problem Statement

Educational institutions often seek ways to identify students that are at risk of failing their exams. This project uses the `student-por.csv` dataset from the UCI Machine Learning Repository to predict whether a student will pass or fail.

# Dataset

- Source: UCI Machine Learning Repository  
- File Used: `student-por.csv`  
- Features: Age, gender, study time, parental education, failures, absences, and grades (G1, G2, G3), among others.  
- Target: A binary label indicating whether the student passed (1) or failed (0), derived from the average of G1, G2, and G3.

#  Approach

1. Data Preprocessing
   - Loaded and parsed the semicolon-separated dataset.
   - Cleaned the column names using `str.strip()`.
   - Encoded categorical variables using Label Encoding and One-Hot Encoding.
   - Created a binary `pass` column: students with average grade ≥ 10 are marked as "Pass".

2. Feature Engineering and Splitting
   - Dropped raw grade columns (G1, G2, G3) after target creation.
   - Split the dataset into training and testing sets (80/20 split).

3. Model Training
   - Trained two classifiers:
     - Logistic Regression
     - Decision Tree Classifier

4. Evaluation
   - Evaluated models on:
     - Accuracy
     - F1 Score
     - Confusion Matrix
   - Selected the better-performing model based on F1 Score.

# Results and Interpretation

- Model Performance:
  - Logistic Regression and Decision Tree both performed reasonably well.
  - Decision Tree achieved slightly better F1 scores, indicating it better balanced false positives and false negatives.
  
- Key Insights:
  - Final grade (`G3`) is strongly correlated with earlier grades (`G1`, `G2`).
  - Support programs (school and family) show some relationship with student success.
  - Female students tend to perform slightly better on average than male students.
  - Absences and past failures are predictive of low performance.


