---
author: "Hugo Authors"
title: "Generating Contours from Point Clouds in Global Mapper"
date: "2022-08-05"
description: "A quick demonstration of a workflow for contour generation using point cloud data in Global Mapper."
tags:
  - tutorial
  - contours
  - point clouds
  - lidar
  - Global Mapper
ShowToc: true
cover:
    image: "images/gen-contours.png"
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    # alt: "<alt text>"
    # caption: "<text>"
    relative: true # To use relative path for cover image, used in hugo Page-bundles
---

# Introduction

Here is a quick video demonstration of my workflow for contour generation using point cloud (lidar in this case) data in Global Mapper.
The data that I used was the lidar point clouds for City of Cape Town (South Africa), but the same workflow can be used for any point cloud data format. Global Mapper 18.0 was used in the recording of this tutorial.

# Steps taken in the workflow

1. Load the point cloud data into Global Mapper.
2. Create an elevation grid from the point cloud data.
3. Generate Contours from the elevation grid created in step 2.

# Tutorial video

{{< youtube eyeUoo7UU48 >}}

Link to the video: [https://youtu.be/eyeUoo7UU48](https://youtu.be/eyeUoo7UU48)

# Useful links

For more information please have a look at the following links:

- Lidar Load Options: https://www.bluemarblegeo.com/knowledgebase/global-mapper-19/Lidar_Module/Lidar_Load_Options.htm
- Create Elevation Grid: https://www.bluemarblegeo.com/knowledgebase/global-mapper-19/Create_Elevation_Grid_from_3D_Vector_Data.htm
- Create Contours: https://www.bluemarblegeo.com/knowledgebase/global-mapper-19/Generate_Contours.htm