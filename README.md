# The Credit Risk Classification Project

## An Overview of the Analysis

 We worked with a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

- Data Reading and Preparation: Read the `Resources/lending_data.csv` into a Pandas DataFrame. The dataset contained information on loans, and the goal was to predict the credit risk level for each loan. The data was split into features (X) and labels (y) accordingly.

- Data Splitting: The dataset was further split into training and testing sets using `train_test_split` from the `sklearn.model_selection` module, enabling the model to be trained on a portion of the data and evaluated on unseen data.

- Model Training and Evaluation - Using the Original Data: The logistic regression model was instantiated and fitted using the original training data (`X_train` and `y_train`). The model's performance was evaluated using metrics such as balanced accuracy, precision, recall, and classification report, providing insights into the model's ability to classify healthy and high-risk loans.

- Data Resampling with RandomOverSampler: To address the class imbalance issue, the `RandomOverSampler` from the `imbalanced-learn` library was used to create synthetic samples of the minority class (high-risk loans) to balance the class distribution.

Model Training and Evaluation -Using the Resampled Data: The logistic regression model was fitted again using the resampled training data (`X_train_resampled` and `y_train_resampled`). The model's performance was evaluated on the testing data using the same metrics as before.

## Results

 In the original data, the first model achieved a balanced accuracy score of `0.9520`, indicating good overall performance. The model displayed high precision `(0.85)` and recall `(0.91)` for class 1, suggesting it can effectively identify high-risk loans. However, after resampling the data, the resampled data model showed improvement, with a significantly higher balanced accuracy score of `0.9937`. The resampled model performed even better in classifying both healthy and high-risk loans, with a minor decrease in precision to `0.84` and significant improvement in recall to `0.99` for class 1. Overall, the second model outperformed first, making it the recommended model to use for credit risk classification.

## Tools Used

- **Python:** Programming language used for data manipulation, machine learning, and evaluation.
- **Jupyter Notebook:** Interactive environment for running and documenting code.
- **Libraries:** Numpy, Pandas, Scikit-learn, and Imbalanced-learn for data handling, machine learning, and dealing with imbalanced datasets.
- **Logistic Regression:** Machine learning algorithm used for binary classification.
- **Data Splitting:** Utilizing train-test split to divide the data into training and testing sets.
- **Metrics:** Balanced Accuracy Scoree, Confusion Matrix, Classification Report