# The Credit Risk Classification Project

## An Overview of the Analysis

 Given a dataset of historical lending activity from a peer-to-peer lending services company, a supervised learning model is built that can identify the creditworthiness of borrowers.

 ### Steps

- __Data Reading and Preparation:__ Read the `Resources/lending_data.csv` into a Pandas DataFrame. The dataset contained information on loans, and the goal is to predict the credit risk level for each loan. The data is split into features (X) and labels (y) accordingly.

- __Data Splitting:__ The dataset is further split into training and testing sets using `train_test_split` from the `sklearn.model_selection` module, enabling the model to be trained on a portion of the data and evaluated on unseen data.

- __Model Training and Evaluation:__ Using the original `lending_data.csv` data, a logistic regression model is instantiated and fitted using the original training data (`X_train` and `y_train`). The model's performance is evaluated using the follwing metrics: balanced accuracy, precision, recall, and classification report, providing insights into the model's ability to classify healthy and high-risk loans.

- __Data Resampling with RandomOverSampler:__ To address the class imbalance issue, the `RandomOverSampler` from the `imbalanced-learn` library is used to create synthetic samples of the minority class (high-risk loans) to balance the class distribution.

- __Model Training and Evaluation:__ The logistic regression model is fitted again using the resampled training data (`X_train_resampled` and `y_train_resampled`). The model's performance is evaluated on the testing data using the same metrics as before.

## Results

In the original data, the first model achieves a balanced accuracy score of `0.9520`, indicating good overall performance. The model displays high precision `(0.85)` and recall `(0.91)` for class 1, suggesting it can effectively identify high-risk loans. However, after resampling the data, the resampled data model shows improvement, with a significantly higher balanced accuracy score of `0.9937`. The resampled model performs even better in classifying both healthy and high-risk loans, with a minor decrease in precision to `0.84` and significant improvement in recall to `0.99` for class 1. Overall, the second model outperforms the first, recommendeding it for use to cassify credit risk.

## Tools Used

- **Python:** Programming language used for data manipulation, machine learning, and evaluation.
- **Jupyter Notebook:** Interactive environment for running and documenting code.
- **Libraries:** Numpy, Pandas, Scikit-learn, and Imbalanced-learn for data handling, machine learning, and dealing with imbalanced datasets.
- **Logistic Regression:** Machine learning algorithm used for binary classification.
- **Data Splitting:** Utilizing train-test split to divide the data into training and testing sets.
- **Metrics:** Balanced Accuracy Scoree, Confusion Matrix, Classification Report
