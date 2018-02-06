---
layout: post
title: Improving old work
date: '2017-11-10 00:00:00 +0800'
categories: gis
tags: [qgis, california, vector, atlas]
image: /assets/2017-11-10-Improving_old_work/Cal_PopDensity.jpeg
description: Trying to fix major issues in the earlier maps I made, when I was starting out in GIS.
---
A post where I try to revamp some previous work I made. Based off a QGIS tutorial.

<!--excerpt-->

![My first map of California's Population](/assets/2017-11-10-Improving_old_work/OldCalPop.png "Old Map of California Population")

![My first map of Northern California Population](/assets/2017-11-10-Improving_old_work/OldNorcalPop.jpg "My first map of Northern California Population")

I submitted the maps above in a Lab assignment during my high school GIS course. It was basically the same as the [QGIS tutorial on table joins](http://www.qgistutorials.com/en/docs/performing_table_joins.html), but it was adapted as an assignment. Looking back, the maps were giving off the wrong impression of the data as it was based on raw population numbers instead of the population density. This is particularly important for a [chloropleth](https://en.wikipedia.org/wiki/Choropleth_map) map which will colourfully exaggerate the population number according to the selected classification scheme. In addition, all the typical map elements are missing, not sure what I thinking there.

So I decided to improve the map! Simply put the reality is a lot less impressive:

![Overview of California's Population Density, per Census Tract](/assets/2017-11-10-Improving_old_work/Cal_PopDensity.jpeg "Overview of California's Population Density, per Census Tract")

In terms of styling I used a **inverted shapeburst** fill for the "water". This can really make the coastline stand out if you adjust the colour values correctly.

The resolution in the above image is pretty decent but just for clarity’s sake I did an atlas as well, generated over the individual counties.

![Population Density of Alameda, per Census Tract ](/assets/2017-11-10-Improving_old_work/Alameda_PopDensity.jpg "Population Density of Alameda, per Census Tract")

![Population Density of Ventura, per Census Tract](/assets/2017-11-10-Improving_old_work/Ventura_PopDensity.jpg "Population Density of Ventura, per Census Tract")

![Population Density of San Joaquin, per Census Tract](/assets/2017-11-10-Improving_old_work/SanJoaquin_PopDensity.jpg "Population Density of San Joaquin, per Census Tract")

![Population Density of Los Angeles, per Census Tract](/assets/2017-11-10-Improving_old_work/LA_PopDensity.jpg "Population Density of Los Angeles, per Census Tract")

Clearly the boundaries of the census tracts and the counties don’t align for some reason. [According to the U.S. Census Bureau](http://libguides.lib.msu.edu/tracts) the tracts *“follow people rather than political boundaries”* so the discrepancies between both cannot be resolved easily. However for the purpose of displaying the population density, these boundaries are only used for reference, so it’s not too much of an issue.
