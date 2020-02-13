---
layout: post
title: Does Access To Transit Impact DUI's In Los Angeles
date: 2017-09-12 13:32:20 +0300
description: Final Project completed for General Assembly Python course in fall of 2019. Exploratory Data Analysis attempts to identify any correlation between the availability of Mass Transit Alternatives and the rate of DUI arrests along 6 freeway segments in Los Angeles. # Add post description (optional)
img: metrotrain.jpg # Add image post (optional)
fig-caption: Photo by Daryan Shamkhali on Unsplash # Add figcaption (optional)
tags: [Exploratory Data Analysis, Python, Pandas, GeoPandas]
---
***Tools Used:***
1. Python
2. Pandas
3. GeoPandas


[View a static version of the Jupyter Notebook](https://jrhutson.github.io/dui_rate_vs_transit/)

[View the Github Repository](https://github.com/JRHutson/dui_rate_vs_transit)


Final Project completed for General Assembly Python course in fall of 2019. Exploratory Data Analysis attempts to identify any correlation between the availability of Mass Transit Alternatives and the rate of DUI arrests along 6 freeway segments in Los Angeles.

The Jupyter Notebook (linked above and in the Github Repo) follows my process to clean the data, isolate relevant data points and identify additional datasets that I needed and test my hypothesis that the rate of DUI's would be lower on freeways that parallel a Metro Rail line.

Initial analysis looked at characteristics of the dataset, such as the time distribution and differences seen when DUI Arrests were isolated from the wider dataset.

### Time Distribution through the day of LA County Sheriffs Arrests
![General Arrest Distribution]({{site.baseurl}}/assets/img/GAFinalProject/SheriffsArrestsTimeDistribution.png)

### Time Distribution through the day of LA County Sheriffs DUI Arrests
![DUI Arrest Distribution]({{site.baseurl}}/assets/img/GAFinalProject/SheriffsDUIArrestsTimeDistribution.png)

While the City of Los Angeles could conceivably be patroled by three Law Enforcement agencies, I was only able to aquire clean arrest data from two of those. The California Highway Patrol data available through the CA State data portal is mixed with reports from other agencies. At the time of this analysis, LA County was only publishing 6 months worth of data whereas City of Los Angeles publishes almost 10 years worth of arrest data. In order to decide whether to limit my scope to the six months of overlap, I looked at how many of the LA County Sheriffs DUI arrests were within the City of Los Angeles. 

### Locations of Sheriffs DUI Arrests compared to City of Los Angeles Boundary
![Sheriffs DUI Arrests vs City of LA]({{site.baseurl}}/assets/img/GAFinalProject/SheriffsDataVsCityBoundary.png)

I combined the total DUI arrests within the City of Los Angeles during that 6mo period and calculated the percentage of DUI arrests that were made by LA County Sheriffs. The percentage was less that 1%, so I decided to focus on the LAPD data and widen the timeframe that I was looking at.

Freeway segments and associated ramps were selected and buffered in QGIS. Because there was not a common attribute to connect a ramp feature to a particular segment of freeway, this was the easiest path.

### Buffered Freeway Segments
![Buffered Freeways]({{site.baseurl}}/assets/img/GAFinalProject/BufferedFreeways.png)



