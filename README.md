# Ecommerce Data Analysis

This repository contains a Jupyter Notebook (`Ecommerce_Data_Analysis.ipynb`) for analyzing an e-commerce customer dataset. The analysis includes data cleaning, exploratory data visualization, customer segmentation using K-Mean clustering method, prediction of churn probability using multinominal logistics regression and Random Forest, and business insights.

## Project Description

The notebook performs a comprehensive analysis of customer churn in an e-commerce dataset. Steps include:
- **Data Loading & Cleaning**: Handling invalid values, imputation with medians, no row removal.
- **Exploratory Data Analysis (EDA)**: Visualizations of churn vs key features (e.g., Lifetime_Value, Customer_Service_Calls).
- **Customer segmentation**: Using K-Mean clustering to divide customers into 3 clusters: loyal customers, the "middle" and the "risky".
- **Modeling**: Random Forest for feature importance and Partial Dependence Plots (PDP) to show how top features affect churn probability.
- **Business Insights**: Conclusions on churn drivers, with recommendations for retention.

The dataset includes features like Age, Lifetime_Value, Cart_Abandonment_Rate, Customer_Service_Calls, etc.

## Source of Data
This dataset is obtained from Kaggle (https://www.kaggle.com/datasets/dhairyajeetsingh/ecommerce-customer-behavior-dataset). Contains 50000 rows of customers data with 25 features, including Customer Demographics (e.g. Age, Gender, Country), Platform Engagement (e.g. Cart_Abandonment_Rate, Session_Duration_Avg, Customer_Service_Calls) and Purchase Behavior (e.g. Total_Purchases, Average_Order_Value).

## Results & Key Insights

### Customer segmentation
- We includes RFM (Recency, Frequency and Monetary) and the engagement metrics like 'Session_Duration_Avg' and 'Customer_Service_Calls' as the citeria of the K-Mean Clustering.
- We divided 3 group of customers:
  - **loyal customers**: Consists of 19% of customers, contribute the **highest RFM** (lifetime value >2400, total number of purchases >20 and average order value ~130),            **highest engagement** (Cart Abandonment Rate <40%, Customer_Service_Calls <4) and **lowest churn rate** (<20%).
  - **The Middle**: Consists of 40% of customers, they are at the middle position in both RFM, engagement and churn rate.
  - **The Risky**: Consists of 41% of customers, contribute the **lowest RFM** (lifetime value <900, total number of purchases <10 and average order value ~120), **lowest           engagement** (Cart Abandonment Rate ~70%, Customer_Service_Calls >7) and **highest churn rate** (>40%). But at the same time, those customer may be the newcomers.

### Multinomianl Logistic Regression Modeling Results
- The Multinomianl Logistic Regression model give a 77% accuracy.

- Key Insights:
1. Customer Service Call is the most influential feature, the odds ratio of churn will **increase for 24.2%** for one extra Customer Service Call.

2. If the customer signed up in the fourth quarter, the odds ratio of churn will be **13.1% higher** than customer signed up in the other quarters.

3. Customers from France have a **8.9% lower** odds ratio of churn, compared to customers from other countries.

4. The odds ratio of churn will **decrease for 4.3%** for one extra purchase.

5. The odds ratio of churn will **increase for 3.8%** for 1% increase in Cart Abandonment Rate.

### Random Forest Modeling Results
- Random Forest Model gives a 92% accuracy for predicting churn risk.
- PDP Plots for the top 5 important features:
  - **High customer service calls** (>5) **double** risk of churn from ~25% to ~50%.
  - **Low Lifetime Value** (<1000) **leads to high risk** of churn (~35–40%), dropping to ~25% at higher values, but with a risk spike for ultra-high LV (>2000).
  - **High cart abandonment** (>60%) **increases churn** up to ~45%.
  - **Younger customers** (<25) have a risk of churn at **50%**, while older customers have a risk of churn at 30%.
  - **Low discount usage** (<30%) **increases churn** from ~30% to ~40%.

### Business Recommendations
1. **Reduce service calls**: Intervene after 3–5 calls with proactive support.
2. **Target low-LV customers**: Win-back offers to push them to mid-LV threshold.
3. **Fix abandonment**: Optimize checkout to reduce rates above 60%.
4. **Retain young customers**: Tailored marketing for <25 age group.
5. **Leverage discounts**: Provide attractive discounts to lower churn risk.

## Installation

To run the notebook, install the required libraries:

```bash
pip install pandas numpy scikit-learn statsmodels matplotlib seaborn xgboost
```

- Python version: 3.12+
- Jupyter Notebook or Google Colab recommended.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Ecommerce_Data_Analysis.git
   cd Ecommerce_Data_Analysis
   ```

2. Download the dataset (`ecommerce_customer_churn_dataset.csv`) and place it in the root folder.

3. Open and run the notebook:
   ```bash
   jupyter notebook Ecommerce_Data_Analysis.ipynb
   ```
   Or upload to Google Colab.

The notebook is self-contained — execute cells sequentially for cleaning, EDA, modeling, and insights.

## Acknowledgments

- Dataset: https://www.kaggle.com/datasets/dhairyajeetsingh/ecommerce-customer-behavior-dataset
- Libraries: Scikit-learn, Statsmodels, Matplotlib, Seaborn.

Contact: Contact marcochow1026 for questions or contributions.
