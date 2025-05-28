# Media Coverage
## Data Summary
Data for this metric was gathered from Media Cloud, an open source platform for media anlysis. Media Cloud is maintained by the [University of Massachusetts Amherst](https://publicinfrastructure.org/), [Northeastern University](https://dataculture.northeastern.edu/), and the [Media Ecosystems Analysis Group](https://www.mediaecosystems.org/).

## Methodology
Media Cloud provides API Tutorial Jupyter Notebooks through [Github](https://github.com/mediacloud/api-tutorial-notebooks). The Notebook "MC02 - SLRBayArea.ipynb" is adapted from these tutorials.

- Performed a Boolean Search for articles about Sea Level Rise in the San Francisco Bay, in both english and spanish
  - ("sea level rise" OR "sea-level rise" OR "SLR" OR “Aumento del nivel del mar”) AND ("San Francisco" OR "SF Bay" OR "San Pablo Bay" OR "S.F. Bay" OR "Suisun Bay")'  
- Used Media Cloud’s “California, United States -State & Local” Collection of 1,265 sources that cover local and national stories about California.  
- Download this data, which stats in January 2023, into an excel spreadsheet. See python Notebook for more detail on how this was completed. 

While Media Clous provides a great overview of Articles, San Francisco Chronicle and Knee Deep Times articles are not properly included in Media Cloud’s database. We emailed them but did not get a response.In addition to the Python Scripts we created a spreadsheet of Chronicle and Knee Deep Times articles during the same time period that will need to be manually updated. 

- Performed an Advanced Google Search w/ Date range specfied
  - "sea level rise" AND "San Francisco" site:sfchronicle.com / "sea level rise" AND "San Francisco" site:kneedeeptimes.org
- This only returns articles published in the chronical/knee deep times that include those exact phrases
- Added a time constraint using the “tools” button to limit the time frame
- Used the same formatting as the python excel sources spreadsheet so the data could be easily combined in power BI 
