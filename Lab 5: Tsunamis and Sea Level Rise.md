# Map of the maxiumum water rise from the 2011 Tohoku Tsunami in the Olympic Peninsula compared with projected climate-induced sea level rise
## GIS Lab 5
![Tohoku_edit](https://user-images.githubusercontent.com/45399983/133865721-5ebfd9e4-8eca-48b9-a0d1-2092d8626ba1.png)

![Extraction_MastersLab5 1](https://user-images.githubusercontent.com/45399983/133898297-db0f44f6-36a8-4ac7-88c8-848748634a58.png)

### Creator's Notes:
The intent of this lab was to show how climate change-induced sea level rise could mimic a short-term natural disaster like a tsunami, and draw attention to how rising sea levels will cause an increase in destruction from storm surges and tsunamis.  

For the Olympic Peninsula map series, I researched what the expected future sea level rise will be in Washington State with climate change (assuming "business as usual" emissions scenario), and
researched the maximum run-up height of water created from the 2011 Tohoku earthquake. I was curious about how
much the tsunami diminished from its origin point in Japan to across the pacific in Washington. Turns out,
a lot! 40 meters. Japan was absolutely overwhelmed by the tsunami, and western Washington had
a large wave, but probably no bigger than for a large storm. In addition to creating a visualization for
these shorelines, I also found how many people would be affected by the sea level rise via census data for
Washington and population density data for Japan. Lots of people were affected in Japan, but only about
90 were affected in Washington for even the biggest expected rise. 

I started by converting files downloaded from the web to usable raster format and projecting them. I
chose NAD83 (the North American datum) for all my files, but chose different zones (10N for Washington,
54N for Japan). I also created a hillshade file to make things pretty, which is where you make the relief on
the map obvious. I found that I had to clip a lot of files for this lab to trim things down to the area that I
was interested in. Sometimes I had to create a new shapefile with the editor tool to make the file I wanted
to clip by. This was nice because I could create custom shapes.

I also used a new tool in this lab called “raster to polygon” which does what you would think, it converts
a raster to a shapefile, since some tools can’t have rasters as inputs (or you need all your inputs to be the
same file type). Of all the tools I used this week though, the reclassify one was most important. It allowed
me to create shorelines by classifying all the individual raster boxes as either water or land. I used this
multiple times for each location to show how the shoreline would look in 2050 vs tsunami inundation and
so on. I color-coded the shorelines so they could be shown all on the same map. The main difference
between the two locations in terms of analysis was that I needed to use “zonal statistics” for the Japan
location. I had to do this because I didn’t have census data, only population density data. This created a
table that allowed me to see the average, max, and minimum population densities in Eastern Japan as
well as the area covered. Japan has a really dense population, so a lot of people were affected by the 2011
tsunami. To figure out how many people were affected by the Tohoku Tsunami's water rise, I found how many people there were on average per square kilometer (data found from using focal statistics tool on my population density raster). Then, I converted the area (also found from focal statistics) to km squared, and multiplied people/area * area, which allowed area to be canceled out.

To see in more detail the different shorelines, I created “data driven map pages” for my Washington location.
ArcMap has this really cool thing where you can set up a map with two different data frames, one has a
large-scale map and one has a small-scale map on it. You overlay a grid on the smaller map (zoomed out
to show all of western Washington in my case) and label each of the grid sections. Then, ArcMap will
automatically create individual pages for each section of the grid. I had a bunch of sections, about 50 in
total. The format is automatically the same across all the pages. 

In the future I would like to try this out with Japan as well, with a detailed infrastructure layer so that viewers could see exactly what was affected. I would also like to apply climate change sea level rise projected shorelines on a map series of Japan. As it turns out, Washington is not that vulnerable to western-Pacific tsunamis or climate-induced sea level rise. I do not think that my data accounts for glacial rebound, which would make the climate change sea level rise even smaller. Essentially, I would like to repeat this lab but only focus on Japan, or repeat it on an area that experineces both hurriances, sea level rise, and land subsidence (e.g. Louisiana or Florida). 
