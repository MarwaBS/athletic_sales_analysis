# Athletic Sales Analysis

## Project Overview

The Athletic Sales Analysis project aims to analyze sales data for women's athletic footwear across various regions, states, and cities in the U.S. over the years 2020 and 2021. This analysis provides insights into sales performance, trends, and the impact of geographic location on product sales. The project utilizes a combination of data preparation techniques, grouping functions, and resampling methods to identify key trends in the data.

## Data Preparation and Cleaning

### 1. Combining DataFrames
To merge the sales data from 2020 and 2021, I used the `concat()` function, which was ideal for vertically stacking the two DataFrames. Since the DataFrames had identical structures, `concat` ensured seamless integration without requiring key-based merging like `join()` or `merge()`. This approach preserved all entries from both years, enabling comprehensive analysis.

### 2. Handling Missing Values
I performed a check for missing values using the `isnull().sum()` method to identify any potential gaps in the dataset that could affect the analysis. Once identified, missing data could be handled through imputation or exclusion based on its impact on the overall results.

### 3. Conversion to Datetime
The **invoice_date** column was converted into a datetime format using `pd.to_datetime()`. This conversion allowed for effective time-based analysis, such as resampling the data into daily and weekly bins. Invalid date entries were handled with `errors='coerce'`, ensuring the dataset remained clean and usable for time series operations.

## Data Analysis

### 1. Total Products Sold by Region, State, and City
To determine which regions, states, and cities sold the most products, I used the `groupby()` function, grouping by **region**, **state**, and **city**. The `groupby()` method was essential in aggregating the total product sales and units sold across multiple locations. After aggregation, the index was reset for better readability, resulting in a table that highlights the locations with the highest sales volumes.

### 2. Pivot Table for Total Sales
The `pivot_table()` function was utilized to create a multi-index pivot table with **invoice_date** as the index and the total sales as the values. This function allowed for a detailed cross-tabulation of sales by region and city, enabling easy comparison of sales across various geographic levels.

### 3. Women's Athletic Footwear Sales
To focus specifically on women's athletic footwear, I filtered the dataset by the **product** column, selecting only sales data related to this product category. This filter allowed for more targeted analysis, providing insights specifically related to women's athletic footwear sales performance.

### 4. Daily and Weekly Sales Resampling
Using the `resample()` function, I resampled the data into daily and weekly bins, aggregating the sales totals for each time period. This allowed for time series analysis, providing valuable insights into daily and weekly sales trends. By using `resample()`, the dataset was broken down into manageable periods, helping to identify peak sales periods for women’s athletic footwear.

### 5. Sorting and Ranking with `nlargest()`
To highlight top-performing regions, cities, and retailers, I utilized the `nlargest()` function. This function enabled ranking by total sales and units sold, allowing me to easily identify the top five regions, states, cities, and retailers that performed best in terms of product sales.

## Results

### Key Findings:
- **Top Regions and Cities**: By aggregating the data through `groupby()` and `pivot_table()`, I identified the regions, states, and cities with the highest product sales.
- **Top Retailers**: Using similar aggregation techniques, the analysis revealed the top-performing retailers in terms of total sales.
- **Women's Athletic Footwear Sales**: A filtered analysis of women's athletic footwear sales indicated key geographic areas and time periods with peak sales performance.
- **Time-Based Sales Trends**: Through daily and weekly resampling, I identified the days and weeks with the highest total sales for women's athletic footwear, providing insight into sales patterns.

## Conclusion

This project demonstrates the effective use of Python's Pandas library for data preparation, cleaning, and analysis. Through functions like `groupby()`, `pivot_table()`, `resample()`, and `concat()`, I was able to uncover trends in women's athletic footwear sales across regions and time periods. These insights can be leveraged to inform strategic business decisions related to product offerings, marketing, and inventory management in the athletic footwear market.
