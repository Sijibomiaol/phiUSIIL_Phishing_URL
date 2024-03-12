This project focuses on the classification of URLs into phishing and non-phishing categories. Here's a summary of the steps involved:

1. **Data Loading and Exploration**: The dataset containing URL features and labels is loaded using pandas. Object columns are identified and dropped, leaving only numerical features for analysis.

2. **Data Preprocessing**: The dataset is split into training and testing sets using train_test_split for model evaluation. Correlation analysis is performed to identify correlated features and reduce redundancy.

3. **Feature Selection**: Mutual information is utilized to select the top features relevant for classification. The SelectKBest method is applied to choose the top 10 features based on mutual information scores.

4. **Model Training - LightGBM**: A LightGBM classifier is trained on the selected features with binary classification objective. Model performance is evaluated using cross-validation and feature importance is visualized.

5. **Model Evaluation - LightGBM**: The trained LightGBM model is evaluated on the test set using accuracy and classification report metrics.

6. **Model Training - XGBoost**: Another classification model, XGBoost, is trained using a pipeline approach with hyperparameter tuning using Bayesian optimization.

7. **Model Evaluation - XGBoost**: The optimized XGBoost model is evaluated on the test set using accuracy and classification report metrics. Feature importance is visualized using plot_importance.

Both LightGBM and XGBoost models achieve high accuracy (close to 1.00) on the test set and exhibit excellent precision, recall, and F1-score for both classes (phishing and non-phishing URLs). Overall, the project demonstrates effective classification of URLs using machine learning techniques.

Please Take Note

Certainly! In this project, feature selection plays a crucial role in improving model performance by identifying the most informative features and reducing dimensionality. Initially, the dataset contains 54 features, which could potentially lead to overfitting and increased computational complexity. Therefore, selecting the most relevant features is essential for building efficient and accurate classification models.

Three methods for feature selection are employed in this project:

Correlation Analysis: Correlation analysis is performed to identify features that are highly correlated with each other. Highly correlated features may provide redundant information, leading to overfitting and inefficient model training. By removing these redundant features, the dimensionality of the dataset is reduced while preserving the most relevant information.

Mutual Information: Mutual information measures the dependency between two variables and is particularly useful for feature selection in classification tasks. It quantifies how much information one feature provides about the target variable (in this case, whether a URL is phishing or not). Features with high mutual information scores are considered more informative for the classification task and are thus selected for model training.

SelectKBest: SelectKBest is a univariate feature selection method that selects the top K features based on a given scoring function. In this project, mutual_info_classif is used as the scoring function to evaluate the relevance of each feature to the target variable. By selecting the top K features with the highest mutual information scores, the most informative features are retained for model training.

Among these three methods, SelectKBest with mutual information scoring is used to select the top 10 features for model training in both LightGBM and XGBoost classifiers. This method is preferred because it directly considers the relationship between each feature and the target variable, making it well-suited for classification tasks.

As for the model used in training the dataset, two powerful gradient boosting algorithms are employed:

LightGBM (Light Gradient Boosting Machine): LightGBM is a gradient boosting framework developed by Microsoft that is known for its high efficiency, speed, and accuracy. It is designed to handle large datasets efficiently and provides excellent performance for classification tasks. In this project, a LightGBM classifier with a binary classification objective is trained on the selected features.

XGBoost (Extreme Gradient Boosting): XGBoost is another gradient boosting algorithm known for its scalability, speed, and performance. It is widely used in machine learning competitions and production environments due to its accuracy and efficiency. In this project, an XGBoost classifier is trained using a pipeline approach with hyperparameter tuning using Bayesian optimization.

Both LightGBM and XGBoost models are powerful ensemble methods that are well-suited for classification tasks, and they achieve high accuracy and performance in this project. The choice between the two may depend on factors such as the specific requirements of the application, computational resources, and the need for interpretability.

