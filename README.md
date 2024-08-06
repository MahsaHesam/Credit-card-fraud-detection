# credit card fraud detection

![image](https://github.com/user-attachments/assets/32cce6b1-83bc-41da-8843-7e4f8510ce98)




Team Members: Mahsa Hesampour, Riona Espedido, Erin Nicol

# Executive Summary:

Credit card fraud has become an increasingly prevalent issue in today's digital age.
Sophisticated cybercriminals employ various tactics, from phishing scams to data breaches, to steal sensitive financial information. As a result, the financial burden on individuals and businesses is substantial. To combat this growing threat, robust fraud detection systems are essential. These systems utilize advanced algorithms and machine learning to analyze transaction patterns, identify anomalies, and prevent fraudulent activities in real-time. By proactively detecting and mitigating fraud, financial institutions can safeguard their customers' assets and maintain trust.  

# Introduction:
 
This project aims to leverage the power of machine learning to develop a robust and efficient credit card fraud detection system. By analyzing vast amounts of transaction data, the model will identify patterns indicative of fraudulent activity, enabling real-time detection and prevention of financial losses. This research will explore various machine learning algorithms and techniques to optimize fraud detection accuracy and minimize false positives, ultimately contributing to a more secure financial ecosystem.

# Approach:

![image](https://github.com/user-attachments/assets/b68a7a9e-5ab4-42f8-8380-835a0aa91f84)

**1. Problem:**
The primary objective of this project is to predict credit card fraud

**2. Data Sourcing:**
The dataset for this project was sourced from the following link:
https://www.kaggle.com/datasets/dhanushnarayananr/credit-card-fraud

**3. Variables**

- Distance from home **:** This could indicate unusual transaction locations.

- Distance from last transaction **:** Large distances might suggest fraudulent activity.

- Ratio to median purchase price **:** Outliers in purchase amounts can be indicative of fraud.

- Repeat retailer **:** Frequent transactions at the same retailer might be normal or fraudulent, depending on other factors.

- Used chip **:** This could be relevant if chip-based transactions are more secure.

- Used pin number **:** PIN usage might correlate with fraud risk.

- Online order **:** Online transactions often have fraud patterns that are different from those in-store.

- Fraud **:** This is the target variable, indicating whether a transaction is fraudulent.

**4. Exploratory Data Analysis and Dependencies:**

We conducted an in-depth investigation and evaluation of the raw data. 


**5. Data Preparation:**

Spark Installation:

- Defines the Spark version.
- Sets up the environment variables for Spark and Java.
- Installs Java OpenJDK.
- Downloads and extracts the Spark archive.
- Installs Findspark and PySpark libraries.
- Sets up environment variables for Spark's home directory.
- Initializes Findspark.
 -Creates a SparkSession with an application name.
- Prints the Spark version for verification.

**6. Data Loading and Preprocessing:**

- Uploads a CSV file using Colab's file upload widget.
- Reads the uploaded CSV file into a Spark DataFrame named df using spark.read.csv.
- Creates temporary views for the DataFrame named transactions using df.createOrReplaceTempView.
  
**7. Feature and Target Definition:**

- This section define the feature set (X) by selecting all columns from df except the target column ("fraud").
Defines the target vector (y) by converting the "fraud" column in the DataFrame to a NumPy array.

**8. Splitting Data into Train and Test Sets:**

- This section convert the Spark DataFrames (X and y) to Pandas DataFrames (X_pd and y_pd).
Splits the Pandas DataFrames into training and testing sets using train_test_split from scikit-learn.

**9. Data Scaling:**

- This section creates a StandardScaler instance named scaler.


**10. Findings:**

![image](https://github.com/user-attachments/assets/0099620a-9bf7-458f-a52a-024a6aabd776)

- distance_from_home  had the strongest positive correlation with fraud  which suggests that fraudulent transactions tend to occur further away from the cardholder's home. 
- "Distance_from_last_transaction" and "repeat_retailer" also show a moderate positive correlation with fraud, indicating that transactions that occur far from the previous transaction and those made at new retailers are more likely to be fraudulent. 
- "Used_chip" and "used_pin_number" have a weak negative correlation with fraud, suggesting that using a chip card or PIN number may slightly decrease the likelihood of fraud. 
- "Online_order" has a strong positive correlation with fraud, indicating that online transactions are more likely to be fraudulent.



![image](https://github.com/user-attachments/assets/8931a658-eabb-48de-abea-e5c5a92fbad3)

**Confusion Matrix:**

The confusion matrix provides a breakdown of how accurately a classification model performed on a dataset. In this case, we have two classes: 0 and 1.
- Predicted 0 / Actual 0: 228025 instances were correctly classified as class 0.
- Predicted 1 / Actual 0: 0 instances were incorrectly classified as class 1 (false positives).
- Predicted 0 / Actual 1: 2 instances were incorrectly classified as class 0 (false negatives).
- Predicted 1 / Actual 1: 21973 instances were correctly classified as class 1.
  
**Accuracy Score:**
  
The accuracy score is 0.999992, which means the model correctly classified 99.9992% of the instances.

**Classification Report:**

This report provides a more detailed evaluation of the model's performance, including:
- Precision: The ability of the model to correctly predict positive instances (class 1) out of all predicted positive instances. Here, precision is 1.00 for both classes, indicating that the model is very good at identifying true positives.
- Recall: The ability of the model to correctly identify all actual positive instances (class 1). Recall is also 1.00 for both classes, indicating that the model is very good at capturing all true positives.
- F1-score: The harmonic mean of precision and recall, providing a balanced measure of the model's performance. The F1-score is 1.00 for both classes, indicating excellent performance.
- Support: The number of instances in each class.
- 
**Summary:**
  
The model demonstrates exceptional performance on this dataset, with near-perfect accuracy, precision, recall, and F1-scores for both classes. However, it's important to consider the context of this dataset and the potential limitations of such high scores. It's possible that the dataset is imbalanced or that the model is overfitting to the training data. Further analysis would be needed to draw more definitive conclusions.


![image](https://github.com/user-attachments/assets/35bd2184-9013-48b7-81a4-6d6d61ba4019)



**Confusion Matrix:**

The confusion matrix provides a breakdown of how accurately a classification model performed on a dataset. In this case, we have two classes: 0 and 1.
- Predicted 0 / Actual 0: 70834 instances were correctly classified as class 0.
- Predicted 1 / Actual 0: 3 instances were incorrectly classified as class 1 (false positives).
- Predicted 0 / Actual 1: 22 instances were incorrectly classified as class 0 (false negatives).
- Predicted 1 / Actual 1: 71299 instances were correctly classified as class 1.
- 
**Accuracy Score:**
  
The accuracy score is 0.9998241393379198, which means the model correctly classified 99.9824% of the instances.

**Classification Report:**

This report provides a more detailed evaluation of the model's performance, including:
- Precision: The ability of the model to correctly predict positive instances (class 1) out of all predicted positive instances. Here, precision is 1.00 for both classes, indicating that the model is very good at identifying true positives.
- Recall: The ability of the model to correctly identify all actual positive instances (class 1). Recall is also 1.00 for both classes, indicating that the model is very good at capturing all true positives.
- F1-score: The harmonic mean of precision and recall, providing a balanced measure of the model's performance. The F1-score is 1.00 for both classes, indicating excellent performance.
- Support: The number of instances in each class.
- 
**Summary:**
  
The model demonstrates exceptional performance on this dataset, with near-perfect accuracy, precision, recall, and F1-scores for both classes. However, it's important to consider the context of this dataset and the potential limitations of such high scores. It's possible that the dataset is imbalanced or that the model is overfitting to the training data. Further analysis would be needed to draw more definitive conclusions.

**11. Data Ethics:**

This Dataset is publicly available on Kaggle.

**12. Limitations:**
- **Our Dataset**
- Synthetic Data: Due to the limited access to authentic credit card information, our synthetic dataset was unable to fully replicate the complexities of a real-world scenario This limitation may affect the model's generalizability and performance in practical applications.
- Optimization: The dataset was designed specifically for fraud detection, which meant there was minimal need for data cleaning or optimization. However, this also meant that the models were not tested against real-world challenges such as noisy or incomplete data.
- Limited Features: The dataset lacked detailed information and had a limited number of features, which restricted our ability to perform a more in-depth analysis and derive detailed insights.
- Scenarios: The synthetic data may not encompass all possible credit card fraud scenarios and types. As a result, the models may not be fully equipped to handle more sophisticated credit card fraud that could be encountered in real-world settings.

**Performace issues using SQL in Colab compared to Python** 
- Execution Time Of  queries in Google Colab: We found running SQL commands was slower compared Python  

    

**Folders:**

- Presentation: Containing PowerPoint presentation
- Resources: Containing our Dataset
- Main codes for analysis: Containing all our analysis




