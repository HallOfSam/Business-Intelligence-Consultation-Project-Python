  # Overview
  
  **It’s no secret that rent prices have been skyrocketing as of lately, and many may pose the question as to “why”? We chose to investigate a specific factor that may contribute to the increased cost of living, crime rates.** 
  
  **By gathering, cleaning, and merging relevant datasets from various sources, as well as ruuning multivariate linear regression analyses in Python Jupyter Notebooks, this report finds a negavie impact of crimes per capita on the average rental prices across 51 major US cities over a time span of 11 years, from 2005 to 2015.**

# Quick Glimpse of the Deatils
To understand more details about the project, please refer to the "Executive Summary" pdf file. For a quick glimpse, please read the following:

# The Data
To examine the issue of how crimes per capita may affect the rent prices in certain cities, we gathered a US crime dataset from Kaggle (1970-2015) and rent estimate datasets (2005-2015) from the Office of Policy Development and Research (PDR). Due to the differences in our datasets, we decided to study the years 2005 to 2015, and we merged the two datasets based on city, state, and year after data cleaning.

We also included and merged the following 2 datasets with our existing one because
unemployment rate and median household income might be confounding variables in our
experiment:
● Unemployment data - US Bureau of Labor Statistics (2005-2015)
● Median Household Income Data - US Census Dataset (2005-2015)


# The Approach & Findings
We hypothesize two possible outcomes:
1. $𝐻_0$: Crimes per capita do NOT have an impact on average rent prices
2. $𝐻_a$ : Crimes per capita do have an impact on average rent prices

After data cleaning process, ummary statistics roughly suggested that crimes per capita moved in the opposite direction as the average rent prices from 2005-2015, while the median household moved in the same direction. Correlation coefficients coincided with our simple observations from the summary statistics. One thing worth noticing was that the 2008 financial crisis disrupted the unemployment rate data and rendered the correlation coefficient between unemployment rate and average rent prices less meaningful.

Based on our observations above, we started our study with a simple linear regression model, where the average rent prices was the dependent variable and crimes per capita was the independent variable. The univariate model indicates that crimes per capita have a negative impact on the average rent at a 1% significance level. According to the model, a unit change in crimes per capita leads to -0.1424 unit change in the average rent (in USD).

In order to isolate the effect of crimes per capita on average rent prices from potential confounding variables, we then conducted a multivariate linear regression analysis to integrate unemployment rate and median household income into our existing model. We found that using the MLR model, crimes per capita still have a negative impact on average rent prices at a 1% significance level, and a unit change in crimes per capita leads to -0.0.0945 unit change in the
average rent (in USD).

Furthermore, we investigated a subtopic about whether crimes per capita affect the average rent prices of different apartment types (0-bedroom, 1-bedroom, 2-bedroom, 3-bedroom, 4-bedroom apartments) differently. Slicing our datasets into 5 different subsets and using a similar multivariate linear regression analysis, we found out that crimes per capita do NOT have an impact on the average rent prices of 0 and 1-bedroom apartments at a 5% significance level, while they DO have a negative impact on the average rent prices of 2, 3, and 4-bedroom apartments at a 1% significance level. One thing one might notice is that we used logged variables for this subtopic study, which is because we wanted to interpret the results using percentage change instead of unit change, but this did not yield statistically significantly different results from not using logged variables.

# The Evaluation

Pointing the lens on the number of bedrooms showed that statistically crime has no effecton rent prices for studio (0-bedroom) and 1-bedroom apartments. Inadvertently, the regression analysis showed, controlling for median income and unemployment, that crime does have an effect on 2, 3, and 4 bedroom apartment units.

Our interpretation for these differences is that the average rent prices of larger two, three
and four bedroom homes might be more sensitive to changes in crimes per capita because
families (instead of individuals) typically stay in larger homes, and these groups of people place
a greater emphasis on safety. Therefore, would be willing to pay a higher rental price to ensure
the safety of their loved ones.

# The Conclusion

In conclusion, when we look at average rent across different apartment types in the 51
major cities from 2005-2015, we reject the null hypothesis and conclude that crimes per capita
do have an effect on average rent prices. Moreover, crimes per capita have a negative effect on
average rent prices.
