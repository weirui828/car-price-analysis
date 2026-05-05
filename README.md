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

- Incorporate geographic data (region/state) to account for local market variation.
- Explore time-series trends to understand how prices shift seasonally.
- Build a simple pricing tool that dealers can use to estimate fair market value for a given vehicle configuration.

## Repository Structure

```
car-price-analysis/
├── data/
│   └── vehicles.csv        # Raw dataset (~426K used car listings)
├── images/
│   ├── crisp.png            # CRISP-DM framework diagram
│   └── kurt.jpeg            # Header image
├── analyzer.ipynb           # Full analysis notebook
└── README.md
```
