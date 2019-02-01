# Capstone Report

Descriptive Title
Using Foursquare API and DB-Scan to direct new expansion opportunity for a small food conglomerate.



## Introduction
#### Problem & Background 
The following proposal was presented by a small food conglomerate - "We are based out of Toronto and would like to branch out to either the east or west coast of the United States. The two cities that interest us are San Francisco on the west coast and New York on the east coast. Out of these two cities, which one is a more ideal location for our business?" 

#### Audience
This conglomerate would like to utilize its resources effectively and does not have the means to establish a large number of franchises in either location. Therefore, they were willing to strategize in order to maximize their impact. Similar ventures, especially those in the service industry can use this or a similar model to make decisions on where to expand while optimizing their investment. 

## Data
#### Description
To solve this problem, the venue categories for each location in the neighborhoods of each of the cities would be required. For this data, the websites containing the neighborhoods and their respective postal codes are listed below along with a file containing the required geospatial-coordinates.

#### Source
Link to the neighborhood and postal code information for each city: <br>
Toronto - https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M <br>
New York City - https://www.health.ny.gov/statistics/cancer/registry/appendix/neighborhoods.htm <br>
San  Francisco - http://www.healthysf.org/bdi/outcomes/zipmap.htm <br>
Link to the latitude and longitude of every zip code in the united states: <br>
https://gist.github.com/erichurst/7882666 <br>
(The geospatial-coordinates for Toronto are taken from the file provided in the previous project named 'Geospatial_Coordinates') <br>
This information will allow the use of Foursquare API to gather venue categories for the analysis.

## Methodology
#### Exploratory data analysis
For the exploratory data analysis, two tables are created:
The first consisted of the top 10 'most common venues', which were retrieved for each neighborhood in that city.
The second summarized each specific rank from the first able for: <br>
The number of unique venues in that rank, and <br>
The top venue for that rank or the venue category that has the highest frequently

#### Machine Learning Algorithm
The DB-Scan machine learning algorithm was implemented with an epsilon value of 0.5, and a 'minimum points' of 5. Other parameters remained constant with the metric being Euclidean, algorithm being 'auto', and the leaf size being 30. Based on the most common venue categories, the DB-Scan algorithm will be used to cluster neighborhoods. The tables formed will then compare the top venue categories for all the neighborhoods of that city.

## Results
On the initial run with the eps set to 0.5, the number of clusters formed were more or less the same with each city having 1 cluster (labelled "0"), but unlike New York City, Toronto and San Francisco have a few neighborhoods that are considered to be noise and not part of a cluster (labelled "-1").

From the compiled results, the count of the types of venue categories and the names of the neighborhoods that were not clustered at the end of each run :
Toronto <br>
5 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
3 Café/Coffee shop/Bakery/Donut shop <br>
1 pub <br>
1 hotel <br>
Roselawn <br>
Forest Hill West, Forest Hill North <br>
Berczy Park <br>
Central Bay <br>

4 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
4 Café/Coffee shop/Bakery/Donut shop <br>
1 pub/brewery <br>
1 hotel <br>
Roselawn <br>
Forest Hill West, Forest Hill North <br>
Berczy park <br>
King Richmond <br>

5 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
3 Café/Coffee shop/Bakery/Donut shop <br>
1 pub/brewery <br>
1 hotel <br>
Yorkville, North Midtown, The Annex <br>
Harbod, UofT <br>
Union Station, Harbourfront East, Toronto Islands <br>
Little Portugal, Trinity <br>
	
New York City <br>
8 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
2 Café/Coffee shop/Bakery/Donut shop <br>

7 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
2 Café/Coffee shop/Bakery/Donut shop <br>
1 pharmacy <br>

8 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
2 Café/Coffee shop/Bakery/Donut shop <br>
	
San Francisco <br>
0 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
5 Café/Coffee shop/Bakery/Donut shop <br>
1 park <br>
4 stores <br>
St. Francis Wood <br>

1 Pizza place/Restaurant/Deli / Bodega/Sandwich Place<br>
4 Café/Coffee shop/Bakery/Donut shop <br> 
0 park <br>
3 stores <br>
St. Francis Wood <br>

2 Pizza place/Restaurant/Deli / Bodega/Sandwich Place <br>
4 Café/Coffee shop/Bakery/Donut shop <br>
1 park <br>
3 stores <br>
St. Francis Wood <br>
	
	
## Discussion
#### Observations
From the first table, and based on the clusters formed, Toronto had 4 neighborhoods not clustered, while San Francisco consistently had 1 not clustered, and New York City had 0 not clustered.

Running the script a few times shows that the 4 neighborhoods that are not clustered, are Roselawn, and Forest Hill West/Forest Hill North consistently, with the other two neighborhoods being varied due to the starting points of the centers given by DB-Scan. On the other hand, San Francisco consistently shows St. Francis Wood as no clustered. This is because St. Francis Wood has a Monument / Landmark, Garden, Gun Range, and a Trail all in one area which is highly uncommon for San Francisco neighborhoods. New York City consistently has no cluster exclusions.

A high-level view based on the clusters would signal a similarity between Toronto and San Francisco. However, after looking into the results it seems all that can be said is that there are many neighborhoods in Toronto that are unique with respect to each other, while San Francisco, they are more or less the same apart from St. Francis Wood.

From the second table, Toronto shows a good balance between places to eat, as in Pizza place/Restaurant/Deli / Bodega/Sandwich Place vs. smaller more intimate venues, Café/Coffee shop/Bakery/Donut shop. On the contrary, both New York City and San Francisco leaned towards one side. New York City had around 7 to 8 out of 10 of its top venues being larger dining venue (Pizza place/Restaurant/Deli / Bodega/Sandwich) and the rest being smaller dining venues, whereas San Francisco had around 4 to 5 out of 10 being smaller dining venues (Café/Coffee shop/Bakery/Donut shop) with 1 being a larger dining venue and the rest being stores.

#### Recommendations 
There needs to be more insight gathered, i.e. costs of business, exact setup location, etc. and choosing just one location might prove difficult in terms of existing local competition. Additionally, if there are any existing partnership in the Toronto area that are willing to assist this transition either directly or through their known contacts located in either of the cities.

## Conclusion
Based on the analysis, the best option would be to split your venture into two sections. To take advantage of minimal competition, one section would focus on creating a smaller dining venue in New York City while the other would create a larger dining venue in San Francisco. Another option would be to choose which area to focus on (larger or smaller dining venue) and branch out to the appropriate city. It comes down to whether the investment is better utilized tackling both areas at once or directed at a single location.
