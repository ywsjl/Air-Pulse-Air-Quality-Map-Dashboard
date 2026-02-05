# Air-Pulse-Air-Quality-Map-Dashboard

## Brief Project Description
This project aims to create a delayed, web-based air quality map and dashboard system that displays a short delay of readings from AirGradient’s ambient monitors, using its open data feeds. The platform will include a public-facing map for awareness and institutional dashboards for stakeholders to analyse trends and evaluate interventions. Demonstrating the added value of hyperlocal monitoring and supporting evidence-based decision-making in school environments.
The objectives of this project are:
1.	Create a filter that allows users to select schools and/ or borough to view the devices. 
2.	Implement delayed data integration for its device reading on the map.
3.	Each device will be displayed by a clickable marker displaying its readings and school green initiatives. 
4.	Real-time air quality display with colour-coded indicators.
5.	Monthly summaries of spikes missed by gov data, average deviation and term time trends.
6.	Record spike detections during school drop-off and pick-up windows.
7.	Coordinate term-time awareness. (holidays; seasonal comparison)
8.	Pre- device onboarding
9.	Add boolean flags to the overlay system for green walls, cycle-to-school initiatives, awareness training, additional monitor types, and map must support toggling overlays on/off

## Tools Used for now
Data Handling: Application Programming Interface (API) consumption.
JSON parse historical and real-time data.
Web Application:
Dash is the framework to develop the dashboard & Render is
the hosting platform.
## Challenges & Limitations
The first challenge involved extracting the appropriate dataset from the ONSPD API, which contains postcode centroids for the entire UK. Initially, I attempted to filter the data by drawing custom parameters on their interactive map to create a narrowed dataset for London. However, upon examining the metadata, I discovered this approach failed to capture all London postcode centroids, as my manually drawn boundaries did not accurately match London's geography.

I then attempted to use the complete UK dataset, but this proved impractical as 331,690 datapoints exceeded the processing capacity of both Dash and Render, causing performance issues.

The solution was to create a filter using the original API data within my notebook. I created a query using a list of all Inner London Local Authority District (LAD) codes to extract only the relevant postcode centroids. This approach yielded a manageable dataset while ensuring complete coverage of the target area.

The next challenge involved the interactive functionality on Render. Specifically, the clickable feature was not displaying detailed information such as site_code, site_name, PM2.5, NO2, and colour_code. This issue remains unresolved, but I have identified a potential cause in the code (Figure 5). I suspect the issue stems from the indexing notation [0], which may need to be removed to enable proper data retrieval and display

