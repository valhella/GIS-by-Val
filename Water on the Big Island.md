# Mean Annual Rainfall, Watersheds, & Rivers on the Big Island of Hawaii

![Masters_Lab7_Page_1](https://user-images.githubusercontent.com/45399983/133866211-7100e3cc-2010-47ea-beee-3c2e21399135.png)

#### Creator's Notes:
The focus of the lab was seeing if mean annual rainfall
affected drainage density on the Big Island of Hawaii. Conceptually, drainage density is not that
difficult to get (it’s just stream length divided by area of the watershed), but finding drainage
density for every watershed on a map is surprisingly challenging. To start off, I collected DEM
data, a stream polygon file for comparison with my own created streams and for calculating stream
length, and rainfall data for the big island of Hawaii. I of course made sure they all lined up on the
map by putting them in the same projection.

After projecting, I processed the DEM to find the slope and fill in any imperfections/divots in the
landscape. Arc has some cool hydrology tools that allowed me to then find the predicted flow
direction of water over the land, and how it would accumulate downstream. I had to reclassify the
data once I had done this to show a reasonable number of streams, since Arc will assume that
rainfall is equal all over the land and fill in any stream-channel like hollows with a stream line. In
fact, rainfall is concentrated in Hawaii in the northeast, and there are hardly any real streams (as
seen on my downloaded stream data) in the south. I played around with the reclassifying boundary
for a while until I found an O.K. match with the real stream data, though of course with my created
streams there were a bunch in the south where there wouldn’t be streams in real life. After I did
this, I turned my created streams file (which was a raster file—very pixelated) into a polyline
(which is a shapefile). Finally, I created a new blank shapefile. I turned on the editor toolbar in
order to create new points within this shapefile. I added points to the terminuses of most of my
created streams, making sure to place the points on the polyline and within a pixel on the original
raster created streams line. I messed this up originally and needed to go back and re-place a bunch
of points. With all these outlet points laid, I could finally find the watersheds.

Apparently Arc has issues with computing watersheds when some watersheds are nested or when
they overlap, so we had to use python to write our own multi-function script. This involved using
the outlet points and flow direction raster created in ArcMap to make a watershed raster. From
there I turned the watershed raster into a polygon and filled the holes in it to get rid of areas that
had no overland drainage (like ponds). I also inputted the annual rainfall data that I found and
calculated the mean using zonal statistics, which resulted in a table being created. Last, I joined
this table with my watershed polygon so that when I opened the data table in ArcMap all the data
would be in one place.

This python script resulted in individual watershed shapefiles being created, so I merged them all
into one file. After that I added a field in the data table and calculated the area of each watershed
using “calculate geometry”. Super neat. Then I intersected my merged watershed shapefile with
the streams data I downloaded. This is so that the stream length data and watershed area data would
be in the same data table. After that I used a tool called “dissolve”, in which I separated all the data
by a unique attribute of each watershed, in this case an “FID”. After that I just added a field to the
data table on this new file and used the built-in calculator to get drainage density. I exported this
data table to excel and plotted mean annual rainfall against drainage density….and got an R squared value of about 0, so there was no correlation. I thought that maybe slope might have
something to do with drainage density, so I used zonal statistics (tool in Arcmap this time, not as
a python function) to get average slope for each watershed. I exported this data and plotted slope
against drainage density, and again got no correlation. After I made my map showing the most
important bits of data, I realized the lack of correlation between precipitation and drainage density
may be due to the eastern side of Hawaii, where I could see that there was a lot of rainfall but few
streams. This very well could have thrown off the data. The lack of correlation between slope and
drainage density likely just means there are more important factors than slope-or maybe taking the
average slope over a large watershed was not a detailed enough approach. Regardless, more data
analysis of this sort would reveal if the relationships I discovered between my variables (or the
lack thereof) is consistent across the islands.
