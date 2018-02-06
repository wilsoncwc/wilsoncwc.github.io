---
layout: post
title: Residential areas with high proximity to facilities
date: '2017-09-23 00:00:00 +0800'
categories: gis
tags: [qgis, singapore, vector, atlas]
image: /assets/2017-09-23-Residential_areas_with_high_proximity_to_Facilities/Overview.jpeg
description: Finding the best areas to live in Singapore, based on proximity to amenities.
---
This is an expansion of an earlier project of mine during my internship. The objective of the project was to create a simple introduction to GIS for elementary school children around the age of 12.

<!--excerpt-->

I then decided to create buffer zones of amenities, bearing in mind that people would be interested in living close to such facilities. On hindsight, children aren't likely to be bothered with knowing the best residential locations, so this is not really well suited for the objective. But hey, the idea was still approved by my supervisor.

## Overview

The main challenge for these maps was to find the point data for the amenities. The easiest way for find data related to Singapore is [data.gov.sg](https://data.gov.sg/), an excellent repository for open source data of all kinds. However if you can't find what you want there, you might have to resort to manually inputting coordinates of your desired points.

I found that too troublesome to go through, and so I just used available point data for sports facilities, community centres, hawker centres and MRT stations.

![Overview](/assets/2017-09-23-Residential_areas_with_high_proximity_to_Facilities/Overview.jpeg "Overview")

I first made buffers of 1km around the point data, and used the QGIS intersection tool to find the intersect of all four layers. This creates "zones of 1km proximity" to all the facilities, which is shown in the map above

You can then use atlas generation in the print composer to zoom in onto the specific planning areas that contain the high proximity zones.

![Lorong Chuan Planning Zone](/assets/2017-09-23-Residential_areas_with_high_proximity_to_Facilities/Atlas_LorongChuan.jpg "Lorong Chuan Planning Zone")

![Dover Planning Zone](/assets/2017-09-23-Residential_areas_with_high_proximity_to_Facilities/Atlas_Dover.jpg "Dover Planning Zone")

![Buona Vista Planning Zone](/assets/2017-09-23-Residential_areas_with_high_proximity_to_Facilities/Atlas_BuonaVista.jpg "Buona Vista Planning Zone")

The idea behind this is that it should be flexible to choose which kind of amenities you would like to be close to and then intersect the relevant layers. These four amenities can be replaced with any other kinds of facilities, as long as you have the data.
