# Tutorial #2: Accessing Remote Sensing Data With A&#961;&#961;EEARS

Observing Earth from Above (Env 329) - Fall 2023

Schmid College of Science and Technology

Chapman University

---

## Learning Objectives (Total Estimated Time - 50 minutes): 

1. Access and practice using the A&#961;&#961;EEARS Interface.
2. Familiarize yourself with QGIS's toolbars, buttons, & layout.
3. Download & visualize temperature data From ECOSTRESS in QGIS.
---

<p align="center">
	<img src="AppearsLogo.png" alt="NASA AppEEARS Logo" width = 300>
</p>

## Welcome Back! 

Today, we are introducing A&#961;&#961;EEARS, The Application for Extracting and Exploring Analysis Ready Samples, which is a web-based application  designed to efficiently connect users with geospatial data that has been generated by satellite remote sensing instruments associated with agencies such as NASA and the U.S. Geological Survey. Different satellite remote sensing make their data available through different platforms, but today we are going to use A&#961;&#961;EEARS to access data from the [ECOsystem Spaceborne Thermal Radiometer Experiment on Space Station (ECOSTRESS)](https://ecostress.jpl.nasa.gov/) instrument. 

To begin, head over to <a href="https://appeears.earthdatacloud.nasa.gov/" target="_blank"> https://appeears.earthdatacloud.nasa.gov/</a>. Click the *Sign In* button to register for an Earthdata account, or login if you already have an account.

<p align="center">
	<img src="AppEEARShome.png" alt="AppEEARS Homepage" width = 1000>
</p>

A&#961;&#961;EEARS is designed to allow you to download either point (i.e., data from a given latitude/longitude) or area (i.e., all of the pixels that fall within a given area) data. It also allows you to choose the timespan for the data and the type of data you wish to request.  

1. To access satellite data use the *Extract* dropdown menu to select *Area*. 
2. Next select *Start a New Request*.

---
## Motivation For Today's Tutorial : Death Valley

<p align="center">
	<img src="DeathValleySignECOSTRESS.png" alt="Death Valley National Park with ECOSTRESS Satellite" width = 600>
</p>

ECOSTRESS primarily measures land surface temperatures (LST), so let's look at the thermometer at one of the hottest places on the planet: Death Valley, California. The highest recorded ground temperature was verified at 201 degrees F on July 15, 1972. However, it recently had one of the hottest months on record, where air temperatures reached upwards of 128 degrees F in July of 2023. We are going to download the land surface temperature data from ECOSTRESS for those days to see how close it was to breaking the ground surface temperature record.

**NOTE: ECOSTRESS launched on July 9, 2018, so as you think about potential projects, you cannot design a project that requires data before that date.**

---

## Accessing ECOSTRESS Data through A&#961;&#961;EEARS

### Create a Request

3. Select the *Start a new request* to request data for a new area and new time period.
4. Enter a useful name for the request you are going to submit, maybe something like "Death Valley Temperature Experiment." Getting in the habit of assigning unique and relevant names will be useful when you start making many requests for data from A&#961;&#961;EEARS.

Now, we need to specify to A&#961;&#961;EEARS your geographic area of interest (AOI), which in this case is Death Valley National Park. This can be accomplished a few different ways:
* Using the map interface to draw a rectangle or polygon that encompasses your AOI.
* Uploading a [shapefile](https://en.wikipedia.org/wiki/Shapefile) that describes your AOI.	

Today, we are going to use a shapefile describing a polygon of the park boundaries that we already drew for you in QGIS. In later tutorials, you will draw your own.

5. Download the <a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial2_AccessingRemoteSensingDataWithAppears/DeathValleyNationalPark.zip" target="_blank"> DeathValleyNationalPark.zip</a> shapefile and save it somewhere you can remember. A folder containing all of the files for this tutorial sounds effective and orderly. 

<p align="center">
	<img src="ExtractDeathValley.png" alt="Extract Area Sample Settings" width = 800>
</p>

6. Drag and drop (or use the *click here to select the file* link) to upload the shapefile DeathValleyNationalPark.zip. The map should update with a polygon encompassing Death Valley National Park.
7. Update the *Start* and *End* Date Fields for our month of interest: 07/01/2023 to 07/31/2023

While A&#961;&#961;EEARS provides access to a wealth of [different data products](https://appeears.earthdatacloud.nasa.gov/products), here we are primarily focusing on data from the ECOSTRESS instrument.

<p align="center">
	<img src="LayerSettings.png" alt="Layer Settings" width = 600>
</p>

8. Under *Select the layers to include in the sample* type the word "ECOSTRESS" and scroll until you can click on *ECOSTRESS Land Surface Temperature & Emissivity (LST&E)*. From there, scroll until you see the Land Surface Temperature (*SDS_LST*) option. Click on the "+" sign to add the layer into your cart. Next, clear the current category selection using the small "x" to the right of the *ECOSTRESS Land Surface Temperature & Emissivity (LST&E)* blue box. Then search for "Cloud" and add *Cloud_final* from the *ECOSTRESS Cloud Mask Instantaneous* category to your selected layers cart.

If you want to learn more about the types and formats of the ECOSTRESS Mission data, you can find all sorts of interesting facts here: <a href="https://lpdaac.usgs.gov/data/get-started-data/collection-overview/missions/ecostress-overview/" target="_blank"> https://lpdaac.usgs.gov/data/get-started-data/collection-overview/missions/ecostress-overview/</a>.

9. Under *Output Options*, we want to use GeoTIFF (Geographic Tagged Image File Format; essentially an image file where the corresponding geographic information is embedded in the file) and *Native Projection* for projection.
10. Click *Submit* to complete the data request. At the top, you should see a green banner:

<p align="center">
	<img src="RequestSuccess.png" alt="Green Success Banner" width = 1000>
</p>

---
---
---
---
---
---

<p align="center">
	<img src="QgisLogo.png" alt="QGIS Logo" width="300">
</p>

Since we need to wait for A&#961;&#961;EEARS to process your request, it is a good time to get you acquainted with how we will use QGIS to run our analyses and visualize our data.

<a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial3_MakingBasicMapsInQGIS/Tutorial3_MakingBasicMapsInQGIS.html" target="_blank"> Follow this link to complete Tutorial 3: Making Basic Maps In QGIS, while you wait.</a>

After you finish, there will be a link back here to continue to work with our data request.


---
---
---
---
---
---


## Data Check

11. It is time to check back on the status of your request. When your data is ready, you will receive an email with the subject line "A&#961;&#961;EEARS Request Complete" at whichever email address you used when creating your EarthData login. Most small requests will take 15 minutes or less, larger ones can take upwards of an hour. You can also track the progress of your request and access the data at https://appeears.earthdatacloud.nasa.gov/explore. Follow the *Explore* link in your completed request email (or via the explore menu tab on the A&#961;&#961;EEARS homepage) to access your data.

**NOTE: While using the A&#961;&#961;EEARS interface you will occasionally encounter an error, or the system may be out-of-service for maintenance or updating. If it is the latter, there will be a banner at the top of the A&#961;&#961;EEARS webpage with information about the timeline to restore service. If you encounter an error without a banner present, you can submit a support ticket at :** <a href="https://lpdaac.usgs.gov/lpdaac-contact-us/" target="_blank"> https://lpdaac.usgs.gov/lpdaac-contact-us/</a>.

**NOTE: For these tutorials, if the A&#961;&#961;EEARS interface is not functioning, we have provided links at the end of each page to the necessary files.**

<p align="center">
	<img src="ExploreLST.png" alt="Explore Land Surface Temperature" width = 800>
</p>

12. Before we download the files, we should preview the data using the built-in A&#961;&#961;EEARS visualizations. First, make sure the Land Surface Temperature (LST) layer is selected. Under *Layer Stats*, you will see a boxplot timeseries of the temperature data across the range of dates (x-axis) and observed temperature that the instrument observed for each date (y-axis). See the image below for what you can learn from a boxplot. Next, hover over the boxplots in the timeseries to see all sorts of useful information, including the date and time of day of the satellite pass. While 7/26/2023 had the hottest air temperature of the month, our observations of surface temperature are among the lowest! Why is that? Have we discovered some new physical property of the desert? Well no, the satellite pass was simply at 9:49 AM, which was not exactly the hottest part of the day.

**Note: ECOSTRESS makes temperature observations on the Kelvin scale, not degrees Fahrenheit or Celsius.** 

&nbsp;

<p align="center">
  <img src="HowToBoxplot.png" width = 500 />
</p>

You are likely noticing that the distribution of temperatures for a given [orbital pass](https://en.wikipedia.org/wiki/Orbital_pass) from the instrument is quite variable. In some instances, like on Tuesday, 7/11/2023, all of the temperatures are close to the median. On other days, like Monday, 7/31/2023, the temperatures vary considerably. If this was a different locale, it could mean that there is a lot of variation in surface temperatures across this geographic area of interest. However, in this case we know Death Valley is consistently a hot desert, so it is more likely there is another culprit, clouds.

<p align="center">
  <img src="Clouds.png" width = 250 />
</p>

Satellite observations have many advantages, but they can not accurately measure through clouds. To account for this possibility, the ECOTRESS mission (and others) have built cloud detection algorithms and included that data in A&#961;&#961;EEARS. Checking for the effects of cloud cover on the accuracy and precision of the results is an important part of data quality control and assurance. 

<p align="center">
	<img src="ExploreClouds.png" alt="Explore Cloudiness" width = 800>
</p>

13. Change the layer in the built-in A&#961;&#961;EEARS visualizations to Cloud_final. Now, we have a different visualization, the output of the cloud detecting algorithm. The bar chart breaks down the percentage of pixels that are clear (represented in blue) and pixels that have clouds (orange). Satellite passes that are free of clouds, or have few clouds, tend to have higher quality data with fewer outliers because there is little interference. To make our temperature map, let's use data from the hottest cloud free day: 7/28/2023. 

### Download The Data

Output data files returned by AppEEARS have the following naming convention:  

`<ProductShortName>.<Version>_<LayerName>_doy<Year><JulianDate>_<AppEEARSFeatureID>.<FileFormat>`  

Example output file name (.tif): 

   ECO2LSTE.001_SDS_LST_doy2023209214149_aid0001.tif 

**where:**  

    <ProductShortName> .......... ECO2LSTE 
    <Version> ................... 001  
    <LayerName> ................. SDS_LST 
    <Year> ...................... 2023  
    <JulianDate> ................ 209  
    <AppEEARSFeatureID> ......... aid0001 
    <FileFormat> ................ tif

In this case, we are primarily concerned with the layer name, which corresponds to our variable of interest (i.e., Land surface temperature = *SDS_LST*), and with the time of the satellite pass (i.e. Year = 2023, Julian Date = 209).

<p align="center">
	<img src="Julian209.png" alt="Julian Calendar Information" width = 600>
</p>

14. Access the download page by scrolling to the top of the page, selecting the *Explore* menu and selecting the middle button next to your request, *Download the contents of the request* <img src="DownloadButton.png" alt="Download Button" width = 25>. Use the Julian Calendar and file naming convention listed above to determine what filename we need to download the land surface temperature data for 7/28/2023. There can be multiple files that match the date and layer you requested, in this case there are two. Download both files into the same folder that you saved the DeathValleyNationalPark.zip shapefile.

**NOTE:** <a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial2_AccessingRemoteSensingDataWithAppears/Julian_Calendar.png" target="_blank"> You can access the Julian Calendar table anytime be clicking this link. Watch out for leap years!</a>. 

<p align="center">
	<img src="DownloadInstructions.png" alt="Download Instructions" width = 800>
</p>

---
## Visualizing the Death Valley Surface Temperature Data in QGIS

### Adding a Google Satellite Basemap

In the last tutorial, we added in a simple basemap through a service included in the base QGIS installation. Today, we are going to expand QGIS's functionality by using an available plugin: HCMGIS. [Plugins](https://docs.qgis.org/3.28/en/docs/training_manual/qgis_plugins/fetching_plugins.html) are external pieces of software that add useful features to QGIS. 

<p align="center">
	<img src="QGIS_Plugins.png" alt="QGIS Plugin Instructions" width = 1000>
</p>

15. Open QGIS and start a new project by selecting the *Project* menu &rarr; then *New*. To install the HCMGIS plugin, click on the *Plugins* drop down menu and select *Manage and Install Plugins*.
16. In the next window, make sure *All* is selected in the first window pane and search for HCMGIS. HCMGIS is plugin that allows for easy imports of a wide selection of basemaps.
17. Click *Install Plugin* and wait for the installation to complete.


<p align="center">
	<img src="GoogleBasemap.png" alt="Google Satellite Basemap" width = 1000>
</p>

18. To quickly and easily add a basemap, all you need to do is find the *HCMGIS* menu bar, select *Basemap*, then pick your preferred map. For today's map, we will use *Google Satellite*, though you could play around with other options. Some other favorites are "ESRI Imagery", "ESRI Delorme," "Stamen Terrain," and "NASA Black Marble," though their utility depends on the goal(s) of your map. Note that clicking on a basemap type automatically adds a new layer to your map, as seen in the layer browser window.

### Importing Our ECOSTRESS Death Valley Layer

<p align="center">
	<img src="ImportLST.png" alt="Import Land Surface Data Into QGIS" width = 1000>
</p>

19. Use the *browser* window to find the folder where you saved the two land surface temperature .tif files. Double click each file to add them to your map. Again, notice they are now also listed in the *Layers* window.

<p align="center">
	<img src="SymbologyLST.png" alt="Change Symbology" width = 500>
</p>

20. Congrats! You now have ECOSTRESS data on a map. But wait...let's make it look just a little better before you celebrate your win. QGIS doesn't know what kind of data this is and has defaulted to displaying the information in grayscale, which isn't that useful to our eyes. For each land surface temperature layer, right click on the layer name in the *Layers* window and select *Layer Properties*. On the menu bar to the left, select *Symbology* and change the *Render type* to Singleband pseudocolor. Since this is temperature, it is common to use a red color ramp. QGIS has automatically determined the minimum and maximum values from the datafiles; however, we have two files, so we need to make them match. Specify 306.82 as the minimum and 347 as the maximum for both layers. Click apply.

21. Lastly, add in the border from the DeathValleyNationalPark.zip shapefile. In the *Browser* window expand the zip file using the small arrow next to the filename. Double click on *Death Valley National Park.shp* to add the layer. Right click on the layer in the *Layers* window and change the symbology to *outline blue*. 

22. Now we can celebrate... Your map should resemble the one below:

<p align="center">
	<img src="TempMap1.png" alt="Map" width = 800>
</p>

**NOTE: There was not full data coverage for the entire park available, that is why the Northernmost part of the park does not have any color overlayed. This happens sometimes due to the orbit of the satellite.**

23. Save your QGIS Project into the folder with all of the other files from this tutorial by going to the *Project* menu bar at the top and selecting *Save As...*. Maintain the file format as .QGZ.

24. Finally, export your map. From the *Project* menu, navigate to *Import/Export* and select *Export Map To Image*. Increase the resolution to 200 dots per inch (DPI). You will submit this map, so save it into the same folder. 

Congratulations! You have learned how to download ECOSTRESS instrument data from A&#961;&#961;EEARS and make a basic map in QGIS.

---

## Map of The Week Assignments

1. Watch the YouTube Video: ["Why All Maps Are Wrong"](https://youtu.be/kIID5FDi2JQ)
2. Read the article <a href="https://open.lib.umn.edu/mapping/chapter/7-lying-with-maps/" target="_blank"> Lying With Maps</a> from the University of Minnesota. 
3. Submit your timezone map and land surface temperature map from this tutorial.
---
## Data
In case you encountered any issues with the A&#961;&#961;EEARS database, here are copies of the ECOSTRESS GeoTIFF files for Death Valley:
* <a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial2_AccessingRemoteSensingDataWithAppears/ECO2LSTE.001_SDS_LST_doy2023209214149_aid0001.tif" target="_blank"> ECO2LSTE.001_SDS_LST_doy2023209214149_aid0001.tif</a> 
* <a href="https://jeremydforsythe.github.io/icecream-tutorials/Tutorial2_AccessingRemoteSensingDataWithAppears/ECO2LSTE.001_SDS_LST_doy2023209214057_aid0001.tif" target="_blank"> ECO2LSTE.001_SDS_LST_doy2023209214057_aid0001.tif</a> 
---
Recommended Citation: Forsythe, J.D., G.R. Goldsmith, and J.B. Fisher. 2023. Tutorial 2: Observing Earth from Above. Chapman University. https://jeremydforsythe.github.io/icecream-tutorials/

This work is supported by funding from NASA ECOSTRESS Mission Grant #80NSSC23K0309 (I.C.E. C.R.E.A.M.: Integrating Communication of ECOSTRESS Into Community Research, Education, Applications, and Media).