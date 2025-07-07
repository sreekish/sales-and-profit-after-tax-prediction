# Sales and Profit Prediction for 46 Industries
This project focuses on building predictive models to estimate Sales and Profit % across 46 different industries using financial and operational data.
## Data Preparation
### Data Sources
**10-K data.csv:** Consist of columns such as firmcode, year ,month, day, date, sales, employee_salaries, selling_distn_exp, advt_exp, rnd_exp, total_asset, net_fixed_asset, gross_fixed_asset, current_assets, investments, inventories	accounts_receivables, cash_balance, cashflow_from_oper, industry_id.  
**10-K industry data:** Consists of Industry ID and Industry name.  
**Data merging**
The 2 datasets are merged using join function with Industry ID as common key.
### Target Variables:
Sales, Profit After Tax: used for calculating profit%
Records with missing values in these columns were removed, as they are the target variables for prediction.
## Data Cleaning & Imputation
### Outlier Removal
Records with EBITDA > 105% of Sales were considered unrealistic and removed.
### Missing Value Treatment
**Set to 0 for:** advertising_expenses, selling_distribution_expenses, research_expenses, provision_expenses, depreciation, interest_expenses, investments.  
**Filled using previous year’s value for:** employee_salary, total_liabilities, current_liabilities, accounts_payable, debt, total_assets, net_fixed_assets, gross_fixed_assets, current_assets.  
**Remaining numeric features:** Imputed using the mean value per firm and industry and any residuals are filled using 0.  
## Modelling
**Linear Regression Model:** Built with features that has t-score greater than 1.96.  
**Decision Tree Model:** Built with features that has t-score greater than 2.  
