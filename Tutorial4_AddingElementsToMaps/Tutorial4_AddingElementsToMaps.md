# Tutorial #4: Adding Elements To Maps

Observing Earth from Above (Env 329) - Fall 2023

Schmid College of Science and Technology

Chapman University

---

## Objectives : 

1. Learn the map making features in QGIS.
2. Introduce basic map elements.
2. Create a NASA worthy map of surface temperatures from Death Valley National Park.

---

## Motivation For Today's Tutorial : NASA Press Releases

<p align="center">
	<img src="ecostress_banner.jpg" alt="ECOSTRESS Banner" width = 800>
</p>

The idea of this course is to change the way we approach climate disaster analyses and immerse you in the process of science communication. Today we are going to create a publish worthy map of the Death Valley National Park surface temperature experiment we ran in last class. Today's tutorial will provide you with the basic working knowledge to create beautiful and informative maps. Later in the course you will use these skills to analyze current climate disasters and publish your maps through NASA's Jet Propulsion Lab.

---

## Create A Base Map

<p align="center">
	<img src="BaseMap.png" alt="Add Basemap" width = 800>
</p>

1. Create a new project (*Project* &rarr; *New*)
2. Add the ESRI National Geographic Basemap by either:
	* Using the *XYZ Tiles* function in the *Browser* window
	* Using the *HCMGIS* Menu (*HCMGIS* &rarr; *Basemaps* &rarr; *ESRI National Geographic*)
3. Zoom in to California.
4. Start a new print layout by going to the *Project* menu, then select *New Print Layout*. Enter whatever name you would like. I went with *Death Valley Inset*.
5. Now select the menu *Add Item*, then *Add Map*. Start at one corner of the white rectangle window and drag to the opposite diagonal corner to set the map space. You will see that the rectangle window will be rendered with the map from the main QGIS canvas.

<p align="center">
	<img src="InsetItem.png" alt="Item Properties" width = 800>
</p>

6. Click on the *Item Properties* tab.
7. Adjust the *Scale*, which is the zoom level, to 7000000 and hit enter.
8. Check both *Lock layers* and *Lock layer styles* boxes. This will ensure that if we turn off some layers or change their styles, this view will not change.

---

## Add An Inset

9. Let's add our map from the last tutorial as an inset to this map. First, return back to the main QGIS window. Add a second basemap layer following the same instructions as above, but this time use *Google Satellite*.
10. Uncheck the box next to the ESRI National Geographic layer in the *Layer* window, and QGIS will keep the layer in the project but not display any of its information.

### Importing Our ECOSTRESS Death Valley Layer From The Previous Tutorial

11. Use the *browser* window to find the folder that you saved the two land surface temperature tif files in from the last tutorial. Double click each file to add them to your map.
12. Adjust the symbology for each of the land surface temperature layer by right clicking on the layer name in the *Layers* window and select *Layer Properties*. On the menu bar to the left select *Symbology* and change the *Render type* to Singleband pseudocolor. Use the red color ramp and remember to match the minimum and maximum values from the surface temperature, 306.82 as the minimum and 347 as the maximum for both layers. Click apply.

<p align="center">
	<img src="DVlines.png" alt="Border Lines" width = 400>
</p>

13. Add in the border from the DeathValleyNationalPark.zip shapefile. In the *Browser* window expand the zip file using the small arrow next to the filename. Double click on *Death Valley National Park.shp* to add the layer. Right click on the layer in the *Layers* window and change it's symbology to *outline blue*. The lines are a little thin, let's make them thicker. First, click on the *Simple Line* selection in the dialog box.
14. Change the *Stroke width* to 3 mm. Click the *Apply* button at the bottom of the window.
15. Zoom in so that the outline of Death Valley National Park fits nicely in the window, it should look like this:

<p align="center">
	<img src="DV_LST.png" alt="Death Valley LST Redo" width = 800>
</p>

### Adding in our Land Surface Temperature Map as an Inset

16. Now that we have the map how we like it the main window, switch back to the Print Layout window. Select the menu *Add Item*, then *Add Map*. Click and create an inset of the land surface temperature to the East of California.

<p align="center">
	<img src="AddInset.png" alt="Add Inset" width = 800>
</p>

17. Under the *Item Properties* for the inset map (typically numbered *Map 2* in the *Items* window), change the scale to 1300000.

<p align="center">
	<img src="RegionShade.png" alt="Add Inset" width = 800>
</p>

18. QGIS has an excellent tool for automatically highlighting the area on the main map that is represented in an inset. First, select *Map 1* (or whatever your main map number is) in the *Items* window. 
19. Next under *Item Properties* scroll down to find the *Overviews* menu. Click the green plus sign to an overview.
20. Under map frame select *Map 2* (or whatever you have named your inset map). The area from the inset should now be highlighted on the main map. Adjust the highlight color to match your mood.

<p align="center">
	<img src="TempLegend1.png" alt="Add Temperature Legend" width = 800>
</p>

---

## Basic Map Elements

### Adding a Legend

21. Select *Map 2* from the *Items* window.
22. From the *Add Item* menu bar, select *Legend*. Draw the legend as a box in the top left corner of the inset map. We can adjust its size later, so don't worry too much about how it looks right now.
23. Under *Item Properties* enter "ECOSTRESS_Degrees (F)".
24. For *Wrap text on* enter an underscore "_".
25. Deselect the check box next to *Auto update*.
26. Remove all legend entries except one of our ECOSTRESS surface temperature layers, by selecting the ones you want to remove and using the minus button. 

**NOTE: We matched the temperature ranges for both of the layers, so that is why we only need one legend.**

The SI unit of temperature set for the International System of Units is Kelvin (K), which is how the land surface temperature observations made by ECOSTRESS are reported. You can use the formulas below to convert K into degrees Celsius or Fahrenheit, which are often more intuitive to your target audiences. 
	* C = K - 273.15
	* F = (K − 273.15) × 9/5 + 32

<p align="center">
	<img src="TempScale1.png" alt="Legend Scale" width = 800>
</p>

27. To change the scale of the legend bar, double click on the scale in the *Legend Items* property window.

<p align="center">
	<img src="TempScale2.png" alt="Adjust Temperature Scale" width = 500>
</p>

28. Converting our temperature scale to degrees Fahrenheit yields a range of 92.6 to 164.9, enter that in the place of the default minimum and maximum values. Let's also adjust the width to 12 mm and the height to 60 mm. Use the back arrow to go back to *Item Properties*.

<p align="center">
	<img src="TempLegend2.png" alt="Adjust Temperature Legend Background" width = 1000>
</p>

29. Let's make the legend look a little more professional by adjusting the background color. Scroll down and look for the *Background* section of the *Item Properties*. Use the arrow to expand your options. Here you can change the color, but for now let's leave it white but change the *Opacity* to 44%. This makes the legend back more transparent, giving it a cleaner look. It should resemble the screenshot above. Return back to the list of item properties.

### Adding Gridlines

<p align="center">
	<img src="AddGrid.png" alt="Add Gridlines" width = 800>
</p>

30. Let's add gridlines to our inset map so readers can tell where the GPS coordinates of our analyses are at a quick glance. Select the inset map in the *Items* browser, it is likely named "Map 2".
31. Select the *Item Properties* tab and scroll down until you reach the *Grids* subsection. Click the plus sign to add a set of gridlines.

By default, the grid lines use the same units and projections as the currently selected map projections. However, it is more common and useful to display grid lines in degrees. 

32. We can select a different CRS for the grid and customize the aesthetics by clicking the *Modify Grid* button.

<p align="center">
	<img src="GridProps1.png" alt="Gridlines Style" width = 500> 
</p>

33. Make the following modifications (see above and below screenshots for reference):

* Keep the *Grid Type* as *Solid*. 
* Change the *CRS* to *EPSG:4326 - WGS 84* to display GPS coordinates as decimal degrees. 
* Change the *X* & *Y Interval*s to 0.5.
* Change *Frame style* to *Zebra*.
* Check the box for *Draw Coordinates*.
* Disable the *Right* Coordinates.
* Change *Coordinate precision* to 1.

<p align="center">
	<img src="GridProps2.png" alt="GPS Coordinates" width = 400>
</p>

Your map should now resemble:

<p align="center">
	<img src="DVwGrids.png" alt="GPS Coordinates" width = 800>
</p>

**NOTE: This same procedure could have been done for the main map instead of the inlet map, if that suits your vision.**

Let's add a couple more small details to bring this map to the next level.

### Adding a Scalebar

Will we now have coordinates for the inset map, it can be critical for the reader to know the scale of the maps they are looking at. This is achieved with a scalebar, which QGIS can automatically render for you.

<p align="center">
	<img src="Scalebar.png" alt="Add Scalebar" width = 800>
</p>

34. With the main map (likely "Map 1") highlighted in the *Items* browser,  click the *Add Item* menu at the top of the screen and select *Add Scalebar*.
35. Draw the scalebar on the main map in a logical place. I like the bottom left corner, which thus far has remained underutilized. 
36. Under *Item Properties* verify that the main map is the map associated with the scalebar. Here you could also adjust the style or units to your liking, but I am just going to stick with the defaults.


### Adding a North Arrow

It is customary to indicate which direction is North on a map with a symbol of an arrow pointed North. This is a simple add in QGIS. 

<p align="center">
	<img src="NorthArrow1.png" alt="Adding North Arrow" width = 800>
</p>

37. Click the *Add Item* menu at the top of the screen and select *Add North Arrow*.
38. Select your preferred North arrow symbol, I am going with a traditional looking compass style with the cardinal directions labeled. Draw the North arrow in an appropriate place, I selected a centered location above the scalebar. 

**NOTE: *SVG Images* tend to look cleaner and sharper compared to the *Raster Image* options.**

<p align="center">
	<img src="NorthArrow2.png" alt="Styling the North Arrow" width = 800>
</p>

39.  To adjust the properties of the North arrow, scroll down on the *Item Properties* window to find such useful features as changing color or size.

### Adding a Title

<p align="center">
	<img src="TextBox.png" alt="Adding a Title" width = 800>
</p>

One last addition, let's add a title to the map. 

40. Click the *Add Item* menu at the top of the screen and select *Add Label*.
41. Click on your map and draw a box where you want the title to be. 
42. In the Item Properties tab, expand the Label section and enter the text to title the map, I went with "Death Valley Surface Temperatures July 2023". You may want to play around with the spacing to get it to look clean and professional.
43. Under the *Appearance* drop down you can click on the font box to open up the *Text Format* window. 
44. From here you can pick your favorite font and size. You could also change the font color under the *Appearance* dropdown as well.
45.  You can also adjust the alignment, I set mine to *Center* horizontal alignment and *Middle* vertical.
46. Check the box next to *Frame* and adjust the parameters to draw a frame around your title.

### Exporting Your Map

<p align="center">
	<img src="Export.png" alt="Exporting Your Map" width = 800>
</p>

Now that our map looks exactly how we want it to look, we want to be able to share it with friends, family, our Instagram followers, and ultimately... NASA. 

47. To do so, select the *Layout* dropdown menu, then *Export as Image*. 
48. The *Export resolution* controls how much detail the output image contains. Smaller resolution = smaller filesize but with less detail saved. More resolution = more detail saved but larger filesize. If storage is an issue for you, go with 300 dpi, if not I like 600 dpi to capture the detail in most cases.
49. Click *Save* and bask in the glory of your first ECOSTRESS map, which (hopefully) resembles the one below. Congratulations... You did a thing!


**NOTE: There may be times when you want to export as PDF, particularly when the map needs to be scalable to different sizes.**

<p align="center">
	<img src="DeathValleyLSTfinal.png" alt="Final Death Valley LST Map" width = 800>
</p>

---

## Answering Our Original Question

<p align="center">
	<img src="DeathValleySign.jpg" alt="Final Death Valley LST Map" width = 600>
</p>

If you recall our motivation for this exercise was to see if an analysis with ECOSTRESS supported that land surface temperatures in Death Valley National Park came close to breaking the surface temperature record. 

Given that the highest recorded ground temperature of 201 degrees F was verified on July 15, 1972, it appears that our analysis does not support that surface temperatures exceeded that record in July of 2023, despite that it was one of the hottest months in recorded history for air temperatures.

**NOTE: It is important to remember that the process of science "supports" or "does not support" hypotheses. It does not entirely "prove" or "disprove" ideas. There are many factors that prevent our analyses from being entirely conclusive. These include the measurement error of our instrument, the times of day the satellite passed over the study site, cloudiness, etc...**

The real power of the ECOSTRESS satellite comes in its geographic and temporal continuity. For instance, it is easy to see from our map which parts of Death Valley have the highest surface temperature. We could also track this seasonally, to see the effect of vegetation. The possibilities are endless.

---

## Map of the Week Assignments

1. Read <a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial4_AddingElementsToMaps/s41467-020-19160-7.pdf" target="_blank"> The misuse of colour in science communication by Crameri, F., Shephard, G.E. & Heron, P.J.  Nat Commun 11, 5444 (2020).</a>
2. Have fun and make an interesting temperature map designed with your favorite theme in mind and submit it before next class. You could use this map or create a new one. Example themes to get your brain churning:
	* Wes Anderson
	* Van Gogh
	* Antique
	* Rick and Morty
	* The Best Taylor Swift Album (Obviously Midnights)

---

## Data
In case you encountered any issues with the A&#961;&#961;EEARS database, here are copies of the ECOSTRESS GeoTIFF files for Death Valley:
* <a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial2_AccessingRemoteSensingDataWithAppears/ECO2LSTE.001_SDS_LST_doy2023209214149_aid0001.tif" target="_blank"> ECO2LSTE.001_SDS_LST_doy2023209214149_aid0001.tif</a> 
* <a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial2_AccessingRemoteSensingDataWithAppears/ECO2LSTE.001_SDS_LST_doy2023209214057_aid0001.tif" target="_blank"> ECO2LSTE.001_SDS_LST_doy2023209214057_aid0001.tif</a> 

---
Citation: Forsythe, Goldsmith, Fisher 2023. 