# Sutton_CUSP-GX6006_TermProject
Nate's Term Project for GUSP-GX 6006 Data Visualization

This GitHub project is the culmination of my work on my Term Project for my Data Visualization class (hi Professor James). This project relies entirely on open data for its analysis, making it possible for other users to emulate on their own computers. 

The data for this project includes
* [NYC Open Data City Bench Locations](https://data.cityofnewyork.us/Transportation/City-Bench-Locations/kuxa-tauh)
* [NYC Community District Boundaries](https://www1.nyc.gov/site/planning/data-maps/open-data/districts-download-metadata.page)
* [NYC Borough Boundaries](https://data.cityofnewyork.us/City-Government/Borough-Boundaries/tqmj-j8zm)
* [MTA NYCT Bus Routes](http://web.mta.info/developers/developer-data-terms.html#data)
* [NYC American Community Survey (ACS) Demographic Data](https://www1.nyc.gov/site/planning/planning-level/nyc-population/american-community-survey.page.page)

Interactive maps can be viewed [here](http://ns4117.shinyapps.io/Sutton_CUSP-GX6006_TermProject?_ga=2.56203112.2117046887.1651371054-1215810372.1651371054)

Steps required for data *before* the analysis: 
* Read the City Bench data from the NYC Socrata Open Data API (SODA) (already includes columns with the geometry (lat/long))
* Convert Bench data to shapefile in QGIS (using this geometry information)
* Download the Community District boundaries (already provided in a shapefile)
* Download the Borough boundaries (already in a shapefile)
* Download the MTA NYCT Bus Routes
  * Each borough has its own `gtfs` folder, which contains a `shapes.txt` file
  * Load each `shapes.txt` file into QGIS and combine into a file for the 5 boroughs
  * Convert the combined `shapes` file into maps of the routes by using the "Points to Path" tool
    * (Optional) Clip routes that go over water or cross between boroughs oddly
  * Save the routes shapefile and use in R
*  Download the demographics data from the URL (data is by community district)

After downloading and converting the data as necessary, the remainder of the steps required to produce the visualizations are shown in the R Notebook. 