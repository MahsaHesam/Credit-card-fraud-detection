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

# Random Forest Model
# KNN Model
#

**11. Data Ethics:**

This Dataset is publicly available on Kaggle.

**12. Limitations:**
- Our Dataset

  -*limited dataset* was not able to fully replicate a model in a real world scenario because of the limited access to authentic credit card info
  - *optimisation* there was little to no need of cleaning or optimizing our dataset because the original dataset was only designed to create a detection model
  - *limited features* lack of detail in our dataset prevented us from drawing a more in-depth analysis and derive more detailed insights
  - *scenarios* The data may not represent all possible credit card fraud scenarios and types. As a result, the models might not be equipped to handle emerging fraud techniques or highly sophisticated fraud strategies.
  
    

**Folders:**

- Presentation: Containing PowerPoint presentation
- Resources: Containing our Dataset
- Credit card Fraud Detection.ipynb: Our Initial Data analysis
- Data_Modelling.ipynb: ML Analysis
- Readme




