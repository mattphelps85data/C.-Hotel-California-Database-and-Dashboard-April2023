
# Hotel California Data Dashboard

Hotel California (a fictitious company) requested a database be created using SQL, and for some insights to be visualized through Power BI.



## Tech

**Database:** MySQL

**Database Tool:** MySQL Workbench

**Visualization Tool:** Power BI


## Description

Hotel California had two deliverables they were looking for.

1.	Develop a database to analyze and visualize hotel booking data
2.	Build a visual datastory or dashboard using Power BI or Tableau to present to the stakeholders



##  Requested Analysis

•	“Is our hotel revenue growing by year?” 
– We have two hotel types so it would be good to segment revenue by hotel type.

•	“Should we increase our parking lot size?” – We want to understand if there is a trend in guests with personal cars.

•	“What trends can we see in the data?” – Focus on average daily rate and guests to explore seasonality. 


## Database Creation 


1.	Create database – HotelCalifornia
2.	Save each worksheet from full excel workbook as separate csv file
3.	Import flat files into HotelCalifornia database to create tables
4.	HotelCalifornia SQL database completed


```bash
SQL QUERIES

Union the year datasets as one complete dataset

WITH hotels AS (
SELECT * FROM hotel_revenue_2018
UNION
SELECT * FROM hotel_revenue_2019
UNION
SELECT * FROM hotel_revenue_2020)
Revenue By Year and Hotel Type:
SELECT 
arrival_date_year,
hotel,
round(sum((stays_in_weekend_nights + stays_in_week_nights)*adr),2) AS revenue
FROM hotels
GROUP BY arrival_date_year,hotel;

Join Market Segment and Meal Cost to Unioned Dataset

SELECT * FROM hotels
LEFT JOIN hotel_revenue_market_segment
ON hotels.market_segment = hotel_revenue_market_segment.market_segment
LEFT JOIN hotel_revenue_meal_cost
ON hotel_revenue_meal_cost.meal = hotels.meal

```

## PowerBI Dashboard

1.	Added Title
2.	Added Date Slicer
3.	Added Hotel Type Dropdown Menu
4.	Added Country Dropdown Menu
5.	Added Cards for Total Revenue, ADR, Reservations, and Average Discount
6.	Added Dual Line Chart for Revenue by Year and Hotel Type
7.	Added Matrix for Year, Parking Spaces Required, and Parking Percentage
8.	Added Revenue Percentage by Hotel Type Donut
9.	Formatted, styled, and spaced dashboard
10.	Export as pdf. 
11.	Saved pbix file for upload to Power Bi Service.



## Dashboard Screenshot

[![Hotel-California-Dashboard.png](https://i.postimg.cc/sxqLPgSn/Hotel-California-Dashboard.png)](https://postimg.cc/D4Q5nFxs)



## Acknowledgements

 - [@AbsentData](https://www.absentdata.com/)

## Authors

- [@mattphelps85data](https://github.com/mattphelps85data)


[![Matthew-1.png](https://i.postimg.cc/W4rdD6fp/Matthew-1.png)](https://postimg.cc/t1qqwPj8)

