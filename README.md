# Gaussian Generative Model (From Scratch)

This repository contains the implementation and evaluation of a Gaussian Generative Model
for classification, developed from scratch as part of Assignment 3.

The objective is to understand probabilistic generative classifiers, parameter estimation,
regularization, and model evaluation using standard classification metrics.

------------------------------------------------------------

Assignment Objective

- Implement a Gaussian generative classifier from scratch.
- Estimate class priors, class means, and covariance matrices.
- Apply covariance regularization to improve numerical stability.
- Tune hyperparameters using validation data.
- Evaluate classification performance on unseen test data.
- Analyze misclassifications using a confusion matrix.

------------------------------------------------------------

Dataset & Preprocessing

- Dataset loaded using scikit‑learn utilities.
- Data split into:
  - Training set: 70%
  - Validation set: 15%
  - Test set: 15%
- Stratified splitting to preserve class distribution.
- Features standardized using StandardScaler.
- Labels encoded as integer class indices.

------------------------------------------------------------

Gaussian Model Description

Model Type:
- Multivariate Gaussian Generative Classifier
- Shared covariance matrix across all classes

Model Parameters:
- Class prior probabilities (π_k)
- Class mean vectors (μ_k)
- Shared covariance matrix (Σ)
- Regularization parameter (λ)

------------------------------------------------------------

Training Procedure

1. Compute class prior probabilities from training labels.
2. Compute class‑specific mean vectors.
3. Compute a pooled covariance matrix across all classes.
4. Apply regularization to covariance matrix:
   Σ_reg = Σ + λI
5. Store all learned parameters for prediction.

All steps are implemented manually using NumPy.

------------------------------------------------------------

Prediction

- For each test sample:
  - Compute log‑likelihood under each class Gaussian.
  - Add log‑prior probability.
  - Select class with maximum log‑posterior score.
- Output predicted class labels.

------------------------------------------------------------

Hyperparameter Tuning

- Regularization parameter λ is tuned.
- Multiple λ values evaluated.
- Model trained on training set.
- Validation accuracy used to choose best λ.
- Final model retrained using best λ and evaluated on test set.

------------------------------------------------------------

Evaluation Metrics

- Classification Accuracy
- Macro Precision
- Macro Recall
- Macro F1‑Score
- Confusion Matrix

Metrics are computed on the test set.

------------------------------------------------------------

Results & Observations

- Regularization significantly improves covariance stability.
- Gaussian model provides strong performance with low computational cost.
- Most errors occur between classes with similar feature distributions.
- Shared covariance simplifies training but can limit class separation.

------------------------------------------------------------

Implementation Notes

- Gaussian model implemented fully from scratch.
- scikit‑learn is used only for:
  - Data loading
  - Data splitting
  - Standardization
  - Evaluation metrics
- Random seeds fixed for reproducibility.

------------------------------------------------------------

Technologies Used

- Python
- NumPy
- scikit‑learn
- Matplotlib
- Seaborn

------------------------------------------------------------

Authors

Developed by Mohammed Yasser Mohammed
with classmates for a course assignment
email: es-mohamed.yasser2027@alexu.edu.eg
