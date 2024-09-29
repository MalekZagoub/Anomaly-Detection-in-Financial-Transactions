# Anomaly Detection in Financial Bank Transactions

<div style="text-align: center;">
    <img src="https://developer-blogs.nvidia.com/wp-content/uploads/2021/03/featured_img_devblogs-494.png" alt="Project Overview" width="600" height="300">
</div>


# Project Overview
This project focuses on detecting anomalies in financial bank transactions by combining rule-based approaches and advanced clustering techniques. The primary objective is to strengthen financial security by identifying unusual transaction patterns that may indicate fraudulent activities or irregularities. This initiative is part of a broader effort to apply machine learning and data mining techniques to safeguard financial systems.

<br>

<h2>Key Components</h2>

<h3>1. Data Description</h3>
<p><strong>Source</strong>: Financial transaction datasets stored in parquet format.</p>
<p><strong>Data Structure</strong>: The dataset consists of multiple key columns that capture essential transaction details, including:</p>

<ul>
  <li><strong>CUST_CUSTNO</strong>: A unique identifier assigned to each customer.</li>
  <li><strong>ACC_BUSINESSTYPE</strong>: The type of business associated with the account (e.g., individual, enterprise, non-bank credit institution).</li>
  <li><strong>ACC_ACCNO</strong>: The account number from which the transaction was made.</li>
  <li><strong>AMOUNT</strong> and <strong>AMOUNTORIG</strong>: The transaction amounts, provided in both the account's currency and the original transaction currency.</li>
  <li><strong>VALUEDATE</strong>: The recorded date of the transaction, which helps in tracking time-based patterns.</li>
  <li><strong>CONTRA_ACCNO</strong>: The counterparty account involved in the transaction, used to identify the destination or source of the transaction.</li>
  <li>Additional columns capturing transaction-specific details, such as <strong>BRANCH_OFFICE</strong> (location of the transaction), <strong>REASON1</strong> (description of the transaction), and more.</li>
</ul>

<p>This structure provides a detailed framework for both pattern mining and anomaly detection.</p>

<h3>2. Rule-Based Anomaly Detection</h3>
<p><strong>Objective</strong>: To implement and apply predefined rules, provided by the bank, for identifying suspicious transactions and patterns indicative of fraudulent or irregular behavior.</p>

<ul>
  <li><strong>Focus</strong>: Rules are designed to capture activities such as frequent high-value transactions or unusual deposit-withdrawal patterns.</li>
  <li><strong>Key Rule Example</strong>: A rule targeting customers who deposit and withdraw equal amounts on the same day, where the transaction amounts exceed a certain threshold. This may signal irregular business practices or attempts to circumvent detection systems.</li>
</ul>

<p>This rule-based approach serves as the foundation for flagging known suspicious behaviors before exploring more advanced methods.</p>

<h3>3. FP-Growth Analysis</h3>
<p><strong>Objective</strong>: To leverage the FP-Growth algorithm for discovering frequent patterns and generating association rules within the transaction dataset.</p>

<ul>
  <li><strong>Approach</strong>: Transactions are grouped by <strong>CUST_CUSTNO</strong> (customer ID) to evaluate patterns in transaction amounts, helping to differentiate between normal customer behavior and anomalies.</li>
  <li><strong>Metrics</strong>: The analysis employs key metrics such as <strong>lift</strong> and <strong>conviction</strong> to assess the significance of the discovered rules, with higher values indicating stronger relationships between variables (e.g., amounts and transaction frequency).</li>
</ul>

<p>This analysis provides deeper insights into transaction behavior and identifies new potential rules for anomaly detection.</p>

<h3>4. Clustering-Based Anomaly Detection</h3>
<p><strong>Objective</strong>: To complement the rule-based method with clustering algorithms that detect outliers and anomalies that might not follow predefined rules.</p>

<ul>
  <li><strong>Approach</strong>: Utilize algorithms such as <strong>k-means</strong> and <strong>DBSCAN</strong> to group transactions based on similarity across features like transaction amount, dates, and customer profiles.</li>
  <li><strong>Comparison</strong>: The results from clustering are cross-referenced with rule-based anomalies to identify overlaps or discover new suspicious patterns.</li>
  <li><strong>Visualization</strong>: Clusters and identified anomalies are visualized using color-coded graphs and plots, making it easier to communicate findings and understand transaction behaviors at a glance.</li>
</ul>

<p>This combination of clustering and rule-based detection broadens the scope of anomaly identification, allowing for the discovery of previously unseen patterns.</p>

<h3>5. Summaries and Reporting</h3>
<p><strong>Regular Updates</strong>: Periodic reports are generated to summarize findings from both rule-based and clustering approaches. These reports include key insights, rule violations, and visual representations of anomalies.</p>
<p><strong>Interaction with Stakeholders</strong>: Continuous collaboration with the bank and relevant stakeholders ensures that findings are validated, detection rules are fine-tuned, and the overall anomaly detection process remains accurate and up-to-date.</p>

<p>This comprehensive reporting process helps maintain transparency and strengthens the anomaly detection system.</p>


<h2>6. Tools and Technologies</h2>

<ul>
  <li><strong>Data Processing</strong>: Utilized Python, Pandas, and Dask for scalable and efficient processing of large financial datasets, ensuring seamless handling of millions of rows.</li>
  <li><strong>Pattern Mining</strong>: Implemented FP-Growth for mining frequent transaction patterns and generating association rules to uncover significant correlations in the data.</li>
  <li><strong>Anomaly Detection</strong>: Applied custom filtering methods to flag anomalous behavior such as deposits greater than 6,000,000 VND and withdrawals ≥95% of the deposited amount.</li>
  <li><strong>Clustering</strong>: Leveraged Scikit-learn for multilevel clustering techniques, identifying and visualizing potential anomalies. Visualization tools like Matplotlib and Seaborn were used for representing clusters and distributions graphically.</li>
  <li><strong>Deep Learning</strong>: Integrated <strong>VAE-Transformer (Variational Autoencoder + Transformer)</strong>, a hybrid Deep Learning model, for advanced anomaly detection in financial transactions. This approach combines the strength of VAE in dimensionality reduction and feature learning with Transformers for sequential anomaly detection.</li>
  <li><strong>Data Storage</strong>: Employed Google Drive for managing and storing large parquet files, ensuring easy access and processing within a distributed environment.</li>
</ul>

