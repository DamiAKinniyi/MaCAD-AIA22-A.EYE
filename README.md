<p align="center"><img src='./assets/AEye.gif' width=400 height=400 ></p>

# **A.EYE**

Many cities around the world are fast becoming more and more diverse, and increasingly multicultural;  a mosaic of culture and heritage, blending belief systems, habits, cultures, foods and style from all over the world; making for a rich and vibrant city where difference is celebrated. With increasing diversity, city dwellers will have to negotiate identities and their differences such as language, race, class and many other factors important for self identification, forging connection with city on a personal level, and on the macro scale,diversity representation in formal systems need to capture minority groups for intercultural integration, and inclusivity in cities. A.EYE is a tool that uncovers the multiculturalism of Vienna in the allocative scale, showing diversity and inclusivity in terms of age, gender, ethnicity and religion.


![Methodology overview](/assets/Solutions.png)

This project tackles the problem in two scales. One on hand, it maps the diversity of vienna, visually showing the ethnicity, age,gender and religious diversity of the city in static layers on a map. On the other hand, it provides a users with a tool that allows them find relatable spaces in the city. Designed for residents, tourists, and immigrants, the tool connects users to Points of Interests (POI) based on their profiles and preferences, and generates optimum routes to selected POIs


![Methodology overview](/assets/Methodology.png)


## **DATA COLLECTION, ANALYSIS & METRICS**
The two main sources of data collection are [Vienna Open Gov Data](https://www.data.gv.at/suche/?searchterm=&searchin=data&publisherFilter[]=Stadt+Wien&publisherFilter_sub[]=Stadt+Wien) and [OpenStreetMap(OSM)](https://www.openstreetmap.org/#map=18/6.45722/3.38499). 

- **CITY GRAPH**: We extracted the MultiDi graph of the city from through osmnx library. 

- **DEMOGRAPHICS**: We collected demographic data available from open gov data. While the information is rich and shows varieties in religion, income, age demographics, There were certain generalisations that excluded minority groups. For example, gender was classified as male and female, and ethnicity was reduced to just austrian and foreigners. 

    **Sources**
    - Demographic data: **Vienna Open Gov Data** (see 'How to use this repo' for more info)

- **PUBLIC SPACE DATA (POINTS OF INTEREST - POI)**: Places where people meet and infrastructure serving basic needs are good indicator’s of a city’s multiculturalism. Therefore, we collect data on public and recreational establishments, such As restaurants, playgrounds, and sports & leisure centres. 

    **Sources**
    - Restaurant Metadata: osmnx API (see 'How to use this repo' for detailed description)

- **URBAN IMAGE DATA & ACCESSIBILITY**: Given the navigation component of the project, we needed to extract information relevant to pleasant and inclusive mobility within the city. Urban Image data included tree locations to identify green and shaded streets, urban density, comfort infrastructure - drinking fountains, public restrooms).
For accessibility, we collected data on tactile sidewalks, acoustic signals, sidewalk widths, low-sidewalk points (for wheelchair mobility) and metro-elevator locations. These factors were scored on a continuous scale of 0 to 1.

    **Sources**:
    - Tree locations, comfort infrastructure, accessibility infrastructure: **Vienna Open Gov Data**;
    - Urban density: **Image Segmentation of Street Views**

Our integration of AI was to extract more generic and perceptual forms of data.We analysed some streetview image datasets, segmented them and measured their specific pixel count to measure a certain metric. (see AI section for detailed How-to). Open data may not be available in some locations. In such instances AI and Image segmentation methodology highlighted below becomes useful for data extraction. 

## AI - IMAGE SEGMENTATION FOR DATA COLLECTION 

## MATCHING USERS WITH POINTS OF INTEREST(POI)
To match users with relatable public establishments, the web app takes in two sets of inputs. The first set related to the user's profile include With A.EYE, You can find yourself within Vienna as a route which matching your preferences and diversity of Vienna. It takes only 3 steps. Answer simple questions, set start and end points, and boom, you can enjoy Vienna matched to your preferences
- PROFILE: The first set related to the user's profile includes:
    - Age: Child, Young, Elderly
    - Gender: Male, Female, Others
    - Ethnicity: Afro-Carribean, Asian, South-Asian, Middle-Eastern, Latin-American, European
    - with Kids: Checkbox
    - Special needs: Visual or physical.

- PREFERENCES
    - Formality: Slider input
    - Urban Image: Slider input
    - Urban Density: Slider input

Given these inputs, the webapp outputs 20 POIs closest to the location of the user. On clicking on any of the POIs, the webapp generates a route to the selected POI. 

## HOW TO USE THIS REPO

1. **DATA COLLECTION**: Collect data from open gov sources as API endpoints (in json format). All api endpoints for this project are located in 03.Colab/endpoints.json.

2. **GENERATE CITY GRAPH AND CALCULATE URBAN IMAGE & ACCESSIBILITY**: To generate city graph and metrics for accessibility and urban image, use 03.colab/city-graph_urban-metrics.ipynb
    - To generate city graph, the place name must be geocodable with admnistrative boundary. 
    - Load api endpoints of data for different metrics under urban image. Alternatively, you could download data as json or csv and load into the colab. 

Section 02_Public Image and comfort outputs two geojsons (city_graph.geojson and city_nodes.geojson). city_graph.geojson contains city edges with normalised indices for various urban_image parameters. Save the geojson files into a google drive location (set google drive location as root parameter in city-graph_urban-metrics.ipynb).

Section 03_Accessibility outputs two geojson files (acc_visual_friendly.geojson and acc_wheelchair_friendly.geojson).Save the two files into a google drive location as recommended for Section 02.

3. **PUBLIC SPACE DIVERSITY**: To generate Point of interest diversity data, use 03.colab/poi.ipynb
    - downlaod POIs using osm tags {feature:values} to filter and select various types of public spaces. For this project, we used the following features and values:

        - 
    Refer to [OSM Map features](https://wiki.openstreetmap.org/wiki/Map_features) for a list of accessible features.

    This poi.ipynb file outputs a geojson file(poi.geojson) to be used with 03.colab/poi_analysis.ipynb. poi_analysis.ipynb returns outputs the diversity indices for ethnicity and gender for each municipality. The results for each diversity parameter is returned as a geojson file. Save the poi.geojson file to a google drive location.
    Save all geojson files to 01.Data/static layer folder for use on webapp.

4. MATCH USERS TO POINTS OF INTEREST
To generate matching points of interest, use POI_live_layer.py. Create a url link for poi.geojson and add link as the url location for poi_url in POI_live_layer.py

5. PLOT ROUTE TO SELECTED POINT OF INTEREST
To generate route to selected POI, use ROUTE_live_layer.py. Create url links  for each of the following: city_graph.geojson, city_nodes.geojson, acc_wheelchair_friendly.geojson and acc_visual_friendly.geojson. Replace the links for each corresponding parameter in ROUTE_live_layer.py

![Methodology overview](/assets/Diversity.png)
[Work In Progress]