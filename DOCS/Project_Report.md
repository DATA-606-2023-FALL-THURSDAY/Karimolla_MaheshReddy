 
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
- Year   year of the flight that departs
- Month  month of the flight that departs
- Day    day of the flight that departs
- OP_CARRIER  name of the flight
- OP_CARRIER_FL_NUM number of the flight
- ORIGIN  starting location of the flight
- DEST    destination of the flight
- CRS_DEP_TIME   Computer Reservation System departure time
- DEP_TIME    The actual departure time
- DEP_DELAY  The delay in the flight departure
- CRS_ARR_TIME the scheduled arrival time
- ARR_TIME the actual arrival time
- ARR_DELAY The delay in the flight arrival
- CRS_ELAPSED_TIME   in minutes
- ACTUAL_ELAPSED_TIME in minutes
- AIR_TIME in minutes
- DISTANCE in miles
- CARRIER_DELAY in minutes. Carrier delay is within the control of the air carrier.
- WEATHER_DELAY in  minutes. 
- NAS_DELAY
- SECURITY_DELAY
- LATE_AIRCRAFT_DELAY
- 
 

- Dep_delay is the target variable in the project.
- Predict the upcoming delay.

   
