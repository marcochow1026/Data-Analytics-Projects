# Data-Analytics-Projects

# Ecommerce Data Analysis

This repository contains a Jupyter Notebook (`Ecommerce_Data_Analysis.ipynb`) for analyzing an e-commerce customer churn dataset. The analysis includes data cleaning, exploratory data visualization, feature importance using Random Forest, Partial Dependence Plots (PDP) for key features, and business insights on churn drivers.

## Executive Summary

This project analyzes e-commerce customer behavior to identify key drivers of churn. Using a dataset of 50,000 customers, we performed data cleaning, exploratory analysis, and modeling with Random Forest to uncover patterns in churn probability. Key findings:
- High customer service calls (>5) double churn risk from ~25% to ~50%.
- Low Lifetime Value (<1,500) leads to high churn (~35–40%), dropping to ~25% at higher values, but with a risk spike for ultra-high LV (>2,500).
- High cart abandonment (>60%) increases churn to ~45%.
- Younger customers (<25) churn at 50% vs 30% for older ones.
- High discount usage (>30%) reduces churn to ~30%.

These insights suggest focusing on improving customer service, reducing abandonment, and targeting young/low-value customers for retention. The Random Forest model achieved strong performance (e.g., R² ~0.92 for purchase prediction), providing actionable recommendations for e-commerce retention strategies.

## Project Description

The notebook performs a comprehensive analysis of customer churn in an e-commerce dataset. Steps include:
- **Data Loading & Cleaning**: Handling invalid values, imputation with medians, no row removal.
- **Exploratory Data Analysis (EDA)**: Visualizations of churn vs key features (e.g., Lifetime_Value, Customer_Service_Calls).
- **Modeling**: Random Forest for feature importance and Partial Dependence Plots (PDP) to show how top features affect churn probability.
- **Business Insights**: Conclusions on churn drivers, with recommendations for retention.

The dataset includes features like Age, Lifetime_Value, Cart_Abandonment_Rate, Customer_Service_Calls, etc.

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

## Results & Key Insights

### Exploratory Visualizations
- **Churn vs Lifetime_Value**: High churn (~35–40%) at low LV, drops to ~25% at mid-high LV, with a risk spike at ultra-high LV.
- **Churn vs Customer_Service_Calls**: Churn doubles after 5 calls, nearing 100% at 20+ calls.

### Modeling Results
- Random Forest feature importance: Top drivers include Customer_Service_Calls, Lifetime_Value, Cart_Abandonment_Rate, Age, Discount_Usage_Rate.
- PDP Plots: 
  - Customer_Service_Calls: Sharp increase in churn after 5 calls.
  - Lifetime_Value: Decreases churn up to ~2,000, then slight risk increase at extremes.
  - Cart_Abandonment_Rate: Gradual rise in churn above 60%.
  - Age: High churn (~50%) for <25 years, drops to ~30% for older.
  - Discount_Usage_Rate: Lower churn (~30%) for high usage (>30%).

### Business Recommendations
1. **Reduce service calls**: Intervene after 3–5 calls with proactive support.
2. **Target low-LV customers**: Win-back offers to push them to mid-LV threshold.
3. **Fix abandonment**: Optimize checkout to reduce rates above 60%.
4. **Retain young customers**: Tailored marketing for <25 age group.
5. **Leverage discounts**: Use strategically to lower churn in price-sensitive segments.

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.

## Acknowledgments

- Dataset: Assumed to be from a standard e-commerce source.
- Libraries: Scikit-learn, Statsmodels, Matplotlib, Seaborn.

Contact: [Your Name/Email] for questions or contributions.
