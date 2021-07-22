# MTA Turnstile Data Analysis and Location Recommendation
---
by Steven L Truong
## Abstract
---
In this project, I will use the [MTA Turnstile Dataset](http://web.mta.info/developers/turnstile.html) to analyze the volume of traffic in New York City's subway stations to recommend the best location to open the new restaurant for my client - Greenwood LLC. After obtaining the dataset from MTA website, I will clean the data and use `Python's` libraries to visualize it in **graphs, map, and word-clouds** to retrieve useful information. Finally, based on what I have doing analysis, I will communicate my results to my client and help them with their business.  

## Design
---
- The purpose of this project is to answer the client's question: *"What is the best location to open the authentic Vietnamese restaurant?"* By looking at the **analysis and visualization**, we would know the top 5 potential neighborhoods to start the business. 
- Moreover, I will levarage the [**Foursquare API**](https://developer.foursquare.com/docs/api-reference/venues/explore/) to retrieve the most common venues with respect to the neighborhood to get more insights about the data. The process is designed to potentially produce the most optimized results and answer the business' critical question.

## Data
---
- **The main dataset**: the dataset is obtained from the [MTA's website](http://web.mta.info/developers/turnstile.html) and ingested into `Jupyter Notebook` using `SQL`. It contains over **3,500,000** rows (4 months' worth of data - from 11/28/2020 to 03/27/2021) with **11** features whereas two of them are type of **int** and nine are type of **object**. We will mostly focus on the **ENTRIES** feature and the timeframe is between **8AM** and **10PM** everyday. 
- **The additional source of data**: There are also few more features will be used for our purposes acquired by `Square API` such as: latitude, longitude, and common venues.

## Algorithms
---
##### Data cleaning
Almost all raw data that we pull from the internet is messy and this dataset is no exception. As a data scientist, we spend significant amount of time to clean and prepare our data for visualization or building models.
- For the purpose of opening the restaurant, we only focus on the data between **8AM-10PM**, so filter the data based on this timeframe helps our process.
- There are duplicate entries that will potentially skew our analysis, do dropping them is always a good idea.
- There are rows that contain *enormous* value of entries (outliers), which is not good for the dataset's integrity and dropping them is also making the dataset is a bit cleaner.

##### Using API
Getting more relevant data almost always helps. By levaraging [**Foursquare API**](https://developer.foursquare.com/docs/api-reference/venues/explore/) to explore nearby venues of the top stations, we can determine which station has more potential to grow as restaurant owners.

## Tools
---
- SQL for data ingestion, storage and extraction into Python notebook.
- Numpy and Pandas for data cleaning and manipulation
- Matplotlib and Seaborn for plotting and visualizing
- Square API
- Other libraries: folium (map rendering), wordcloud (wordcloud generating), requests (handling url requests)


## Communication
---
- The presentation in pdf file is included to logically and visually convey the results of the EDA. Below are few highlights from the presentation:
    - The top 5 stations with the most traffic displayed in bar plot fashion.
![](https://github.com/luongtruong77/EDA-project/blob/main/figures/top_5_barchart.png?raw=true)

    - The top 5 stations with the most traffic displayed in map fashion (higher traffic will be displayed as bigger circle)
![](https://github.com/luongtruong77/EDA-project/blob/main/figures/top_5_map.png?raw=true)

    - The ridership of the top 5 stations by day, by day of the week, and by week displayed in time series line charts.
![](https://github.com/luongtruong77/EDA-project/blob/main/figures/results_page7.png?raw=true)

