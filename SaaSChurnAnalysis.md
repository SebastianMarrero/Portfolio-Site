---
layout: page
title: "SaaS Customer Churn Analysis"
permalink: /saas-churn-analysis/
---

<p>End-to-end analysis of customer churn using a fictional SaaS dataset. This project combines exploratory data analysis, model development, and interpretability techniques to identify key churn drivers and propose data-backed retention strategies.</p>

<h2>Project Overview</h2>
<h3>Purpose</h3>
<ul>
  <li>Identify behavioral and usage-based predictors of churn.</li>
  <li>Compare interpretable and ensemble models for prediction performance.</li>
  <li>Extract actionable insights to inform customer success and engagement.</li>
</ul>

<h3>Dataset & Tools</h3>
<ul>
  <li><strong>Data Source</strong>: Kaggle’s SaaS Churn Dataset</li>
  <li><strong>Tech Stack</strong>: Python (pandas, matplotlib, seaborn, scikit-learn), Jupyter Notebook</li>
  <li><strong>Deployment</strong>: GitHub Pages + Jekyll</li>
</ul>

<h2>Key Business Questions</h2>
<ol>
  <li>What features best predict whether a SaaS customer will churn?</li>
  <li>How do behavior metrics like support calls, payment delays, and inactivity relate to churn?</li>
  <li>Which model provides the best trade-off between interpretability and accuracy?</li>
</ol>

<h2>Data Visualizations</h2>

<h3>Churn by Subscription Type</h3>
<img src="{{ site.baseurl }}/assets/images/ChurnBySubscriptionType.png" alt="Churn by Subscription Type">
<ul>
  <li>Basic plan users showed slightly higher churn than Premium/Standard users.</li>
  <li>Upselling strategies to retain lower-tier customers may help reduce churn.</li>
</ul>

<h3>Churn by Contract Length</h3>
<img src="{{ site.baseurl }}/assets/images/ChurnByContractLength.png" alt="Churn by Contract Length">
<ul>
  <li>Quarterly contracts had highest churn rates.</li>
  <li>Annual plans promote loyalty—an opportunity for longer-term commitment strategies.</li>
</ul>

<h3>Tenure by Churn Status</h3>
<img src="{{ site.baseurl }}/assets/images/TenureBoxplot.png" alt="Tenure by Churn Status">
<ul>
  <li>Shorter-tenure users were more likely to churn.</li>
  <li>Highlights importance of early-stage engagement and onboarding efforts.</li>
</ul>

<h3>Support Calls by Churn Status</h3>
<img src="{{ site.baseurl }}/assets/images/SupportCallsBoxplot.png" alt="Support Calls by Churn Status">
<ul>
  <li>Churners placed more support calls, indicating frustration or dissatisfaction.</li>
</ul>

<h3>Last Interaction by Churn Status</h3>
<img src="{{ site.baseurl }}/assets/images/LastInteractionBoxplot.png" alt="Last Interaction by Churn Status">
<ul>
  <li>Churners tended to show longer periods of inactivity before leaving.</li>
</ul>

<h2>Modeling Results</h2>
<h3>Model Performance Summary</h3>
<table>
  <tr><th>Model</th><th>AUC</th><th>Accuracy</th><th>Churn Recall</th><th>Stay Recall</th></tr>
  <tr><td><strong>Logistic Regression</strong></td><td>0.79</td><td>71%</td><td>77%</td><td>67%</td></tr>
  <tr><td>Random Forest (Default)</td><td>0.62</td><td>50%</td><td>95%</td><td>22%</td></tr>
  <tr><td>Random Forest (Tuned)</td><td>0.68</td><td>56%</td><td>93%</td><td>25%</td></tr>
</table>

<h3>ROC Curve Comparison</h3>
<img src="{{ site.baseurl }}/assets/images/ROC_LR_RF_Comparison.png" alt="ROC Curve - LR vs RF">
<img src="{{ site.baseurl }}/assets/images/ROC_LR_RFT_Comparison.png" alt="ROC Curve - LR vs Tuned RF">
<ul>
  <li>Logistic Regression outperforms both default and tuned Random Forest models.</li>
  <li>Tuning improved RF performance, but Logistic Regression remained most reliable.</li>
</ul>

<h3>Feature Importance (Random Forest)</h3>
<img src="{{ site.baseurl }}/assets/images/FeatureImportance_RF_Orig.png" alt="Feature Importance RF Original">
<img src="{{ site.baseurl }}/assets/images/FeatureImportance_RF_Tuned.png" alt="Feature Importance RF Tuned">
<ul>
  <li>Top drivers: Support Calls, Total Spend, Payment Delay.</li>
  <li>Tuned model emphasized different behavioral features (e.g., Age, Gender).</li>
</ul>

<h3>Logistic Regression Coefficients</h3>
<img src="{{ site.baseurl }}/assets/images/LogisticRegressionCoefficients.png" alt="Logistic Regression Coefficients">
<ul>
  <li>Support Calls (+2.20), Payment Delay (+0.89), Inactivity (+0.52) increase churn risk.</li>
  <li>Tenure (–0.13), Total Spend (–1.40), Usage Frequency reduce churn risk.</li>
</ul>

<h2>Conclusion</h2>
<ul>
  <li>Logistic Regression provides strong AUC and interpretability, making it ideal for churn scoring.</li>
  <li>Behavioral features outperform demographics—support volume, payment issues, and inactivity are key churn flags.</li>
  <li>High-value users (long tenure, high spend) are more loyal—focus retention there.</li>
</ul>

<h2>Reproducibility</h2>
<ol>
  <li>Clone the repo: <code>git clone https://github.com/SebastianMarrero/SaaS_Churn_Analysis.git</code></li>
  <li>Run <code>CustomerChurnEDA.ipynb</code> in Jupyter Lab or VS Code</li>
  <li>View outputs and visuals in <code>/assets/images</code></li>
</ol>

<p><em>Created by Sebastian Marrero — <a href="mailto:sebastianmarrero64@gmail.com">sebastianmarrero64@gmail.com</a> — <a href="https://linkedin.com/in/sebastianmarrero">LinkedIn</a></em></p>
