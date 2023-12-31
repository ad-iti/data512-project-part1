# UW MSDS DATA 512 Project Part 1
#### Investigating the Impact of Wildfire Smoke in Rapid City, South Dakota
Aditi Shrivastava 

## Description
In the first part of the final project for this course, we begin by exploring the prevalence of wildfire smoke in Rapid City, South Dakota via several steps of data acquisition, cleaning, and formatting detailed in ```./code/USGS_data_acquisition.ipnyb```. The resulting final USGS wildfire dataset is too large to store in this repo, but a subset of it is stored as ```./data/final_USGS_data_subset.csv```. The data is primarily sourced from the [Combined wildland fire datasets for the United States and certain territories, 1800s-Present (combined wildland fire polygons)](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) dataset, which was collected and aggregated by the [US Geological Survey](https://www.usgs.gov/). The dataset is relatively well documented, fire polygons are available in ArcGIS and GeoJSON formats. For this exploration, we specifically rely upon the large .JSON formatted file, which can be found in the combined .ZIP file on the website.

Next, we request data from the US Environmental Protection Agency (EPA) Air Quality Service (AQS) [API](https://aqs.epa.gov/aqsweb/documents/data_api.html), which is a historical API that provides data on the Air Quality Index (AQI) statistic. Information on how this statistic is calculate can be found [here](https://www.airnow.gov/sites/default/files/2020-05/aqi-technical-assistance-document-sept2018.pdf). The US EPA was created in the early 1970's. The EPA reports that they only started broad based monitoring with standardized quality assurance procedures in the 1980's. Some [additional information on the Air Quality System can be found in the EPA FAQ](https://www.epa.gov/outdoor-air-quality-data/frequent-questions-about-airdata) on the system.

We pull this data with the intention of comparing the previously computed smoke estimates for Rapid City to the AQI indedices produced by the EPA on a year to year basis. Step by step process for the data requests are found in ```./code/EPA_data_acquisition.ipynb``` and the final EPA data is found in ```./data/final_EPA_data.csv```

We then create a model to find a unique wildfire smoke estimate, a single number to represent the effect and impact of the fire smoke that affects Rapid City every year. While smoke impact should generally be considered the health, tourism, economic or other social problems that result from the smoke, we create the annual estimate of wildfire smoke using the following model:

100*(Square miles burned)^2 / (Distance from Rapid City)

Then, we use this estimate to develop a predictive model based on the fire data and smoke estimate for Rapid City, SD. The model, a polynomial regression of degree 2, is then used to predict smoke estimates for every year for the next 25 years (i.e., 2024-2049), and the resulting fit and the associated confidence interval are both explored. Detailed description and parameters of both the estimate and the predictive model can be found in ```./code/smoke_estimate_viz.ipnyb```. We will further consider other potential social and economic impacts of the wildfire smoke later in Part 2 of this project.

Finally, we use all of the gathered data to illustrate some wildfire trends over time in Rapid City, South Dakota. These are detailed below, and code on how these visualization were produce can be found in ```./code/smoke_estimate_viz.ipynb```. The final outputs and their detailed descriptions can be found in ```./reflection.pdf```.

## Files 

#### data

```USGS_Wildland_Fire_Combined_Dataset.json```
*This dataset is not stored in this repo because it is too large, but is detailed and linked below.*
- As per the USGS website, "These datasets were created by combining 40 different, published wildland fire data sources. Each one of these data sources has a different spatial scale, spatial resolution, and time period for their particular wildland fire dataset. The purpose of these new datasets is to combine these disparate wildfire datasets, using a common set of attributes, into a single set of polygons with a single fire boundary for each fire. This dataset is intended to create a more comprehensive fire dataset than the existing datasets while eliminating duplication of fire polygons and attributes" ([Combined wildland fire datasets](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81)). 

```final_USGS_data.csv```
- This dataset is a filtered and flattened aggregation of the previous .JSON file. We extract only the relevant columns and convert the dataset into a dataframe to be saved as a .CSV. The data is filtered to include only wildfires taking place during or after 1963, and within 1250 miles of Rapid City, South Dakota.

```final_EPA_data.csv```
- We use the EPA AQI API to find monitoring stations near Rapid City, South Dakota, and then extract the average Air Quality Index for each station. The results are then averaged and stored to represent the AQI for each year.
- Note that AQI data is only available for Rapid City during and after the year 1985.

#### code

```USGS_data_acquisition.ipnyb```
- This notebook details all code needed to produce ```data/final_USGS_data.csv```.

```EPA_data_acquisition.ipynb```
- This notebook details all code needed to produce ```data/final_EPA_data.csv```.
- Note that AQI data is only available for Rapid City during and after the year 1985.

```smoke_estimate_viz.ipnyb```
- This notebook creates a unique smoke estimate for each year, and employs a quadratic regression model to predeict the future smoke estimate up to the year 2049. We also perform a brief visual exploration with all our gathered data-- specifically, we produce:
- a histogram showing the number of fires occurring every 50 mile distance from Rapid City
- a time series graph of total acres burned per year for the fires occurring within 1250 miles of Rapid City
- a time series graph containing the fire smoke estimate for Rapid City compared to the AQI estimate

#### reflection.pdf
This file contains snapshots of the produced visualizations, their descriptions, and a reflection on the collaborative aspects of this assignment.

## Special Considerations
- It takes ~1 hour to run all the notebooks in this repo and load all necessary data.
- The EPA only has AQI data available for Rapid City, SD during and after the year 1985.
- The predictive model (quadratic regression) produced in ```./code/smoke_estimate_viz.ipnyb``` is highly uncertain and likely not representative of the next 25 years.
- Fire perimeter estimates are still a work in progress, and likely are not 100% accurate.
