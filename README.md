# Campaign Data Dashboard
## Background
From March to November 2020, I was part of a team of Bluebonnet Data Fellows working on Donna Imam's campaign for the congressional seat in Texas's 31st District. I initially created this Dash page as a way to examine correlations between a mix of demographic variables and election results broken down by precinct, combining chloropleth maps with scatter and bar plots so as not to lose a geographic context that can often be important in these settings. Over time, I ended up adapting it for a variety of purposes, including turfcutting and live canvass progress + early vote tracking.           
<img src="https://github.com/Dahlia-Dry/Campaign-Data-Dashboard/blob/master/example%20usage/main.png" width="80%" height="8I 0%">          
I found the interactivity of Plotly/Dash to be very useful in exploring and communicating relationships between demographic and electoral trends in our district; this Dashboard makes liberal use of callbacks such that many permutations of plots that would be tedious to make individually are made available within a few clicks, and more detailed statistics are often just a mouse hover away.            
<img src="https://github.com/Dahlia-Dry/Campaign-Data-Dashboard/blob/master/example%20usage/targeting.png" width="80%" height="80%">         
This functionality also proved useful for understanding how to prioritize paid voter outreach, as we could really explore a large amount of different factors in ranking precincts from highest to lowest priority and instantaneously see how different selections altered our tentative ordering.             
<img src="https://github.com/Dahlia-Dry/Campaign-Data-Dashboard/blob/master/example%20usage/turfcutting.png" width="80%" height="80%">           

## Usage
I tried my best to make the version of the Dashboard on here as adaptable as possible without also redoing everything from the ground up. I've included some publicly available election results data in the "data" folder so that a functional app can be run by cloning this repo. To go about adapting this project to a different district/campaign, there are two necessary components to change, detailed below.
### 1. Using Different Maps
In the "geometry" folder, I have json and geojson data for the precincts and zipcodes in TX31. Replace these or add another district's geodata; the code uses both the json and geojson formats so both forms are needed. There's a function in utilities.py that can facilitate conversion between the two using pandas as an intermediary.
### 2. Adding Data to the Dashboard
The dashboard uses csv files in the "catalogs" folder to map data files to variables in Plotly. See catalogs/format-explainer.md to understand proper formatting. Mapping single columns is straightforward; more complex preprocessing can be done by modifying the aggregate() function in utilities.py. The most important thing is making sure there's an exact mapping between labels in your geodata and labels in your other datasets.       

Questions/Comments/Concerns: dahlia23@mit.edu
