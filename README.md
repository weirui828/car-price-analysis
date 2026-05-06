# Used Car Price Analysis

## Project Overview

This project analyzes a dataset of ~426,000 used car listings sourced from Kaggle to identify the key factors that drive used car prices. The analysis is intended to provide actionable recommendations to a used car dealership looking to optimize their inventory.

The project follows the **CRISP-DM** framework: Business Understanding → Data Understanding → Data Preparation → Modeling → Evaluation → Deployment.

## Notebook

[`analyzer.ipynb`](analyzer.ipynb)

## Summary of Findings

After cleaning and exploring the dataset, several regression models (Linear Regression, Ridge, Lasso, and others with cross-validation and grid search tuning) were trained to predict used car prices. Key findings include:

- **Year / Age** is the strongest predictor of price — newer vehicles command significantly higher prices.
- **Odometer (mileage)** has a strong negative relationship with price; lower-mileage vehicles are valued considerably higher.
- **Condition** matters: cars listed as "excellent" or "like new" fetch a substantial premium over "fair" or "salvage" condition vehicles.
- **Drive type** (4WD/AWD) and **fuel type** (diesel, hybrid) correlate with higher prices, reflecting consumer demand for capability and efficiency.
- **Cylinders** (engine size) positively correlates with price, particularly for trucks and SUVs.
- **Manufacturer and model** influence price beyond what condition and mileage alone explain — certain brands hold their value better.

## Recommendations for Used Car Dealers

1. **Prioritize low-mileage, newer-year inventory** — these are the strongest price drivers and easiest to communicate to buyers.
2. **Invest in reconditioning** — moving a car from "good" to "excellent" condition can meaningfully increase its sale price.
3. **Stock 4WD/AWD vehicles and diesel trucks** — these segments command price premiums and attract motivated buyers.
4. **Use model-year and odometer as primary pricing signals** when no other data is available; condition and drivetrain refine the estimate further.

## Next Steps

While predicting the raw market price of a vehicle is a useful baseline, dealerships already have access to real-time market pricing tools, such as Kelley Blue Book. To provide true competitive advantage, future iterations of this analysis should shift focus from **pricing** to **profitability**.

Recommended next steps include:

1. **Shift the Target Variable to Profit Margin**  
   By incorporating wholesale acquisition costs and estimated reconditioning costs into the dataset, we can train a model to predict the expected **profit space** of a vehicle, allowing buyers to identify undervalued assets at auction.

2. **Predict "Days on Lot" (Turn Rate)**  
   A high-margin car that takes 120 days to sell is often less profitable than a lower-margin car that sells in 5 days due to floorplan financing costs. A secondary model predicting inventory turn rate based on local demand and vehicle specs would optimize capital allocation.

3. **Incorporate Real-Time Depreciation Curves**  
   Since car age is the #1 driver of price, a time-series analysis predicting *how much value a specific car will lose in the next 60 days* would help dealerships aggressively price and move aging inventory before it crosses the next depreciation cliff.


## Repository Structure

```
car-price-analysis/
├── data/
│   └── vehicles.csv        # Raw dataset (~426K used car listings)
├── images/
├── analyzer.ipynb           # Full analysis notebook
└── README.md
```
