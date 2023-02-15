Demographic and Economic Analysis of Seattle, Washington and Trends in Commercial Real Estate

With many large corporations left with vacant office space post-covid, many are considering requiring that employees return to the workplace. Meanwhile, others are working to create more remote or hybrid options.

How has the COVID-19 pandemic changed the workplace and how can we capitalize on this opportunity to build a workplace of the future?

Our team will examine if there are other options for investment, such as renting out space to other businesses? or creating more rental housing options? or other unique investment opportunities?

We will focus our research on Seattle, Washington.  

Financial Data:
In looking at financial data, we were interested in seeing how covid-19 had affected corporations and if there could be potential profit in renting out empty office space to other businesses or if it might make sense to consider developing them into rental units to attract talent into Washington State and more specifically, Seattle.

To obtain financial data, we used ticker symbols from a list of Publicly Traded Companies Headquartered in Washington that was provided by Washington State Women’s Commission (https://wswc.wa.gov) 

Using these ticker symbols we were able to pull financial data from Financial Modeling Prep: https://financialmodelingprep.com/developer/docs/

We were not able to gather as much corporate financial data as we had hoped. We were able to compare Total Debt, Total Assets and Net Income for 2022.

Description of data exploration

Using the Zillow API to iterate through selected regions and append the data to an empty list to create a Zillow dataframe. Added quarterly date values columns for each fiscal quarter to reduce the likelihood of dates not matching up when merging. Employed a similar process for Nasdaq inflation api to get Consumer Pricing Index information and added quarterly date values. Merged dataframes into one dataframe on the quarterly date values. Adjusted the home values using the CPI data to get the final dataframe using the dataframe to create a time series plot of real vs nominal values.
Used csv file from census data – ACS 2021 5 year and survey of consumer finances, 2019 to get the population, location, median household income, median home value, rental percentage median monthly rent columns. Dropping the null rows and adding columns for housing and rent ratios. Calculate the median for each value. Created scatterplots and linear regression plots for housing cost ratio to median income and rent cost ratio to median income.

Graphs

Graph mapping the correlation between the housing cost ratio and household income.

Graph mapping the correlation between the rent cost ratio and household income.

Graph mapping the time series of seattle home values featuring nominal and real value.

![Graph mapping historic rental vacancy versus the U.S. national average.](/blob/main/Fig1-vacant.png)

![Graph comparing residential vacancy versus a commercial vacancy snapshot.](/blob/main/Fig2-vacant.png)

![Graph mapping the total number of residential and commercial parcels as well as the estimated vacant parcels for each](/blob/main/Fig3-vacant.png)

Data Analysis
Zillow historical home values in Seattle, Washington have been on a continuous rise since 2012, more than doubling in value in that time. However, real value in housing prices have not yet reached their 2007 highs, with Seattle having a drop of real home values from $621,903 to a minimum of $263,317.82 between 2007 and 2009. Looking at the breakdown of housing and rental in Seattle, the housing to income ratio (housing value/median annual income), is 7.09, well above the national average of ~5 implying that homeowners are spending more of their income on housing then they would be living in another location. However, there is very little correlation between median income and the percentage of income going towards housing, suggesting that in all income brackets, people are spending similar percentages of their income on housing. Although, for renters, their rent-to-income ratio is 27% exceeding the national average by over 50% (17%) and their cost of living in Seattle for housing is over 102.2% of the national average. There is a strong correlation between median household income and rent-to-income ratio. So, when looking at lower income residents, their percentage spent on rent is nearly 15% higher than high income people, suggesting it is hard to find low cost rentals in the Seattle area.  
Companies headquartered in Seattle looking to provide more telework options to their employees would have the option of looking outside of Seattle for their employees. With that they might be able to provide less compensation to their employees due to average salaries in that position being lower in rural or smaller metropolitan areas alongside a lower cost of living. This would provide these companies with another effective means with which to reduce costs. 


Limitations:
We were not able to gather as much corporate data as we had hoped. 
Median Income by household was not split in a way to obtain renter or owner income.
Publicly available data was not available for corporate data related to rental rates.
Historic commercial rental vacancy was not readily available and so we had to make do with a single snapshot.

Contributors:
Elizabeth Hansen
Christopher Lynch
Scott McLean
Sheila Troxel

Sources:
Real Estate sources:
https://data.nasdaq.com/api/v3/datatables/ZILLOW/DATA
https://data.nasdaq.com/api/v3/datasets/RATINF/USA_CPI
 Census Data - ACS 2021 5-year
Survey of Consumer Finances, 2019

Population Data sources:
https://www.census.gov/quickfacts/fact/table/seattlecitywashington/PST045222
https://www.seattletimes.com/seattle-news/data/pandemic-didnt-stop-people-from-moving-to-seattle-census-data-shows/
https://www.seattletimes.com/seattle-news/data/while-seattles-population-declined-another-king-county-city-saw-fastest-growth-in-wa/
https://esd.wa.gov/labormarketinfo/employment-estimates

Rental Vacancy sources:
https://www.apartmentlist.com/research/category/data-rent-estimates
https://www.commercialedge.com/blog/national-office-report/
https://geo.wa.gov/datasets/e8f2df3ed92843738f3dd778e92e93fc_0/explore?location=47.602128%2C-122.308183%2C13.93
