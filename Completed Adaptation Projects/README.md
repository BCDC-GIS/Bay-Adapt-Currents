# Completed Adaptation Projects
## Data Source Summary
Data for this metric comes form the [Shoreline Adaptation Project Map (SAPMap)](https://www.ecoatlas.org/regions/group/303) SAPMap was created in 2021 to track adaptation project progress in the Bay and support a living network of community-based partners poised to lead adaptation planning, construction, and monitoring. Data is input by project proponents and maintained by SFEI and BCDC Staff.
## Methodology
Once the SAPMAP Data was downloaded, the spreadsheet was edited to add some additional information for analysis. 

### ADDING SOCIAL AND CONTAMINATION VULNERABILITY DATA
- Opened Habitat Projects Data Spreadsheet in ArcGIS and displayed xy data
- Opened Social and Contamination Vulnerability (2023) from ARCGIS Online
- Joined datasets so vulnerability data appears in the habitat projects spreadsheet
- Useed Table to excel to redownload the table with the new information
- Performed additional desktop research to fill in any projects that did not include XY data, if still unsure of the location used “Unknown” 

**Update Methods:** *upon redownloading SAPMAP Data to include new projects*
- Performed VLOOKUP to pull in info from old datasheet based on the “projectid”
- Filtered data so “sitestatus” is only showing "completed", and "construction completed" projects
- <span style="color:red"> Highlight any Projects that return “#N/A” they are likely new and should be excluded from VLOOKUPs that modify existing columns **(projectid)** </span>
- For any new projects with X,Y coordinates, we copy and pasted the coordinates into the search function on the webmap: [Community Vulnerability + CBO Directory Map](https://bcdc.maps.arcgis.com/apps/webappviewer/index.html?id=526ca82e85eb403489de768498f605f3)
- Projects were labeled as "social", "contamination", "social and contamination", or "low" based on where the X,Y coordinates for the project were located. This data was manually added into the spreadsheet.

*Please note that this analysis is based on point (X, Y) data representing the center of each project. As such, project labeling may not fully capture all vulnerabilities present across the entire project area. Results should be interpreted with this limitation in mind.*

### ADDING FUNDING GROUP INFORMATION
The SAPMAP Data provides detailed information on the funder name and funder agency. However, this is a level of detail deeper than we wanted the map to display. For these reasons we created an additional column called "Funder Group" and classified Funding Sources into five Categories based on the Funder name and funder Agency: “Private”, “Federal”, “State”, “Local”, and “Unknown”. If unsure what a funding source should be categorized as, performed desktop research to determine funding group category.

**Update Methods:**
- Performed VLOOKUP to pull in info from old datasheet based on the “fundingid” 
- Added “funding Group” column back into the new dataset
- Added funding group information for any new projects

### ADDING "FIRST INSTANCE" COLUMN
This is necessary to confirm that we are not double counting project acerage. The “Include Habitat” column attempts to do this, but is inconsistently used by ecoatals project adminstrators. 
- This Column checks if matching pairs of “activityid” and “habitatacres” have occurred previously in the Dataset. If they have it assigns a 0, if it is the first instance it assigns a 1. Only rows that have a 1 are included in the metric to remove double counting of acreage.  
  - FORMULA: =IF(COUNTIFS(T$2:$T2, T2, U$2:$U2, U2)=1,1,0). *Column T Should be “activity ID” and U should be “habitatacres” - if columns change adjust formula*
- when data set is updated must re-add this column and include the formula (starting in row 2)

### ADDING PLACEHOLDER PROJECTS
The "project end date" is used to create the Acres of Adaptation Over Time (cumulative) graph in the dashboard. However, if a year has no projects, it appears as a gap in the data set rather than carrying over the cumulative total from the previous dataset. To fix this we added placeholder projects for the missing years.
- Needs to include 1 in the "first instance" or it will be filtered out
- must copy and paste from previous sheet when the dtaa is updated

When updating data, final step is to archive old sheet and change new sheet name to match what is saved in Power BI (ecoatlas_habitatprojects_Oct)
