# Media Coverage
## Data Summary
Data for this metric was gathered from Media Cloud, an open source platform for media anlysis. Media Cloud is maintained by the [University of Massachusetts Amherst](https://publicinfrastructure.org/), [Northeastern University](https://dataculture.northeastern.edu/), and the [Media Ecosystems Analysis Group](https://www.mediaecosystems.org/). 

## Methodology

Performed a Boolean Search for articles about Sea Level Rise in the San Francisco Bay 

("sea level rise" OR "sea-level rise" OR "SLR" OR “Aumento del nivel del mar”) AND ("San Francisco" OR "SF Bay" OR "San Pablo Bay" OR "S.F. Bay" OR "Suisun Bay")'  

Used Media Cloud’s “California, United States -State & Local” Collection of 1,265 sources that cover local and national stories about California.  

Used Python to download this data, which stats in January 2023, into an excel spreadsheet. See code for more detail on how this was completed. 

San Francisco Chronicle and Knee Deep Times articles are not properly included in Media Cloud’s database. I emailed them but did not get a response. Because the Chronicle is such a major news source in the Bay area I created a spreadsheet of Chronicle articles during the same time period that will need to be manually updated. 

Googled: "sea level rise" AND "San Francisco" site:sfchronicle.com 

This only returns articles published in the chronical that include those exact phrases 

I added a time constraint using the “tools” button to limit the time frame to between Jan 2023 and Apr 2024 

Used the same formatting as the python excel sources spreadsheet so the data could be easily combined in power BI 

Data Update Steps:  

Open python scripts provided in the Adaptation Tracking Metrics folder under 4. Data -> Media Coverage -> Python scripts 

If it is the first time running this code on the computer run the setup script 1st to ensure all the necessary packages are downloaded 

If necessary, you might also need to generate a new API_Key on the Media Cloud website if we have exhausted the current one. 

Once you have taken these steps run the code. It will update the story-list excel file in the Media Coverage folder. 

Open google and search "sea level rise" AND "San Francisco Bay" site:sfchronicle.com 

Use tools to select a start date (should be the date the sheet was last updated) and make the end date today 

Add any articles to the Chronicle spreadsheet 

Repeat these steps but with “site:kneedeeptimes.org” (include in same sheet as chronicle data set) 

Once this is complete refresh the data layers (“chronicle” and “Sheet 1”) in PowerBI. Change the filter date to the end date of the last full month of data 

Power BI Analysis: 

Appended the Chronicle data set to the Stories dataset 

Transform Data -> Append queries 

Created a bar chart to show # of Articles published over time 

X axis – “publish_date” 

Y axis - Count of “Id” aka # of articles 

Filtered data so the current month is excluded 

Created a Table showing top websites publishing articles on Sea Level Rise in the bay 

Media_name” aka news outlet and count of “media_name” aka # of articles that that media outlet has published 
