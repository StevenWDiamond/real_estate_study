## Problem Statement

Our data science team at the Ames Chamber of Commerce has been tasked to understand housing in and around the Ames area:

- What are the most important factors driving real estate prices?
- What factors are not important (paying close attention to those things that are typically assumed to be true)?

We have obtained a dataset from the Assessor's office which was compiled by Dean De Cock at Truman State University. It includes 2,051 home sales in the area between 2006 and 2010. To analyze our data, will be using a regression model and judging our model using the R2 metric.

## Executive Summary
Our team at the Ames Chamber of Commerce was tasked with looking a real estate sales dataset from the Ames area, understanding its implictions and making recommendations on how we can leverage this knowledge to the benefit of our members.

To accomplish this task, we will do the following:

- Clean the data
- Perform an Exploratory Data Analysis to understand what we can from the data itself, add additional information through feature engineering and create a dataset that is completely numerical
- Apply multiple regression methods to determine which best suits this data
- Chose one of these methods, tune the model by varying the inputs and then examine the model

## Table of Contents

- Loading Data
- Data Cleaing
- Exploratory Data Analysis
- Modeling
- Model Selection
- Model Tuning
- Model Evaluation
- Conclusions and Recommendations


## Conclusions

Regression helps us to see if our data can accurately predict outcomes and, in this case, we can say that our data explains nearly 95% of the variation in home prices in the Ames area. Now that we know that we have a solid model, there is much here to be mined for our members. A few sample learnings include:

- Lot area is a significant variable but not it’s shape or slope or street frontage
- Wood decks and screened porches are significant factors
- Most miscellaneous features are not statistically significant, but elevators and tennis courts, while very rare in Ames, are significant to the model
- Overall condition, which had a very small negative correlation, is a significant variable