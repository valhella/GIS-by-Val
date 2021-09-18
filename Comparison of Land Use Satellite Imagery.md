# Comparison of Land Use Satellite Imagery
## GIS Lab 9

![Masters_Lab9_Page_01](https://user-images.githubusercontent.com/45399983/133866112-f5df561e-3dfa-4445-aa69-933766e9ddcd.png)



![Masters_Lab9_Page_02](https://user-images.githubusercontent.com/45399983/133866115-f97445f7-9ed3-4aff-ba7f-71def7983628.png)



![Masters_Lab9_Page_03](https://user-images.githubusercontent.com/45399983/133866120-099b9b59-0985-4b50-9471-fe084a62d0fb.png)



![Masters_Lab9_Page_04](https://user-images.githubusercontent.com/45399983/133866123-dbd341ba-61d7-4966-a175-1705303d06a4.png)



![Masters_Lab9_Page_05](https://user-images.githubusercontent.com/45399983/133866128-e1551b22-d4a1-4b02-91c2-5aa01063db6e.png)



## Project Report: Land Use and Satellite Imagery Analysis for Fort Myers, Florida

Land use classifications extracted via unsupervised classification resulted in highly accurate land use maps
(compared to google earth imagery). Minute details, like the multiple runways at the airport, are readily
visible. In the Landsat 8 land use, most things appear to be in the right place. The only issue is that some
of the farmland appears to have been classified as urban. This could potentially be managed by more
experimentation with increasing the number of classes (I only did 4; open water, wooded wetland, grass,
and urban). When I increased the number of classes (I tried 5 and 6, respectively), it made it much more
difficult to tell what was what. Therefore, I recommend 4 classes, though depending on the complexity of
the area more may be appropriate. Landsat 7-extracted land use appears to over-estimate the amount of
open water on the landscape, when in reality it appears some of this is marshland. This imagery also does
not differentiate grass from agriculture, which again may be solved by more experimentation with the
number of classes. EO-1 ALI-extracted land use appears accurate when compared to Google Earth imagery
from the same year, but resulted in more land being classified as grass and water compared to Landsat 8.
Overall it is difficult to recommend one satellite over the other, since they all yield detailed and mostly
accurate land use maps. If imagery from post-2003 is required, Landsat 7 can automatically be discounted
due to a satellite error causing issues with the images. Landsat 8 images cover broader swaths of land
compared to the narrow strips EO-1 covers, so Landsat 8 may be more practical for large surveys. When I
compared my generated land cover images to the published USGS land cover dataset, my data blew the
gov’t out of the water in terms of fine detail. However, as noted above, I was limited in how many classes
I could create via this unsupervised method in such a complicated area. The USGS had five times as many
land cover classes. Therefore, I would recommend using the USGS land cover dataset only if you are
looking at a very broad area, on the scale of an entire state. If you want to understand anything on the
scale of a city or smaller, creating land cover data from satellites is definitely the way to go.
Please note that some of the discrepancies in land use between the satellites could be due to the fact that
the imagery is from different years. My EO-1 imagery is from October 2005, my Landsat 8 imagery is from
May 2017, and my Landsat 7 imagery is from May 2003 (due to problems with satellite imagery post-
2003). Though the landscape did not appear to change much over this time period (Florida is already
pretty much as developed as it can be, considering how hard it is to build on swamp), it was clear that the
reflectance of water varied depending on the day imagery was taken. This could be why Landsat 7 land
cover shows more water than the other imagery. Or, May 2003 could have been extremely rainy and
caused all depressions in the landscape to fill up. Data on precipitation and topography would help
determine if this were true. For an important project, ground truthing would need to be conducted.
When I was making the land cover dataset, I carefully chose what bands to use in order to create an image
that made sense. I excluded all extraneous bands, such as ones for cirrus clouds, and I also excluded
panchromatic bands. This resulted in me only including bands 1-7 for Landsat 8, bands 1-7 for Landsat 7,
and bands 2-10 for EO-1. When I created false color and true color images, I assigned different bands to
the red, green, and blue wavelengths. When I made the true-color images for EO-1 and Landsat 8, I
assigned Band 4 to red, Band 3 to green, and Band 2 to blue. When I made the true-color image for Landsat
7, I assigned Band 3 to red, Band 2 to green, and Band 1 to blue. I made these designations based on the
USGS FAQ for Landsat. For false color, I wanted to show infrared reflectance, which is created by plants.
