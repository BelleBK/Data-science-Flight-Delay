# Data-science-Flight-Delay
Big Data project Report

This project analyzes flight delay data for two major U.S. airlines: American Airlines (AA) and Delta Airlines (DL). Using PySpark, the dataset was cleaned, filtered, and transformed to explore delay patterns. Several operations such as filtering, aggregation, sorting, and window functions were applied to understand airline performance. The results show that AA has higher average delays than DL, and a small portion of flights experience severe delay or cancellation. This report documents the process and insights gained.

# Introduction
Flight delays impact customer satisfaction, airline costs, and airport operations. Big datasets like flight records are good examples for data processing using distributed systems such as Apache Spark.

The goal of this project is to use PySpark to:
    
    - Clean and prepare the dataset
    - Apply filtering and aggregation
    - Perform window and aggregate window operations
    - Analyze patterns between the two selected airlines (AA and DL)

This project demonstrates practical skills in handling large datasets and extracting insights using PySpark.

# Dataset Description

The dataset contains U.S. domestic flight records with information about:

    - Date, time, airline codes
    - Departure and arrival delays
    - Distance
    - Cancellation and diversion status

Columns Dropped
To simplify analysis, the following columns were removed because they are not required:

    - MKT_CARRIER_FL_NUM
    - OP_UNIQUE_CARRIER
    - TAIL_NUM
    - ORIGIN_AIRPORT_ID
    - DEST_AIRPORT_ID

Subset Used
Only flights from two airlines were included:
- American Airlines (AA)
- Delta Airlines (DL)

This filtered the dataset to 15,006,877 rows.
