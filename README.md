# Analysis of crime rate data in São Paulo

## Segmenting and Clustering Neighborhoods in Sao Paulo, Brazil

### Applied Data Science Capstone Project Report for IBM Data Science Professional Certificate Course

###### Guilherme Moraes Rosa

### Introduction

  São Paulo is a municipality in the Southeast Region of Brazil. The metropolis is the most populous city in Brazil and the Southern Hemisphere, besides being the largest Portuguese-speaking city in the world. It exerts strong international influences in commerce, finance, arts and entertainment. The city's metropolitan area, the Greater São Paulo, ranks as the most populous in Brazil and the 12th most populous on Earth. 
  As the city grows and develops, it becomes increasingly important to examine and understand it quantitiatively. This project seeks to answer the following questions:
    
    . What is the most common crime in the city of São Paulo?
    . What neighborhoods have the highest and lowest crime rate? 
    . What is the most common crime at the highest crime rate neighborhood? 
    . What neighborhoods have the highest robbery and theft rate?
    . Using Foursquare data, what venues are most common at the locations with highest and lowest crime rate?
    . Is crime level, specially theft rates, correlated to the number of venues?

### Target Audience

  The target audience of this report are legislators seeking to improve the city security or anyone that is interested in opening a business or buying a house, but have no idea what neighborhood is safest.

### Data

  The first data source comes from Kaggle from the following link https://www.kaggle.com/inquisitivecrow/crime-data-in-brazil#BO_2016.csv and contains more than 700,000 rows and 20 columns of information about crime at the state of São Paulo during the year of 2016. The data contains a file in csv format. The second data source comes from  https://foursquare.com/.

  Using this data will allow exploration and examination to answer the questions. The São Paulo crime rate data will enable us to properly group crime by neighborhood, and Foursquare will provide us with geographical data. Both data will then allow us to cluster and quantitatively understand the venues most common to that location.

### Methodology

#### The methodology will include:

  1) Loading data set.
  
  2) Exploring the data: A dataset analysis to answer the questions below:
    
    . How many police stations are in the city of São Paulo 
    . What is the crime rate per region?
    . What is the most common crime in the city of São Paulo?
    . What neighborhoods have the highest and lowest crime rate?
    . What is the crime count at the region with highest crime rate?
    . What neighborhoods have the highest robbery and theft rate?

  3) Segment neighborhoods and examine similarity of these regions by crime rates applying K-Means clustering.

  4) Cluster Analysis.

  5) Foursquare data. We will use nearby venues to answer the questions below:
    
    . What is the venue count per region?
    . What is the most common venue in the city of São Paulo? 
    . What venues are most common at the locations with highest and lowest crime rate?

  6) Look if there is a correlation between number of venues and crime rates

  7) Perform k-means statistical analysis on locations of interest based on crimes and number of venues
  
### Loading dataset 
Because of the original dataset size, we will analyze only the data from the city of São Paulo over the first month of 2016. The new created dataset have more than 40,000 rows and 5 columns which are Police Station, Crime, Latitude, Longitude and City. Instead of neighborhood, dataset contains the region which is located the police station.

### Exploring the data: Dataset analysis

To answer the questions above it was used the libraries Pandas and Matplotlib, mainly the built-in functions unique and groupby. On matplotlib it was used bar plot and box plot to better understanding the data. Exploring the count of crimes by neighborhood gives us the first glimpse into the distribution. Examining the crime types enables us to learn the most frequent occuring crimes which we then plot as a bar chart to see most frequenty type.

### Segment neighbourhoods by crime rate

In this section it was used Pandas, Folium and Scikit-learn libraries. To segment regions of São Paulo it was used the algorithm K-Means to create 3 different clusters by crime rates similarity and Folium was used to plot the city map, including clusters. Pandas was used to prepare the data.

### Cluster Analysis

Some analytics was made to determine what each cluster represents, specially the crime percentage per cluster. The findings will be discussed at results section.

### Foursquare data

It was used Pandas and Foursquare data to answer the questions above.

### Is crime rate correlated to the number of venues?

It was used Pandas and Seaborn library to study a possible correlation or not between crime rate and number of venues. A regression plot was used and the results will be discussed later.

### K-Means statistical analysis on locations of interest based on crimes and number of venues

In this section it was used Foursquare data, Pandas, Folium and Scikit-learn libraries. To segment regions of São Paulo it was used the algorithm K-Means to create 3 different clusters by crime rates and venues similarity. Folium was used to plot the city map, including clusters. Pandas was used to prepare the data.

### Results

The analysis enabled us to discover and describe visually and quantitatively:

  #### 1) Statistics about the city of São Paulo, such as:

    .  The most common crime, which is Theft
    .  Crime frequency by region
    .  The most common venue, which is bakery
    .  Venue count by region

  #### 2) Similarity between neighborhoods by crime rate

  The algorithm K-Means was used to segment the neighborhoods in three clusters. Some analytics was made to determine what each cluster represents. The result is that cluster 0 and 2 are much more similar to each other, while cluster 1 looks a bit different, mainly because of theft rate that it is much smaller than in the previous two and murder rate that is up than three times bigger. Cluster 1 also have a higher rate of Rape and Narcotics traffic.

  #### 3) Show the absent of correlation between crime rate and number of venues

  Using Seaborn and Scipy libraries a regression plot was created and the results showed that there is no correlation between crime rate and number of venues. The Pearson Correlation Coefficient is 0.1434107901446711  with a P-value of P = 0.1525082373867819 

  #### 4) Similarity between neighborhoods by crime rate and venue category

  Again, the algorithm K-Means was used to segment the neighborhoods in three clusters. But this time it was segmented considering crime rate and venue category. Using venue and crime data we have mainly two great clusters, the first is located at the city center and the second embrace peripherical regions.


### Discussion

There is value to the city to explore the detailed crime data using data science to predict frequency, location, timing and conditions to best allocated resources for the benefit of its citizens and it's police force. However, human behaviour is complex requiring thick profile data by individual and the conditions surrounding the event(s). To be sufficient for reliable future prediction it would need to demonstrate validity, reliability and sufficiency.

As you can see at the first clustering, cluster 0 and 2 are much more similar to each other, while cluster 1 looks a bit different, mainly because of theft rate that it is much smaller than in the previous two and murder rate that is up than three times bigger. It is interesting to note that cluster 1 is comprised almost by peripheric areas of the city and probably consists of low income neighbourhoods, these areas also have a higher rate of Rape and Narcotics traffic, which is equal to zero for cluster 0 and 2. I can conclude that cluster 1 embrace the more violent regions of the city. Legislators should focus social policies on those areas, improving the population quality of life, and as a side effect diminishing crime rates, which I think it is caused by social inequality. A good idea would be to include social income data together to this analysis. Besides the high theft rate, the safest places to live or open a businness are at cluster 0 and 2.

At the second clustering, using venue and crime data we have mainly two great clusters. The first is located at the city center and the second embrace peripherical regions, which suggests that the city center has a different category of venues when compared to peripherical areas.

### Conclusion

Using a combination of São Paulo crime data and Foursquare venue data we were able to analyze, discover and describe neighborhoods, crime and statistically describe quantitatively venues by locations of interest.
