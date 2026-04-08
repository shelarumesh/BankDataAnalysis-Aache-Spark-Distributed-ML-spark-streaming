# BankDataAnalysis-Aache-Spark-Distributed-ML-spark-streaming
# Distributed Machine Learning in Banking: Predictive & Real-Time Analytics

## Project Overview
This project addresses the challenges of "Big Data" in the banking sector. As banks generate millions of transactions daily, traditional systems often fail to process and analyze this data efficiently. By using a distributed computing ecosystem, this project demonstrates how to store vast amounts of data, predict customer behavior (specifically for term deposits), and monitor transactions in real-time.

---

## Tech Stack
* **Storage:** Hadoop (HDFS)
* **Data Warehouse:** Apache Hive
* **Processing Engine:** Apache Spark (Core & SQL)
* **Machine Learning:** Spark MLlib
* **Real-Time Processing:** Spark Streaming

---

## Step-by-Step Implementation

### 1. Data Ingestion & Storage
The raw banking data (`bank.csv`) is uploaded to the **Hadoop Distributed File System (HDFS)**. This ensures that the data is stored across a cluster of machines, providing fault tolerance and high availability.

### 2. Data Management with Hive
Using **Apache Hive**, we create a structured schema over the raw CSV file. This allows us to perform SQL-like queries to filter and organize data. It acts as our "Data Warehouse," making it easy to pull specific customer segments for analysis.

### 3. Exploratory Data Analysis (EDA) with Spark
We use **Apache Spark** to perform in-memory analysis. Spark is much faster than traditional tools because it avoids frequent disk writes. During this stage, we:
* Identify trends (e.g., how account balance affects loan subscriptions).
* Handle missing values and outliers.
* Clean the data for machine learning.

### 4. Data Preprocessing
Before building the model, we prepare the features:
* **String Indexing:** Converting text categories (like "job") into numbers.
* **Vector Assembler:** Combining all feature columns into a single vector required by the Spark ML engine.

### 5. Real-Time Transaction Monitoring
We implement **Spark Streaming** to simulate a live transaction environment. This allows the system to analyze incoming data in "micro-batches," enabling immediate fraud detection and live customer alerts.

---

## Model Selection

For this project, we selected the **Random Forest Classifier**.

### Why Random Forest?
1.  **Scalability:** It works exceptionally well in a distributed environment, as it builds multiple decision trees in parallel.
2.  **Accuracy:** It is robust against overfitting and handles the non-linear relationships often found in banking data (like the complex link between age, balance, and saving habits).
3.  **Efficiency:** It can handle both numerical and categorical data with minimal manual tuning.

### Evaluation Metrics
The model is evaluated using the **Area Under the ROC Curve (AUC)**. 
$$AUC = \int_{0}^{1} TPR(FPR) \, dFPR$$
This metric helps us understand how well the model distinguishes between customers who will subscribe and those who won't, ensuring our marketing campaign targets the right people.

---

## Conclusion & Success Steps

The project successfully demonstrates that distributed systems are essential for modern banking. By following these final steps, the system provides maximum value:

1.  **Identify High-Value Customers:** The predictive model allows the bank to focus its marketing budget on customers with the highest probability of conversion, increasing ROI.
2.  **Enable Real-Time Safety:** The streaming component ensures that suspicious activities are flagged within seconds, protecting both the bank and the customer.
3.  **Ensure Scalability:** Because the architecture is built on Hadoop and Spark, the bank can easily scale its processing power as its customer base grows simply by adding more nodes to the cluster.
4.  **Operational Efficiency:** Moving from "Batch Processing" to "Real-Time Insight" allows the bank to remain agile and competitive in a fast-paced digital economy.
