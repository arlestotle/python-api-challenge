# Module 6 - python-api-challenge

### In this challege we used what we have learned about Python requests, APIs, and JSON traversaks to asnwer the fundamental question, " What is the weather like as we approach the equator?" This challege was split into two portions: Weather Py and VacationPy.

## Part 1: WeatherPy
#### In this part we visualized the weather of over 500 cities of varying distances from the equator. Using the citipy python library and the open weather map api we created plots to showcase the relationship between weather variables and latitudes.

1. Latitude vs. Temperature
2. Latitude vs. Humidity
3. Latitude vs. Cloudiness
4. Latitude vs. Wind Speed

#### To fulfill the second requirement, compute the linear regression for each relationship. Separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude). You may find it helpful to define a function in order to create the linear regression plots. Including the regression line, the model's formula, and the r values.

##### Temperature vs. Latitude of Northern Hemisphere
###### Based off the rvalue (-0.856) there appears to be a very strong negative relationship between the maximum temperature and latitude of the northern hemisphere. As the latitude in the northern hemisphere increases (gets further from the equator) the maximum temperature decreases.

##### Temperature vs. Latitude of Southern Hemisphere
###### Based off the rvalue (0.650) there appears to be a moderate positive relationship between the maximum temperature and latitude of the southern hemisphere. As the latitude in the southern hemisphere increases (moves closer to the equator) the maximum temperature slightly increases.

##### Humidity vs. Latitude of Northern Hemisphere
###### Based off the rvalue (0.462) there appears to be a weak positive relationship between the humidity and latitude of the northern hemisphere. As the latitude in the northern hemisphere increases the humidity increases.

##### Humidity vs. Latitude of Southern Hemisphere
###### The points on the plot are very scattered which indicate that there may not be much of a correlation between humidity and latitude. Based off the rvalue (0.214) there appears to be a very weak positive relationship between the humidity and latitude of the southern hemisphere.

##### Latitude vs. Cloudiness of Northern Hemisphere
###### Although looking at the datapoints there does not appear to be a clear linear relationship between the cloudniess and latitude of the northern hemisphere, based off of the rvalue (0.247) there is a weak positive correlation between the two variables. As that latitude increases (gets further from the equator) the cloudiness appears to increase.

##### Latitude vs. Cloudiness of Southern Hemisphere
###### Although looking at the datapoints there does not appear to be a clear linear relationship between the cloudniess and latitude of the southern hemisphere, based off of the r-value (0.243) is a very weak positive correlation between the two varaibles. As that latitude increases (gets closer to the equator) the cloudiness appears to increase.

##### Latitude vs. Wind Speed of Northern Hemisphere
###### Based off of the r-value (-0.049) there appears to be no corrlation between the two variables. As that latitude increases (gets further from the equator) the windspeeds appear to slightly decrease.

##### Latitude vs. Wind Speed of Southern Hemisphere
###### Based off of the r-value (-0.077) there appears to be no correlation or a very very very weak negative correlation between the two varaibles. As that latitude increases (gets closer to the equator) the windspeeds appear to slightly decrease.


## Part 2: VacationPy
#### In this deliverable, you'll use your weather data skills to plan future vacations. Also, you'll use Jupyter notebooks, the geoViews Python library, and the Geoapify API.
##### 
1. We created a map that displays a pint for every city in the dataframe taken from part 1, and the size of the point should be the humbidity of each city. 
2. We narrowed down the dateframe to find your ideal weather condition: maz temo lower than 27 by higher than 21, wind speed less that 4.5 and 0 cloudiness. 
    - The city dataframe contained 576 cities to start and after narrowing down the data we were only left with 3 cities (yanchep, talcahuano, and santiago de cao).
3. Created a new dataframe called hotel_df to score the city, country, coordinates (lat and lng), and humidity. 
4. For each city, use the Geoapify API to find the first hotel located within 10,000 meters of your coordinates. 
    - Starting hotel search
        yanchep - nearest hotel: Yanchep Inn
        talcahuano - nearest hotel: Club Recreativo Armada de Chile
        santiago de cao - nearest hotel: Hostal El Encanto
5. Add the hotel name and the country as additional information in the hover message for each city on the map. 

### Outside Help
#### For this assignment, I used outside sources such as Stack Overflow, ChatGPT, Classmates.
##### It is very important to make sure you do not push your api keys!!!
    Adding config.py file.
    api_keys.py
##### It is importnat to note that the city data that you generate is based on random coordinates and different query times, so your outputs will not be an exact match to the provided starter notebook. The last time the code was run ws on 2/08/2024. 
#### From ChatGPT: Add datetime dependency to create date format for graph title (Y-M-D)
        date = datetime.now().strftime("%Y-%m-%d")
        plt.title(f'title of graph ({date})')
#### From ChatGPT: Define a function to create Linear Regression plots
    x_value = <desired x axis>
    y_value = <desired y axis>
    slope = linregress(x_value, y_value) -> This line calculates the slope of the linear regression line using the linregress function, which returns a tuple containing the slope, intercept, correlation coefficient (r-value), p-value, and standard error of the slope.
    (slope, intercept, r_value, pvalue, stderr) = linregress(x_value, y_value) -> This line unpacks the tuple returned by linregress into separate variables for the slope, intercept, r-value, p-value, and standard error.
    y_pred = slope * x_value + intercept ->  This line calculates the predicted y-values (y_pred) based on the linear regression equation: y = mx + b, where m is the slope and b is the intercept.
    linear_regression_eq = "y = " + str(round(slope,2)) + "x + " + str(round(intercept,2)) -> This line constructs a string representing the linear regression equation using the calculated slope and intercept, rounded to two decimal places.


