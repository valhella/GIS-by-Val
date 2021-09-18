# Channel Migration and Sinuosity Changes
## GIS Lab 3

![Masters_map_review_1_Page_4](https://user-images.githubusercontent.com/45399983/133866641-c186c60c-5338-4160-98c6-0f92dd15049f.png)

### Creator's Notes:
My goal was to show how the river’s sinuosity and path changed over time. I could
see that the river eked out meanders and abandoned them when they became too twisty, and varied it’s
course quite a lot over the years.
To understand how the river changed, I traced the paths of the river while viewing one year’s imagery at
a time (in one shapefile, to keep things simple). Then I added the year info for each line to the file in the
Attribute Table. I made them different colors too. Then to calculate sinuosity I downloaded a toolbox file
from ArcGIS’s website that ran a python script. Unfortunately, someone at ArcGIS messed up and
flipped the equation for finding sinuosity, which yielded sinuosity values under 1 (they should be 1 at
the very lowest. A sinuosity value of 1 would indicate a perfectly straight river). To fix this, I opened the
script in a Python viewer program, and simply changed around the part that described which thing to
divide by. I saved the newly edited script and opened it in ArcGIS. I applied it to my river channel
shapefile, which calculated the sinuosity for each year’s path. Turns out, the river was most sinuous in
1940, and least sinuous in 2002. I would have expected it to be most sinuous in 1867 and least in 2009,
but I’m guess that a few factors are at play here:
1. I didn’t trace the pathways accurately.
a. Low quality of imagery in some cases (trees blocking for example) could have prevented
me from capturing the real path of the river.
b. I did not trace the parts of the river where it branched off, so my sinuosity is probably an
underestimate.
2. I don’t know what month the imagery is from, so it could be the dry season in one year and the
wet season in another, which would make comparison less viable.
3. Human intervention (damming) could have altered the river’s behavior from what would be the
expected decreasing sinuosity over time as the river seeks the most efficient course to Puget
Sound.
4. A flood in intervening years could have changed things dramatically
