# Large Woody Debris
## GIS Lab 8

### Creator's Notes: 
For this lab my lab walked around Plum Creek in Oberlin, Ohio and used a Global Positioning System (GPS) devices to record the locations of big trees. After that we
imported our GPS data and compared the locations of the trees with aerial imagery to see how accurate
they were, which is called groundtruthing. If this were a larger-scale study, we probably would have
focused more on groundtruthing. We also took Light Detection and Ranging (lidar) data (a remote sensing
method that uses a pulsed laser to measure distance to earth or whatever object it hits first) from an Ohio
geographic data website called OGRIP. This allowed us to see elevation around Oberlin with trees vs.
without trees, which was cool.

Our goal for this whole lab was to be able to see how many large trees were in close enough proximity to
span the channel of Plum Creek if they fell (I measured the width of plum creek at a bunch of locations
digitally to find the average channel width). It’s important to know this because these trees, called
Potential Large Woody Debris (PWLD) are important for creating mini-habitats in streams, which fish and
microorganisms like. Basically, a good amount of trees in your river is good for the ecosystem at large. In
order to find the number and characteristics of PLWD, I made a Python script that allowed me to split the
lidar data into just trees and just ground and then subtract the ground elevation from the tree elevation
to get the tree heights. Then all I did a few more calculations and asked python to give me all the pixels
with trees in them that met my requirements (had to be tall enough and close enough to the river to span
it). This resulted in a nifty new raster file.

To display the data, I split the PWLD raster into two parts, northeast and southwest. The boundary
between the two was the north-south line between the two reservoirs in the arb, about where the main
path descends into the forest. This boundary coincided with a fairly obvious change in width of the PLWD
raster. The SW section had a much wider zone of trees around the river compared to the north section.
For my analysis I thought it would be interesting to find the number of potential large woody debris trees
in each section separately and see if tree size differed (I thought trees might be bigger in the SW zone just
based on walking there and observing large trees), so I manually counted the pixels for 7 well-defined
trees in the NE raster, averaged them, and then divided the total number of pixels in this raster by the
number of pixels per tree to get the number of PLWD trees. I did the same for the SW raster. The NE
section had 117 pixels per tree and 19,549 pixels total, which worked out to 167 trees. The SW section
had 127 pixels per tree (meaning larger trees) and it had more total pixels, 21,265. This worked out to the
exact same number of trees in each section, 167. Amazing. By opening the data table associated with each
section, I was also able to see how tree height varied. Both sections had a minimum tree height of 18 feet
since that is what I defined as the average channel width, but the northeast section had a maximum tree
height of 104 while the southwest section had a max of 108. More revealing is the mean tree height in
each section, which was 60 feet in the northeast and 63 in the southwest. The difference is small, but it
seems that trees in the southwest grow taller on average and attain a higher stature overall. The
southwest section may have better growing conditions for trees due to soil type, saturation, pH, slope of
land, etc. We did not calculate how likely the trees were to fall (dependent on slope), which would be
important if we wanted to be able to predict future habitat with accuracy.

This method of analysis is prone to a lot of error, because estimating the average number of pixels per
tree was difficult and there was a wide range in size of trees. I tried to standardize which color pixels I counted, but I don’t know how successful I was. It’s unclear how the angle the imagery was taken at could
obscure the data, since very tall trees viewed straight down would not appear very large/wouldn’t cover
very many pixels. This analysis could be improved by comparing minimum number of pixels per tree, which
would result in maximum number of trees in the section, and maximum number of pixels per tree, which
would result in minimum number of trees in the section.
