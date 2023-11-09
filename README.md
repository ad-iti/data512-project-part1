# UW MSDS DATA 512 Project Part 1
#### Investigating the Impact of Wildfire Smoke in Rapid City, Nevada
Aditi Shrivastava 

## Description
In the first part of the final project for this course, we begin by exploring the prevalence of wildfire smoke in Rapid City, Nevada via several steps of data acquisition, cleaning, and formatting detailed in *./code/data_acquisition.ipnyb*. The data is primarily sourced from the [Combined wildland fire datasets for the United States and certain territories, 1800s-Present (combined wildland fire polygons)](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) dataset, which was collected and aggregated by the [US Geological Survey](https://www.usgs.gov/). The dataset is relatively well documented, fire polygons are available in ArcGIS and GeoJSON formats. For this exploration, we specifically rely upon the large .JSON formatted file, which can be found in the combined .ZIP file.

As per the USGS website, "These datasets were created by combining 40 different, published wildland fire data sources. Each one of these data sources has a different spatial scale, spatial resolution, and time period for their particular wildland fire dataset. The purpose of these new datasets is to combine these disparate wildfire datasets, using a common set of attributes, into a single set of polygons with a single fire boundary for each fire. This dataset is intended to create a more comprehensive fire dataset than the existing datasets while eliminating duplication of fire polygons and attributes" ([Combined wildland fire datasets](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81)). The raw .JSON data is stored in *./raw_data/USGS_Wildland_Fire_Combined_Dataset.json*.

We then create a model to find a unique wildfire smoke estimate, a single number to represent the effect and impact of the fire smoke that affects Rapid City every year. While smoke impact should generally be considered the health, tourism, economic or other social problems that result from the smoke, we create the annual estimate of wildfire smoke using the following model:

modelfhdskfjh fkjh kfjhe

Then, we use this estimate to develop a predictive model based on the fire data and smoke estimate for Rapid City, NV. The model predicts smoke estimates for every year for the next 25 years (i.e., 2024-2049). Detailed description and parameters of this model can be found in *./code/smoke_estimate.ipnyb*. We will further consider other potential social and economic impacts of the wildfire smoke later in Part 2 of this project.

Next, we request data from the US Environmental Protection Agency (EPA) Air Quality Service (AQS) [API](https://aqs.epa.gov/aqsweb/documents/data_api.html), which is a historical API that provides data on the Air Quality Index (AQI) statistic. Information on how this statistic is calculate can be found [here](https://www.airnow.gov/sites/default/files/2020-05/aqi-technical-assistance-document-sept2018.pdf). The US EPA was created in the early 1970's. The EPA reports that they only started broad based monitoring with standardized quality assurance procedures in the 1980's. Some [additional information on the Air Quality System can be found in the EPA FAQ](https://www.epa.gov/outdoor-air-quality-data/frequent-questions-about-airdata) on the system.

We pull this data with the intention of comparing the previously computed smoke estimates for Rapid City to the AQI indedices produced by the EPA on a year to year basis. Step by step process for the data requests are found in *./EPA_data_acquisition.ipynb*. 

Finally, we use all of the gathered data to illustrate some wildfire trends over time in Rapid City, Nevada. Specifically, we produce:
- a histogram showing the number of fires occurring every 50 mile distance from Rapid City
- a time series graph of total acres burned per year for the fires occurring within 1250 miles of Rapid City
- a time series graph containing the fire smoke estimate for Rapid City compared to the AQI estimate

These outputs and their detailed descriptions can be found in *./reflection.pdf*.

## Files 

#### raw_data

```USGS_Wildland_Fire_Combined_Dataset.json```
- fnekwfbekwjbfkjwebf

#### intermediate_data

*USGS_Wildland_Fire_Combined_Dataset_Features.csv*
- fhdksjfhkdjshfkjehfew

#### final_data

*final_data.csv*
- fnwkjfbewjkbfkjew

#### code

*data_acquisition.ipnyb*
- dksjhdwe

*smoke_estimate.ipnyb*
- dkjdfhjewh

*EPA_data_acquisition.ipynb*
- dkjhfjkweh

*data_visualization.ipynb*
- dkdjhf dewkjd

#### reflection.pdf
fkdsjhfejdf



