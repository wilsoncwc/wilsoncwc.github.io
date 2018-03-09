---
layout: post
title: Comparing DEMs of Singapore
date: '2018-03-10 00:00:00 +0800'
categories: gis
tags: [qgis, singapore, raster, qgis2web, leaflet]
image: /assets/2018-03-10-Comparing-DEMs-of-Singapore/ASTER.jpg
description: A comparison of global digital elevation models (DEMs) and their representation of Singapore, using hillshaded raster maps made in QGIS, and Leaflet.
---
Precise Digital Elevation Models (**DEMs**) of Singapore are not so readily available online. In order to obtain one, it is necessary to sieve the island out from open source global DEMs. Hence, I thought that it would be useful to compare between those global DEMs and see which gives the best representation of Singapore. For easy comparison, I also made a **Leaflet** map that overlays the DEMs.

<!--excerpt-->

There are several global DEMs available online, and most of them will require you to sign up for a [**NASA Earthdata**](https://urs.earthdata.nasa.gov/home) account. The DEMs covered here come from ASTER, SRTM and ALOS PALSAR.


## ASTER

[Advanced Spaceborne Thermal Emission and Reflection Radiometer (**ASTER**)](https://asterweb.jpl.nasa.gov/) is an Earth-observing satellite sensor that resulted from a joint effort between the United States National Aeronautics and Space Administration (NASA), Japan’s Ministry of Economy, Trade and Industry (METI), and Japan Space Systems (J-spacesystems). ASTER is onboard Terra, a NASA satellite launched in 1999, and it generates the Global Digital Elevation Model (GDEM) using stereo-pair images.

ASTER GDEM data are posted on a 1 Arc-Second (approximately 30 metres at the equator) grid and referenced to the 1984 World Geodetic System (WGS84)/ 1996 Earth Gravitational Model (EGM96) geoid, and comes in GeoTIFF (`.tif`) format. ASTER data can be found [from several sources](https://asterweb.jpl.nasa.gov/data.asp), but I find the [**Earth Explorer**](https://earthexplorer.usgs.gov/) site to be the most intuitive option. The vast majority of Singapore is covered in the N01-E103 tile, while parts of Eastern Singapore, Pulau Ubin and Pulau Tekong can be found in the N01-E104 tile.

[![ASTER DEM](/assets/2018-03-10-Comparing-DEMs-of-Singapore/ASTER.jpg "ASTER DEM")](/assets/2018-03-10-Comparing-DEMs-of-Singapore/ASTER.png)

The ASTER GDEM of Singapore is very complete, perhaps too much so. It includes complete elevation data for water bodies, which appears somewhat confusing as the layer styles them as land. Also, there is _unusually high_ elevation represented in the Mandai area, which is perplexing as it is shown to reach similar elevation as that of Bukit Timah Hill. However, since the coverage by ASTER is the most updated out of all the three, it has the most comprehensive extent of the ongoing land reclamation in the Tuas and Jurong Island areas.


## SRTM

NASA's [Shuttle Radar Topography Mission (**SRTM**)](https://www2.jpl.nasa.gov/srtm/) from 2000 generated one of the most popular high quality DEMs, which is freely available from many online sources. The older releases prior to 2015 only featured a 90 metres sampling for regions outside the United States. Public data sampling is however now available with a 1 Arc-Second, or 30 metres, resolution, so be careful not to download the wrong version. Singapore is represented in two sections again, under the N001E104 and N001E103 tiles.

[![SRTM DEM](/assets/2018-03-10-Comparing-DEMs-of-Singapore/SRTM.jpg "SRTM DEM")](/assets/2018-03-10-Comparing-DEMs-of-Singapore/SRTM.png)

Notably, most of Pulau Tekong is absent from the SRTM data, together with a large portion of the reclaimed land in Tuas, Changi and Jurong Island that developed after 2000. As such the SRTM data from 2000 does have a significantly less comprehensive coverage of the Singapore mainland. It also lacks detail compared to the other DEMs, most noticeably in Pulau Ubin, and portrays a generally lower lying Singapore. It discriminates water bodies and does not include their elevation data.

I used Earth Explorer again to download the SRTM data in the map, but there are many other avenues. One particularly intuitive one is [this Grid-based site](http://dwtkns.com/srtm30m/) by Derek Watkins. The direct downloadable data from the SRTM FTP site comes in `.hgt` format, although `.tif` is available from Earth Explorer. The SRTM DEM is also referenced to the WGS 84 / EGM96 geoid.


## ALOS PALSAR

[Advanced Land Observing Satellite (**ALOS**)](http://www.eorc.jaxa.jp/ALOS/en/index.htm), also known as DAICHI, was a satellite mission of the Japan Aerospace Exploration Agency (JAXA) which ran from 2006 to 2011. The Phased Array type L-band Synthetic Aperture Radar (**PALSAR**) was one of three instruments on the satellite, used for all day and all weather terrain observation.

The DEM from ALOS PALSAR covers Singapore in two separate overlapping tiles, which however don't all come from the same year. The western tile comes from 2011, and the eastern tile is from 2009. They will overlap to a certain extent, meaning that their layers cannot be simply blended together. ALOS PALSAR references each grid to its appropriate Universal Transverse Mercator zone using the WGS84 ellipsoid, so Singapore falls under WGS84 / UTM zone 48N. It comes in GeoTIFF format.

[![ALOS PALSAR DEM](/assets/2018-03-10-Comparing-DEMs-of-Singapore/ALOSPALSAR.jpg "ALOS PALSAR DEM")](/assets/2018-03-10-Comparing-DEMs-of-Singapore/ALOSPALSAR.png)

ALOS PALSAR's DEM features a much more extensive coverage of the land reclamation, but not to the same extent as the ASTER GDEM. It, however, arguably generates a more accurate portrayal of the elevation around the Central Water Catchment. The most critical point though, is that it portrays a relatively flat Singapore, which comes from _uniformity_ in its gradient. The data also distinguishes water bodies and does not reflect their elevation.

ALOS PALSAR data can be downloaded from [Alaska Satellite Facility's data portal, Vertex](https://vertex.daac.asf.alaska.edu/), which requires an Earthdata account. The data selected should be the **Radiometric Terrain Corrected** dataset.

---

## Leaflet

In order to easily compare the DEMs as overlays, I used the plugin [qgis2web](https://plugins.qgis.org/plugins/qgis2web/) to make the following Leaflet map, which allows for simple switching between the three DEMs with their appropriate georeferencing. For reference, I also included the locations of **triangulation stations**, which give the exact elevation at that points.


<iframe src="https://wilsoncwc.github.io/singapore-dem" frameborder="0" allowfullscreen style="height: 500px; width: 100%;"> </iframe>


The extent of the DEMs can be easily compared, and the ASTER DEM evidently has the most comprehensive coverage. All of the three GDEM layers were given the same styling, so the differences in representation can be fairly observed. The more notable points include the apparent high elevation in Mandai for the ASTER GDEM, and the relatively lower-lying elevation overall for the SRTM DEM, and the uniformity of the ALOS PALSAR DEM.

---

## Conclusion

With Singapore and its ever-changing terrain due to land reclamation, it is important to use the most recent datasets available in order to accurately represent the landmass. The continuously updated **ASTER** GDEM currently provides the most up-to-date DEM of Singapore, altogether it may require a few adjustments in order to distinguish water bodies from land. However, if a more accurate portrayal is desired, I would go with the **ALOS PALSAR** DEM.
