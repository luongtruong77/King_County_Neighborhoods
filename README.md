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
In this section, I will do exploratory analysis and visualize the data obtained to have a first look at our chosen area. To complete this task, I decided to divide my methodology into 5 sub-sections.
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
