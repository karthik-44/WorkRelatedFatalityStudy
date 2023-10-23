# WorkRelatedFatalityStudy
This repo contains the files for the project -- [Work Related Fatality Study.](https://hicounselor.com/projects/work-related-fatality-study-an-in-depth-analysis-using-python-and-mysql)  
This project is conducted by [**HiCounselor**](https://hicounselor.com).  
This project aims at cleaning the dataset, analyzing the given dataset and mine informational insights using Python and MySQL.  

On a high level, the following are the steps performed:  

- Read the raw data from the .csv file provided.
- Clean the data as per our analysis requirement.
- Create a clean dataset which is ready for our analysis.
- Install and configure MySQL Database server.(Optional - while working on hicounselor's sandbox machine it is not required)
- Create the database(schema), user and import the cleaned dataset as a table.(Optional - while working on hicounselor's sandbox machine it is not required)
- Perform the analysis. (Done in two methods - using pandas dataframes, SQL queries)

## Module 1

1. Read the data from the fatality.csv file provided.
2. Drop the unwanted columns and clean the dataset as needed for our analysis.
3. Export the data to a file fatalities_cleaned.csv which is the cleaner version.
4. Login to the database using the provided details and import the cleaned version into the database.


## Module 2

### Task 1. What is the number of reported incidents?

There are **14914** reported incidents.  

### Task 2. What is the year to year change for the number of fatal incidents?
The task is to calculates the year-to-year percentage changes(Round it of to nearest whole number) in the number of fatalities for each incident year, excluding the year 2022.



| incident_year | n_fatalities | previous_year | year_to_year |
|--------------|-------------|---------------|--------------|
|     2009     |     515     |     NaN       |     NaN      |
|     2010     |    1110     |     515.0     |     116.0    |
|     2011     |    1185     |     1110.0    |      7.0     |
|     2012     |     997     |     1185.0    |     -16.0    |
|     2013     |    1189     |     997.0     |     19.0     |
|     2014     |    1345     |     1189.0    |     13.0     |
|     2015     |    1148     |     1345.0    |    -15.0     |
|     2016     |    1106     |     1148.0    |     -4.0     |
|     2017     |    1541     |     1106.0    |     39.0     |
|     2018     |    1260     |     1541.0    |    -18.0     |
|     2019     |    1376     |     1260.0    |      9.0     |
|     2020     |    1119     |     1376.0    |    -19.0     |
|     2021     |     950     |     1119.0    |    -15.0     |


### Task 3. What is the number of fatalities that received a citation?
The task is to calculates the total number of fatalities that received a citation.

| citation  | n_fatalities |
|----------|-------------|
| unknown  |     8886    |
|    yes   |     3345    |
|    no    |     2683    |


### Task 4. What day of the week has the most fatalities and what is the overall percentage?
The task is to calculates day of the week that reported more number of fatalities and percentage(Rounds the percentage to two decimal places).

| day_of_week | n_fatalities | percentage |
|-------------|--------------|------------|
|   tuesday   |     2728     |   18.29    |
|  wednesday  |     2706     |   18.14    |
|    monday   |     2626     |   17.61    |
|   thursday  |     2612     |   17.51    |
|    friday   |     2335     |   15.66    |
|  saturday   |     1177     |   7.89     |
|   sunday    |     730      |   4.89     |


### Task 5. What is the number of fatalities involving welding?
The task is to calculates the total number of fatalities during welding.

There are **79** fatalities involving welding.


### Task 6. Select the last 5 from the previous query
The task is to calculates the last 5 fatalities during welding.

|   id   | incident_date | day_of_week |    city    |  state  |               description               |  plan  | citation | incident_year |
|-------|--------------|------------|------------|---------|----------------------------------------|-------|----------|---------------|
|  9587 |  2021-04-14  |  wednesday | cleveland  |  ohio   | Worker electrocuted by portable welding machine.  | federal |   yes    |      2021     |
|  9812 |  2021-01-30  |  saturday  |  mission   |  texas  | Worker died in welding explosion.       | federal |   yes    |      2021     |
|  9999 |  2020-12-10  |  thursday  |   urbana   |  ohio   | Worker fatally crushed by seam welder. | federal |   yes    |      2020     |
| 10678 |  2020-05-24  |   sunday   |  dallas    |  texas  | Worker electrocuted while welding HVAC pipe. | federal |   no    |      2020     |
| 11743 |  2019-07-08  |   monday   | kingwood   |  texas  | Worker electrocuted while welding air conditioning... | federal |   no    |      2019     |

### Task 7. Select the top 5 states with the most fatal incidents.
The task is to calculates the top 5 states which have most fatal incidents.


|    state   | n_fatalities |
|------------|--------------|
|    texas   |     1758     |
| california |     1352     |
|   florida  |     1021     |
|  new york  |     726      |
|  illinois  |     635      |


### Task 8. What are the top 5 states that had the most workplace fatalities from stabbings?
The task is to calculates the top 5 states which have most fatal incidents happed from stabbing.


|     state     | stabbing_fatalities |
|--------------|----------------------|
|   new york   |          7           |
|  california  |          5           |
|   kentucky   |          5           |
|   illinois   |          3           |
| connecticut  |          2           |


### Task 9. What are the top 10 states that had the most workplace fatalities from shootings?
The task is to calculates the top 10 states which have most fatal incidents happed from shooting.


|    state     | shooting_fatalities |
|-------------|----------------------|
|   indiana   |         28           |
|  california  |         23           |
|    texas    |         21           |
|   new york  |         20           |
|   florida   |         14           |
|   kentucky  |         13           |
|    nevada   |          9           |
|   illinois  |          9           |
|    oregon   |          9           |
|  washington  |          8           |


### Task 10. What is the total number of shooting deaths per year?
The task is to calculates the total number of deaths caused by shooting each year.(In Decreasing order)

| incident_year | shooting_fatalities |
|--------------|----------------------|
|     2021     |          38          |
|     2015     |          28          |
|     2016     |          28          |
|     2020     |          27          |
|     2019     |          24          |
|     2018     |          21          |
|     2013     |          19          |
|     2014     |          18          |
|     2010     |          16          |
|     2017     |          14          |
|     2011     |          13          |
|     2009     |          10          |
|     2012     |           9          |
|     2022     |           2          |



