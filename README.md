Fraudulent Claim Detection


Problem Statement
•	Company: Global Insure, a prominent insurance company.
•	Challenge or Problem: The company processes thousands of claims annually. A significant portion is fraudulent, resulting in substantial financial losses. The existing process relies on manual inspections, which are inefficient and often identify fraud after payout. To implement a data-driven fraud detection system that classifies claims as fraudulent or legitimate early in the process, reducing losses and improving efficiency.

Objective: 
•	Analytical Goal: Build a predictive model that uses historical claim and customer data to classify new claims as fraudulent or legitimate.
•	Business Impact: Improve early fraud detection, enhance claims processing, and minimize manual intervention.

Methodology / Approach: 
To develop the fraud detection model, the CRISP-DM (Cross-Industry Standard Process for Data Mining) framework was adopted. This structured methodology ensured a systematic and efficient approach to model development and evaluation. The key steps followed are outlined below:
1.	Data Preparation:Collected, consolidated, and formatted the raw data to ensure it was suitable for analysis.
2.	Data Cleaning:Addressed missing values, corrected inconsistent data types, and ensured data integrity.
3.	Data Splitting:Segregated the dataset into training and test sets to enable unbiased model evaluation.
4.	Exploratory Data Analysis (EDA):Performed in-depth analysis on the training data to uncover patterns, trends, and anomalies within fraudulent and legitimate claims.
5.	Feature Engineering:Developed new predictive features to enhance model accuracy and better capture fraud indicators.
6.	Model Development:Constructed and trained two machine learning models:
      Logistic Regression
      Random Forest
7.	Feature Selection:
      For Logistic Regression, applied Recursive Feature Elimination with Cross-Validation (RFECV).
  	  For Random Forest, used Feature Importance scores to identify the most impactful variables.
9.	Model Fine-Tuning:
      Optimized the classification threshold for Logistic Regression to balance precision and recall.
  	  Applied GridSearchCV to tune hyperparameters and improve performance for both models.
11.	Model Evaluation:Measured performance using a suite of evaluation metrics, including:
- Accuracy
- Recall (with emphasis on fraud detection)
- F1-Score

Techniques: 
Specific tools or methods used at different steps of model building are mentioned below:
1.	Preprocessing: One-Hot Encoding, StandardScaler
2.	Algorithms: Logistic Regression, Random Forests
3.	Optimization: GridSearchCV, Sensitivity-Specificity Tradeoff
4.	Evaluation: Accuracy, Confusion Matrix, Recall

Key Insights: Several significant observations were made during the data analysis:
1.	Months_as_customer: Higher fraud incidence among newer customers.
2.	Age: Younger individuals (under 30) are more likely to commit fraud.
3.	Policy_deductible: Fraud is more common with lower deductibles.
4.	Umbrella_limit: No significant difference.
5.	Capital_gains: Slightly higher in fraud cases.
6.	Capital_loss: Similar in both classes.
7.	Number_of_vehicles_involved: Multiple vehicles indicate higher fraud risk.
8.	Bodily_injuries: Slightly higher in fraud cases.
9.	Witnesses: Higher witness count correlates with fraud.
10.	Claim Components: Injury, Property, and Vehicle claims are higher in fraud cases.

Logistic Regression outperformed Random Forests in terms of Recall, making it the better model for detecting fraudulent claims, with a Recall of 90.5% on the validation data.

Significant Features: The coefficient scores provide insights into the relative importance of each feature in predicting the target variable, which, in this case, is likely related to identifying whether a claim is fraudulent or not. Below is the Regression equation

1.5584 + 4.2153 (insured_hobbies_chess) + 3.5445 (insured_hobbies_cross-fit) – 22.7954 (insured_hobbies_dancing) – 3.4093 (incident_severity_Minor Damage) – 3.2046 (incident_severity_Total Loss)

Insights / Recommendations: 

Based on the model output, the following insights are drawn:
1.	insured_hobbies_cross-fit: Similarly, claims with insured individuals who have a hobby of cross- fit are also positively associated with fraud. The coefficient (3.5445) indicates that these claims are more likely to be fraudulent.
2.	insured_hobbies_chess: Claims with the insured person having a hobby of chess are positively associated with fraud. The coefficient (4.2153) suggests that if the insured person plays chess, it increases the log-odds of a fraudulent claim
3.	incident_severity_Minor Damage: Claims with minor damage as the incident severity are negatively associated with fraud. The coefficient (-3.4093) suggests that minor damage claims are less likely to be fraudulent compared to more severe damage claims.
4.	incident_severity_Total Loss: Claims with total loss as the incident severity are also negatively associated with fraud. The negative coefficient (-3.2046) implies that total loss incidents are less likely to be fraudulent compared to minor damage or other less severe claims.

Recommendations:

1.	Prioritize Scrutiny for Specific Hobbies: Claims associated with individuals who list chess or cross-fit as hobbies should be flagged for additional verification, as they show a higher likelihood of fraud. These claims should undergo enhanced review procedures to reduce the risk of fraudulent payouts.
2.	Expedite Minor Damage Claims: As minor damage claims are statistically less likely to be fraudulent, the approval process for these can be streamlined. This approach can improve turnaround times and boost operational efficiency.
3.	Simplify Processing for Total Loss Claims: Claims involving a total loss exhibit a lower association with fraud. These can be deprioritized for manual review or processed with fewer checks, optimizing resource allocation.
4.	Focus on Intermediate Claims for Fraud Detection: Greater attention should be given to claims that do not fall under 'Minor Damage' or 'Total Loss', as these are more prone to fraudulent activity and warrant closer inspection.


Case study team members: - Rajesh Mishra, Harshitha Praturi, Argha Chakraborty
