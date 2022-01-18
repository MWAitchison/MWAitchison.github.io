# London House Price Predictions

**Project description:** Over the past 40 years, the 32 boroughs which make up Greater London have seen
great fluctuating appreciation in house prices, which I can begin to explain the
interborough house price disparity with the aid of past literature. Due to the number
of boroughs, I cluster all 32 into four clusters via traditional euclidean k-means
clustering and k-means longitudinal clustering which produced identical clustering
subsets when optimised. With the more manageable four timeseries objects, I could
apply several models of varying success in order to forecast the next five years.
These included the basic benchmark methods of the average forecast, the Naïve
method, and with drift. The final model I concluded with was an ARIMA model for
each cluster predicting the next five years of the House Price Index for that cluster
of boroughs. By calculating the percentage change between the March 2021 House
Prices Index and my March 2026 predicted value, we discover the cluster which
contains Kensington and Chelsea, and Westminster has the largest price increase
of an estimated 16.7%. The risk associated with a five-year investment reveals the
best risk vs reward cluster prediction is attributed to the cluster which contains the
Northwestern boroughs.

## Clustering Techniques
Taking the initial 
```r
# Data Wrangling House Price Index for London −−−−
## Loading dataset
HousePriceIndex <− read.csv ("Data/UK_House_price_index.csv")
HousePriceIndex
## S e l e c t i n g only the London Boroughs and renaming Data column
AveragePrice <− HousePriceIndex [−1,c(1,3:34)] %>%
rename(Date = X)
# Convert to dataframe
AveragePrice <− as.data.frame(apply(AveragePrice,2,as.numeric))
```


