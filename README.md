# Best Strategy to Buy Used Car Considering Value, Worth, and Depreciation 🚗📈

## Project Overview

In this project, we explore the Vehicle Sales dataset to identify the best used cars to buy based on their potential resale value and low depreciation. The goal is to provide insights and data-driven recommendations for someone looking to purchase cars considering value and worth. By analyzing factors such as model popularity, mileage, car color, and age, we aim to pinpoint cars that hold their value well over time.

## Table of Contents

- [Introduction](#introduction)
- [Intended Audience](#intended-audience)
- [Key Contents](#key-contents)
- [Dataset](#dataset)
- [Data Analysis](#data-analysis)
- [Feature Engineering](#feature-engineering)
- [Machine Learning](#machine-learning)
- [Key Findings](#key-findings)
- [Conclusion](#conclusion)
- [Usage](#usage)

## Introduction

When considering the purchase of a vehicle, one of the key questions that often arises is its potential resale value. Many buyers wonder about the factors that can influence the selling price later on. Understanding these factors is crucial for making informed decisions and maximizing the value of your worth buying.

Cars are among the most commonly used modes of transportation in the USA. While some individuals purchase cars based on their personal preferences, others do not. Some individuals seek cars that align with their lifestyle, while others prioritize value and affordability, along with the potential for resale at a good price with low depreciation and high liquidity. Today, we will explore the considerations and factors involved in purchasing a car for its worth, low depreciation, and potential for resale value.

In this exploration of the vehicle sales dataset, we aim to identify the best strategy for buying cars for customers by considering value, worth, price changes, and quick resale potential. By analyzing factors such as model popularity, mileage, car color, and the age of the vehicle, we aim to pinpoint cars that hold their value well over time. This will help us determine which cars can be sold to dealerships or directly to buyers at a good price, while minimizing depreciation and ensuring high liquidity.

## Target Audience

1. **Used car shoppers**: Those in the market for a pre-owned vehicle seeking guidance on making a value-conscious purchase.
2. **Economical buyers**: Individuals looking to optimize their car-buying budget by understanding factors influencing resale prices.
3. **Automotive industry enthusiasts**: Those interested in the economics and trends of the automotive market.
4. **Financial advisors**: Professionals assisting clients with major purchasing decisions, including selecting vehicles with strong resale value.
5. **Car Dealers and Sales Professionals**: Dealerships and salespersons can use the insights from the project to advise customers on car models that hold their value well and sell quickly, improving customer satisfaction and turnover.


## Key Contents
1. Guide to buy Car 
2. Car Depreciation Percentage Change table
3. Table of Average Price in Popular Model

## Dataset 📊

### Dataset Description:

The "Vehicle Sales and Market Trends Dataset" provides a comprehensive collection of information pertaining to the sales transactions of various vehicles. This dataset encompasses details such as the year, make, model, trim, body type, transmission type, VIN (Vehicle Identification Number), state of registration, condition rating, odometer reading, exterior and interior colors, seller information, Manheim Market Report (MMR) values, selling prices, and sale dates.

The dataset can be found [here](https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data/data).

### Column Descriptions:

- **year**: The year the vehicle was manufactured.
- **make**: The manufacturer or brand of the vehicle.
- **model**: The specific model of the vehicle.
- **trim**: The specific trim or version of the vehicle model.
- **body**: The body type of the vehicle.
- **transmission**: The type of transmission the vehicle uses.
- **VIN**: The Vehicle Identification Number, a unique code to identify individual motor vehicles.
- **state**: The state where the vehicle is registered or sold.
- **condition**: The condition rating of the vehicle.
- **odometer**: The mileage of the vehicle at the time of sale.
- **color**: The exterior color of the vehicle.
- **interior**: The interior color of the vehicle.
- **seller**: Information about the seller or dealership.
- **MMR**: Manheim Market Report values, which provide estimated wholesale prices based on the vehicle's condition and other factors.
- **sellingprice**: The actual selling price of the vehicle.
- **saledate**: The date the vehicle was sold.


## Data Analysis 🔍

The analysis focuses on several key aspects:
- **Model Popularity**: Identifying which car models are popular and retain their value.
- **Mileage**: Analyzing how mileage affects the resale value of cars.
- **Car Color**: Investigating the impact of car color on resale liquidity.
- **Age of Vehicle**: Understanding how the age of the vehicle correlates with its depreciation.
- **Percentage Price Change**: Analyze how the price changes with mileage

## Feature Engineer

### K-means Clustering

To group similar cars together to indicate groups worth buying, we use two key parameters: odometer and price. The details of these features are below:

1. **Average Car Price Percent Change**: This is calculated across three mileage ranges(20,000-25,000 miles, 45,000-50,000 miles, and 95,000-100,000 miles). If there are missing values for the car model name in each range, they are filled with the average percentage change in each range. Since it is not possible to find the brand-new price of the car, the average price of cars with a 5,000-mile odometer reading is used as the base value. The percent change in price is then calculated for each mileage range and rescaled to a range of -1 to 1 to reflect the percent change across low, moderate, and high mileage ranges. 

2. **Number of Sold Cars**: This reflects the liquidity of each car model. By examining the number of cars sold, we can gauge how easily each model sells, providing insights into their market demand and resale potential.

These two features are good measures for determining the best cars to buy.

### Linear Regression 

Predict unknown percent change with various odometer values.

1. **Percentage Change:** 
   - Group all car models by each 5000-mile odometer range from 0 to 100,000 miles and calculate the average.
   - Calculate the percentage change from each column based on the '1-5000' mileage column.
   - Drop missing values in the '1-5000' mileage column and remove outliers.
   - Change the range of odometer values in each columns to the median odometer value in the columns.

2. **Mileage Range:** 
   - The minimum mileage of the feature is 2750 miles, and the maximum is 97500 miles.
   - The forecast will be made until a certain percentage change is reached, even if it is -100%.


## Machine learning

### K-means Clustering

To identify which cars were great choices to buy and had high resale potential, I used K-means clustering. I grouped the cars using the number of cars sold per brand in the dataset to measure liquidity and the percentage change in price across three mileage ranges to reflect depreciation. I used the Elbow Method to determine the optimal number of clusters. Each cluster was then analyzed to determine the characteristics of the cars within it, helping to identify groups that were advantageous to purchase.

### Linear Regression

Linear Regression was utilized to predict the percentage drop in sales price for each ranges of mileage. This process included preparing the data by selecting 'feature' (Value explanation is in feature engineer section) and 'percentage_change' from each range as the target variable, splitting the dataset into training and testing sets, and training the linear regression model on the training data. The model's performance was evaluated using metrics such as Mean Squared Error (MSE) and R-squared (R²). The relationship between mileage and percentage change in sales price was visualized through scatter plots, includi


## Key Findings 📈

1. **Mileage Impact**: Vehicles with mileage under 10,000 tend to have a higher resale value. For example, the Ford F150 shows a stable price increase up to 30,000 miles, after which the value drops dramatically.
2. **Model Preferences**: The Nissan Altima is a great choice for higher mileage (over 15,000 miles) due to its gradual depreciation compared to other models.
3. **Color and Resale**: Certain car colors may have a significant impact on resale value, which is explored in the analysis
4. **price table of top 20 cars K-Means model in each range**
5. **average precentgage price change

## Conclusion
   To display visualization please click here!['here']

## Usage 🛠️

To explore the analysis and findings:
1. Clone the repository: `git clone https://github.com/Kittisak-M/Best-Buys-Cars-Resale-Value.git`
2. Navigate to the project directory: `cd Best-Buys-Cars-Resale-Value`
3. Follow the instructions in the `notebooks` directory to run the analysis.


