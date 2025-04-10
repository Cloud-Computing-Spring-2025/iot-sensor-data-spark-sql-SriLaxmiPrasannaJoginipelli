# IoT Sensor Data Analysis with Spark SQL

## Objective

This assignment focuses on analyzing synthetic IoT sensor data using PySpark and Spark SQL. You'll learn to load and explore data, filter and aggregate values, work with time-based features, use window functions for ranking, and create pivot tables for insights.

Each task saves its output as a `.csv` file.

---

## ⚙️ Setup Instructions

Make sure Python and pip are installed. To install run the following commands:

```bash
python --version
pip install pyspark
pip install faker
```
## Task1: Load & Basic Exploration

### Objective:

- Load sensor_data.csv using Spark.
- Create a temp view sensor_readings.
- Perform basic queries:
- Show the first 5 rows.
- Count total records.
- Retrieve distinct locations or sensor types.

### Output:

- task1_output.csv

### Sample Output :

+---------+-------------------+-----------+--------+-------------------+-----------+
|sensor_id|timestamp          |temperature|humidity|location           |sensor_type|
+---------+-------------------+-----------+--------+-------------------+-----------+
|1007     |2025-03-28 08:15:22|34.5       |72.3    |BuildingA_Floor1   |TypeA      |
...



## Task2: Filtering & Simple Aggregations
### Objective:

- Filter temperature values outside the range of 18–30.
- Count how many are in-range vs out-of-range.
- Group by location and compute:
-- Avg temperature
-- Avg humidity

### Output:

- task2_output.csv

### Sample Output:

+-------------------+-----------------+------------------+
|location           |avg_temperature  |avg_humidity      |
+-------------------+-----------------+------------------+
|BuildingA_Floor1   |25.9             |63.4              |
...

## Task 3: Time-Based Analysis
### Objective:

- Convert timestamp column to proper timestamp datatype.
- Extract hour_of_day from timestamp.
- Group by hour and calculate average temperature.
- Identify the hottest hour.
### Output:

- task3_output.csv

### Sample Output:

+-----------+-----------+
|hour_of_day|avg_temp   |
+-----------+-----------+
|0          |25.4       |
|1          |26.8       |
...
## Task 4: Window Function
### Objective:

- Compute average temperature for each sensor.
- Use a window function (RANK or DENSE_RANK) to rank sensors by avg temperature.
- Display the top 5 sensors.
### Output:

- task4_output.csv

### Sample Output:

+---------+-----------+---------+
|sensor_id|avg_temp   |rank_temp|
+---------+-----------+---------+
|1010     |30.2       |1        |
...
## Task 5: Pivot Table & Interpretation
### Objective:

- Create a pivot table:
- Rows → location
- Columns → hour_of_day (0–23)
- Values → avg temperature
- Identify which (location, hour) has the highest avg temperature.
### Output:

- task5_output.csv
  
### Sample Output:

location           | 0    | 1    | 2    | ... | 23
---------------------------------------------------
BuildingA_Floor1   |25.6  |24.9  |23.7  | ... |26.3
BuildingB_Floor2   |28.1  |26.2  |26.0  | ... |28.5


## Commands to Run
```bash
python data_generator.py
python task1.py
python task2.py
python task3.py
python task4.py
python task5.py
```




