# ROAD_ACCIDENT_ANALYSIS_POWERBI

POWER BI ROAD ACCIDENT ANALYSIS IN UNITED KINGDOM
Dataset Link: https://www.kaggle.com/datasets/tsiaras/uk-road-safety-accidents-and-vehicles


**Requirement Gathering:**
Stakeholders in the project (who are users of this dashboard)
Raw Data Overview
Connecting Data with PowerBI
Data Cleaning
Data Processing
Data Modelling
Background design in Power Point
Data visualization and chart design
Report and dashboard building
Insights


**REQUIREMNT**

Clients wants to create a Road Accident Dashboard for year 2021 and 2022,so that they can have insight on below requirements

1. Primary KPI - total casualities and total accident values for current year and Yoy growth
2. Primary KPI's - total casualities by accident severity for current year and Yoy growth
3. Secondary KPI's - total casualities with respect to vehicle type for  current year
4. Monthly trend showing comparision of casualities for current year and previous year
5. Casualities by Road type for current year
6. Current year casualities by area/location and by day/night
7. Total casualities and total accidents by location

**STAKEHOLDERS**
1. Ministry of transport
2. Road transport department
3. Police force
4. Emergency services department
5. Road safety cops
6. Transport operators
7. Traffic management agencies
8. Public
9. Media

**POWERBI FUNCTIONALITIES**
1. how to connect to raw data
2. data cleaning in powerbi
3. data processing
4. Time intelligence function/calander table in powerbi
5. Data modelling(relationship between multiple tables)
6. YTD and YoY grwoth calculations using DAX
7. Creating custom columns and measures in reports
8. Importing images
9.creating different charts and generating insights
10.export the report to users


**Power query is the kitchen of the powerbi,where we cook,clean,shape the data**

Functions:
Calendar = Calendarauto() -->we have to leave blank, as it willstart from january,if we give '1' it will skip january and start 'feb' as first month of that particular year

Calendar -calendar(min(date),max(date))

Year = Year(CALENDAR[Date])

month = format(calendar[date],"mmm")

CY Casualities = totalytd(sum(data[number of casualities]),calendar[date])-->current year

PY Casualities = calculate(data[number of casualities]),sameperiodlastyear(calendar[date]))-->previous year

YoY Casualities = ([cy casualities]-[py casualities])/[py casualities] -->year on year casualities
Note: we attached this below cy casualities which indicates that the number is less compared to last year

CY Accidents count = totalytd(count(data[accident_index]),calendar[date])

PY Accidents = calculate(data[accident_index]),sameperiodlastyear(calendar[date]))

YoY Accidents = ([cy Accidents count]-[py Accidents])/[py Accidents] -->year on year casualities
