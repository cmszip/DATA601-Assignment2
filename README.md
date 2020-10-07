![Baltimore Panoramic](https://cdn.pixabay.com/photo/2018/04/21/04/14/panoramic-3337675_960_720.jpg)
# Forecasting in Hindsight: Assessing if Baltimore's 8 Day Forecasted Temperatures are in Line with Historical Norms
<b>by Clifton Saul</b>

## Project Overview & Background

This project's task is to use an API to retrieve temperature forecast data and compare it to historical temperatures for those same days. This topic was chosen from the author's own personal interests in weather and his hometown of Baltimore. It was also chosen because it uses a free API and is therefore easily replicated. There does not appear to be a similar project available on Github currently, based on a some searches conducted via Google. There are, however, a lot of interesting data science projects on Github regarding the weather, from using machine learning to develop weather forecasts, to app development, to tornado prediction, and more.

## Repo Contents & Navigation

* <b>[Data](https://github.com/cmszip/DATA601-Assignment2/tree/main/Data)</b> - Folder containing datasets used in this project.
  * <b>[Baltimore7DayForecast.csv](https://github.com/cmszip/DATA601-Assignment2/tree/main/Data)</b> - dataset of Baltimore's forecasted temperatures initially retrieved from OpenWeather API. See [Notebook 1](https://github.com/cmszip/DATA601-Assignment2/blob/main/Notebooks/Notebook%201%20-%20Weather%20Data%20Acquisition%20%26%20Cleaning.ipynb) for more details on using this API.
  * <b>[USW00093721.csv](https://github.com/cmszip/DATA601-Assignment2/blob/main/Data/USW00093721.csv)</b> - dataset of temperature and precipitation readings from the US Weather Station in Baltimore. Taken from Carnegie Mellon University at [this webpage](https://kilthub.cmu.edu/articles/dataset/Compiled_daily_temperature_and_precipitation_data_for_the_U_S_cities/7890488?file=20881932).
  * <b>[CombinedWeather.csv](https://github.com/cmszip/DATA601-Assignment2/blob/main/Data/CombinedWeather.csv)</b> - cleaned dataset formed from the merging of the two previously mentioned datasets.
* <b>[Images](https://github.com/cmszip/DATA601-Assignment2/tree/main/Images)</b> - Folder containing images used in this project.
* <b>[Notebooks](https://github.com/cmszip/DATA601-Assignment2/tree/main/Notebooks)</b> - Folder containing the Jupyter notebooks used in this project.
  * <b>[Notebook 1 - Weather Data Acquisition & Cleaning](https://github.com/cmszip/DATA601-Assignment2/blob/main/Notebooks/Notebook%201%20-%20Weather%20Data%20Acquisition%20%26%20Cleaning.ipynb)</b> - Jupyter notebook where OpenWeather API was called to retrieve data, and datasets were cleaned in preparation for analysis. Code to use API and save the data retrieved can be found in the second codeblock. 
  * <b>[Notebook 2 - Weather Data Analysis](https://github.com/cmszip/DATA601-Assignment2/blob/main/Notebooks/Notebook%202%20-%20Weather%20Data%20Analysis.ipynb)</b> - Jupyter notebook where data analysis is conducted to answer research question.
  * <b>[Notebook 3 - Summary Presentation](https://github.com/cmszip/DATA601-Assignment2/blob/main/Notebooks/Notebook%203%20-%20Summary%20Presentation.ipynb)</b> - Jupyter notebook that provides the data analysis from Notebook 2 without viewing the code. This is meant to provide a cleaner notebook to read from.
* <b>[License](https://github.com/cmszip/DATA601-Assignment2/blob/main/LICENSE)</b> - MIT license and copyright.

## Motivation

Fall is a season of change and transition. But one thing never seems to change: people will talk about the weather. Conversation and jokes abound about the supposed craziness of the weather and temperature changes.
![Image of Maryland Weather](https://i.pinimg.com/originals/c8/bb/06/c8bb061b99aa996672391f44b9bec5a7.jpg)

However, we rarely stop and take a moment to wonder if the weather is actually odd or if it's typical for the given time of year. People should be able to discern if the weather truly is uncommon, and the author wants to provide a useful tool for others to do just that.

## Goals

Given the above motivation, the primary goal of this project is to determine if Baltimore's forecasted temperatures are in line with historical data. If so, it will explain how the forecasted data falls within historical norms. If not, it will explain how the forecasted temperatures differ from historical norms.

A secondary goal is a more personal one. This author hopes to build experience using an API to effectively retrieve data. This project will use the 8 day forecast provided by OpenWeather API and compare it to the historical temperatures taken from Baltimore's US Weather Station for the same area over those same days.


## Data Overview

Data was pulled from two different sources: OpenWeather API and from Carnegie Mellon University's repository of US Weather Station data. 

In order to use OpenWeather's API, you must first create an account [at this page](https://openweathermap.org/api) to receive your personal API key. Accounts vary in price and access, but this project uses data that can be gathered from the free account. The specific API we used was [OpenWeather's One Call API](https://openweathermap.org/api/one-call-api), which pulls forecasted weather data of eight days for a selected latitude and longitude. Because this project is focused on Baltimore's forecast, the values for latitude and longitude were those for Baltimore, MD.

An important note: this project can be replicated, but not for the exact same dates, as this project pulled data on October 3, 2020 to receive a forecast from October 3, 2020 to October 10, 2020. Instead, if you wish to replicate this project, you can use [OpenWeather's One Call API](https://openweathermap.org/api/one-call-api) to pull forecasting data for the week ahead of when you run the code seen in the notebook. From there, you will need to alter the code used to clean the dataset from Carnegie Mellon University. That dataset is taken from [this csv]. The alterations you should make are in the seventh code block of the [data acquisition and cleaning notebook], specifically within the "Pull and Clean Historical Data" section and beneath "# Remove dates outside forecast range". Modify the month(s) and days you wish to focus on or exclude. Once you've done this, you will be able to replicate this project for the time you wish to conduct it.

The dataset from Carnegie Mellon University contains data from the US Weather Station in Baltimore. These include daily weather readings from 1871 to 2018. Because the US Weather Station in Baltimore moved in 1950 from downtown Baltimore to the Baltimore Washington Thurgood Marshall International Airport (BWI), we only used data dating from 1950 and later.

Below is information on each dataset and the packages used in this project:

#### The OpenWeather API 
The original dataset of the 8 day forecast includes:
  * 8 rows
  * 21 columns:
    * Column datatypes:
      * float64: 11
      * int64: 7
      * object: 3
 
 This dataset was altered to include:
  * 8 rows
  * 7 columns
    * Column datatypes:
      * datetime64: 1
      * float64: 3
      * int64: 3
      
 #### US Weather Station Data
 The original csv file of historical weather data from the Baltimore weather station includes:
  * 54,421 rows
  * 5 columns
    * Column datatypes:
      * float64: 3
      * int64: 1
      * object: 1
      
 This dataset was altered to include:
  * 560 rows
  * 7 columns
    * Column datatypes:
      * datetime64: 1
      * float64: 3
      * int64: 3
 
 #### Merged Dataset
 These two datasets were combined and altered to create the following dataset:
  * 568 rows
  * 8 columns
    * Column datatypes:
      * datetime64: 1
      * float64: 3
      * int64: 3
      * object: 1
      
#### Packages
Packages used to retrieve, clean, alter, and analyze the data included:
 * datetime
 * json
 * matplotlib
 * numpy
 * pandas
 * requests
 * seaborn
 
## Summary

The forecasted temperatures for Baltimore, MD, USA for the week dating from October 3, 2020 to October 10, 2020 are common for the time period historically. The average forecasted high temperature is approximately 1.5 degrees Fahrenheit below the average high from 1950 to 2018. However, the average forecasted low temperature is more than 6 degrees Fahrenheit above the the average low from 1950 to 2018. What is most notable is that the temperature is rather stable, as the difference between the forecasted high and low temperatures is only 63.68% of the average historic difference between high and low temperatures. This means that we can expect less temperature change during the upcoming week than is typical. No heavy coats needed yet. 

## Limitations
One of the main limitations of this project regards the dataset. It is only 568 rows. This is due mainly to the small window of time we are exploring (an eight day period). Additionally, while the original dataset from Carnegie Mellon University contains data beginning in 1871, we decided to remove all data from before 1950. The reasoning behind this is that the original US Weather Station for Baltimore was located in downtown Baltimore until 1950, when it was moved to its current location at the airport that is now known as BWI. For consistency of data, the decision to shrink the dataset was made. Further exploration to compare the forecast to dates beginning in the 1870s could be done, however.

## Contributors

Clifton Saul

## [License & copyright](https://github.com/cmszip/DATA601-Assignment2/blob/main/LICENSE) 

© Clifton M Saul Jr.
