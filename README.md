# Best Strategy to Buy Used Car Considering Value, Worth and Deprecation  🚗📈



## Project Overview

In this project, we explore the Vehicle Sales dataset to identify the best brand-new or used cars to buy based on their potential resale value and low depreciation. The goal is to provide insights and data-driven recommendations for consumers and dealerships looking to make informed decisions when purchasing vehicles. By analyzing factors such as model popularity, mileage, car color, and age, we aim to pinpoint cars that hold their value well over time.


## Table of Contents

- [Introduction](#introduction)
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

## Dataset 📊

### Dataset Description:

The "Vehicle Sales and Market Trends Dataset" provides a comprehensive collection of information pertaining to the sales transactions of various vehicles. This dataset encompasses details such as the year, make, model, trim, body type, transmission type, VIN (Vehicle Identification Number), state of registration, condition rating, odometer reading, exterior and interior colors, seller information, Manheim Market Report (MMR) values, selling prices, and sale dates.

The dataset can be found [here](https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data/data).

### Column Descriptions:

- **year**: The year the vehicle was manufactured.
- **make**: The manufacturer or brand of the vehicle (e.g., Ford, Toyota).
- **model**: The specific model of the vehicle (e.g., F-150, Camry).
- **trim**: The specific trim or version of the vehicle model (e.g., SE, Sport).
- **body**: The body type of the vehicle (e.g., sedan, SUV, truck).
- **transmission**: The type of transmission the vehicle uses (e.g., automatic, manual).
- **VIN**: The Vehicle Identification Number, a unique code to identify individual motor vehicles.
- **state**: The state where the vehicle is registered or sold.
- **condition**: The condition rating of the vehicle (e.g., excellent, good, fair).
- **odometer**: The mileage of the vehicle at the time of sale.
- **color**: The exterior color of the vehicle.
- **interior**: The interior color of the vehicle.
- **seller**: Information about the seller or dealership.
- **MMR**: Manheim Market Report values, which provide estimated wholesale prices based on the vehicle's condition and other factors.
- **sellingprice**: The actual selling price of the vehicle.
- **saledate**: The date the vehicle was sold.

This dataset is used to perform detailed analyses and derive actionable insights.


## Data Analysis 🔍

The analysis focuses on several key aspects:
- **Model Popularity**: Identifying which car models are popular and retain their value.
- **Mileage**: Analyzing how mileage affects the resale value of cars.
- **Car Color**: Investigating the impact of car color on resale value.
- **Age of Vehicle**: Understanding how the age of the vehicle correlates with its depreciation.
## Feature Engineer
    K-Means Clustering:Average percentchange in 3 range rescale each range to -1,1 then plus these value together
    K-Means Clustering: Number of Car solds
    Linear Regression


## Machine learning
I want to know which cars are great choice to buy so I use K-means clustering to group car by using number of car sold brand name in the dataset to measure liquidity and percent change in 3 ranges which reflex depreciation or price changing in each range

metric to measure Linear R² and 
2 technique has been used in this project


K-Means Clustering was used to identify which groups(Elbow method used to indicate number of cluster) of cars are good to buy by considering factors such as liquidity and the decrease in sales price in each mileage.Each cluster was then analyzed to determine the characteristics of cars within it, helping to identify groups that are advantageous to purchase.

Linear Regression was utilized to predict the percentage drop in sales price for each ranges of mileage. This process included preparing the data by selecting 'feature' (Value explanation is in feature engineer section) and 'percentage_change' from each range as the target variable, splitting the dataset into training and testing sets, and training the linear regression model on the training data. The model's performance was evaluated using metrics such as Mean Squared Error (MSE) and R-squared (R²). The relationship between mileage and percentage change in sales price was visualized through scatter plots, includi


## Key Findings 📈

1. **Mileage Impact**: Vehicles with mileage under 10,000 tend to have a higher resale value. For example, the Ford F150 shows a stable price increase up to 30,000 miles, after which the value drops dramatically.
2. **Model Preferences**: The Nissan Altima is a great choice for higher mileage (over 15,000 miles) due to its gradual depreciation compared to other models.
3. **Color and Resale**: Certain car colors may have a significant impact on resale value, which is explored in the analysis
4. **price table of top 20 cars K-Means model in each range**
5. **average precentgage price change

## Conclusion


## Usage 🛠️

To explore the analysis and findings:
1. Clone the repository: `git clone https://github.com/Kittisak-M/Best-Buys-Cars-Resale-Value.git`
2. Navigate to the project directory: `cd Best-Buys-Cars-Resale-Value`
3. Follow the instructions in the `notebooks` directory to run the analysis.


