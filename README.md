# UW MSDS DATA 512 Project Part 1
#### Investigating the Impact of Wildfire Smoke in Rapid City, Nevada
Aditi Shrivastava 

## Description
In the first part of the final project for this course, we begin by exploring the prevalence of wildfire smoke in Rapid City, Nevada via several steps of data acquisition, cleaning, and formatting detailed in *./code/data_acquisition.ipnyb*. The data is primarily sourced from the [Combined wildland fire datasets for the United States and certain territories, 1800s-Present (combined wildland fire polygons)](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) dataset, which was collected and aggregated by the [US Geological Survey](https://www.usgs.gov/). The dataset is relatively well documented, fire polygons are available in ArcGIS and GeoJSON formats. For this exploration, we specifically rely upon the large .JSON formatted file, which can be found in the combined .ZIP file.

As per the USGS website, "These datasets were created by combining 40 different, published wildland fire data sources. Each one of these data sources has a different spatial scale, spatial resolution, and time period for their particular wildland fire dataset. The purpose of these new datasets is to combine these disparate wildfire datasets, using a common set of attributes, into a single set of polygons with a single fire boundary for each fire. This dataset is intended to create a more comprehensive fire dataset than the existing datasets while eliminating duplication of fire polygons and attributes" ([Combined wildland fire datasets](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81)). The raw .JSON data is stored in *./raw_data/USGS_Wildland_Fire_Combined_Dataset.json*.

We then create a model to find a unique *wildfire smoke esimate*, a single number to represent the effect and impact of the fire smoke that affects Rapid City every year. While smoke impact should generally be considered the health, tourism, economic or other social problems that result from the smoke, we create the annual estimate of wildfire smoke using the following model:

modelfhdskfjh fkjh kfjhe

Detailed description and parameters of this model can be found in *./code/smoke_estimate.ipnyb*. We will further consider other potential social and economic impacts of the wildfire smoke later in Part 2 of this project.

compare to aqi

Finally, I perform an visual analysis of the article coverage of US cities on Wikipedia and how the quality of articles about cities varies among states. The final output of this exploration is a series of tables that show, briefly:
- The states with the greatest and least coverage of cities on Wikipedia compared to their population.
- The states with the highest and lowest proportion of high quality articles about cities.
- A ranking of US geographic regions by articles-per-person and proportion of high quality articles.
