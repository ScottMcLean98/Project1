# Demographic and Economic Analysis of Seattle, Washington and Trends in Commercial Real Estate

With many large corporations left with vacant office space post-covid, many are considering requiring that employees return to the workplace. Meanwhile, others are working to create more remote or hybrid options.

###### How has the COVID-19 pandemic changed the workplace and how can we capitalize on this opportunity to build a workplace of the future?

Our team will examine if there are other options for investment, such as renting out space to other businesses? or creating more rental housing options? or other unique investment opportunities?

We will focus our research on Seattle, Washington.  

## Data Exploration
###### Financial Data:
In looking at financial data, we were interested in seeing how covid-19 had affected corporations and if there could be potential profit in renting out empty office space to other businesses or if it might make sense to consider developing them into rental units to attract talent into Washington State and more specifically, Seattle.

To obtain financial data, we used ticker symbols from a list of Publicly Traded Companies Headquartered in Washington that was provided by Washington State Women’s Commission (https://wswc.wa.gov) 

Using these ticker symbols we were able to pull financial data from Financial Modeling Prep: https://financialmodelingprep.com/developer/docs/

We were not able to gather as much corporate financial data as we had hoped. We were able to examine Total Debt, Total Assets and Net Income for 2022. 
The limited amount of data was able to show us that total assets are slightly above total debt. Net income is mostly positive, however Amazon was an outlier with debt, assets and income being vastly different than other companies in the state of Washington with headquarters in Seattle.

## Graphs
###### Financials for popular publicly traded companies headquartered in Washington State:
Total Current Assets for 2022

![Graph mapping total current assets for 2022.](https://github.com/ScottMcLean98/Project1/blob/main/TOTALcurrentassets2022.png)

Total Debt for 2022 by company

![Graph mapping Total Debt for 2022.](https://github.com/ScottMcLean98/Project1/blob/main/TotalDebt2022.png)

Total Net Income for 2022 4QTR reporting

![Graph mapping Net Income for 2022.](https://github.com/ScottMcLean98/Project1/blob/main/NetIncome4QTR2022.png)

###### Description of data exploration:

Using the Zillow API to iterate through selected regions and append the data to an empty list to create a Zillow dataframe. Added quarterly date values columns for each fiscal quarter to reduce the likelihood of dates not matching up when merging. Employed a similar process for Nasdaq inflation api to get Consumer Pricing Index information and added quarterly date values. Merged dataframes into one dataframe on the quarterly date values. Adjusted the home values using the CPI data to get the final dataframe using the dataframe to create a time series plot of real vs nominal values.
Used csv file from census data – ACS 2021 5 year and survey of consumer finances, 2019 to get the population, location, median household income, median home value, rental percentage median monthly rent columns. Dropping the null rows and adding columns for housing and rent ratios. Calculate the median for each value. Created scatterplots and linear regression plots for housing cost ratio to median income and rent cost ratio to median income.

###### Data exploration for vacancy rates in Seattle:

Using apartment vacancy rates from the past 5 years, the desired city was parsed out and then transformed into percentages. This was then plotted on a line graph compared to the national average provided by ApartmentList.com. The graph was recreated with the addition of the commercial vacancy rate in December 2022 with an additional line added for further clarification and emphasis on the difference between commercial and residential rates. Finally, Seattle parcel data was taken from the Washington GIS page, after having been filtered down from all parcels in Washington.
Each parcel contains an associated land use code which was translated based on the code index in Washington Legislation website. Specifically the land codes 11-19 and 61-69 were selected as they most fit the residential vs commercial descriptions. The totals from each of these groups were added together to get a total number of parcels for residential and commercial use. These totals were then multiplied by the vacancy rates for residential/commercial in December 2022 in order to get a rough estimate of the numbr of potentially vacant parcels.

## Graphs
###### Housing Cost Graphs in Seattle, WA:

Regression analysis between housing cost ratio and household income:

![Graph mapping the correlation between the housing cost ratio and household income.](https://github.com/ScottMcLean98/Project1/blob/main/Graphs/HCR.png)

Regression analysis between rent cost ratio and household income:

![Graph mapping the correlation between the rent cost ratio and household income.](https://github.com/ScottMcLean98/Project1/blob/main/Graphs/RCR.png)

Time setires analysis of nominal vs real housing prices in Seattle:

![Graph mapping the time series of seattle home values featuring nominal and real value.](https://github.com/ScottMcLean98/Project1/blob/main/Graphs/HVTS.png)

###### Graphs describing vacancy rates in Seattle, WA:

Figure 1:

![Graph mapping historic rental vacancy versus the U.S. national average.](https://github.com/ScottMcLean98/Project1/blob/main/Fig1-vacant.png)

Figure 2:

![Graph comparing residential vacancy versus a commercial vacancy snapshot.](https://github.com/ScottMcLean98/Project1/blob/main/Fig2-vacant.png)

Figure 3:

![Graph mapping the total number of residential and commercial parcels as well as the estimated vacant parcels for each](https://github.com/ScottMcLean98/Project1/blob/main/Fig3-vacant.png)

## Data Analysis
###### Housing Costs:
Zillow historical home values in Seattle, Washington have been on a continuous rise since 2012, more than doubling in value in that time. However, real value in housing prices have not yet reached their 2007 highs, with Seattle having a drop of real home values from $621,903 to a minimum of $263,317.82 between 2007 and 2009. Looking at the breakdown of housing and rental in Seattle, the housing to income ratio (housing value/median annual income), is 7.09, well above the national average of ~5 implying that homeowners are spending more of their income on housing then they would be living in another location. However, there is very little correlation between median income and the percentage of income going towards housing, suggesting that in all income brackets, people are spending similar percentages of their income on housing. Although, for renters, their rent-to-income ratio is 27% exceeding the national average by over 50% (17%) and their cost of living in Seattle for housing is over 102.2% of the national average. There is a strong correlation between median household income and rent-to-income ratio. So, when looking at lower income residents, their percentage spent on rent is nearly 15% higher than high income people, suggesting it is hard to find low cost rentals in the Seattle area.  

Companies headquartered in Seattle looking to provide more telework options to their employees would have the option of looking outside of Seattle for their employees. With that they might be able to provide less compensation to their employees due to average salaries in that position being lower in rural or smaller metropolitan areas alongside a lower cost of living. This would provide these companies with another effective means with which to reduce costs. 

###### Vacancy Rates:
Figure 1 in the vacancy group shows the fluctuations of the residential vacancy rate in Seattle over the past 5 years plotted with the national average computed by ApartmentList.com. From mid-2020 to mid-2021 the vacancy rates violently spike in response to the COVID-19 pandemic. ApartmentList.com made the conclusion that this was because people were fleeing from large cities to smaller ones. This also shows how large of an impact COVID-19 had on renters and landlords alike.

The second figure is a copy of the prior figure with the addition of the commercial vacancy rate in Seattle in December 2022. The blue line is simply for reference and to make the difference clearer. What this shows is how much higher the vacancy rate in commercial properties is. What I would've loved is to have found the commercial vacancy rate over time similar to the residential vacancy rate, but this provides a decent snapshot. This figure suggest that the commercial real estate market is more saturated than the residential one if there is a higher vacancy rate there. We could conclude based off of this graph that companies should look into renting out office space to be turned into apartments.

The final figure shows the number of residential parcels to commercial ones and then further breaking that down into vacant and occupied parcels based on the vacancy rates from above. The vacancy rate is just a calculated estimate but it shows how many more residential parcels there are compared to commercial ones. This is most likely due to the addition of actual private residences whereas the prior data mainly looked at apartment/rental residences however the difference is staggering. Based on this graph and the prior ones, the conclusion would be drawn that to get their money's worth, companies should be renting unused office space to other companies. This especially if the cost of renovating office space into apartment spaces.


## Limitations:
We were not able to gather as much corporate data as we had hoped. 
Median Income by household was not split in a way to obtain renter or owner income.
Publicly available data was not available for corporate data related to rental rates.
Historic commercial rental vacancy was not readily available and so we had to make do with a single snapshot.

## Contributors:
Elizabeth Hansen

Christopher Lynch

Scott McLean

Sheila Troxel

## Sources:
###### Real Estate sources:
https://data.nasdaq.com/api/v3/datatables/ZILLOW/DATA
https://data.nasdaq.com/api/v3/datasets/RATINF/USA_CPI
 Census Data - ACS 2021 5-year
Survey of Consumer Finances, 2019

###### Population Data sources:
https://www.census.gov/quickfacts/fact/table/seattlecitywashington/PST045222
https://www.seattletimes.com/seattle-news/data/pandemic-didnt-stop-people-from-moving-to-seattle-census-data-shows/
https://www.seattletimes.com/seattle-news/data/while-seattles-population-declined-another-king-county-city-saw-fastest-growth-in-wa/
https://esd.wa.gov/labormarketinfo/employment-estimates

###### Rental Vacancy sources:
https://www.apartmentlist.com/research/category/data-rent-estimates
https://www.commercialedge.com/blog/national-office-report/
https://geo.wa.gov/datasets/e8f2df3ed92843738f3dd778e92e93fc_0/explore?location=47.602128%2C-122.308183%2C13.93
https://apps.leg.wa.gov/wac/default.aspx?cite=458-53-030

###### Financial data sources:
Washington State Women’s Commission (https://wswc.wa.gov) 
https://financialmodelingprep.com/developer/docs/
