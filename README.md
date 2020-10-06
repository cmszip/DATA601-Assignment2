![Baltimore Panoramic](https://cdn.pixabay.com/photo/2018/04/21/04/14/panoramic-3337675_960_720.jpg)
# Forecasting in Hindsight: Assessing if Baltimore's 8 Day Forecasted Temperatures are in Line with Historical Norms
<b>by Clifton Saul</b>

## Repo Contents & Navigation
To be completed

## Motivation

Fall is a season of change and transition. But one thing never seems to change: people will talk about the weather. Conversation and jokes abound about the supposed craziness of the weather and temperature changes.
![Image of Maryland Weather](https://i.pinimg.com/originals/c8/bb/06/c8bb061b99aa996672391f44b9bec5a7.jpg)

However, we rarely stop and take a moment to wonder if the weather is actually odd or if it's typical for the given time of year.

## Goal

Given the above motivation, the goal of this project is to determine if Baltimore's forecasted temperatures are in line with historical data. If so, it will explain how the forecasted data falls within historical norms. If not, it will explain how the forecasted temperatures differ from historical norms. This project will use the 8 day forecast provided by OpenWeather API and compare it to the historical temperatures taken from Baltimore's US Weather Station for the same area over those same days. 

## Data Overview

Data was pulled from two different sources: OpenWeather API and from Carnegie Mellon University's repository of US Weather Station data. Below is information on each dataset, including the finalized one:

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

Using API and historical data to compare Baltimore forecast to historical temperatures for those same days.
