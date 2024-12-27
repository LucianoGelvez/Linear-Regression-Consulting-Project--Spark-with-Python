# Linear Regression Consulting Project



This project implements a linear regression model to predict the number of crew members required for cruise ships, based on various ship characteristics. This exercise is part of the course "Spark and Python for Big Data with PySpark".

## Project Overview

This project was created as part of a consulting task for Hyundai Heavy Industries, one of the world's largest ship manufacturers. The goal is to develop a predictive model that can estimate the number of crew members needed for a given cruise ship, considering several features.

## Data Description

The dataset contains measurements of ship size, capacity, crew, and age for 158 cruise ships. The data is saved in a CSV file called `cruise_ship_info.csv`.

### Variables/Columns

- **Ship Name**: Name of the ship
- **Cruise Line**: Name of the cruise line
- **Age (as of 2013)**: Age of the ship
- **Tonnage (1000s of tons)**: Tonnage of the ship
- **Passengers (100s)**: Number of passengers
- **Length (100s of feet)**: Length of the ship
- **Cabins (100s)**: Number of cabins
- **Passenger Density**: Passenger density
- **Crew (100s)**: Number of crew members

## Objective

The objective of this project is to create a regression model that will help predict how many crew members will be needed for future ships. The client also mentioned that they have found that particular cruise lines will differ in acceptable crew counts, so it is most likely an important feature to include in your analysis.

## Methodology

The project uses the following steps:

1.  **Data Loading and Preparation:**
    *   The data is loaded from a CSV file into a Spark DataFrame.
    *   The schema of the data is printed to ensure correct data loading.
2.  **Feature Engineering:**
    *   The categorical feature `Cruise_line` is converted into numerical values using `StringIndexer`.
    *   The numerical features are assembled into a single feature vector using `VectorAssembler`.
3.  **Linear Regression Model:**
    *   A linear regression model is trained on a 70% split of the data for training and 30% for testing.
    *   The model is trained on the training data using the 'crew' column as the label.
4.  **Model Evaluation:**
    *   The model's performance is evaluated using metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R-squared (R2).


## Results

The model was evaluated using the test dataset, and the following metrics were obtained:

- **Mean Absolute Error**: 3.741997604310364e-15
- **Root Mean Squared Error**: 1.2731741044904679
- **R2**: 0.8729579576038606


## Conclusion

The linear regression model performs well in predicting the number of crew members required for future ships based on the given features. The inclusion of the `Cruise_line` feature, indexed as `Cruise_line_num`, was crucial in improving the model's performance.

## Repository Structure

- `Linear_Regression_Consulting_Project.ipynb`: Jupyter notebook containing the entire project code and analysis.
- `cruise_ship_info.csv`: Dataset used for the project.

## Usage

To run this project, ensure that you have PySpark installed and that you have access to the dataset `cruise_ship_info.csv`. You can run the code using the jupyter notebook `Linear_Regression_Consulting_Project.ipynb`

1.  **Set Up:** Ensure you have a Spark environment running.
2.  **Data:** Place the `cruise_ship_info.csv` in the same directory as the script or adjust the file path in the code.
3.  **Run:** Execute the Python script.

## Code and Libraries

The code is implemented using PySpark and the following libraries:

-   `pyspark.sql.SparkSession`: For Spark session management.
-   `pyspark.ml.regression.LinearRegression`: For the linear regression model.
-   `pyspark.ml.feature.StringIndexer`: For converting string-type categorical data to numbers.
-   `pyspark.ml.feature.VectorAssembler`: For assembling features into a single vector.
-   `pyspark.ml.evaluation.RegressionEvaluator`: For regression evaluation metrics



