# Joseph Regan Hutson

Examples of personal projects that I have worked on.

## Data Exploration

**Is the rate of DUI arrests impacted by access to transit?**

Exploratory Data Analysis looking at the rate of DUI arrests along 6 freeway segments in Los Angeles. Completed as part of General Assembly Python Programming Course.

[View a static version of the Jupyter Notebook](https://jrhutson.github.io/dui_rate_vs_transit/)

[View the Github Repository](https://github.com/JRHutson/dui_rate_vs_transit)

***Tools Used:***
1. Python
2. Pandas
3. GeoPandas

## Mapping

**LA Regional Food Bank locator map.**

Part of a volunteer project with the LA Regional Food Bank, this dynamic webmap is designed for end users to easily find food resources in their area. Symbology communicates locations that will be distributing food in the next few days. 

[Open the Map.](http://jrhutson.github.io/Food-Resource-Map/)

[View the Github Repository](https://github.com/JRHutson/Food-Resource-Map)

***Tools Used:***
1. HTML
2. Javascript
3. Leaflet

## General Scripting

**Identifying Gateway IP**

This script was used to support a very large data collection effort. In order for the system being deployed to function it was necessary to know the Gateway IP address of each computer it would be installed on. Once other data was collected through ESRI's Survey 123 app, this script would run daily to pull features that had been uploaded to the server, identify the needed data and update the feature. One of the datasets queried contains over 1 Million rows, leading to the need to use Pandas in the process. 

[View the Github Repository](https://github.com/JRHutson/PopulateGatewayIP)

***Tools Used:***
1. Python
2. Pandas
3. ArcGIS API for Python

**Apartment Hunting with Python**

This script was used to find my current apartment. It searches Craigslist for postings meeting my search criteria for size, rent, etc... I wanted to be near transit, so it then calculates the distance between the post Geotag and the nearest LA Metro Gold Line station. If the distance is less than the maximum distance set, the listing is posted to a Slack channel so that I would get notified on my phone. 

[View the Github Repository](https://github.com/JRHutson/CraigslistHousing)

***Tools Used:***
1. Python
2. GeoJSON
3. Craigslist Library
