# IBM_Python_Coursera_Capstone

## Introduction
#### Problem - Background 
The following proposal was presented by a small food conglomerate - "We are based out of Toronto and would like to branch out to either the east or west coast of the United States. The two cities that interest us are San Francisco on the west coast and New York on the east coast. Out of these two cities, which one is a more ideal location for our business?" 

#### Audience
This conglomerate would like to utilize its resources effectively and does not have the means to establish a large number of franchises in either location. Therefore, they were willing to strategize in order to maximize their impact. Similar ventures, especially those in the service industry can use this or a similar model to make decisions on where to expand while optimizing their investment. 

## Data
#### Description
To solve this problem, the venue categories for each location in the neighborhoods of each of the cities would be required. For this data, the websites containing the neighborhoods and their respective postal codes are listed below along with a file containing the required geospatial-coordinates.

#### Source
Link to the neighborhood and postal code information for each city:<br>
Toronto - https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M\<br>
New York City - https://www.health.ny.gov/statistics/cancer/registry/appendix/neighborhoods.htm\<br>
San  Francisco - http://www.healthysf.org/bdi/outcomes/zipmap.htm

Link to the latitude and longitude of every zip code in the united states:<br>
https://gist.github.com/erichurst/7882666<br>
(The geospatial-coordinates for Toronto are taken from the file provided in the previous project named 'Geospatial_Coordinates')

This information will be used to gather venue information through functions using the Foursquare API. The venue category will then be used to cluster neighborhoods and compare the top venue categories for all the neighborhoods of that city, while the DB-Scan algorithm will automatically cluster the neighborhoods for each city.
