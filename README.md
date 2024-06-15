
# README.md

## Title:

Honda Car Sales Dataset and Power BI Dashboards

## Description:

Customers and employees are the two target user groups for the two separate dashboards created in this project, which uses Power BI to analyse sales data of Honda automobiles.  

Customer Trends Dashboard: This dashboard provides an overview of Honda car sales and consumer ratings across different models and countries. It serves as a powerful tool for customers who are interested in understanding the popularity, performance, and overall satisfaction levels of various Honda car models across different countries.

Sales Performance Dashboard: This Dashboard is designed to provide Honda employees with detailed insights into sales performance and predictive analytics. This dashboard aids in strategic planning, performance tracking, and decision-making processes.

## Table of Contents:

Dataset Description 

Tools Used

DAX Functions

Insights and Features

Usage




## Dataset Description:
The dataset consists of the following columns:

Year: The year of manufacture.

Make: The one and only Honda.

Model: The model of the vehicle.

Condition: The condition of the vehicle (new, used, etc.).

Price: The price of the vehicle.

Consumer_Rating: Average consumer rating.

Consumer_Review_: Consumer review count.

Exterior_Color: Exterior color of the vehicle.

Drivetrain: Drivetrain type (FWD, RWD, etc.).

Fuel_Type: Type of fuel used (Gasoline, Hybrid).

Transmission: Type of transmission (Automatic, Manual, etc.).

Engine: Engine specifications.

VIN: Vehicle Identification Number.

Stock_: Stock number.

Mileage: Mileage of the vehicle.

Comfort_Rating: Comfort rating out of 5.

Interior_Design_Rating: Interior design rating out of 5.

Performance_Rating: Performance rating out of 5.

Value_For_Money_Rating: Value for money rating out of 5.

Exterior_Styling_Rating: Exterior styling rating out of 5.

Reliability_Rating: Reliability rating out of 5.

State: State where the vehicle is sold.

Seller_Type: Type of seller.

min_MPG: Minimum miles per gallon.

max_MPG: Maximum miles per gallon.

avg_MPG: Average miles per gallon.


## Tool Used:

PowerBI

## DAX Functions:

Model Ratings:

Average of Every Customer Ratings: Calculated using 
```http
 AVG COMFORT RATING = CONCATENATE(FORMAT(AVERAGE(honda_data[Comfort_Rating]),"0.00"),"/5").
 ```
 ```http
AVG Exterior_Styling_Rating = CONCATENATE(FORMAT(AVERAGE(honda_data[Exterior_Styling_Rating]),"0.00"),"/5")
 ```
```http
AVG Interior_Design_Rating = CONCATENATE(FORMAT(AVERAGE(honda_data[Interior_Design_Rating]),"0.00"),"/5")
 ```
```http
AVG PERFORMANCE = CONCATENATE(FORMAT(AVERAGE(honda_data[Performance_Rating]),"0.00"),"/5")
 ```
```http
AVG Value_For_Money_Rating = CONCATENATE(FORMAT(AVERAGE(honda_data[Value_For_Money_Rating]),"0.00"),"/5")
 ```
```http
AVG RATING = CONCATENATE(FORMAT(AVERAGE(honda_data[Consumer_Rating]),"0.00"),"/5")
 ```
Average Price: 
```http
AVG PRICE = AVERAGE(honda_data[Price])
 ```
Normalized Price:
```http
Normalized Price = 
VAR Price = honda_data[AVG PRICE]
VAR MinPrice = MIN(honda_data[Price])
VAR MaxPrice = MAX(honda_data[Price])
RETURN DIVIDE(Price - MinPrice, MaxPrice - MinPrice)
Total Vehicles: Displays the total number of vehicles sold.
```
```http
TOTAL VEHICLES = DISTINCTCOUNT(honda_data[VIN])
```
Fuel Type and Condition: Shows the fuel type  of the vehicles.

```http
BEV VEHI = CALCULATE([TOTAL VEHICLES],honda_data[Fuel_Type] = "Gasoline")
```
```http
% OF BEV = [BEV VEHI] / [TOTAL VEHICLES] 
```
```http
HBEV VEHI = CALCULATE([TOTAL VEHICLES],honda_data[Fuel_Type] = "Hybrid")
```
```http
% OF HBEV = [HBEV VEHI] / [TOTAL VEHICLES] 
```
## Insights and Features:
### 1. Customer Trends Dashboard
Name: HONDA CUSTOMER VOICE DASHBOARD


 **Total Vehicles Sold**
   - Displays the cumulative number of vehicles sold.

 **Top 5 Models**
   - Lists the top 5 Honda models based on sales.

 **Top Countries**
   - Highlights countries with the highest vehicle sales.

 **Year-wise Sales**
   - Shows total vehicles sold per year.

 **Interactive Slicers**

 - **Model Filter**
    - Customers can filter the data by specific models, allowing for a focused view of the desired cars.

  - **Price Binning**
    - Segments vehicles into different price ranges, making it easier to find models within their budget.

  - **Ratings Filter**
    - Filters models based on consumer ratings, helping prioritize highly-rated vehicles.

 **Model Ratings**
   - Displays ratings for every model.

 **Fuel Type and Condition Analysis**
  - Breaks down vehicles by fuel type (e.g., Gasoline, Hybrid) and condition (e.g., New, Used). This helps customers make informed choices based on fuel efficiency preferences and budget considerations.

 **Average Price of the Top 5 Models (Tree Map)**
  - Visualizes the average price of the top 5 models using a tree map. Each segment represents a top-selling model, with the size reflecting its average price. This provides a clear comparison of pricing among popular models, aiding customers in understanding price distribution and relative costs.

### 2. Sales Performance Dashboard
Name: HONDA SALES AND PERFORMANCE DASHBOARD

 **Predicted Decade Sales**:
  - Forecasts sales for the next decade using predictive analytics.

 **Normalized Price Visualization**:
   -  Shows the normalized prices across different models.

 **Dynamic Animations**: 
 - Provides animated visuals for key metrics such as price, mileage, engine specifications, and total cars sold. This dynamic representation helps in understanding fluctuations and trends over time.

 **Data Cards**:
   - **Total Customer Review Counts**: Displays the total number of customer reviews.
   - **Total Colors**: Shows the total number of car colors available.
   - **Customer State Counts**: Indicates the number of customer states, reflecting geographic reach and market penetration.
   - **Total Model Counts**: Displays the total number of models available, showing the breadth of the product line.
   - **Average Mileage**: Provides the average mileage of the vehicles, important for assessing fuel efficiency and performance.

 **Interactive Slicers**:
   - **Model Filter**: Allows employees to filter data by specific car models, focusing on particular segments.
   - **Color Filter**: Enables filtering by car color, useful for analyzing trends in color preferences.
   - **State Filter**: Allows filtering by state, helping to understand regional sales performance.
## Usage:

### Opening the Dashboards
Power BI Desktop: Open the Power BI Desktop application.

Load the Dataset: Load the Honda_sell_sales_data dataset into Power BI.

Open Dashboards: Open the downloaded pre-built dashboards for customer and employee insights.

### Interacting with the Dashboards

Filters: Use the slicers to customize the views based on model, price, ratings, color, and state.

Visuals: Interact with various charts and graphs to gain deeper insights into the data.

## Author:

 [@Ramya M N](https://github.com/RamyaMN28)

