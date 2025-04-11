# IoT Sensor Data with Spark SQL

## Objective
This assignment focuses on analyzing IoT sensor data using **Spark SQL**. You'll work on tasks like loading CSVs, querying with SQL, filtering data, applying aggregations, using window functions, and creating pivot tables — all on structured sensor data.

---

## 📂 Dataset
- **sensor_data.csv** — Contains simulated IoT sensor readings, including:
  - `sensor_id`, `timestamp`, `temperature`, `humidity`, `location`, and `sensor_type`

---

## Tasks Implemented

### Task 1: Load & Basic Exploration

**Objective:**
- Load `sensor_data.csv` using Spark
- Create a temporary view: `sensor_readings`
- Show the first 5 rows, count total records, and list distinct locations or sensor types

**Expected Output:**
CSV file: `task1_output.csv`


---

### Task 2: Filtering & Simple Aggregations

**Objective:**
- Filter temperature values outside the range 18–30
- Count in-range vs. out-of-range values
- Group by `location` and compute:
  - Average temperature
  - Average humidity

**Expected Output:**
CSV file: `task2_output.csv`


---

### Task 3: Time-Based Analysis

**Objective:**
- Convert the `timestamp` string to a proper timestamp type
- Extract `hour_of_day` (0–23)
- Group by hour and calculate average temperature
- Identify the hottest hour

**Expected Output:**
CSV file: `task3_output.csv`


---

### Task 4: Window Function

**Objective:**
- Compute average temperature for each sensor
- Rank sensors by average temperature using a window function (`RANK()` or `DENSE_RANK()`)

**Expected Output:**
CSV file: `task4_output.csv`


---

### Task 5: Pivot & Interpretation

**Objective:**
- Create a pivot table:
  - Rows: `location`
  - Columns: `hour_of_day` (0–23)
  - Values: Average temperature
- Identify the (location, hour) with the highest temperature
- Interpret trends in heat distribution

**Expected Output:**
CSV file: `task5_output.csv`


---

## Commands to Run

### Python & Library Setup
```bash
python --version
pip install pyspark
pip install faker
```

### Generate data
```bash

python data_generator.py

```
### Run tasks

```bash
python task1.py
```
```bash
python task2.py
```
```bash
python task3.py
```
```bash
python task4.py
```
```bash
python task5.py
```






