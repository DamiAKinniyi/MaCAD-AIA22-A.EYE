In this folder, geojson files for static layers are comtained.

## Structure for Static layer

* BIO  
    * &ensp;Age  
        &emsp;Adult  
            &emsp;&ensp;"This layer shows the distribution of adults (20-74) by region."  
            &emsp;&ensp;adult.geojson  
            
        &emsp;Old  
            &emsp;&ensp;"This layer shows the distribution of elderly (75-) by region."  
            &emsp;&ensp;old.geojson  
              
        &emsp;Young  
            &emsp;&ensp;"This layer shows the distribution of youth (0-19) by region."  
            &emsp;&ensp;young.geojson  
              
    * &ensp;Ethnic diversity  
        &emsp;div_ethnic_diversity_index.geojson (Show as geo: "diversity_index" , Attributes: "afro_ratio", "asian_ratio", "mid_east_ratio", "south_asian_ratio", "latinx_ratio", "european_ratio")  
        &emsp;&ensp;"This layer shows diversity of residents as diversity index by region, having attributes for breakdown."  
            &emsp;Afro Carribean  
                &emsp;&ensp;"This layer shows the distribution of Afro Carribean people by region."  
                &emsp;&ensp;div_afro_carribean_heatmap.geojson  
            &emsp;Asian  
                &emsp;&ensp;"This layer shows the distribution of Asian people by region."  
                &emsp;&ensp;div_asian_heatmap.geojson  
            &emsp;Europian  
                &emsp;&ensp;"This layer shows the distribution of European people by region."  
                &emsp;&ensp;div_european_origin_heatmap.geojson  
            &emsp;Latinx  
                &emsp;&ensp;"This layer shows the distribution of Latin and American people by region."  
                &emsp;&ensp;div_latin_american_heatmap.geojson  
            &emsp;Mid_east  
                &emsp;&ensp;"This layer shows the distribution of Middle east people by region."  
                &emsp;&ensp;div_mid_east_heatmap.geojson  
            &emsp;South_asian  
                &emsp;&ensp;"This layer shows the distribution of South asian people by region."  
                &emsp;&ensp;div_south_asian_heatmap.geojson  
            &emsp;LGBTQ  
                &emsp;&ensp;"This layer shows the distribution of LGBTQ people by region."  
                &emsp;&ensp;div_lgbtq_heatmap.geojson  

    * &ensp;Income  
        &emsp;"This layer shows diversity of total income by region, having attributes for that of male and female."  
        &emsp;Income.geojson (Show as geo: "INC_TOT_VALUE" , Attributes: "INC_MAL_VALUE", "INC_FEM_VALUE")  
  
    * &ensp;Population  
        &emsp;"This layer shows diversity of total population by region, having attributes for that of men, women, austrian, foreigner and density."  
        &emsp;Population.geojson (Show as geo: "total_pop" , Attributes: "tot_men", "tot_wom", "tot_aus_ratio", "tot_foreign_ratio", "density")  
        
    * &ensp;Religion  
        &emsp;"This layer shows diversity of religion by region, having attributes for breakdown."  
        &emsp;Religion.geojson (Show as geo: "rom-cath" , Attributes: "evang", "jew", "islam", "ortho", "other", "without")  
        
    
* Urban Diversity  
    * &ensp;Greenness  
        &emsp;"This layer shows diversity of greenness by street, having attributes for name of streets and tree counts."  
        &emsp;trees.geojson (Show as geo: "tree_index" , Attributes: "name", "tree_counts")  
        
    * &ensp;Public Image  
        &emsp;"This layer shows diversity of public image by street, having attributes for name of streets, tree index, public toilets counts, and drinking fountain counts."  
        &emsp;public_image.geojson (Show as geo: "weighted_sum" , Attributes: "name", "tree_index", "public_toilets", "drinking_fountain")  
        
    * &ensp;Urban Density  This layer shows diversity of urban density by street.  
        &emsp;urban_density.geojson (Show as geo: "urban_density")  
        

* Accessibility  
    * &ensp;Physical  
        &emsp;"This layer shows diversity of physical accessibility by street, having attributes for name of streets, elevations, sidewalks, and parkings for disables."  
        &emsp;acc_wheelchair_friendly.geojson (Show as geo: "wheelchair_friendly_index" , Attributes: "name", "elevators", "low_sidewalk", "sidewalk_width", "disabled_parking")  
        
    * &ensp;Visual  
        &emsp;"This layer shows diversity of visual accessibility by street, having attributes for name of streets, acoustic lights, and sidewalks."  
        &emsp;acc_visual_friendly.geojson (Show as geo: "visual_friendly_index" , Attributes: "name", "acoustic_lights", "tactile_sidewalks", "low_sidewalk")  