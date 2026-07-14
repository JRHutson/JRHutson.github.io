---
layout: post
title: Portland Pastry 10K Walk
date: 2026-06-06 13:32:20 +0300
description: Webmap project created to support a community 10K walk. # Add post description (optional)
img: PastryMap.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Web-Map, Leaflet, Community, Pro-Bono]
---
***Tools Used:***
1. Q-GIS
2. Mapbox
3. Leaflet
4. GitHub Pages


[View the live map](https://jrhutson.github.io/Portland-pastry-10k/)



I developed this interactive webmap to support a commumity event called the Portland Pastry 10K.\
This grassroots event organized a 10K walk to foster community in Portland Oregon and support local small businesses.\
The map I developed:
* Coordinates with the event branding.
* Allows participants to easily reference their current position and the intended route.
* Provides details on participating businesses in pop-ups.
    * Social Media links for all.
    * Physical addresses for permanent brick and mortar locations.
  
  
  

---
---
## Data Digitization

Route and Vendor data were digitized using Q-GIS.\
This method was ideal for a number of reasons:
* Ease of export of data to Geo-JSON.
* Able to ensure that data projection matches map projection.
* Granular control of data attibute fields.

### Data Manipulation in Q-GIS
![Data Manipulation in Q-GIS]({{site.url}}/assets/img/PastryMapQGIS.jpg)

### Attribute Manipulation in Q-GIS
![Attribute Manipulation in Q-GIS]({{site.url}}/assets/img/PastryMapQGISAttributes.jpg)


---
## Color Choice
The information provided by the organizers told me that Salmon was going to be the primary color for the event's materials.\
I knew that I would need complimentary colors in order to style the map in a way that would be both pleasing and ledgible.\
A free [Color Palette Generator](https://www.colorpalettegenerator.co) allowed me to start with my primary color and assemble a group of other colors that would fit well, while providing highlights or contrast as needed.

### Pastry Map Color Palette
![Pastry Map Color Palette]({{site.url}}/assets/img/PastryMapColorPalette.jpg)

---
## Basemap Styling in Mapbox

Because I wanted all aspects of the map to fit with the event branding, I needed a way to create and host my own custom basemap.\
After reviewing their plans, I confirmed that my expected usage would fall well within the Mapbox Free Tier.\


### Feature Prioritization
I made sure that my styling focused on local streets and paths that would be the most relevant features for participants.\
Salmon made sense as the primary background color, to fit with the event branding.\
Other colors from my palette ensured that streets, paths and labels would complement the salmon background.

### Feature Styling
Styling for prioritized features was configured through Mapbox Studio.
![Styling Features in Mapbox]({{site.url}}/assets/img/PastryMapMapboxFeatures.jpg)

---
## Leaflet Map Development

### Locations of Sheriffs DUI Arrests compared to City of Los Angeles Boundary
![Sheriffs DUI Arrests vs City of LA]({{site.url}}/assets/img/GAFinalProject/SheriffsDataVsCityBoundary.png)

I combined the total DUI arrests within the City of Los Angeles during that 6mo period and calculated the percentage of DUI arrests that were made by LA County Sheriffs. 

How much of an impact would the Sheriff's data have?

  In the 6 Months of available data LA County Sheriffs only made 39 DUI arrests within the city limits of Los Angeles. This makes sense, as they typically patrol unincorporated parts of the county.

  In the same time period, LAPD made 4255 arrests within the city.  

  39/4255 = 0.00916

__Less than 1% of DUI Arrests in the City of LA were from LA County Sheriff's during that 6mo period__

Due to the low percentage I decided to exclude the Sheriff's data and focus on the LAPD data. This allowed me to widen the timeframe I was looking at and base my analysis on a much larger dataset.

---
## Connecting DUI's to Freeway Segments
Freeway segments and associated ramps were selected and buffered in QGIS. Because there was not a common attribute to connect a ramp feature to a particular segment of freeway, this was the easiest path.

### Freeway Segments
![Freeway Segments]({{site.url}}/assets/img/GAFinalProject/FreewaySegments.png)

| Freeway Segment | Rail Alternative? | Line |
| :---: | :---: | :---: |
| 10 | Yes | E Line (Expo) |
| 101 | Yes | B Line (Red) |
| 110 | Yes | L Line (Gold) |
| 405 | No | None |
| 5 | No | None |
| 118 | No | None |

### DUI's Falling Within Buffers
![Freeway DUI's]({{site.url}}/assets/img/GAFinalProject/DUIsInFreewayBuffers.png)

---
## Comparing DUI Incidence
![Raw DUI Incidence]({{site.url}}/assets/img/GAFinalProject/RawDUIRateBySegment.png)

## Initial Conclusions
  1. This is not the pattern expected, the segments with the most DUI's are those with a rail option.
  2. Need to isolate other possible variables.
  3. Segments are not all the same length. Additionally, traffic levels may be different.
  3. Data needs to be normalized to ensure we are making a valid comparison

## Normalizing for Traffic
AADT (Average Annual Daily Total) Traffic Counts from California Department of Transportation were brought into the analysis. The same buffers were used to select all data points that fell within a buffer and take the average.

![AADT Points]({{site.url}}/assets/img/GAFinalProject/AADTPoints.png)

This gives us the average number of cars traveling along that segment of freeway per day.

After converting the DUI data into a rate of DUI's per 1000 cars.

![Normalized Data]({{site.url}}/assets/img/GAFinalProject/NormalizedComparison.png)

With the data normalized, the three freeway segments with rail alternatives all have the highest rate of DUI arrests.

---

## Conclusions

  1. Based on the normalized data, the initial hypothesis must be rejected.
  2. The correlation between high DUI's and Rail, might indicate that similar factors contribute to them.
    * For example, population centers that contribute to DUI's would also be a factor in transit funding.

## Questions for Future Analysis

  * Does a new Metro Line influence the rate of DUI's when it opens?
  * What is the distribution of DUI's in Los Angeles?
  * What are the trends in DUI incidence and distribution over time?