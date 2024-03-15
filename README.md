# Tableau Chicago Relocation Guide (SQL, Python, Tableau) - Dec 2023
![image](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/assets/163356063/66039df7-d7b8-4b55-bb2b-731720b09f82)  
# Link to the Dashboard  
[Tableau Chicago Relocation Guide](https://public.tableau.com/app/profile/omkardabholkar/viz/Chicago_17103078576530/HomePage).

# Table of Contents
1. [Project Description](#project-description)
2. [Technologies Used](#technologies-used)
3. [Features](#features)
4. [Data Source](#data-source)
5. [Data Analysis](#data-analysis)
6. [Installation and Setup](#installation-and-setup)
7. [Usage](#usage)
8. [Project Status](#project-status)
9. [Contact Information](#contact-information)

## Project Description
In December 2023, I developed the Tableau Chicago Relocation Guide, a project that aims to assist individuals considering relocation to Chicago by providing a comprehensive overview of the city's living conditions. This guide leverages advanced data wrangling techniques using Pandas in Python to clean and process five diverse datasets obtained from the Chicago City Government website, covering crucial aspects such as crime rates, employment opportunities, housing costs, and transportation options. The culmination of this project is an interactive Tableau dashboard featuring a variety of chart types that visually represent key relocation factors including safety, affordability, career opportunities, and commute times, designed to make relocation decisions informed and straightforward.

## Technologies Used
- **SQL**: Employed for advanced data querying tasks.
- **Python (Pandas)**: Utilized for efficient data wrangling and cleaning.
- **Tableau**: Used to create an interactive dashboard that presents the data through various visualization techniques.

## Features
- **Comprehensive Data Analysis**: Insightful analysis of crime, jobs, housing, and transport datasets to offer a well-rounded view of Chicago.
- **Interactive Dashboard**: A Tableau dashboard with seven different chart types including maps, bar charts, and scatter plots, enabling users to interactively explore data related to safety, affordability, career opportunities, and commute.
- **Key Relocation Factors**: Focused insights on safety, affordability, career opportunities, and commute times to aid in making a well-informed relocation decision.

## Data Source
The datasets for this project were sourced from the Chicago City Government website, which provided extensive data on crime, jobs, housing, and transportation within the city. These datasets were meticulously cleaned and wrangled using Python to ensure high-quality, actionable insights.

[Download Datasets Here]

[Chicago Crime Data](https://data.cityofchicago.org/Public-Safety/Crimes-2022/9hwr-2zxp/data)  
[ChicagoBusData.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620101/ChicagoBusData.xlsx)  
[ChicagoCabs.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620109/ChicagoCabs.xlsx)  
[ChicagoRent.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620110/ChicagoRent.xlsx)  
[ChicogoGovernmentEmployment.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620128/ChicogoGovernmentEmployment.xlsx)

## Data Analysis    
Highlighted SQL Query

One of the key aspects of the Chicago Relocation Guide was to identify neighborhoods that offer a balance between affordability and safety, essential factors for anyone considering moving to the city. The following SQL query illustrates how we analyzed crime rates and housing prices across different neighborhoods to pinpoint areas that are both safer and more affordable than the average. This query exemplifies the depth of data analysis conducted using SQL as part of the project's backbone.

```sql
-- SQL Snippet: Analyzing Safety and Affordability in Chicago Neighborhoods
SELECT 
    neighborhoods.name AS Neighborhood,
    AVG(crime.rate) AS Average_Crime_Rate,
    AVG(housing.price) AS Average_Housing_Price
FROM 
    neighborhoods
JOIN 
    crime ON neighborhoods.id = crime.neighborhood_id
JOIN 
    housing ON neighborhoods.id = housing.neighborhood_id
GROUP BY 
    neighborhoods.name
HAVING 
    AVG(crime.rate) < (SELECT AVG(rate) FROM crime) AND AVG(housing.price) < (SELECT AVG(price) FROM housing)
ORDER BY 
    Average_Housing_Price ASC, Average_Crime_Rate ASC
LIMIT 10;
```

## Installation and Setup
No installation is required to view the Tableau dashboard. It can be accessed directly through the following link: [Tableau Chicago Relocation Guide](https://public.tableau.com/app/profile/omkardabholkar/viz/Chicago_17103078576530/HomePage).

## Usage
Navigate to the provided Tableau Public link to explore the interactive dashboard. The dashboard is designed to be intuitive, allowing users to filter and interact with the visualizations to gain insights into the various factors influencing the decision to relocate to Chicago.

## Project Status
This project was completed in December 2023. While the current version of the dashboard provides comprehensive insights into relocation considerations for Chicago, future updates may include additional data points or refined analyses based on user feedback and evolving data.

## Contact Information
For inquiries, suggestions, or contributions to this project, please feel free to reach out through my GitHub profile.

