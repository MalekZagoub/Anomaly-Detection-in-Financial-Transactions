# Anomaly Detection in Financial Bank Transactions

<div style="text-align: center;">
    <img src="https://developer-blogs.nvidia.com/wp-content/uploads/2021/03/featured_img_devblogs-494.png" alt="Project Overview" width="600" height="300">
</div>



# Project Overview
This project focuses on detecting anomalies in financial bank transactions by leveraging both rule-based approaches and advanced clustering techniques. The primary objective is to enhance financial security by identifying unusual patterns in transaction data that may indicate fraudulent activities or other irregularities. The project is part of a broader effort to apply machine learning and data mining techniques in the field of financial security.
Key Components

# 1. Data Description
Source: Financial transaction datasets stored in parquet format.
Data Structure: The data includes columns such as:

CUST_CUSTNO: Customer identifier.

ACC_BUSINESSTYPE: Type of business (e.g., individual, enterprise).

ACC_ACCNO: Account number.

AMOUNT and AMOUNTORIG: Transaction amounts in different currencies.
VALUEDATE: Transaction date.

CONTRA_ACCNO: Contra account number.

Other transaction-specific details like BRANCH_OFFICE, REASON1, etc.

# 2. Rule-Based Anomaly Detection
Objective: Implement predefined rules provided by the bank to filter and identify anomalies.
# 3. FP-Growth Analysis
Objective: Apply the FP-Growth algorithm to mine frequent patterns and association rules in the transaction data.
Approach: Group customers by CUST_CUSTNO and their respective transaction amounts, and identify normal and anomalous transaction patterns by analyzing metrics such as lift and conviction.
# 4. Clustering-Based Anomaly Detection
Objective: Utilize multilevel clustering to detect anomalies that may not be captured by rule-based methods.
Approach:
Apply clustering algorithms to group transactions based on similarity.<br>
Compare clustering results with anomalies detected by rule-based methods.<br>
Visualize clusters and the distribution of anomalies using color-coded graphs and plots.<br>
# 5. Summaries and Reporting
Regular Updates: Provide periodic summaries of findings, including rule-based results, clustering insights, and comparisons. <br>
Interaction with Stakeholders: Communicate with the bank to verify findings and adjust the detection rules as needed.
# 6. Tools and Technologies
Data Processing: Python, Pandas, Dask for handling large datasets.

Pattern Mining: FP-Growth for association rule mining.

Clustering: Scikit-learn, visualization with Matplotlib and Seaborn.

Data Storage: Google Drive integration for managing parquet files.

