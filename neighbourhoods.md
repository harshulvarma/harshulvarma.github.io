## Finding Similiar Neighbourhoods in Toronto

*Jupyter Notebook Link:* <https://nbviewer.jupyter.org/github/harshulvarma/recommending_neighbourhoods/blob/main/Finding_Similar_Neighborhoods.ipynb>

*GitHub Repository Link:* <https://github.com/harshulvarma/recommending_neighbourhoods>

### Overview

In this project I want to make a tool for home movers to find similiar neighbourhoods in Toronto. In order to do so following tasks were done:
- Scraped and cleaned Toronto postal code, neighbourhoods, and borough data from wikipedia.
- Added Toronto population data through open data portal from census
- Retrieved popular venues using Foursquare API using geo coordinates of each postal area and grouped key venue categories
- Clustered Toronto neighbourhoods based on above features
- Computed Euclidean distance and cosine similiarities to recommend neighbourhoods

<img src="images/neighbourhoods.jpg?raw=true"/>

Future changes include addition of census data such as demographics, economics etc. to find even more similiarities within neighbourhoods. To find similiar neighbourhoods I will also explore recommender systems such as collaborative filtering. Lastly the notebook will be deployed as an interactive tool for user to be recommeneded neighbourhoods.

### Tools Utilised:
- pandas
- beautifulsoup
- folium
- Foursquare API
- geopy
- scikit-learn
