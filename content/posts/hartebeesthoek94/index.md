---
author: "Hugo Authors"
title: "South African Hartebeesthoek94 Coordinate System Web Map"
date: "2022-09-13"
description: "A web map application to help visualise the South African Hartebeesthoek94 Coordinate System"
tags:
  - web map
  - ArcGIS Online
  - coordinate systems
  - Hartebeesthoek94
ShowToc: true
cover:
    image: "images/SA_Hartebeesthoek94_webmap.jpg"
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    # alt: "<alt text>"
    # caption: "<text>"
    relative: true # To use relative path for cover image, used in hugo Page-bundles
---

# Background

In South Africa, the official coordinate system used (since 1999) is the Hartebeesthoek94 Datum. It refrences the WGS84 ellispoid with the International Terrestrial Reference Frame 1991 (ITRF91) coordinates of the Hartebeesthoek Radio Astronomy Observatory Telescope used as the origin of the system. The Gauss Conform Projection (modification of the Mercator projection) is used for the computation of the plane YLo and XLo co-ordinates, commonly known as the "Lo. co-ordinate system". This projection only projects one degree of longitude on either side of the central maridian, which means the projection is in segments of 2 degrees of longitude wide, often referred to as the "Lo bands". These zones or Lo bands are therefore named according to their respective longitude of origin i.e. Lo 19°, Lo 21°, Lo 23° etc.

# Web Map

Since it can sometimes be a bit of a struggle to find the correct Lo band to use for your project, I have decided to create a handy web map app indicating the position of these Lo Bands. 

I used QGIS and ArcGIS Online to create and host these feature layers. It is hosted on my ArcGIS Online Public Account, so I used one of their handy Instant App templates to display and interact with the web map. One useful feature is the search function, which lets you conveniently locate your site area and then visualise where the Lo Band boundaries are in relation to it. The basemap can also be switched between Topographic and Satelite Imagery (with labels). 

Now you never have to guess anymore!

<iframe src="https://www.arcgis.com/apps/instant/basic/index.html?appid=2aea5d52876040bcbbbc67e4ccc8b663" width="800" height="450" frameborder="0" style="border:0" allowfullscreen>iFrames are not supported on this page.</iframe>

Link to the web map app: [https://arcg.is/0PeOf4](https://arcg.is/0PeOf4)

# Useful links

For more information please have a look at the following links:

- Datums and Coordinate Systems of South Africa: https://ngi.dalrrd.gov.za/index.php/technical-information/geodesy-and-gps/datum-s-and-coordinate-systems