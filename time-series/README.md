
# Zillow Time Series Analysis

## Business Understanding


A client broker is looking advise his clients as to where they should invest in residential real estate.  They want to buy in the US but are agnostic as to where.  

The clients are looking for an understanding of past performance for both long and short term time horizons (3 year ROI and 10 year ROI) as well as gaging volatility in each local market place (represented by the coefficient of variance).  They also want to see forward looking modeling projections.

1. What has shown the best long term appreciation?
2. What has shown the best short term appreciation?
3. What location has the least amount of risk investing?
4. Can future median house prices in a location be predicted and what are the projections?
5. Where do we recomend investing?


## Objective

Conduct a time series analysis to predict the five best locations to invest in based on ROI.

## Methods

ROI Equations:
df['ROI3'] = (df['2018-04']/ df['2015-04'])-1
df['ROI10']= (df['2018-04']/ df['2008-04'])-1

CV: Standard Deviation / Mean for both 3 and 10 year time horizons.

## EDA

5 Zip Codes with highest 3 year ROI and lowest 3 year CV
![image](https://user-images.githubusercontent.com/106030704/211175371-b2c5e2fb-4f73-45df-aced-c3dc1f22540f.png)

5 Zip Codes with highest 10 year ROI and lowest 10 year CV
![image](https://user-images.githubusercontent.com/106030704/211175379-71a67b67-0060-4b16-9dd9-000170f86f0a.png)

Average Median Home Values over time.
![image](https://user-images.githubusercontent.com/106030704/211175434-46126f35-538d-47cd-9692-1d8e90e4d923.png)


## Modeling

SARIMAX Model diagnostics
![image](https://user-images.githubusercontent.com/106030704/211175458-05e7b8fa-92c9-4c18-9ebb-1b32130042e5.png)

Dynamic Forecast
![image](https://user-images.githubusercontent.com/106030704/211175472-524fef21-9600-47a4-aceb-af3bfff8e648.png)
The root mean squared error is $960

Future Prediction
![image](https://user-images.githubusercontent.com/106030704/211175497-3f75da00-e1cc-4920-a932-262e2655531f.png)


## Findings

10 of the top 50 zipcodes with the highest 10 year ROI were in Santa Clara County.  The average ROI over 10 years was 88% in Santa Clara county as compared to 13% on average over the same period nationwide.

4 of the top 5 counties with the most top 50 '3 year ROI' zipcodes are in Florida.  The average 3 year ROI in Florida is 36% as compared to the 21% national average.

The best investment for a longer time horizon is Santa Clara County in California.  For investors more interested in short term flips, the state of Florida and specifically Brevard, Volusia, Polk, and Duval counties.

5 zipcodes with the highest 10 year ROI: 

1. 02116 in Boston, MA
2. 03215 in Waterville Valley, New Hampshire
3. 94574 in St. Helena, CA
4. 96752 in Kauai County, Hawaii
5. 96722 in Kaui County, Hawaii

5 zipcodes with highest 3 year ROI:
1. 2790 in northeastern North Carolina
2. 30032 in Dekalb County, Georgia
3. 19134 in Philadelphia, PA
4. 28208 in Charlotte, North Carolina
5. 33705 in St. Petersberg, Florida

5 zipcodes with lowest 10 year CV:
1. 64836 in Jasper County, Missouri
2. 16508 in Erie, PA
3. 64801 in Jasper County, Missouri
4. 64870 in Jasper Country, Missouri
5. 79934 in El Paso, Texas

Our forecast model shows a short term price dip followed by a steady trend up over the next three years.
