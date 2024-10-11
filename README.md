# Athletic Sales Analysis

## Project Overview

The Athletic Sales Analysis project aims to analyze sales data for women's athletic footwear across various regions, states, and cities in the U.S. over the years 2020 and 2021. This analysis provides insights into sales performance, trends, and the impact of geographic location on product sales.

## Data Preparation and Cleaning

### Combining DataFrames

To combine the sales data from 2020 and 2021, I utilized the `concat` function. This method was chosen because it is more efficient for appending DataFrames vertically (i.e., stacking them on top of each other). Since both DataFrames had identical structures and columns, `concat` allowed for a seamless integration of the two datasets without the need for key-based matching, which would have been necessary with a join or merge. This approach not only simplifies the data merging process but also ensures that all entries from both years are retained for analysis.

### Handling Missing Values

After combining the DataFrames, I checked for null values using the `isnull().sum()` method. This step is crucial for identifying any missing data that could impact the analysis. Any null values found can be addressed through various imputation techniques or excluded from the analysis as appropriate.

### Conversion to Datetime

The "invoice_date" column was converted to a datetime data type to facilitate accurate date-based analysis. Using the `pd.to_datetime()` function, I specified the date format to correctly interpret the string representations of dates. Additionally, the `errors='coerce'` parameter was included to convert any invalid dates into `NaT` (Not a Time). This ensures that the dataset remains robust, allowing for effective time series operations, such as resampling and sorting by date.

## Data Analysis

### Total Products Sold

I calculated the total products sold per region, state, and city using the `groupby()` function and then reset the index to create a summarized DataFrame. The resulting table highlights the locations with the highest sales, which can be critical for identifying key markets.

### Pivot Table for Total Products Sold

To further analyze total products sold, I created a pivot table with the "invoice_date" as the index and the total sales as the values. This pivot table allows for easy aggregation and visualization of sales data across different dimensions.

### Women's Athletic Footwear Sales

To focus specifically on women's athletic footwear, I filtered the sales data based on the product name. This step enables a more detailed analysis of a targeted product category.

### Daily Sales Resampling

I resampled the pivot table into daily bins to examine total sales for each day. This time series analysis provides insights into daily sales trends, allowing for the identification of peak sales periods.

## Results

The analysis reveals trends and patterns in sales data, providing valuable insights into the performance of women's athletic footwear across various locations and time periods. The results can inform marketing strategies, inventory management, and sales forecasting.

## Conclusion

This project showcases the process of data preparation, cleaning, and analysis using Python's Pandas library. The insights gained from this analysis can help drive informed business decisions in the athletic footwear market.
