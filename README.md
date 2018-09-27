# observation-assessment-trainees

This test is designed to demonstrate your backend development skills. 
We are looking for you to demonstrate:

* The ability to write clean, semantic code using a backend language (Java, C++, Python, C#,  etc)
* An understanding of basic programming concepts and object oriented programming 
* The ability to transform input data to produce an output

# Problem

Observations made primarily for the purpose of providing information on the present state of the atmosphere and for weather forecasts are termed synoptic. These observations over the land surface include measurements of a wide range of meteorological elements made at observing stations such as Camborne in Cornwall.

You should write an application that takes the observation data from the input/simple-input.json file and transform this data to produce a simple-output.json file similar to the format below (N.B. The values are just an example): 

```json
{
  "station" : {
    "name" : "Shanghai/Hongqiao",
    "distance" : {
      "km" : 38.76,
      "miles" : 24.08
    },
    "latitude" : 31.2001,
    "longitude" : 121.3333
  },
  "observations" : [ {
    "localTime" : "00:00",
    "localDate" : "2017-02-19",
    "weatherType" : 2,
    "weatherTypeText" : "Partly Cloudy",
    "temperature" : {
      "C" : 9,
      "F" : 48
    },
    "wind" : {
      "windSpeedMph" : 15,
      "windSpeedKph" : 25,
      "windDirection" : "NNE",
      "windDirectionFull" : "North North Easterly",
      "windDirectionAbbreviation" : "NNE"
    },
    "humidityPercent" : 71,
    "pressureMb" : 1027,
    "pressureDirection" : "Falling",
    "visibility" : "Moderate",
    "updateTimestamp" : "2017-02-19T00:00:00+08:00"
  } ]
}
```

The following details will help to generate the output content, you are advised to use this in your application:

* airPressureInHectoPascal is mapped to the pressureMillibars
* airTemperature mapped to the Temperature
* observedUntil is mapped to the date
* distance km/miles is the distance between the station location and the weather forecast location 
* External libraries may be used

* You can calculate the wind direction from below details

| WIND direction | Degree Direction|
| :------------: | :----:          | 
| N              | 348.75 - 11.24  |
| NNE            | 11.25 - 33.74   |
| NE             | 33.75 - 56.24   |
| ENE            | 56.25 - 78.74   |
| E              | 78.75 - 101.24  |
| ESE            | 101.25 - 123.74 |
| SE             | 123.75 - 146.24 |
| SSE            | 146.25 - 168.74 |
| S              | 168.75 - 191.24 |
| SSW            | 191.25 - 213.74 |
| SW             | 213.75 - 236.24 |
| WSW            | 236.25 - 258.74 |
| W              | 258.75 - 281.24 |
| WNW            | 281.25 - 303.74 |
| NW             | 303.75 - 326.24 |
| NNW            | 326.25 - 348.74 |

* You can calculate the weather description and weather type from the below details

| weatherSymbolCode | Description     | WeatherType |
| :------------:    | :----:          | :---: 	  |
| -99               | Not available   | -99		  |
| 200000            | Clear Sky       | 0		  |
| 100000            | Sunny           | 1		  |
| 210000            | Partly Cloudy   | 2		  |
| 110000            | Sunny Intervals | 3		  |
| 300006            | Sandstorm       | 4		  |	
| 300003            | Mist            | 5		  |
| 300004            | Fog             | 6		  |
| 310000			| Light Cloud 	   | 7		  |
| 320000			| Thick Cloud	   | 8		  |


* You can calculate visibility from the below details

| visibility in meter | Description     |
| :---------------:   | :----------:    | 
| 40000 - INT-max     | Excellent       |
| 20000 - 39999       | Very Good       |
| 10000 - 19999       | Good            |
| 4000 - 9999         | Moderate        |
| 1000 - 3999         | Poor            |
| 0 - 999             | Very Poor       |


Create your solution in a clearly marked and sensibly named folder which contains all your source files. 

## Must Have:
* Upload all your source code, input and output files.
* An output file in JSON format produced using the data from the simple-input.json file.
* You MUST not edit the structure of the data in the input JSON file.
 

## Bonus Points:
* Add a README.md
* Your application still works if there are missing/null values in the input json file
* Output has support for another language eg: Welsh
* Output your data to a REST endpoint

