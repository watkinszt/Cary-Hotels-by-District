# Cary Hotels by Council District  
### GHY 5818 – Lab 6  
### Author: Zach Watkins  

## Overview  
This project visualizes the distribution and types of hotels across the Town of Cary, North Carolina. By combining point data for hotels with Cary’s council district boundaries, the map highlights how lodging availability and hotel categories vary across different parts of the town.

## Technologies Used  
- **Leaflet.js** – Web mapping library used to build the interactive map  
- **Chroma.js** – ColorBrewer palettes for choropleth and point symbolization  
- **Font Awesome** – Hotel icons for point markers  
- **QGIS** – Spatial analysis and attribute editing  
- **Overpass Turbo** – Extraction of OSM hotel data  
- **GeoJSON** – Data exchange format for both point and polygon layers  

## Data Sources  
- **Town of Cary GIS** – Council district boundaries (`council-districts.geojson`)  
- **OpenStreetMap via Overpass Turbo** – All hotels tagged with `tourism=hotel`  
- **User-generated classification** – Added `HotelType` field to categorize each hotel  

## Methodology  
1. Queried Overpass Turbo for all hotel features in Cary.  
2. Exported the data into QGIS and created a new text field, **HotelType**.  
3. Classified each hotel as **Chain**, **Extended Stay**, or **Independent** based on name/brand.  
4. Loaded Cary council districts into QGIS.  
5. Used **Count Points in Polygon** to generate a **Hotel_Count** field for each district.  
6. Exported cleaned GeoJSON layers to the project’s `assets/` folder.  
7. Built the interactive web map in Leaflet using ColorBrewer’s **Oranges** palette for district shading and Dark2 for hotel colors.

## Reflection (150 words)  
For this lab, I explored how to combine open-source data with municipal GIS boundaries to create an interactive web map. My goal was to examine how hotel density varies across Cary’s council districts. Using Overpass Turbo, I extracted all hotel locations from OpenStreetMap, then brought the dataset into QGIS. I created a custom field called **HotelType** and manually classified every hotel as a chain, extended stay, or independent property. This required paying attention to brand names and local lodging characteristics. For the district layer, I used the **Count Points in Polygon** tool to calculate the number of hotels within each district, which allowed me to build a choropleth visualization. Bringing the processed data into Leaflet gave me experience integrating spatial analysis with web cartography. Overall, the project strengthened my skills in data cleaning, classification, spatial analysis, and presenting GIS results on an interactive map.