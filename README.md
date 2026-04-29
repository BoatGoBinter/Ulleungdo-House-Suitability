# Finding the Most Suitable Place to Build a House on Ulleung Island

## Introduction
Ulleung Island is an island east of the Korean peninsula owned and administered by the Republic of Korea. I have always been fascinated by this island due to its isolation from the mainland. With a population of around 9,000 and an area of 72.86 kilometers, the island obviously quite small and unpopulated. Thus, it remains relatively unspoken about in Korean society. When Koreans hear ‘Ulleungdo’, they mostly think of it as an island with little infrastructure without much of a purpose other than as a means for fishing and visiting Dokdo Island, a national symbol of Korea. However, Ulleung Island is much more than this. It is a beautiful island with a close, tight-knit community. In the future, I hope to visit this island and maybe even retire there to live a peaceful life. Thus, I decided to create a suitability map of where I want to build a house on Ulleung Island.

## Methods
For my methods of finding a suitable place, I decided to have three core variables to pick the best place to live: slope, distance to roads, and distance to coast. The reason for slope is obvious as it is impractical to build a house on land that is not flat or close to flat. Distance to roads is convenient as being close to a road means you can drive around the island more easily. Lastly, I prefer living near the sea for a coastal view. However, it is important to note that there are weights on these variables, with slope having the highest and distance to roads higher than distance to sea. For specifics, in my main map I put these weights: slope at 50%, distance to roads at 30%, and distance to the coast at 20%. I prioritized buildability while still considering accessibility and coastal proximity.

I acquired the data from the ALOS Global Digital Surface Model (AW3D30) provided by the Japan Aerospace Exploration Agency for elevation, the Database of Global Administrative Areas (GADM) for polygon boundaries which were used to calculate the distances of points to the coast, and OpenStreetMap for road data. All variables were reprojected to WGS 1984 UTM Zone 52N to ensure consistent units and accurate spatial analysis. I generated slope from the ALOS DSM and calculated Euclidean distance rasters for roads and the coastline, then reclassified each layer into a common 1–5 suitability scale. I converted the rasters to integer format and combined them using a weighted overlay (slope 50%, roads 30%, coast 20%) to produce the final residential site suitability map.

## Data Downloads
- https://gadm.org/download_country.html  
- https://www.eorc.jaxa.jp/ALOS/en/aw3d30/data/html_v2404/dl/download_v2404.htm?N035E130_N037E130  
- https://download.geofabrik.de/asia/south-korea.html  


## Results & Conclusion
For the results, I created two maps. The first map is more heavily weighted on a flat slope while the other map is more generalized and has looser acceptability.

Overall, these results emulate where most people on Ulleung Island live. Thus, I am quite happy with my suitability model. If I wanted to go further into this suitability model, I would first remove the surrounding coast from the variables as I had trouble removing them. My quick workaround was to remove absolute zeroes from my slope. However, this is not the most professional method of fixing everything. Moreover, I need to filter out these very small rocks. If you look at the north and north-east coasts of Ulleungdo on the second final map, there are incredibly tiny rocks that are nowhere close to being suitable to stand on, let alone build on. Some are just pillared rocks, but they are marked as suitable. This is a problem with the slope data. I am very happy with how this turned out and this project was incredibly fun.
