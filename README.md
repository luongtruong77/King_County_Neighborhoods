# 1. Introduction
- In this project, I choose **King county, Washington, USA** to be my geographical area of investigation. King county is most populous and important county of Washington state with the estimated population of more than two million people. As of 2018, the median household income of King county was **$95009**, which is approximately ***45%*** higher than national average; and is one of the most educated regions in the US with **53.2%** of its residents age 25 or holder holding a bachelor's or higher in 2018 (https://www.kingcounty.gov/, 2018), which makes king county is of the best place to live in the US.
- More specifically, as a long-time Washingtonian, I will focus on only some citites that I personally think that they are major cities of the county (namely Seattle, Bellevue, Renton, etc.) with top companies having their headquarters (Amazon, Starbucks, Microsoft, Boeing, etc.)
- The main **question** to answer in this project is that: if a family of four with a upper-middle class income wants to move to this area, which city (neighborhood) would be best to live in terms of **property value, safety, community**, etc.
- We will use data science tools to explore, analyze, and visualize the data obtained from variety of sources to decide which neighborhood is the best for the stakeholders.
# 2. Data
- For the safety factor, I obtained King county's incidents 2019 dataset from King county's Sheriff Office (https://data.kingcounty.gov) to determine which city is the safest among the county's major cities.
- For the property factor, I used King county house price dataset from Kaggle and King county zipcode centroids dataset from Amazon AWS (https://prod-hub-indexer.s3.amazonaws.com) to determine which most appropriate neighborhood of the chosen city.
- We will explore nearby and common venues of the area using Foursquare API and cluster them into several clusters. The coordinates used in the algorithms will be extracted from house price dataset and zipcode centroid dataset.
# 3.Methodology
In this section, I will do exploratory analysis and visualize the data obtained to have a first look at our chosen area. To complete this task, I decided to divide my methodology into 4 sub-sections.
### 3.1 Crime rates analysis
In this section, we will take a quick look at the crime rates reported in 2019 by the Sheriff's office in the major cities of King County to determine which city is the safest. </br>
Once we find which one is the safest, we will pick that city to become the city of interest to dig deeper into it.
### 3.2 House prices analysis
In this section, we will do a quick house prices analysis of our chosen city to get a broad feeling about how expensive house prices are around the neighborhood.
### 3.3 Explore the neighborhoods
In this section, we will:
- Use geopy library to get the latitude and longitude values of our chosen city.
- Use **Folium** library to create a city's map and its neighborhoods.
- Use **Foursquare API** to explore the neighborhoods to get to know more about the city itself.
### 3.4 Cluster the neighborhoods
In this section, we will:
- Use KMean algorithm to cluster neighborhoods into different clusters.
- Explore nearby venues for each cluster and assign names for each cluster based on its own characteristics.
# 4.Results
### 4.1 Crime rates analysis
This is the first 10 rows of King County's crime dataset after loading data in pandaframe and cleaning it. The original dataset has 15 columns but I only choose features that are in our interest to display.
![](/images/4.1p1.png)
I then define 5 major cities, which are SEATTLE, BELLEVUE, KENT, RENTON, and FEDERAL WAY based on criteria of kingcounty.gov and use **matplotlib library** to plot the graph.</br>
This graph shows number of crimes commited by five major cities in 2019 in King County.
![](/images/4.1p2.png)
As we can see from the graph, **Bellevue** is the safest city with the least crime counts reported in 2019. Even though **Seattle** is the most popular and biggest city of King County, with almost 8000 cases committed in 2019, it is not a very safe city to consider buying properties or to live a peaceful life. </br>
Now that we have chosen **Bellevue** as our city of interest, let's dive deeper into it and explore its house prices in the past.
### 4.2 House prices analysis
In this section, I use zipcode dataset of King county from kingcounty.gov and house price dataset from Kaggle to merge and filter the data. Even though we are not digging too deep into this house price dataset, let's look at the overal correlation between its features by the heatmap created by using **seaborn library**.
![](/images/4.2p1.png)
Even though the dataset about house prices look very interesting, we are not going to analyze the price as a whole, but rather comparing the average house prices by **Bellevue**'s zipcodes. If you are interested in the house price dataset, for more in depth of King County's house prices analysis and prediction, please visit [HERE](https://github.com/luongtruong7793/House-Sales-in-King-County-WA/blob/master/House%20Sales%20in%20King%20County%2C%20USA.ipynb) . Throughout this project, I will use *zipcode* as an indicator of the neighborhood since I do not have much data on the neighborhoods themselves and the maps (will be created later) will tell pretty much everything we need to know about **Bellevue**.
