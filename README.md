# learning-remote-sensing

## About
This is a repo containing all of the code I wrote when attempting to learn about remote sensing in Python. This read-me also contains the general notes that I took throughout my process; however, the more specific technical details are simply implemented in the code. I do not own any of the following materials, and have linked back to all the sources at the bottom of the document.

## Table of Contents
  1. [Remote Sensing Basics](https://github.com/kamalnarra/learning-remote-sensing/edit/main/README.md#remote-sensing-basics)
  2. [Vector Data](https://github.com/kamalnarra/learning-remote-sensing/edit/main/README.md#vector-data)
  3. [Coordinate Reference Systems](https://github.com/kamalnarra/learning-remote-sensing#coordinate-reference-systems)

## Remote Sensing Basics

  ### What Is Remote Sensing?
  - Remote Sensing: Data collection that doesn't require direct contact with the subject being measured.
  - Satellite images are an example of remote sensing, as they sense the emission and reflection of energy off the surface of Earth without coming into contact with it.

  ### The Electromagnetic Spectrum
  - The Electromagnetic Spectrum: The range of all forms of light that exist.
  - Atmospheric Window: The wavelengths of the electromagnetic spectrum that can make it through the Earth's atmosphere. Includes optical, infrared, and radio.

    ![Electromagnetic Spectrum](https://blog.descarteslabs.com/hs-fs/hubfs/Visible_Spectrum_web.jpg?width=690&name=Visible_Spectrum_web.jpg)

  ### Atmospheric Correction
  - The atmosphere alters the amount of radiation that hits the Earth and gets back to the satellite.
  - Surface Reflectance: The amount of light reflected by the surface of the earth. The optimal standard for remote sensing data. 
  - Data needs to be corrected to understand what is happening on the earth. Organizations like NASA have algorithms to do this.

  ### Spectral Signals
  - TO DO

  ### Radiation-Target Interactions
  - TO DO

  ### Passive vs Active Remote Sensing
  - Passive Remote Sensing: Measures the amount of electromagnetic energy naturally reflected off the Earth.
  - Active Remote Sensing: Transmits energy that bounces off the Earth and returns to the satellite. Get past cloud cover.

    ![Types of Sensing](https://blog.descarteslabs.com/hs-fs/hubfs/Passive%20vs%20Active%20Remote%20Sensing.png?width=1030&name=Passive%20vs%20Active%20Remote%20Sensing.png)

  ### Resolution Types
  - Spectral Resolution: Sensitivity of the sensor to the range of the electromagnetic spectrum.
  - Spatial Resolution: How much land a pixel is equavalent to in the image. Measured in meters per pixel.
  - Temporal Resolution: Frequency of image updates of a given area.

## Vector Data

  ### Intro to Vector Data
  - Vector Data: Data that displays geometric values that demarcate the shape of a space. There are three types of vector data: points, lines, polygons.
  - Vertices: An individual (x,y) value, and a component of all forms of vector data.
    
    ![Types of Vector Data](https://www.earthdatascience.org/images/earth-analytics/spatial-data/points-lines-polygons-vector-data-types.png) 

  ### Shapefiles
  - Shapefiles: The file format that vector data is stored in. Each shapefile can only contain one type of vector.
  - Attributes: Objects in a shapefile have specific properties that describe the data (i.e: name, speed limit, open/closed).
  
    ![Attribute Examples](https://www.earthdatascience.org/images/earth-analytics/spatial-data/spatial-attribute-tables.png)
    
  - There are three important types of shapefiles: 
    - .shp: Contains the geometry.
    - .shx: Indexes the geometry.
    - .dbf: Stores attributes in a table.
    - There can be other types of files as well, but they are not necessary.

## Coordinate Reference Systems

  ### Intro to CRS
  - In two dimensions we use (x,y) coordinates to represent points in space. The coordinate reference system maps 3D data to a 2D plane.
 
    ![CRS Overview](https://www.earthdatascience.org/images/earth-analytics/spatial-data/what-is-a-crs.png)
    
  ### Components of a CRS
  - If data is in different CRS they won't line up.
  - Horizontal and Vertical Units: The units used to define the grid alongs its axes.
  - Datum: Describes which model is used to represent the Earth and where it is positioned.
  - Projection Information: The equation used to convert 3D to 2D
  
  ### Importance of CRS
  - Coordinate System: The (x,y) grid that the data is overlayed on.
  - Horizontal and Vertical Units: The units used to define the grid alongs its axes.
  - Datum: Describes which model is used to represent the Earth and where it is positioned.
  - Projection Information: The equation used to convert 3D to 2D. HOw you take the 3D datum and make it a 2D map.
  
  ### Geographic vs Projected CRS
  - Geographic CRS: Use longitude, latitude, and sometimes height to describe any location on the Earth. Latitude is always consistent; however, longitude is not uniform, and     ends up translating poorly. The further you get from the equator the less accurate longitude gets. Good for globalized data.
  - Projected CRS: Maintains constant lengths and angles across both longitude and latitude. Usually localized. Good for regional data, and distance-sensitive data.
 
  ### Types of Projections
  - You can wrap the globe in different shapes and view the map in reference to how it would appear from the surface of the shapes.
  
    ![Types of Projections](https://docs.qgis.org/3.16/en/_images/projection_families.png)
  
  ### Universal Transverse Mercator
  - Very common projected CRS.
  - Divides the globe into 60 zones and uses a Mercator projection on each individual zone.
  - The origin is at the bottom-left, similar to Q1 in a 2D graph.


  ### On the Fly Projection
  - Sometimes different layers of data are projected differently, so they won't map correctly.
  - On the fly systems let you define a certain starting projection, and all future projections will be autopatically converted to that one.

## Sources
  - [Educational Series: A Look into the Fundamentals of Remote Sensing](https://blog.descarteslabs.com/a-look-into-the-fundamentals-of-remote-sensing)
  - [Intermediate Earth Data Science Textbook](https://www.earthdatascience.org/courses/use-data-open-source-python/)
  - [Coordinate Reference Systems](https://docs.qgis.org/3.16/en/docs/gentle_gis_introduction/coordinate_reference_systems.html)
  - 
