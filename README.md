# Used Car Price Analysis

## Project Overview

This project analyzes a Kaggle dataset of ~426,000 used car listings to figure out what really drives used car prices. The goal is to give a used car dealership some practical, data-backed recommendations on what kind of inventory they should stock up on.

I structured the project around the **CRISP-DM** framework: Business Understanding → Data Understanding → Data Preparation → Modeling → Evaluation → Deployment.

## Notebook

You can find the full analysis here: [`analyzer.ipynb`](analyzer.ipynb)

## Summary of Findings

After cleaning up the data (handling missing values, dropping weird outliers), I built and tuned a few regression models (Linear, Ridge, Lasso) to predict prices. The Lasso model performed the best. Here is what the model tells us:

- **Car Age:** This is the single biggest price driver. Older vehicles lose value significantly with every passing year.
- **Mileage (Odometer):** This is the second biggest factor. A low-mileage car commands a premium, largely independent of its age.
- **Brand and Model Value:** The specific make and model of the car is a massive driver of price. Certain models hold their value significantly better than others.
- **Fuel Type (Diesel Premium):** Compared to the baseline of a diesel engine, all other fuel types (gas, hybrid, electric) are significantly cheaper. 
- **Clean Titles:** The model heavily penalizes anything less than a clean title (e.g., salvage, rebuilt, parts only). A clean title is a must for premium pricing.
- **Vehicle Type:** Specialty body styles like convertibles, off-roaders, coupes, and pickup trucks hold their value noticeably better than standard sedans or SUVs.

## Recommendations for Dealers

1. **Prioritize newer, low-mileage cars.** Since age and odometer readings are the two strongest predictors of a high price, these are your safest investments.
2. **Leverage brand and model reputation.** Because model value is such a strong predictor of price, prioritize acquiring models known for high historical resale value, as they command a premium regardless of other factors.
3. **Source more diesel vehicles.** There is a clear market premium for diesel engines over gas and hybrids.
4. **Avoid compromised titles.** Unless you can acquire them at a severe discount, salvage or rebuilt titles drag down the resale value too much to be worthwhile.
5. **Target specialty body styles.** Fun or utility-focused vehicles (trucks, off-roaders, convertibles) command measurable premiums and are worth stocking up on over standard commuter cars.

## Next Steps

Predicting the market price is a good start, but dealerships already have tools like Kelley Blue Book for that. To make this analysis truly useful for a business, future iterations should focus on **profitability** instead of just pricing.

Here's what I'd look into next:

1. **Predict Profit Margins:** If we can get data on wholesale auction prices and repair costs, we could build a model to spot undervalued cars at auctions that will yield the highest profit margins.
2. **Predict "Days on Lot":** A high-margin car isn't great if it sits on the lot for 120 days eating up financing costs. We should build a model to estimate how fast a car will sell based on local demand.
3. **Model Depreciation Curves:** Since age is the biggest price driver, it would be useful to predict exactly how much value a car will lose over the next 30 to 60 days. This would help dealers know when to aggressively discount a car before it hits a depreciation cliff. A time series model will be very helpful in predicting the depreciation rate.

## Repository Structure

```
car-price-analysis/
├── data/
│   └── vehicles.csv   # Raw dataset (~426K used car listings)
├── images/
├── analyzer.ipynb     # Full analysis notebook
└── README.md
```
