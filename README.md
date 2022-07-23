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
- PROFILE
- PREFERENCES

## HOW TO USE THIS REPO
![Methodology overview](/assets/Diversity.png)
[Work In Progress]