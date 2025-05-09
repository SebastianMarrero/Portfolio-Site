---
layout: page
title: "Credit Card Fraud Detection Analysis"
permalink: /credit-card-fraud-analysis/
---
<p><a class="btn" href="https://github.com/SebastianMarrero/Credit-Card-Fraud-Analysis" target="_blank">View on GitHub</a></p>


<p>Comprehensive classification analysis on the <a href="https://www.kaggle.com/datasets/sgpjesus/bank-account-fraud-dataset-neurips-2022" target="_blank">Feedzai BAF Dataset Suite</a>, built for detecting fraud in highly imbalanced credit card application data. This project leverages Logistic Regression, XGBoost, and LightGBM with class balancing techniques (SMOTE and <code>scale_pos_weight</code>) to identify fraudulent patterns while minimizing false positives. Visualizations and model performance metrics such as precision, recall, F1, and PR AUC are included throughout.</p>

<h2>Project Overview</h2>

<h3>Purpose</h3>
<ul>
  <li>Detect fraud in credit card applications using interpretable, high-recall models.</li>
  <li>Compare class balancing methods for tree-based classifiers in extreme imbalance settings.</li>
  <li>Visualize feature behavior and clarify performance trade-offs between models.</li>
</ul>

<h3>Dataset Background</h3>
<ul>
  <li>~1M applications from the <strong>Feedzai BAF Dataset</strong> (synthetic, NeurIPS 2022).</li>
  <li>Target variable: <code>fraud_bool</code> — 1 = fraud, 0 = not fraud.</li>
  <li>Fraud prevalence: ~1.1% (extreme class imbalance).</li>
</ul>

<h3>Tech Stack</h3>
<ul>
  <li><strong>Python</strong> (Pandas, Scikit-learn, XGBoost, LightGBM, Imbalanced-learn, Seaborn, Matplotlib)</li>
  <li><strong>Jupyter Notebook</strong> for modeling and EDA</li>
  <li><strong>GitHub Pages + Jekyll</strong> for publishing</li>
</ul>

<h2>Exploratory Data Analysis</h2>

<h3>Fraud Class Distribution</h3>
<img src="{{ site.baseurl }}/assets/images/FraudClassDistribution.png" alt="Fraud Class Distribution">
<ul>
  <li>Fraud accounts for only 1.1% of cases — justifying the use of resampling or weighting strategies.</li>
</ul>

<h3>Numerical Features by Class (KDE)</h3>
<img src="{{ site.baseurl }}/assets/images/kde_plot_numerical_features_class_status.png" alt="KDE Plot">
<ul>
  <li>Key indicators: <code>credit_risk_score</code>, <code>velocity_6h</code>, <code>session_length_in_minutes</code>.</li>
  <li>Even when KDE peaks are similar, subtle separation suggests high feature utility for fraud detection.</li>
</ul>

<h3>Correlation Heatmap</h3>
<img src="{{ site.baseurl }}/assets/images/Correlation_Heatmap.png" alt="Correlation Heatmap">
<ul>
  <li>Features like <code>velocity_6h</code>, <code>proposed_credit_limit</code>, and <code>credit_risk_score</code> show moderate correlation with fraud.</li>
</ul>

<h3>Categorical Feature Insights</h3>
<p><em>Note: Labels are anonymized to protect privacy but still hold predictive value.</em></p>

<img src="{{ site.baseurl }}/assets/images/Categorical_feature_distribution_by_device_os.png" alt="Device OS">
<ul>
  <li>Fraud is prevalent on Windows operating system compared to other OSes.</li>
</ul>

<img src="{{ site.baseurl }}/assets/images/Categorical_feature_distribution_by_employment_status.png" alt="Employment Status">
<ul>
  <li>CA employment status has an unusually high number of frauds relative to the other employment categories.</li>
  <li>However, it also contains the largest quantity of non-fraudulent applications, indicating general prevalence in the data.</li>
  <li>No single employment status category shows stark differences in fraud rates, limiting standalone predictive power.</li>
</ul>

<img src="{{ site.baseurl }}/assets/images/Categorical_feature_distribution_by_housing_status.png" alt="Housing Status">
<ul>
  <li>Fraud counts are noticeably higher for BA, BB, and BC compared to other housing statuses.</li>
  <li>Fraud is especially rare in BG and BF even though they have significant non-fraud counts.</li>
</ul>

<img src="{{ site.baseurl }}/assets/images/Categorical_feature_distribution_by_payment_type.png" alt="Payment Type">
<ul>
  <li>AA, AB, AC, and AD payment types all show strong fraud representation relative to their non-fraud base.</li>
  <li>AE payment type is an outlier with an extremely low fraud rate despite high non-fraud volume.</li>
</ul>

<img src="{{ site.baseurl }}/assets/images/Categorical_feature_distribution_by_source.png" alt="Source">
<ul>
  <li>Fraud via Internet source shows a higher total count for both fraudulent and non-fraudulent cases than Teleapp.</li>
  <li>While it's unclear if the internet channel is inherently riskier, it captures the majority of all applications.</li>
</ul>

<h2>Modeling and Class Imbalance Handling</h2>

<h3>Logistic Regression</h3>
<img src="{{ site.baseurl }}/assets/images/Precision-Recall_Curve_LR.png" alt="PR Curve - Logistic Regression">
<ul>
  <li><strong>Original:</strong> Recall = 0.01, Precision = 0.64, F1 = 0.03</li>
  <li><strong>SMOTE:</strong> Recall = 0.77, Precision = 0.05, F1 = 0.09</li>
</ul>
<ul>
  <li>SMOTE increased recall from 1% to 77%, but precision dropped to just 5%.</li>
  <li>This version misclassified thousands of non-fraudulent applications, leading to poor real-world usability.</li>
</ul>

<h3>XGBoost</h3>
<img src="{{ site.baseurl }}/assets/images/Precision-Recall_Curve_XGBoost.png" alt="PR Curve - XGBoost">
<ul>
  <li><strong>Original:</strong> Recall = 0.03, Precision = 0.41, F1 = 0.06</li>
  <li><strong>SMOTE:</strong> Recall = 0.90, Precision = 0.02, F1 = 0.03</li>
</ul>
<ul>
  <li>SMOTE severely hurt precision — model flagged over 130,000 legitimate applications as fraudulent.</li>
  <li>Original model retained better precision but low recall (0.03).</li>
  <li>Weighted model struck a middle ground — 60% recall and 7% precision, making it more viable.</li>
</ul>

<h3>LightGBM</h3>
<img src="{{ site.baseurl }}/assets/images/LightGBM_PR_Curve.png" alt="PR Curve - LightGBM">
<ul>
  <li><strong>Original:</strong> Recall = 0.05, Precision = 0.42, F1 = 0.08</li>
  <li><strong>SMOTE:</strong> Recall = 0.99, Precision = 0.01, F1 = 0.02</li>
</ul>
<ul>
  <li>SMOTE pushed recall to 99% but precision to 1% — rendering the model unusable in production.</li>
  <li>Weighted LightGBM delivered a much better balance: 79% recall, 5% precision.</li>
</ul>

<h3>Weighted LightGBM and XGBoost</h3>
<img src="{{ site.baseurl }}/assets/images/Weighted_PR_Curve.png" alt="Weighted PR Curve - Tree Models">
<ul>
  <li><strong>LightGBM (Weighted):</strong> Recall = 0.79, Precision = 0.05, F1 = 0.09</li>
  <li><strong>XGBoost (Weighted):</strong> Recall = 0.60, Precision = 0.07, F1 = 0.12</li>
</ul>
<ul>
  <li>Weighted LightGBM achieved the highest PR AUC (0.162), making it the best overall performer.</li>
  <li>Both models avoided the catastrophic overfitting seen with SMOTE.</li>
  <li>XGBoost’s weighted version correctly identified over 179,000 legitimate applications while keeping false positives low.</li>
</ul>

<h2>Model Evaluation Summary</h2>

<table>
  <thead>
    <tr><th>Model</th><th>Recall</th><th>Precision</th><th>F1 Score</th><th>PR AUC</th></tr>
  </thead>
  <tbody>
    <tr><td><strong>LightGBM (Weighted)</strong></td><td>0.79</td><td>0.05</td><td>0.09</td><td>0.162</td></tr>
    <tr><td>XGBoost (Weighted)</td><td>0.60</td><td>0.07</td><td>0.12</td><td>0.126</td></tr>
    <tr><td>Logistic Regression</td><td>0.01</td><td>0.64</td><td>0.03</td><td>0.140</td></tr>
    <tr><td>LightGBM (SMOTE)</td><td>0.99</td><td>0.01</td><td>0.02</td><td>0.017</td></tr>
  </tbody>
</table>

<h2>Key Insights</h2>
<ul>
  <li>SMOTE oversampling harms precision for tree-based models due to synthetic noise overfitting.</li>
  <li><code>scale_pos_weight</code> offers superior fraud detection trade-offs in XGBoost and LightGBM.</li>
  <li>Velocity metrics and credit scores remain among the strongest predictors.</li>
</ul>

<h2>How to Reproduce</h2>
<ol>
  <li>Clone the repo: <code>git clone https://github.com/SebastianMarrero/Credit-Card-Fraud-Analysis.git</code></li>
  <li>Open <code>Credit Card Fraud Analysis.ipynb</code> in Jupyter</li>
  <li>Run cells in order; visualizations will populate <code>/assets/images</code></li>
  <li>Modify hyperparameters or balancing techniques to experiment further</li>
</ol>

<p><em>Created by Sebastian Marrero — <a href="mailto:sebastianmarrero64@gmail.com">sebastianmarrero64@gmail.com</a> — <a href="https://linkedin.com/in/sebastianmarrero">LinkedIn</a></em></p>
