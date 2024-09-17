# Anomaly Detection in Financial Bank Transactions

<div style="text-align: center;">
    <img src="https://developer-blogs.nvidia.com/wp-content/uploads/2021/03/featured_img_devblogs-494.png" alt="Project Overview" width="600" height="300">
</div>


# Project Overview
This project focuses on detecting anomalies in financial bank transactions by combining rule-based approaches and advanced clustering techniques. The primary objective is to strengthen financial security by identifying unusual transaction patterns that may indicate fraudulent activities or irregularities. This initiative is part of a broader effort to apply machine learning and data mining techniques to safeguard financial systems.

<br>

# Key Components
<br>
1.Data Description  
Source: Financial transaction datasets stored in parquet format.
Data Structure: The data includes the following key columns:

<ul> <li><b>CUST_CUSTNO</b>: Unique customer identifier.</li> <li><b>ACC_BUSINESSTYPE</b>: Type of business (e.g., individual, enterprise).</li> <li><b>ACC_ACCNO</b>: Account number associated with the transaction.</li> <li><b>AMOUNT</b> and <b>AMOUNTORIG</b>: Transaction amounts in different currencies.</li> <li><b>VALUEDATE</b>: Date the transaction was recorded.</li> <li><b>CONTRA_ACCNO</b>: Contra account number involved in the transaction.</li> <li>Additional transaction-specific details such as <b>BRANCH_OFFICE</b>, <b>REASON1</b>, etc.</li> </ul> <br>
2. Rule-Based Anomaly Detection
Objective: Implement predefined rules provided by the bank to identify suspicious transactions and anomalies, such as customers making frequent high-value transactions within short time frames.
Key Rule Example: A rule targeting customers who made both deposits and withdrawals of 100,000 VND on the same day, which could indicate irregular business practices.

<br>
3. FP-Growth Analysis
Objective: Apply the FP-Growth algorithm to mine frequent patterns and discover association rules within the transaction data.
Approach: Group customers by CUST_CUSTNO and analyze transaction amounts to differentiate between normal and anomalous patterns. Metrics such as lift and conviction are used to evaluate the significance of these rules.

<br>
4. Clustering-Based Anomaly Detection
Objective: Utilize multilevel clustering to detect anomalies that may not be captured by rule-based methods.
Approach:

<ul> <li>Apply clustering algorithms (e.g., k-means, DBSCAN) to group transactions based on similarity across various features (amounts, dates, and customer profiles).</li> <li>Compare clustering results with the anomalies identified through rule-based methods.</li> <li>Visualize clusters and anomalies using **color-coded graphs** and **plots** for better interpretation and communication.</li> </ul> <br>
5. Summaries and Reporting
Regular Updates: Periodic reports on findings from both rule-based and clustering methods, including key insights and visualizations.
Interaction with Stakeholders: Continuous collaboration with the bank to verify findings, adjust detection rules, and ensure the accuracy of anomaly detection.
<br>
6. Tools and Technologies
Data Processing: Python, Pandas, and Dask for efficient handling and processing of large financial datasets.
Pattern Mining: FP-Growth for mining frequent patterns and generating association rules.
Clustering: Scikit-learn, with visualization tools like Matplotlib and Seaborn for plotting results.
Data Storage: Integration with Google Drive for storing and managing parquet files.
<br>
7. Additional Enhancements
Anomaly Filters: Custom rules were developed to detect transactions involving unusual deposit and withdrawal patterns (e.g., where deposits are greater than 6,000,000 VND and withdrawals are ≥95% of the deposited amount).
Multilevel Clustering: Added multilevel clustering techniques to identify anomalous clusters and compared them with rule-based anomalies to find overlaps or missed detections.

