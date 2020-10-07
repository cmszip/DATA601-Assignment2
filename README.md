![Baltimore Panoramic](https://cdn.pixabay.com/photo/2018/04/21/04/14/panoramic-3337675_960_720.jpg)
# Forecasting in Hindsight: Assessing if Baltimore's 8 Day Forecasted Temperatures are in Line with Historical Norms
<b>by Clifton Saul</b>

## Project Overview & Background

This project's task is to use an API to retrieve temperature forecast data and compare it to historical temperatures for those same days. This topic was chosen from the author's own personal interests in weather and his hometown of Baltimore. It was also chosen because it uses a free API and is therefore easily replicated. There does not appear to be a similar project available on Github currently, based on a limited search on Google. There is, however, a lot of interesting data science projects regarding the weather, from using machine learning to develop weather forecasts, to app development, to tornado prediction, and more.

## Repo Contents & Navigation
To be completed

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
 * pandas   * json
 * requests * datetime
 * numpy    * matplotlib
 * seaborn

## Contributors

Clifton Saul

## [License & copyright] 

© Clifton M Saul Jr.
