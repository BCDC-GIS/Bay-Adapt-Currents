# Research on Sea Level Rise in the Bay Area
## Data Source Summary
Using [Open Alex](https://openalex.org/works?page=1&filter=default.search%3A%22Sea%20Level%20Rise%22%20AND%20%22San%20Francisco%20Bay%22&view=list,report,api), BCDC staff searched for Articles on "Sea Level Rise" and " San Francisco Bay." Open Alex is an index of over 250M scholarly works from 250k sources. These works are linked to We 90M disambiguated authors and 100k institutions, as well as enriching them with topic information, SDGs, citation counts, and much more. Open Alex is run by [Our Research](https://ourresearch.org/), a nonprofit dedicated to making research open.

## Methodology
Open Alex assigns each article a relevancy score for the topic and works are generated from more to less relevant. BCDC staff performed an API pull of the top 1,000 articles based on the search criteria (Open Alex limits you to 10 API pulls of 100 articles each).  

[Top 1000 most relevant Articles API:](https://api.openalex.org/works?page=1&filter=default.search:%22Sea+Level+Rise%22+AND+%22San+Francisco+Bay%22&per_page=100) 

- API Only loads 100 articles at a time and has a max of ten pages. Loads articles by relevance to the chosen topic. Need to do a seperate API Pull for each page  

**STEP ONE:**

Opened new excel file -> data -> from web -> insert API URL -> right clicked on “list” next to results and selected “drill down” -> right clicked on “list” and selected “To Table” -> Delimiter = None, pressed ok -> expanded column by hitting button next to column1 and selected: 

- Id
- Title
- relevance_score
- Publication_year
- Publication_date
- Language
- Primary_location
- Type
- Type_crossref
- Open_access
- Authorships
- Cited_by_count
- Referenced_works_count

**STEP TWO:** 
- Once expanded, clicked the button next to open_access and selected “is_oa”
- Clicked the button next to Authorship and Expand to New Rows, clicked again and select “author” and “institutions” 
    - clicked authorships.author and selected “display_name"
    - clicked authorship.institutions and expanded to new rows, clicked again and selected “display_name”, “country_code” and “type” 
- Clicked the button next to primary_location and selected “source”
    - Clicked the button next to source and selected “display_name” 

*Note: After this step there will be repeats of articles with more than one author or institution*

**STEP THREE:**

Repeated steps for each subsequent API pull.  To get the next API pull changed “page=1” in the API to page=2, then page =3 ext. Until we reached page = 10. (the limit is 1000) 

*Note: When complete there should be ten sheets in the excel book*

**STEP FOUR**

Searched “append query” and select in excel. -> Chose “three or more tables” -> Selected all tables (except the one already in use) and pressed okay. This created a new table with all of the pages combined. 

**UPDATING DATA**

Data can be updated by refreshing the spreadheets. Right click on any cell in both spreadsheets and Hit Refresh to update the API pulls. 

