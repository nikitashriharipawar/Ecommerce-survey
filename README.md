# Ecommerce Survey-Dashboard

### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiMTgwZGI3MTMtM2Q4MS00NjFkLTk5ODQtMjkyOWY4ZjAxMGYwIiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9

## Problem Statement

This dashboard helps the Ecommerce company to analyze their overall data. Forexample, how many orders were shippd, unavailable, cancelled, what are total numbers of customers and sellers.
They can also identify the review scores by customers so that they can work on minimum review score. The company can also verify price and freight value as per their products.
by knowning, different types of payment methods used by customers, they can advertise the discounts, coupons with respective to their payment methods.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a excel file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that some of the columns with empty values, hence transform the dateset with 100% column accurancy.
- Step 5 : For calculating time intelligence, seperate table with calender name was created and under model view it was connected to order dataset.
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted to create filters panel.
- Step 8 : Visual filters (Slicers) were added for four fields named "Year", Month", "City", "Review Score" & "Zip code". LAstely Clear button created to clear any applied filters to dashboard using bookmark.
- Step 9 : Different card visuals were added to the canvas, representing total number of customers, sellers, products.
- Step 10 : A pie chart was added in order to calculate the freight value by payment type.
- Step 11 : A tree map was added to check the review score and bigger box representing maximum review score by month ie August, following by smaller boxes for months. 
- Step 12 : In the report view, under the insert tab, two text boxes were added to the canvas, in one of them name of the dashboard was mentioned & in the other one creation date was mentioned.
- Step 13 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted & similarly using image option company's logo was added to the report design area. 
- Step 14 : New table with name Measures_table was created. 
- Step 15 : New measure was created to find orders delivered, orders shipped, orders cancelled, orders unavailable.

Following DAX expression was written for the same,
        
    Orders Delivered = 
    CALCULATE(COUNTA(olist_orders_dataset[order_status]), 
    FILTER(olist_orders_dataset,olist_orders_dataset[order_status]="delivered"))

	Orders shipped = 
    CALCULATE(COUNTA(olist_orders_dataset[order_status]),
    FILTER(olist_orders_dataset,olist_orders_dataset[order_status]="shipped"))

	Orders Cancelled = 
    CALCULATE(COUNTA(olist_orders_dataset[order_status]),
    FILTER(olist_orders_dataset,olist_orders_dataset[order_status]="canceled"))

	Orders Unavailable = 
    CALCULATE(COUNTA(olist_orders_dataset[order_status]),
    FILTER(olist_orders_dataset,olist_orders_dataset[order_status]="unavailable"))
        
- Step 16 : Are chart visual was created for price by year.
- Step 17 : Map visual created for customer as per their geographical location.
- Step 18 : The report was then published to Power BI Service.
 
 
# Snapshot of Dashboard (Power BI Service)

![d1](https://github.com/nikitashriharipawar/Ecommerce-survey/assets/86060741/d6352e98-bb6b-4273-abfa-d17a87f3a1d3)


 
 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard](https://github.com/nikitashriharipawar/Ecommerce-survey/assets/86060741/954222ee-a378-4ff3-8e1a-9ca10b286418)


# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Overall summary

	a) Total Number of Customers = 99.44K
	b) Total Number of Sellers = 3095
	c) Total Number of products = 32.95K
	d) Average price of item = 120.65
	e) Orders delivered = 96K
	f) Orders cancelled = 625
	g) Orders shipped = 1107
	h) Orders unavailable = 609

Pie chart visual for freight value by payment type

	a) boleto = 20%
	b) credit card = 20% 
	c) debit card = 20%
	d) not defined = 20%
	e) voucher = 20%

Treemap visual for Review score by month achieving maximum review score in August month.
    
           
### [2] Price and fright value as per product category

### [3] Donut chart for review score by customer 

	a) Min review score: 16.62%
	b) Max review score: 83.38% 
  
### [4] Area chart for Price by year where Max price of 7,403,330 was achieved in 2018

### [5] Map Visual for customers as per their geographical location
