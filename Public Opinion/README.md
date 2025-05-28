# Public Opinion
## Data Summary
Data for this Metric was gathered from the [Yale Program on Climate Change Communication (YPCCC) Climate Opinions Maps](https://climatecommunication.yale.edu/visualizations-data/ycom-us/. You can learn more about the survey and model methodology [here](https://climatecommunication.yale.edu/visualizations-data/ycom-us/). 

Those surveyed were asked: "Recently, you may have noticed that global warming has been getting some attention in the news. Global warming refers to the idea that the world’s average temperature has been increasing over the past 150 years, may be increasing more in the future, and that the world’s climate may change as a result. What do you think: Do you think that global warming is happening?" The possible responses were "Yes", "No", or "I don't know". Those who answered "Yes" were included as the percentage who believe climate change is happening. 

## Methodology
- Filtered “Geoname” so only Alameda, Contra Costa, Marin, Napa, San Francisco, San Mateo, Santa Clara, Sanoma, Solano, California, and the United States are selected
- Filtered “Varname” so only “happening” is selected
- Selected “geoname” as well as all annual data columns that were not null” and transposed them into a new sheet (flipped columns and rows).
- Added a row between each year called “20xxpop” and inserted 1-yr ACS county population data into the corresponding cell.
- Created a column called “Bay Area” and summed the Bay Area population for each year from each of the nine county populations
- Calculated the weighted population average for the Bay area 
