# Python API Assignment- Weather Analysis

Overview
------
In this assignment, I was tasked with creating a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, I used the OpenWeatherMap API, CitiPy Python library, and Google Maps API.
### Part 1
I created a set of unique, random latitude and longitude combinations and used the Citipy library to identify the nearest city for each lat/lng combination. Using the OpenWeatherMap API, I made a series of API calls to get the latitude, longitude, maximum temperature, humidity (%), cloudiness (%), and wind speed for each of the cities. Once I had the data for each of my 550 unique cities, I exported it to a csv and used that data for my analyses.
### Part 2
I used the Google Maps API to make a humidity heat map for my cities. Then I narrowed down my list of cities to those that fit certain weather criteria and stored these cities in a dataframe. Using the Google Maps API, I made a series of API calls to collect a list of hotels near these locations. Finally, I added markers for the hotels to my heatmap.

Project Layout
------
### Part 1: **WeatherPy**
* WeatherPy.ipynb
    * Code used to generate lat/lng combinations, make API calls, and gather data for unique cities
* WeatherPy2.ipynb
    * scatter plots/analyses of unique city weather data
* weather_dataframe.csv
    * csv with unique city data generated in WeatherPy, and imported into/used in WeatherPy2
* output_data
    * PNGs of plots

### Part 2: **VacationPy**
* VacationPy.ipynb
    * code for both heatmaps, ideal weather criteria dataframe, and API calls to find hotel locations
* output_data
    * PNGs of heatmaps

WeatherPy Charts
------
## City Scatter Plots

### City Latitude vs. Max Temperature

![lat_temp](https://user-images.githubusercontent.com/69160361/103430774-c357a780-4b84-11eb-8e09-3e6e689c5b2c.png)


The above plot shows city latitudes vs max temperatures (in Fahrenheit) for 10/20/20. The above code plots the latitude values on the x-axis and the max temperatures on the y-axis. This scatter plot shows the relationship between the location of a city and the max temperatures it experiences. This allows us to see if there is a correlation between the two variables. This plot shows that as latitude increases, max temperature decreases.

### City Latitude vs. Humidity

![lat_humid](https://user-images.githubusercontent.com/69160361/103430794-f1d58280-4b84-11eb-8dec-2989276da44e.png)

The above plot shows city latitudes vs humidity (in %) for 10/20/20. The above code plots the latitude values on the x-axis and the humidity % on the y-axis. This scatter plot shows the relationship between the location of a city and the humidity it experiences. This plot shows that latitude and humidity do not have a linear relationship, however most cities regardless of the latitude have a humidity % of above 40%.

### City Latitude vs. Cloudiness

![lat_cloudiness](https://user-images.githubusercontent.com/69160361/103430798-fac65400-4b84-11eb-9efd-6dfcf17746aa.png)

The above plot shows city latitudes vs cloudiness (in %) for 10/20/20. The above code plots the latitude values on the x-axis and the cloudiness % on the y-axis. This scatter plot shows the relationship between the location of a city and the amount of cloudiness it experiences. This plot shows that there is not a linear relationship between latitude and cloudiness. Cities at a latitude of -40 can have cloudiness % ranging from 0 to 100, and the same goes for cities with a latitude of 20, 40, 60, etc. From this plot, you can infer that there is not a correlation between latitude of a city and cloudiness %.

### City Latitude vs. Wind Speed

![lat_windspeed](https://user-images.githubusercontent.com/69160361/103430802-031e8f00-4b85-11eb-893a-526da480c316.png)

The above plot shows city latitudes vs wind speed (in mph) for 10/20/20. The above code plots the latitude values on the x-axis and the wind speed on the y-axis. This scatter plot shows the relationship between the location of a city and the wind speeds. This plot shows that wind speed generally does not exceed 20 mph, regardless of the latitude. This plot does not show a clear linear relationship/correlation between latitude and wind speed.

## Northern vs. Southern Hemisphere- Linear Regressions

### **City Latitude vs. Max Temperature**
#### Northern Hemisphere

![northlat_temp](https://user-images.githubusercontent.com/69160361/103430849-9788f180-4b85-11eb-93de-429c563378c5.png)

The r-value is: -0.86

#### Southern Hemisphere

![southlat_temp](https://user-images.githubusercontent.com/69160361/103430863-a2438680-4b85-11eb-80dd-4cb08421b7da.png)

The r-value is: 0.76

### **City Latitude vs. Humidity**
#### Northern Hemisphere

![northlat_humid](https://user-images.githubusercontent.com/69160361/103430869-aec7df00-4b85-11eb-8f80-5773591d134d.png)

The r-value is: 0.31

#### Southern Hemisphere

![southlat_humid](https://user-images.githubusercontent.com/69160361/103430874-b25b6600-4b85-11eb-8d08-316042aa527e.png)

The r-value is: 0.11

### **City Latitude vs. Cloudiness**
#### Northern Hemisphere

![northlat_cloud](https://user-images.githubusercontent.com/69160361/103430891-c0a98200-4b85-11eb-9173-b445d6ffa507.png)

The r-value is: 0.24

#### Southern Hemisphere

![southlat_cloud](https://user-images.githubusercontent.com/69160361/103430892-c3a47280-4b85-11eb-9739-30502d5e53d4.png)

The r-value is: 0.20

### **City Latitude vs. Wind Speed**
#### Northern Hemisphere

![northlat_wind](https://user-images.githubusercontent.com/69160361/103430897-c7d09000-4b85-11eb-8989-0fbb9e210a2f.png)

The r-value is: 0.01

#### Southern Hemisphere

![southlat_wind](https://user-images.githubusercontent.com/69160361/103430900-cacb8080-4b85-11eb-8ac2-c17a081bd16a.png)

The r-value is: -0.15

### **Observable Trends**

1) The linear regressions for max temp vs latitude show a different relationship depending on the hemisphere. In the northern hemisphere, there is a strong negative correlation (r-value = -0.86) between temperature and latitude, where as the latitude increases the max temperature decreases. In the southern hemisphere, the opposite relationship is observed. There is a strong positive correlation (r-value = 0.75) in the southern hemisphere, where as latitude increases max temperature increases. This shows that weather relationships can be dependent on the location you are looking at. 

2)  The linear regression for humidity % vs latitude shows that in the northern hemisphere, a weak positive correlation (r value = 0.31) exists where as latitude increases, humidity % increases. For the southern hemisphere, no relationship exists between latitude and humidity %(r value = 0.11). This shows that relationships between certain weather elements (in this case, humidity and latitude) may only exist in certain areas. This analysis showed that humidity and latititude do have a relationship/correlate in the northern hemisphere, but in the southern hemisphere this relationship does not exist. 

3)  By comparing the scatter plots with all the city data to the plots when we split the cities by nothern/southern hemisphere, we can see that certain relationships will not be picked up when we look at all of the city latitudes together. Unique relationships exist in each hemisphere, and this shows the value in conducting further, more detailed analyses because these relationships would not have been uncovered if we only examined the latitude data as a whole. 

VacationPy
------

### Humidity Heatmap

![map](https://user-images.githubusercontent.com/69160361/97351395-4db71e80-1857-11eb-8d84-87ba07434172.png)

![map (1)](https://user-images.githubusercontent.com/69160361/97351437-5dcefe00-1857-11eb-8219-44bcff590f56.png)

![map (2)](https://user-images.githubusercontent.com/69160361/97351468-6aebed00-1857-11eb-8763-288793fa9032.png)

![map (3)](https://user-images.githubusercontent.com/69160361/97351496-77704580-1857-11eb-9593-33b77a1736be.png)


### Heatmap with Hotel Markers

![map (4)](https://user-images.githubusercontent.com/69160361/97351537-835c0780-1857-11eb-9969-5b282f079ba6.png)

![map (5)](https://user-images.githubusercontent.com/69160361/97351570-8e169c80-1857-11eb-9384-99c456867dbb.png)

![map (6)](https://user-images.githubusercontent.com/69160361/97351607-9969c800-1857-11eb-81c8-b2bf4d92e538.png)
