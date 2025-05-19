# Amazon Sales Analysis: Sales Insights with Python

## Overview :
This project provides an exploratory data analysis (EDA) of Amazon sales data. The analysis aims to uncover key insights about product performance, pricing strategies, and customer behavior.  The primary focus is to understand which product categories drive the most revenue, which categories have the deepest discounts, and which categories exhibit the highest customer engagement.

## Key Insights :
This Amazon Sales Analysis project reveals that Electronics is the dominant product category in terms of product availability and customer reviews. Higher-priced electronics, such as Laptops and Tablets, tend to have the deepest discounts. While Electronics has the highest review volume, Office Products and Tablets receive the highest average ratings, and Kitchen & Dining has the most ratings overall. A significant portion of reviews are from anonymous users. Most products are priced between ₹100 and ₹5000, with higher-priced items often having larger discounts, and discounts between 50% and 65% appear to drive more purchases.

## Problem Statement : Illuminate Various Key Insights from Amazon Sales Data

Amazon, a global e-commerce giant, has strategically expanded beyond online retail into diverse sectors like cloud computing (AWS) and digital streaming (Prime Video), demonstrating a continuous drive for innovation and market dominance. Its vast customer network and technological infrastructure position it as a major player in the evolving digital landscape.

### Goal :

The goal of this project is to conduct exploratory data analysis and determine which category of products has the highest revenue, which category offers the most discounts, which category has the highest customer engagement, and other insights.

### Data Source :

The dataset used in this analysis is contained in the `amazon.csv` file.  It is assumed that this file is located in the same directory as the analysis scripts or notebooks.The dataset has 1465 rows.
Features:

-   product_id - Product ID
-   product_name - Name of the Product
-   category - Category of the Product
-   discounted_price - Discounted Price of the Product
-   actual_price - Actual Price of the Product
-   discount_percentage - Percentage of Discount for the Product
-   rating - Rating of the Product
-   rating_count - Number of people who voted for the Amazon rating
-   about_product - Description about the Product
-   user_id - ID of the user who wrote review for the Product
-   user_name - Name of the user who wrote review for the Product
-   review_id - ID of the user review
-   review_title - Short review
-   review_content - Long review
-   img_link - Image Link of the Product
-   product_link - Official Website Link of the Product


### Project Structure :

The project consists of the following files:

* `AmazonSalesAnalysis.ipynb`: A Jupyter Notebook containing the Python code for data loading, cleaning, and analysis.
* `amazon.csv`: The dataset containing Amazon sales data.
* `README.md`: This file, providing an overview of the project.

### Dependencies :

The project uses the following Python libraries:

* `numpy` (as `np`): For numerical computations, especially with large arrays of data.
* `pandas` (as `pd`): For data manipulation and analysis using DataFrames.
* `matplotlib.pyplot` (as `plt`): For creating basic plots and charts.
* `seaborn` (as `sns`): For creating more visually appealing and informative statistical graphics.

### Steps Involved :
The data analysis process can be broadly divided into two key stages:

I. Data Cleaning and Preprocessing 

II. Exploratory Data Analysis (EDA)


### I. Data Cleaning and Preprocessing :

* Import necessary libraries.
* Load the data-set `amazon.csv` into a `df_amazon` dataframe.
* Check for null values and data type of each columns.
* Removing symbols before changing the data types from `actual_price`, `discounted_price`, `rating_count` & `discount_percentage` columns.
* Changing Data type of price, percentage & rating related columns to float data type (float data type to provide precision).
  * The `rating` column has a values error -> `|`.
  * Replacing the value by visiting the product site with the provided `product_link`.
* Checking for duplicate values.
* Creating `Category` and `Sub-Category column` from `category` column.
  * The `category` column is split using `|` as the delimitor , and since the 0th and 1st column of the split data frame `df_category_split` has no null so only these two are selected rest are dropped.
  * More formating the resulted `Category` & `Sub-Category` columns.
* Creating a Feedback Score Column.
  * Creating a Categorical column containing categories from `very low quality` to `excellent quality`.
* Dealing with `user_id` & `user_name` column.
  * Since the user_id and user_name column has multiple ids and names in same cell. 
  * Now we need each user_id and user_name in individual rows. 
  * And then create a new dataframe `df_customer_info` of it.


### II. Exploratory Data Analysis (EDA) :

#### Visual I :-> Product V/s Category and Sub-Category
![image](https://github.com/user-attachments/assets/c0e85545-a9aa-4485-a8f9-d1c46aad6d10)

Findings: 
* Most Popular Category -> Electronics.
* Most Popular Category -> Accessories & Peripheral.


#### Visual II :-> Average price and Average discounted price V/s Sub-category
![image](https://github.com/user-attachments/assets/04b3ff2f-18e1-4325-a615-30bd02eef704)

Findings: 
* Laptops, Tablets, Home Theater, TV & Video & Monitors categories have the highest disounted price.


#### Visual III :-> Top 5 Most Expensive products & Top 5 Least Expensive products
![image](https://github.com/user-attachments/assets/a6c29670-d50d-415a-8a50-266f7f8a4178)

Findings: 
* Top 5 Most Expensive products belongs to Electronics Category
* Top 5 Least Expensive products belongs to Office products and Electronics Category.


#### Visual IV :-> Top 5 Most & Least purchased products
![image](https://github.com/user-attachments/assets/5027c61b-8d1d-458e-81ba-3634c5c1fcda)

Findings: 
* All the products belong to Electronics.


#### Visual V :-> Category & Sub-Category by Rating
![image](https://github.com/user-attachments/assets/839597c0-19be-4b4d-83f3-f855bcb2607a)

Findings: 
* Office Products and Tablets have the highest rating.
* Almost all categoires and sub-categories have avgrage rating above 3.


#### Visual VI :-> Top 5 Most & Least Rated Sub-Categories
![image](https://github.com/user-attachments/assets/8452fdec-914e-4d3c-85f0-5e5e66dd29f2)

Findings: 
* Kitchen & Dining has the highest rating count means more products are being purchased from this Sub-category.
* While Laptops has the least rating count means less products are puchased from this Sub-category.


#### Visual VII :-> Top 10 Customers who reviewed the most products
![image](https://github.com/user-attachments/assets/d3961607-997c-4af7-846e-8e17cb0d11bb)

Findings: 
* With a majority of users being anonymous, it raises concerns that their reviews may lack authenticity.


#### Visual VIII :-> Reviews per Category and Sub-Category
![image](https://github.com/user-attachments/assets/5acbcab2-dacd-4c89-86e4-da7478599902)

Findings: 
* Highly Reviewed Category and Sub-Category are Electronics and Accessories and Pheripherals.


#### Visual IX :-> Top 5 Most and Least Reviewed Products
![image](https://github.com/user-attachments/assets/7a29cd08-6d66-4616-803a-ec6f0615671d)

Findings: 
* Top 5 Most and Least Reviewed products are from electronics category.


#### Visual X :-> Price, discount price and discount percentage distribution
![image](https://github.com/user-attachments/assets/c50f3b79-2e9e-4f74-bb91-05d65be3fa4b)

Findings: 
* Price Distribution shows most of the products have price in range of Rs. 100 to Rs. 5000.
* Discounted Price Distribution shows that higher the price of product higher is the discount.
* Discounted Percentage shows products are mostly purchased when they have disount 50% to 65 %.


### Summary :

* Dominant Product Category:
  * The Electronics category stands out as the most prevalent in terms of the number of products offered and the volume of reviews received, indicating its significant presence on Amazon.
  * The Accessories & Peripheral sub-category within Electronics is particularly popular.
* Pricing and Discounts:
  * Products in higher-priced sub-categories like Laptops, Tablets, Home Theater, TV & Video, and Monitors tend to have the highest absolute discounted prices.
  * A significant portion of purchases appears to occur when products have discounts ranging from 50% to 65%.
* Customer Engagement and Ratings:
  * While Electronics receives the most reviews, Office Products and Tablets exhibit the highest average product ratings.
  * Kitchen & Dining has the highest number of ratings, suggesting a large volume of customer feedback and potentially higher purchase activity in this sub-category.
* Reviewer Anonymity:
  * A notable number of product reviews are submitted by anonymous users, which could raise questions about the authenticity and reliability of this feedback.
* Product Performance:
  * The top 5 most expensive and most purchased products all belong to the Electronics category.
  * Similarly, the most and least reviewed products are also within the Electronics category.
* Price Distribution:
  * The majority of products in the dataset are priced between ₹100 and ₹5000. Higher-priced products tend to have larger absolute discounts.
