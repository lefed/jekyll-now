---
published: false
---

---
layout: post
title: Predicting Energy Use in Commercial Buildings in SF Using Linear Regression
---

Energy use among commercial buildings is highly variable, and has a significant impact on national [GHG emissions](https://www.epa.gov/ghgemissions/global-greenhouse-gas-emissions-data) and power supply needs for the electricity grid. Predicting building energy demand is particularly important for smart control of grid assets.

For a recent machine learning project, I chose to try to use linear regression techniques to predict the annual per square foot energy use intensity (EUI) of commercial buildings in San Francisco.

Below is a brief overview of my project and conclusions.

### Combining Two Datasets

I chose to combine two data sets for this project. I used information from the [City of San Francisco's Existing Commercial Buildings Energy Performance Ordinance Report](https://data.sfgov.org/Energy-and-Environment/Existing-Commercial-Buildings-Energy-Performance-O/j2j3-acqj)
in order to provide my 'target' for my machine learning algorithm - in this case I used 2015 weather normalized site EUI in kBTU/SF - in combination with commercial property data scraped from the [SF Planning Department's Property Information Map](http://propertymap.sfplanning.org/) using Selenium and Beautiful Soup.

### Cleaning the Data

Using python and pandas, I cleaned the data that I collected from the SF Property Information Map and Existing Commercial Buildings Energy Performance Ordinance Report to remove erroneous data such as building dates after 2015 and to convert strings into usable datetime objects and categorical variables into dummy variables that could be used in my linear regression models.

### Feature Engineering

In order to test and improve my model's performance, I included features that had quality data points and may have an influence on yearly energy use such as year built, status of compliance with energy audits, and property value. I also created classifications of building types based on owner inputed classifications such as those for higher education facilities, various office types, or healthcare facilities.

Possible predictors used in my model included:
- Postal Code
- Energy Audit Status 
- Property Type
- Date Next Energy Audit Due
- Land Value
- Structure Value
- Basement Area
- Building Area
- Last Sale Price
- Last Sale Date
- Parcel Area
- Year Built
- Parcel Frontage, Depth, Shape
- Construction Type
- Number of Units, Stories, Rooms, Bathrooms, Bedrooms

### Testing of Models

Due to the relatively small size of my dataset (approximately 1000 valid entries) and the relative variability of my target, I found that decision tree based methods such as Random Forest did not work well for finding correlations or making predictions. Linear models did not perform well (my highest model R2 score was around 0.52), however they provided insight as to the elements that were important and had performance better than randomly taking the mean of the data.

### Cross-Validation, Feature Scaling, and Coefficient Penalization



### Important Features

### Conclusions

### What I would try next
