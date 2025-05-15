# 🏠 Real Estate Regression Analysis

This project explores the factors influencing residential property sale prices using real estate transaction data from Connecticut (2017–2022). The project applies multi-linear regression modeling, interaction effects, and residual diagnostics to understand how variables like year, estimated value, locality, and tax rate affect home prices.

## Project Goals
- Understand which features most strongly affect real estate sale prices.
- Use linear regression and transformation techniques to improve model fit.
- Evaluate model performance through statistical tests and diagnostic plots.

## Data Overview
- Source: `RealEstatePrice.csv`
- Variables: `Date`, `Year`, `Locality`, `Estimated.Value`, `Sale Price`, `Property`, `num_rooms`, `num_bathrooms`, `carpet_area`, `property_tax_rate`, `Face`.

## Data Processing
- Removed NAs and zero values
- Filtered years 2017 – 2022
- Subset to top 2 categories for `Locality`, `Property`, `Residential`, and `Face`
- Scaled sale price and estimated value to thousands of dollars

## Exploratory Data Analysis
- Most variables are right-skewed; log-transformation was necessary for better modeling
- Strong correlation between features (e.g., rooms and carpet area) addressed via VIF analysis
- North and West are dominant directions; Waterbury and Bridgeport are top localities

## Model Building & Evaluation
- Stepwise regression and full model comparisons conducted
- Best model:
  ```
  ln(Sale Price) = 0 + Year + Estimated Value + Locality + Property Tax Rate + Estimated Value × Locality
  ```
- Adjusted R² of best model: **0.9886**
- Model met linearity and constant variance assumptions, but violated normality and independence

## Techniques Used
- Multi-linear regression
- Forward stepwise selection
- Log-transformation of response
- VIF (Variance Inflation Factor) analysis
- ANOVA for model comparison
- Residual diagnostics: Breusch-Pagan, Shapiro-Wilk, Durbin-Watson

## 📁 Folder Structure
```
├── data/                # dataset 
├── code/                # R code
├── Report               # R code
└── README.md            
```

## Conclusion
- The final model identified key drivers of property prices including time (Year), valuation, locality, and tax rate.
- Log-transformation and interaction terms significantly improved model fit.
- Future work should address normality issues and extend data coverage for better generalization.

---
