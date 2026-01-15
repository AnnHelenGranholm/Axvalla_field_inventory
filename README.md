## Axvalla_field_inventory
Location of photos collected during a field inventory at Axvalla hed, in may 2024.

The point of this map is to learn a way to make my field data publicly available. Comparing remote sensing data such as aerial orthophotos or satellite imagery to field photos and field data increases the quality of vegetation mapping by aerial photo interpretation. By using python scripts in a colab notebook I could extract and convert time and location per iphone photo and add them as point markers in a map showing where and when I took the photos. Processing the data was quick and free, an effective method that saves resources. The map is accessible to the public, making it easy to distribute. The availability of the map enables discussion, teaching and further analysis. This test was made with a small subset of my field photos, making it a showcase of a possible method. Further tweeking is needed.

Material
-
- image files in jpg format, collected using an iphone with locations activated


Method
-
* upload and extract zipped image files in colab notebook
* extract exif data from jpg files using pillow
* convert GPS coordinates to decimal lat lon
* create list with ID, lat lon and date taken  
* convert list to pandas dataframe
* convert date taken to datetime objects
* create geometry for points using lat lon
* create geopandas geodataframe with point geometry and crs:4386 (WGS84)
* each point has ImageID, date and time, LAT and LON in WGS84
* reproject to crs:3006 (SWEREF) 
* save to shapefile
* create map with Esri.WorldImagery tiles using folium
* add points in shapefile as markers
* save as index.html
* publish in github repository

Result
- 
- the markers are correctly located in the part of Axvalla hed we visited in may 2024
- the map is available to the public

Discussion
-
Using python to extract and create a shapefile from exif data in my photos is simple and effective. One downside is the size of the images files which slows down the process. I used a small subset of images just to develop and test the method. Now that I have a working script, I can repeat it with all our photos and generate a proper field inventory map. Since I only extract the coordinates and time data I should add a pre-processing step, prior to upload of the jpg files, which downsamples copies of our images without loosing the exif data. just zipping the image file folder isnt enough.

In every marker there is a link to the corresponding image file. The link doesnt work yet since I havnt found a way to publish the images on github, or the like. Would like to have the images pop up in a small window or in a pane e g to the right (or left, below etc) to enable cross-examination of the background alongside with the photo. It would enable a comparison of remote sensing data such as e g a map, satellite data or orthophoto to the photo showing ground cover, shrubs and/or trees and scenery. I could also add auxiliary field data such as biogeographical region, soil data, species, vegetation type code etc. Comparing aerial photos to field photos and field data increases the quality of our aerial photo interpretation.
 

  
