# porter_nn-regression

## Porter Delivery Time Estimation (Neural Network Regression)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/raghav1saboo/porter_nn-regression/blob/main/Porter_Delivery_Time_Estimation.ipynb)

## Overview

This repository contains a Jupyter Notebook that implements a neural network regression model to estimate food delivery times for Porter, India's largest marketplace for intra-city logistics. The project aims to provide accurate delivery time predictions to customers based on order details, restaurant information, and delivery partner availability.

Porter works with numerous restaurants and needs an efficient way to manage customer expectations by providing reliable estimated delivery times.

## Problem Statement

Given various attributes related to an order (e.g., restaurant category, order protocol, items, prices, and delivery partner status), the goal is to predict the `actual_delivery_time` as accurately as possible. This estimation will help Porter optimize ad placement and improve customer satisfaction.

## Dataset

The dataset used for this project is named `Porter data` (likely `[porter_data.csv](https://drive.google.com/file/d/1kkgBGldeswHBgVKEJiqqG7VZvqZNMc-5/view)` or similar, assumed to be available in the repository). Each row corresponds to a unique delivery.

## Data Dictionary

| Feature                             | Description                                                                                                                                              |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `market_id`                         | Integer ID for the market where the restaurant is located.                                                                                               |
| `created_at`                        | The timestamp at which the order was placed.                                                                                                             |
| `actual_delivery_time`              | The timestamp when the order was delivered (used to derive the target variable).                                                                         |
| `store_primary_category`            | Category for the restaurant (e.g., "fast food", "pizza").                                                                                                |
| `order_protocol`                    | Integer code value for order protocol (how the order was placed, e.g., through Porter app, call to restaurant, pre-booked, third-party).                 |
| `total_items`                       | Total number of items in the order.                                                                                                                      |
| `subtotal`                          | Final price of the order.                                                                                                                                |
| `num_distinct_items`                | The number of distinct items in the order.                                                                                                               |
| `min_item_price`                    | Price of the cheapest item in the order.                                                                                                                 |
| `max_item_price`                    | Price of the costliest item in the order.                                                                                                                |
| `total_onshift_partners`            | Number of delivery partners on duty at the time the order was placed.                                                                                    |
| `total_busy_partners`               | Number of delivery partners attending to other tasks.                                                                                                    |
| `total_outstanding_orders`          | Total number of orders to be fulfilled at the moment.                                                                                                    |
| `estimated_store_to_consumer_driving_duration` | Approximate travel time from the restaurant to the customer.                                                                                     |

## Concepts & Techniques Used

This project involves a comprehensive data science workflow, including:

* **Exploratory Data Analysis (EDA):**
    * Understanding data structure and characteristics.
    * Visualizing distributions (`Countplots`, `scatterplots`).
    * Identifying and handling outliers.
* **Data Preprocessing & Feature Engineering:**
    * **Target Column Creation:** Calculating `time_taken` (delivery duration in minutes) from `created_at` and `actual_delivery_time`.
    * Extracting time-based features: `hour_of_day` and `day_of_the_week`.
    * Handling null values.
    * Encoding categorical columns (e.g., one-hot encoding).
* **Data Splitting & Scaling:**
    * Splitting the dataset into training and testing sets.
    * Scaling numerical features for optimal neural network performance.
* **Neural Network Regression:**
    * Designing and implementing a simple neural network.
    * Experimenting with different network configurations.
    * Understanding and tuning hyperparameters (activation functions, optimizers, epochs).
    * Training the neural network.
    * Evaluating model performance using metrics like Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE).

## Getting Started

1.  Clone this repository to your local machine:
    ```bash
    git clone [https://github.com/raghav1saboo/porter_nn-regression.git](https://github.com/raghav1saboo/porter_nn-regression.git)
    ```
2.  Navigate to the repository directory:
    ```bash
    cd porter_nn-regression
    ```
3.  Ensure you have the necessary data file (e.g., `porter_data.csv`) in the root of the repository.
4.  Open and run the Jupyter Notebook `Porter_Delivery_Time_Estimation.ipynb`.

## Contributing

Contributions are welcome! If you have any suggestions or improvements, feel free to open an issue or submit a pull request.

## License

[Optional: Add a license if you have one, e.g., MIT License]
