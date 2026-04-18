# Bank-Loan-Default-Risk-Analysis
End-to-end loan default risk analysis using SQL, Python &amp; Power BI on 255K+ records — identifying high-risk borrower segments for a banking use case.

Overview
An end-to-end loan default risk analysis project on 255,347 loan records to identify key drivers of borrower default in a banking context. The project covers SQL business analysis, Python EDA, machine learning, and a Power BI dashboard — simulating a real analyst workflow.

Problem Statement
Banks lose significant revenue when borrowers fail to repay loans. This project analyzes borrower profiles to answer: who is most likely to default, and why?

Tools & Technologies
LayerToolsData AnalysisSQL (MySQL), PythonLibrariesPandas, NumPy, Matplotlib, Seaborn, Scikit-learnVisualizationPower BIDataset Size255,347 rows, 18 columns

Project Structure
Bank-Loan-Default-Risk-Analysis/
├── data/
│   └── loan_default.csv
├── sql/
│   └── loan_default_analysis.sql
├── notebook/
│   └── loan_default_analysis.ipynb
├── dashboard/
│   └── bank_loan_default_dashboard.png
└── README.md

Key Findings

Overall default rate: 11.52% across 117K customers
Unemployed borrowers default at 13.37% — highest among all employment types
Low-income borrowers (<$50K) default at 17.17% — nearly 1.5x the overall average
Young adults (under 25) carry 20.87% default rate — highest age segment
Business-purpose loans default most at 12.28% among all loan purposes
Borrowers without a co-signer default at 12.74% vs lower with co-signer present
Top 3 default predictors: Credit Score, DTI Ratio, Income


SQL Analysis
30+ queries covering:

Overall and segment-wise default rates
Default rate by employment type, education, loan purpose, age group, marital status
Income bracket segmentation and default rate per range
Credit score and DTI ratio risk profiling
Window functions: RANK, ROW_NUMBER, running averages
Subqueries filtering above-average risk borrowers
Multivariate risk: combined low credit score + high DTI analysis
Loan-to-Income ratio bucketing


Python EDA & Machine Learning

Checked for null values, duplicates, and class imbalance (88/12 split)
Distribution plots for CreditScore, Income, LoanAmount, Age, DTIRatio
Correlation heatmap across all 18 variables
Boxplots comparing defaulters vs non-defaulters across key features
Feature engineering: Loan-to-Income ratio, risk score column
Label encoded categorical variables, dropped LoanID
Model: Logistic Regression with class_weight='balanced'
Stratified 80/20 train-test split to preserve class ratio
Confusion matrix and classification report (Precision, Recall, F1)
Feature importance bar chart — top predictors identified


Power BI Dashboard
8-panel dashboard including:
KPI Cards: Total Customers · Total Defaults · Overall Default Rate · Avg Credit Score · Avg Loan Amount
Visuals: Default rate by employment type · Default rate by education · Default rate by DTI category · Default rate by loan term · Default rate by age category · Default rate by loan purpose · Default rate by credit score category
Show Image

Business Recommendations

Tighter screening for unemployed applicants — 13.37% default rate warrants stricter eligibility criteria
Co-signer requirements for high-DTI borrowers — co-signer presence meaningfully reduces default risk
Age-based risk tiers — borrowers under 25 need additional income and credit verification given 20.87% default rate


Dataset
Public dataset — 255,347 records with features including Age, Income, LoanAmount, CreditScore, MonthsEmployed, NumCreditLines, InterestRate, LoanTerm, DTIRatio, EmploymentType, LoanPurpose, HasCoSigner, and Default flag.
