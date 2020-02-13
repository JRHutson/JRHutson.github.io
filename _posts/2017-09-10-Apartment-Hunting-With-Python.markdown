---
layout: post
title: Apartment Hunting With Python
date: 2017-09-10 00:00:00 +0300
description: Python automation script used to facilitate an apartment search. # Add post description (optional)
img: topdownstreets.jpg # Add image post (optional)
tags: [Python, Automation] # add tag
---
***Tools Used:***
1. Python
2. GeoJSON
3. Craigslist Library


[View the Github Repository](https://github.com/JRHutson/CraigslistHousing)


This script was used to find my current apartment. It searches Craigslist for postings meeting my search criteria for size, rent, etc... My other criteria was being near transit, so it calculates the distance between the post Geotag and the nearest LA Metro L Line (Gold) station. If the distance is less than the maximum distance set, the listing is posted to a Slack channel to provide notification. 