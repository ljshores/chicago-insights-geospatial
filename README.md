# Chicago Geospatial Analysis



## Intro/Overview

This is an analytical project aimed at utilizing spatial data to gain insights about the different areas in Chicago in terms of demographics, businesses, transportation, crime, and rents, and how these factors interact. A dashboard was built as an end product for users to dig into areas and features of interest and it was packaged as a tool on a site for public use using Dash and served using Render.

You can look at the app here: [WindyCity Insights App](https://chicago-insights-app.onrender.com/)

### Key Takeaway: 

Chicago is a city that has some very stark trends in how race, wealth, access to businesses and even transportation play out spatially. You can glean a lot about a person based on where they live in the city.

## Problem Statement

Where we live is one of the most important factors in our quality of life. And different people prioritize different things in the spaces that they occupy. Chicago is the third largest city in the US, and in my personal opinion one of the best. But it faces many challenges and is often called one of the most segregated cities in the country. This analysis digs into features of interest at a spatial level so that we can gain some insights into the different areas of the city.

## Objective: 

Gain valuable spatial insights about the city of Chicago. Create a tool that would help a user better understand Chicago neighborhoods, and could potentially help a user understand where they would want to and could afford to live in the city.

## Data

Information about a team’s demographics, relationship, background, and performance in the race was scraped from Wikipedia and a Fandom site.  NLP methods were used to experiment with the use of occupation as a variable in the model.

- Boundaries - Community Areas and Zip https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6 https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-ZIP-Codes/gdcf-axmw
- National Historical GIS (NHGIS) [https://www.nhgis.org](https://www.nhgis.org/) Block Group and tract level info for: Race, edu attainment, median hh income, and employment status. A census block group is the smallest geographic area for which the Bureau of the Census collects and tabulates decennial census data. 2021 American Community Survey: 5-Year Data (2017-2021)
- Business Licenses https://data.cityofchicago.org/Community-Economic-Development/Business-Licenses-Current-Active/uupf-x98q
- Crime https://data.cityofchicago.org/Public-Safety/Crimes-2020/qzdf-xmn8
- L Stops https://data.cityofchicago.org/Transportation/CTA-System-Information-List-of-L-Stops/8pix-ypme
- Rental listings were scraped from realtor.com

## Navigating this Repo

01_Geospatial_Analysis_Exploring_Chicago.ipynb - more formal analysis of different aspects of the city. This notebook is used in conjunction with powerpoint presentation

01a_Business_License_Classification.ipynb - separate work done to format business license categories. WIP

Exploring_Chicago_Spatial_Data.ipynb - precursor to more polished analysis and work that contributed to building tool

Realtor_Listing_Scraper-For_PROD-GoldForNewProj.ipynb - this notebook is a scraper for getting rental data to be used in the app/analysis


## Methodology

Geospatial analysis problem. Started with a base map of Chicago and its community areas and began to layer in other map boundaries such as block groups from other datasets. Then I used geo data such as lat longs to layer in different features such as crimes, business locations, and L Stops to build a grand dataset.

Data cleaning/manipulation was necessary to make more succinct categories for some features for example for businesses and crimes.

Utilized geopandas for layering/merging the data and matplotlib for plotting. I used plotly for maps on the dashboard application.

## Results/Conclusion

There are some clear trends in the data:

- Strong positive correlation between an area’s proportion of white residents and income levels.
- Block groups that are majority black tend to be overwhelmingly black, whereas majority white block groups tend to have more diversity (non-black) comparatively
- Wealth is concentrated on the north side and in downtown areas. Crimes such as theft tend to be high in these areas.
- Low-income areas are concentrated on the south and west sides and these areas see more violent crimes
- Businesses such as as bars and restaurants are more concentrated on the north and central areas of the city
- Rent prices follow race and income trends.

### Interpretation:

With such clear trends in the data, it confirms that Chicago is indeed a very siloed/segregated city when it comes to demographics and economic landscape. A tool like this could be very helpful to digging deeper on a more granular level so that users can assess/explore areas of the city that may be suited to their needs and priorities.

### Next Steps/Improvements:

Create a live data pipeline that constantly updates rental listings, so that the dashboard is always up-to-date
