Payroll Risk Scoring System

Objective
The objective of this project is to build a Payroll Risk Scoring System that identifies high-risk payroll records using employee payroll data. The system analyzes salary components such as gross pay, net pay, deductions, and bonuses to understand overall salary behavior. Since direct attendance and leave records are not available, attendance patterns and leave frequency are inferred from payroll deductions and arrear adjustments. By combining these derived features, the system aims to detect unusual or abnormal payroll patterns that may indicate potential payroll issues or inconsistencies. The final goal is to support payroll teams by highlighting records that require further review.
Dataset Description
Payroll encompasses a comprehensive suite of activities related to employee compensation, encompassing everything from meticulously calculating individual paychecks, considering factors such as base salary, overtime, bonuses, and commissions, to ensuring timely and accurate processing of payments through various methods like direct deposit or check disbursement. Furthermore, it involves adhering to a complex web of federal, state, and local tax regulations, including the accurate withholding and remittance of taxes such as income tax, Social Security, and Medicare. Finally, payroll encompasses the generation of crucial reports for financial accounting, tax filings, and internal analysis, providing valuable insights into labor costs and overall business performance.
Data Cleaning
The following data cleaning steps were performed:
Checked missing values across all columns
Filled missing values in important numeric payroll fields such as total deductions and arrear statutory bonus
Removed unnecessary columns such as employee names and date fields that were not relevant for risk analysis
Cleaned column names for consistency
Feature Engineering
Since raw attendance and leave data were not available, attendance and leave behavior were inferred using payroll information:
Deduction Ratio = Total Deductions / Gross Salary
Net-to-Gross Ratio = Net Salary / Gross Salary
These ratios act as proxies for attendance patterns and leave frequency. Salary behavior was analyzed using gross and net salary relationships.
Exploratory Data Analysis (EDA)
Basic EDA was performed to understand payroll patterns:
Salary distribution analysis
Relationship between gross salary and net salary
Deduction patterns as an indicator of attendance behavior
Comparison of salary and deduction patterns between normal and high-risk payroll records
Payroll Risk Label Creation
A binary target variable payroll_risk was created:
0 – Normal payroll record
1 – High-risk payroll record
Payroll risk was identified using threshold-based rules on deduction ratio and net-to-gross salary ratio.
Modeling
Three machine learning models were trained and evaluated:
1.Logistic Regression
2.Random Forest Classifier
3.Gradient Boosting Classifier
The dataset was split into training and testing sets, and models were evaluated using accuracy, precision, recall, and F1-score.
Model Comparison
A comparison table was created to compare the performance of all three models. Among the models, Gradient Boosting showed better overall performance and generalization.
Feature Importance
Feature importance analysis was performed using the Random Forest model to understand which features contributed most to payroll risk prediction
Model Justification
Logistic Regression was used as a baseline linear model. Random Forest was used to capture non-linear relationships and reduce variance by averaging multiple decision trees. Gradient Boosting was selected as the final model as it minimizes the loss function iteratively and showed better performance in identifying high-risk payroll records.

Conclusion
This project successfully demonstrates a payroll risk scoring approach using derived attendance, leave, and salary features. The system is able to identify high-risk payroll records and can assist payroll teams in detecting anomalies and potential payroll issues.

