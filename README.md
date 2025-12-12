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

# Data Cleaning and Preparation
Filtering for AA and DL :

    df = df.filter(df.MKT_UNIQUE_CARRIER.isin("AA", "DL"))

Drop some column :

    cols_to_drop = ["MKT_CARRIER_FL_NUM", "OP_UNIQUE_CARRIER", "TAIL_NUM", "ORIGIN_AIRPORT_ID", "DEST_AIRPORT_ID"]
    df = df.drop(*cols_to_drop)

Filtering Operations :
Multiple queries were implemented to extract subsets of interest.

Key Findings:

    - Flights with departure delay > 30 minutes: 1,529,331 flights (10.19%)
    - Cancelled flights: 330,196 flights (2.20%)
    - Flights with arrival or departure delay > 60 minutes: 968,754 flights (6.46%)

These insights reflect that while cancellation rates remained relatively low, moderate to severe delays were common.

Advanced Quarterly Delay Analysis (2020–2024)

To understand seasonal patterns, the average departure delay was calculated for each airline × quarter × year combination.

Key Observations Based on the Line Graph:

    -- AA consistently shows higher delay levels than DL across most quarters.
    -- The year 2021 showed a sharp rise in delays for both airlines, with AA peaking significantly in 2021-Q3.
    -- DL remained more stable but experienced noticeable increases in 2022-Q2 and 2023-Q3.
    -- AA reached its highest levels in 2023-Q3 to 2024-Q3, approaching nearly 20 minutes average delay.
    -- DL displayed a milder trend with smaller fluctuations.

These patterns suggest that AA experienced greater operational disruptions relative to DL, particularly during high-travel seasons and post-pandemic recovery periods.

