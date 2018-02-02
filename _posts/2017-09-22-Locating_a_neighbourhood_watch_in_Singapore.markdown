---
layout: post
title: Locating a neighbourhood watch in Singapore
date: '2017-09-22 00:00:00 +0800'
categories: qgis singapore vector raster
tags: qgis singapore vector raster
---
Lab Assignment #3 for my high school GIS course.

# Introduction

A client wishes to identify areas and clusters of crimes rates in Singapore using GIS, in order to access the feasibility of initiating a grassroots project on urban neighbourhood watch at some of these areas or clusters.

# Summary of Considerations

Type of crime is to be considered as not every single crime would be relevant to a neighbourhood watch. According to Bennett et al. (2008), the majority of neighbourhood watches worldwide focuses on robberies. However in the case of Singapore,  the Neighbourhood Watch Groups (NWGs) established look at many other types of crimes, including unlicensed money lending (UML) and harassment. Hence, all type of crimes should be analysed.

# Spatial Analysis

![Density of all crime cases reported per NPC, 2013](/img/2017-09-22-Locating_a_neighbourhood_watch_in_Singapore/CrimeDensity.jpeg "Density of all crime cases reported per NPC, 2013")

The first map done, featured above, showcases the density of crime cases for each planning area.

![Heatmap of all reported crime cases, 2013](/img/2017-09-22-Locating_a_neighbourhood_watch_in_Singapore/HeatmapOfCrimeDensity.jpeg "Heatmap of all reported crime cases, 2013")

A weighted heatmap of the crime cases, which does not discriminate well for specific localities within planning areas due to the utilization of the polygon centriods as the centre. However it can still be acceptable to first consider the chloropleth map to identify clusters, and then to use the heatmap to delimit hotspots.

![SPF Establishments, 1km Buffer](/img/2017-09-22-Locating_a_neighbourhood_watch_in_Singapore/SPFEstablishmentsBuffer.jpeg "SPF Establishments, 1km Buffer")

Subsequently the Singapore Police Force (SPF) Neighbourhood Police Centres and Posts were mapped for the hotspots to identify areas that would have sufficient local police support for the NWGs. Buffer zones of 1km were used to visualize the reach of the police centres and posts.

Based on the high crime density in the planning areas Ang Mo Kio South and Bedok North, and the thorough police presence in those areas, those clusters would be good localities to initiate NWGs.
