 
## 1. Title and Author

- Project Title: Flight delay analysis and prediction.
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- Author: Mahesh Reddy Karimolla
- Link to the author's GitHub profile: https://github.com/LW23290
- Link to the author's LinkedIn progile: https://www.linkedin.com/in/mahesh-reddy-karimolla/
- Link to your PowerPoint presentation file
- Link to your  YouTube video 
    
## 2. Background
- Flight delays are a major issue in the aviation sector, causing aggravation for travelers and costing airlines money. Flight delays can happen for a number of causes, such as bad weather, technical problems, airport congestion, and air traffic control constraints.

- In addition to aggravating passengers, flight delays also increase traveler stress since they increase the cost of lodging and meals. The ensuing lack of trust in airlines may also hurt their reputation and lower demand from passengers. Airlines also spend more money on their crew, aircraft repositioning, and more fuel as a result of their efforts to reduce elapsed time.

  

## Research Questions
- Relationship between the average departure and arrival delay times for each airport.
- Distribution of the average delay by distance.
- Average delay by airline, average delay by flight distance, average delay by destination.
- to predict the upcoming delay.

## 3. Data 
- Data sources: The data has been collected from the Kaggle.
- Dataset contains U.S. flight data of the year 2009. The rows of the dataset represent specific flights from that year, while the columns contain extensive information on the flight such as airline, flight date, departure delay, arrival delay, etc.
- The entire dataset contains CSV files for each year, which in total amass to ~800MB. Moreover, each file has approximately 6 million rows per year.

## Data Description
- The dataset contains flight information for a given year, including the month, day, and various attributes related to each flight.
- There are 24 columns in this dataset, with 3 columns of categorical data (OP_CARRIER, ORIGIN, and DEST), 4 columns of integer data (year, month, day, and OP_CARRIER_FL_NUM), and 17 columns of float data.

### Data Set Columns
- Year   year of the flight that departs,    int16
- Month  month of the flight that departs,    int16
- Day    day of the flight that departs,     int16
- OP_CARRIER  name of the flight,    int16
- OP_CARRIER_FL_NUM number of the flight, int16
- ORIGIN  starting location of the flight,   Category
- DEST    destination of the flight, category
- CRS_DEP_TIME   Computer Reservation System departure time,   float16
- DEP_TIME    The actual departure time,    float16
- DEP_DELAY  The delay in the flight departure,   float16
- CRS_ARR_TIME the scheduled arrival time,   float16
- ARR_TIME the actual arrival time,    float16
- ARR_DELAY The delay in the flight arrival,   float16
- CRS_ELAPSED_TIME   in minutes,    float16
- ACTUAL_ELAPSED_TIME in minutes,    float16
- AIR_TIME in minutes,    float16
- DISTANCE in miles,    float16
- CARRIER_DELAY in minutes. Carrier delay is within the control of the air carrier,    float16
- WEATHER_DELAY in  minutes, Weather delay is caused by extreme or hazardous weather conditions that are forecasted or manifest themselves on point of departure, enroute, or on point of arrival.   float16
- NAS_DELAY in minutes, Delay that is within the control of the National Airspace System (NAS) may include: non-extreme weather conditions, airport operations, heavy traffic volume, air traffic control, etc.   float16
- SECURITY_DELAY in minutes, Security delay is caused by evacuation of a terminal or concourse, re-boarding of aircraft because of security breach, inoperative screening equipment and/or long lines in excess of 29 minutes at screening areas.   float16
- LATE_AIRCRAFT_DELAY in minutes, Arrival delay at an airport due to the late arrival of the same aircraft at a previous airport. The ripple effect of an earlier delay at downstream airports is referred to as delay propagation.  float16


- Dep_delay is the target variable in the project.
- Predict the upcoming delay.

## Exploratory Data Analysis

#### Data Loading
- Loaded the data which is in the csv file to the jupyter notebook as a data frame(data).

#### Data cleaing
- know the columns that the present in the data.
- Datatypes of the data.
- checking for the null values present in the data.
- removed the columns that are not required for the analysis and the prediction.
- There are 24 columns in this dataset, with 3 columns of categorical data (OP_CARRIER, ORIGIN, and DEST), 4 columns of integer data (year, month, day, and OP_CARRIER_FL_NUM), and 17 columns of float data.
- The float columns include information about the scheduled and actual departure and arrival times, departure and arrival delays, whether the flight was cancelled or diverted, the elapsed time, air time, and distance of the flight, and the reasons for any delays, if applicable.

#### Expoloratory Data Analysis
- Imported  the spark session.
- Read the csv file into RDD.
- Conver the RDD into Data frame.

#### Cause for the airline delay
![Unknown](https://github.com/DATA-606-2023-FALL-THURSDAY/Karimolla_MaheshReddy/assets/143559004/103db5f1-e4b9-4783-9634-0c6ba5c8d1d9)
-  The chart has four bars, each representing one of the four delay causes: Carrier Delay, National Airspace System (NAS) Delay, Security Delay, and Late Aircraft Delay. The height of each bar represents the percentage of total delay time caused by that particular delay reason.indicates the relative contribution of each delay cause to the total delay time


#### Average Delay by Airline
![Unknown-2](https://github.com/DATA-606-2023-FALL-THURSDAY/Karimolla_MaheshReddy/assets/143559004/cb78f781-c1ab-4594-89ef-262e307ac495)

- we can see the output is a bar chart which is  showing the average departure and arrival delay for 23 airlines i.e from our data. The visualization compares the average delay times for each airline and highlights which airlines have higher average delays for both departure and arrival times in a clear manner.

#### Total Number of flights per Airline
![Unknown-3](https://github.com/DATA-606-2023-FALL-THURSDAY/Karimolla_MaheshReddy/assets/143559004/5ea8f319-2775-4ea6-933d-20b450202070)

- The output is a line graph showing the number of flights. The visualization highlights  that which airlines operate the most flights and how they compare to one another
The graph displays each airline's name on the x-axis and the number of flights on the y-axis, where the data points are connected with a dotted line.WN has airlines operate most flights compared to others.

#### Busiest airports by number of flights
![Unknown-4](https://github.com/DATA-606-2023-FALL-THURSDAY/Karimolla_MaheshReddy/assets/143559004/3614dfd9-b781-467e-9578-e3ba3dfd49a9)

- this visualization is a pie chart showing the distribution of the number of flights operated by the 20 busiest airports. The visualization indicates the relative proportion of flights handled by each airport. The graph displays each airport's name as a label and the percentage of total flights. The size of the slice represents the relative contribution of each airport to the total number of flights.The larger the slice, the more flights departed from that airport. It also displays the percentage of flights as well as the name of the airport.this makes easy to compare the relative popularity of different airports and identify the top contributors to the total number of flights in the dataset.

#### Average Delay by origin
![Unknown-5](https://github.com/DATA-606-2023-FALL-THURSDAY/Karimolla_MaheshReddy/assets/143559004/87f0d6ec-ffc6-4174-b6e0-8ff1314ca0e2)

- The visualization looks like scatter plot of the average delay by origin airport, with different colors representing departure and arrival delays. The x-axis represents the average departure delay in minutes, and the y-axis represents the average arrival delay in minutes. The plot shows the relationship between these two variables for each origin airport, and the color of each point represents whether it is an arrival delay in blue color and departure delay in red color. It is useful for identifying airports that tend to have longer delays for either arrivals or departures, as well as for seeing the overall relationship between departure and arrival delays.

#### Average Delay by Destination
![Unknown-6](https://github.com/DATA-606-2023-FALL-THURSDAY/Karimolla_MaheshReddy/assets/143559004/438ce3be-62c9-4acb-9af5-01214e41c11b)

- here we can see the output shows  relationship between the average departure and arrival delay , with each point representing an airport. The points are color-coded to differentiate between arrival and departure delays.
there is a strong positive correlation between average departure and arrival delay times for most airports. This indicates that airports with longer departure delays also tend to have longer arrival delays. and it also shows that there are some airports with very high average delays, particularly in the top right corner of the plot where both departure and arrival delays are high. Overall, we can say that the visualization provides a useful way to compare delay times between different airports.

#### Average Delay by Flight distance
![Unknown-7](https://github.com/DATA-606-2023-FALL-THURSDAY/Karimolla_MaheshReddy/assets/143559004/993342ac-e9e0-46fc-b98c-6767c113203a)

- The visualization is a kernel density plot that shows the distribution of the average delay times by distance. The x-axis represents the average delay time in minutes and the y-axis represents the density of flights for a particular average delay time. The red curve represents the average departure delay and the green curve represents the average arrival delay.

### Machine Learning

- Features: ’DEST’, CRS_DEP_TIME, DISTANCE, CARRIER DELAY, WEATHER_DELAY, NAS_DELAY, SECURITY_DELAY.
- Departure Delay(Dep_Delay) is the target variable.
- Performed a linear regression model.
- Root Mean Squared Error (RMSE) : 0.0040336353
- R-Squared (R2) Score : 0.99999998378

- RMSE value is approximately 0.0047. so the average, the model's predictions have an error of around 0.0047 units when predicting flight delay. this model's predictions have very low average error, while the high R2 score indicates that the model can explain a significant amount of the variance in the flight delay. These evaluation metrics indicate that the linear regression model performs exceptionally well in predicting flight delays

### Findings from Analysis
- We found Percentage of total delay time. Four delay causes - carrier delay, NAS delay, security delay, and late aircraft delay
- The average departure and arrival delay. United Airlines (UA) has the highest average departure delay time, while Frontier Airlines (F9) has the highest average arrival delay time. On the other hand, Hawaiian Airlines (HA) has the lowest average delay time for both departure and arrival
- Comparison of the number of flights operated by each airline.
- The distribution of the number of flights operated by the 20 busiest airports.
-Positive correlation between the average departure delay and arrival delay for each origin airport
- Relationship between the average departure and arrival delay times for each airport.
- Distribution of the average delay times by distance.
- The highest number of delayed departures is Atlanta (ATL), followed by Chicago O'Hare (ORD), and Dallas/Fort Worth (DFW).
- Top 5 airports with the highest proportion of delayed arrivals are ATL, ORD, DFW, LAX, and DEN.
- Implemented the machine learning model to predict the upcoming delay.
