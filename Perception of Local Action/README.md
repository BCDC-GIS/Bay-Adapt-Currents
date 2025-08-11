# Perception of Local Action
## Data Summary
Data for this Metric was gathered from the [Yale Program on Climate Change Communication (YPCCC) Climate Opinions Maps](https://climatecommunication.yale.edu/visualizations-data/ycom-us/. You can learn more about the survey and model methodology [here](https://climatecommunication.yale.edu/visualizations-data/ycom-us/). 

Those surveyed were asked: "Do you think local officials should be doing more or less to address global warming?" The possible responses were "much more," "more," "currently doing the right amount," "less,"  or "much less." Those who answered "more" or "much more" were combined to create the population that thinks local officials should be doing more.

## Methodology
- Filtered Data data so we are only looking at localofficials and the nine county bay area
- Filtered “Geoname” so only Alameda, Contra Costa, Marin, Napa, San Francisco, San Mateo, Santa Clara, Sanoma, Solano, California, and the United States are selected
- Filtered “Varname” so only “localofficials” is selected
- Selected “geoname” as well as all annual data columns that were not null” and transposed them into a new sheet (flipped columns and rows).
- Added a row between each year called “20xxpop” and inserted 1-yr ACS county population data into the corresponding cell.
- Created a column called “Bay Area” and summed the Bay Area population for each year from each of the nine county populations
- Calculated the weighted population average for the Bay area 
