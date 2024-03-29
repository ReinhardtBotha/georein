---
author: "Hugo Authors"
title: "Modify properties of multiple layers with Python"
date: "2022-09-14"
description: "Tutorial on how to modify properties of multiple layers in a map with Python"
tags:
  - tutorial
  - python
  - Arcpy
  - ArcGIS Pro
ShowToc: true
cover:
    image: "images/DefinitionQueryPython.png"
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    # alt: "<alt text>"
    # caption: "<text>"
    relative: true # To use relative path for cover image, used in hugo Page-bundles
---

# Introduction

It is possible to view and/or modify layer properties with Python code using the `arcpy.mp` module in ArcGIS Pro. In this tutorial, I'll show you how to achieve this, which will allow you to automate this process. 

## Notes

- **Different layer types support different layer properties.** For example, a feature layer supports the `definitionQuery` property, but raster layers don't. There are two approaches for determining which properties can be modified.
    1. Use the `is` properties method to establish what type of layer it is, in order to determine which properties can be changed. For example, to check whether it is a feature layer use:
      `isFeatureLayer`.
    2. Use the ``supports`` method, which will attempt to set a specific property and return ``True`` if it was successful. For example, to see whether the layer supports the `definitionQuery` property, run:
      `supports("DEFINITIONQUERY")`.

- **Only the following properties can be modified:**

`brightness, contrast, definitionQuery, maxThreshold, metadata, minThreshold, name, showLabels, symbology, transparency, and visible`

# Python Code Steps

The following steps can be performed in a Python Notebook within an ArcGIS Pro project. In this tutorial, we will modify the Definition Query property of Feature Layers.

## 1. Create a list of layers

To create the list of layers, you first need to reference the ArcGIS Pro project and the map containing the layers. Referencing the ArcGIS Pro project is possible in two ways: 

1. Set the variable of the ArcGIS Pro project from a path with the following code:

`aprx = arcpy.mp.ArcGISProject(r"C:\Projects\MyProject.aprx")`

2. Or use the `CURRENT` keyword, to reference the current open project:

`aprx = arcpy.mp.ArcGISProject("CURRENT")`

For this tutorial, we will be using the `CURRENT` keyword method. 

After referencing the ArcGIS Pro project, a variable, `m`, must be created for the map containing the target layers. In this case, the `activeMap` property will be used. i.e:

`m = aprx.activeMap`

And finally the list can be created using the `listLayers()` method. i.e:

`lyrList = m.listLayers()`

Your complete code block for this step should look like this:

```python
aprx = arcpy.mp.ArcGISProject("CURRENT")
m = aprx.activeMap
lyrList = m.listLayers()
```

## 2. Iterate through the list of layers

Now that we have created a list of the layers, we will iterate through the list, but only for Feature Layers, which support the `definitionQuery` property. 

Write a for loop to achieve this:
```python
for lyr in lyrList:
    if lyr.isFeatureLayer:
```
If you wish to view the layer names in the list, it can be printed out using: `print(lyr.name)`

## 3. Modify properties of layers in the list

Finally, the properties can be modified of the feature layers in the list. In this case, we want to modify the `definitionQuery` property. This can be done using the following code:

```python
lyr.definitionQuery = "MyFieldName = 'MyFieldValue'"
```
Where "MyFieldName" should be replaced by the field name which you want to apply the Definition Query to, and "MyFieldValue" replaced with the value you want to set.

**Here is an example of what your code can look like:**

```python {linenos=true}
aprx = arcpy.mp.ArcGISProject("CURRENT")
m = aprx.activeMap
lyrList = m.listLayers()
for lyr in lyrList:
    if lyr.isFeatureLayer:
        print(lyr.name)
        lyr.definitionQuery = "MyFieldName = 'MyFieldValue'"
```

# Useful links

For more information please have a look at the following links:

- Introduction to arcpy.mp: https://pro.arcgis.com/en/pro-app/latest/arcpy/mapping/introduction-to-arcpy-mp.htm