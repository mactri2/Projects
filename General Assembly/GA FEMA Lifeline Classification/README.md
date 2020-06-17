## Problem Statement
New Light Technologies requested that our team to complete project surrounding emergency preparedness and economic analysis. The goal for this project is two fold. Can data available on Yelp be used to:

(1) Categorize businesses in an affected area by FEMA Lifelines
(2) Estimate potential impact of a disaster on the area


## Executive Summary
New Light Technologies (NLT) specializes in enterprise information solutions and products that combine IT ingenuity and industry intelligence to drive high-performance results. To meet customer needs, NLT has developed products and services that meet and exceed the customers needs on both open source and COTS platforms. In addition to developing technologies, NLT also resells a variety of products and services that are positioned to enhance our customers technology needs and experience on their technology investments. NLT is vendor agnostic and always has the customers best interest in recommending solutions that include third-party technologies as a trusted technology implementation partner.


## Seven FEMA Lifelines
In the event of a disaster FEMA has identified seven different lifelines that require attention in an affected area. Those are as follows:

1. Safety and Security
2. Food, Water, and Sheltering
3. Health and Medical
4. Energy (Power and Fuel)
5. Communication
6. Transportation
7. Hazardous Waste

## Notebooks
This repository contains the following notebooks that are best accessed in the order listed:

1. Yelp Fusion API
2. Data Cleaning
3. Power_Grid_Analysis


## Using Yelp to categorize businesses by Lifeline
This is something that can be done using Yelp's API. In our notebook titled "Yelp Fusion API" we demonstrate the necessary code to retrieve business information. To ensure that we were returning relevant businesses we went through each of the 1,766 possible Yelp categories line by line (view them here: https://www.yelp.com/developers/documentation/v3/category_list) and the ones that we felt would return businesses that could serve as one of the lifelines. The relevant categories are as follows:

(1) Police Department, Fire Department
(2) Homeless Shelters, Community Centers, Food Banks, Animal Shelters
(3) Hospitals, Emergency Rooms, Emergency Medicine, Medical Centers
(4) Utilities, Natural Gas Suppliers, Electric Suppliers, Water Suppliers, Fuel Docks, Service Stations
(5) Telecommunications, Print Media, Radio Stations, Television Stations
(6) Airlines, Bus Stations, Ferries, Metro Stations, Public Transportation, Trains, Taxis
(7) Biohazard Cleanup, Hazardous Waste Cleanup
The code in the notebook can be used to return information within those categories for a business in any city, state, or zip code. Some caveats to consider:

Categories can be passed as a parameter all at once. As is shown in the notebook we separated them by lifeline to make it easier to label each business with the appropriate number.
Categories must be entered as a string, as one lower case word, and (if searching for multiple categories at a time) as a list.

*For example when we searched for businesses that would be labeled as lifeline number seven, we did the following - 'categories': ['hazardouswastecleanup', 'biohazardcleanup'].

*The 'radius' parameter can be a maximum of 40,000 meters (25 miles). It is passed as - 'radius': 40000.

*The maximum businesses the API will return in one search is 50. The limit parameter is passed as - 'limit': 50. If there are more than 50 businesses in a set of categories (as was the case in our health/medical and energy lifelines) than the offset parameter needs to be included the next time the code is run so that the second set of 50 businesses gets returned - 'offset': 50. Each step throughout the entire process is further explained within the notebook. We chose the city of Boston, MA to demonstrate how the tool works.

## Beyond Yelp
Regarding the second part of our problem statement - there was a problem using the data available on Yelp to quantify potential disaster impact. Aside from being able to get a count of how many potential lifelines there isn't much else in the way of information.

Map visualizations (both static images used in our presentation and the interactive one used in the accompanying Jupyter Python Notebook) were made possible through the use of Chart Studio's Plotly library and Plotly's graph_objs object with a Scattermapbox.


Still maps containing infrastructure data were made with the MacOS version of QGIS, an open source GIS application, into which various data shapefiles were imported.

The underlying maps were made possible through Mapbox's free tier and its Studio web service, using the monochrome style map.
Data of major infrastructure was obtained as follows:
-   Fixed Microwave Service Transmitters (commonly used as backhaul and backbone links for cellular services) were obtained through the Homeland Infrastructure Foundation Level Data of the ARCGIS.com website here:
ï‚§	https://hifld-geoplatform.opendata.arcgis.com/datasets/microwave-service-towers
-	New England Electrical Transmission Lines, 2013 to 2022, were obtained from Stanford Libraries Digital Repository here:
ï‚§	https://purl.stanford.edu/kk901rf6252
-	Electrical substations within the continental US that are within 20 mines of the coastline were obtained from Data.gov (aggregated by the National Oceanic and Atmospheric Administration, part of the US Department of Commerce), here:
ï‚§	https://catalog.data.gov/dataset/substations
- Additional data was available at [MassGIS](https://docs.digital.mass.gov/dataset/massgis-data-transmission-lines) and the [US Energy Information Agency (EIA)](https://www.eia.gov/maps/layer_info-m.php).

Maps including one diagramming FEMA's disaster risk assessment, were obtained  from the official City of Boston report on Natural Hazard Mitigation plan available at  https://www.cityofboston.gov/

## Issues
The limited data from Yelp can only be collected by city, state, or zip code whereas all of our supplemental data is available only at the county level making us unable to cross reference the data. Our attempts to group counties in a meaningful way also proved to be fruitless.

## Suggestions
If the goal is to have a tool that can categorize businesses by lifeline in a given state, city, or zip code by using Yelp data, that can be done. However if a more tangible metric is desired for estimating impact beyond a count of businesses by lifeline, Yelp would have to make more information available such as:

Revenue
Number of Employees
Specific services provided

## Credit
Credit is given to the previous Data Science Immersives Cohort including [Atlanta](https://github.com/awharmon/FEMA-Lifelines-Categorization-for-Disaster-Response), [Boston](https://github.com/micahluedtke/FEMA_lifelines), and [Chicago](https://github.com/jwasham12/Client-Project) for their guidelines and presentations.
