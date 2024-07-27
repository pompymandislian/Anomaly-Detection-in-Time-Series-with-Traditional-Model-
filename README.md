# Anomaly Detection in Time Series

This project involves using various approaches to detect anomalies in time series data. Below are the steps taken and the results obtained.

## Analysis Steps

### Step 1: Global Anomaly Detection
- **Method Used:** Interquartile Range (IQR)
- **Description:** Applied IQR to detect anomalies globally across the entire dataset.
- **Result:** 0% anomaly detected. The result suggests that IQR may not be effective for annual data due to its large range, resulting in no anomalies being detected on a global scale.

### Step 2: Daily Anomaly Detection
- **Method Used:** Rolling Window (1 Day) with IQR
- **Description:** Data was split into daily windows and anomalies were detected using IQR based on changes from one day to the next.
- **Result:** 9.2% anomaly detected. This method is more sensitive to daily changes and thus shows a higher percentage of anomalies.

### Step 3: Weekly Anomaly Detection (7 Days)
- **Method Used:** Rolling Window (7 Days) with IQR and Z-Score
- **Description:** Data was split into weekly windows, and anomalies were initially detected using IQR. As IQR yielded 0% anomalies, Z-Score with a threshold of 3 was used.
- **Result:** 23.8% anomaly detected with Z-Score. Z-Score is more effective in capturing anomalies on a weekly basis compared to IQR.

### Step 4: Monthly Anomaly Detection (30 Days)
- **Method Used:** Rolling Window (30 Days) with Z-Score
- **Description:** Data was split into monthly windows, and anomalies were detected using Z-Score based on the previous 30 days.
- **Result:** 23.8% anomaly detected. This result is consistent with the weekly Z-Score method, indicating its effectiveness for longer periods.

## Combined Results

- **Combination of Total Data, Daily, and Weekly Rolling:**
  - **Result:** 11.4% anomaly detected. Combining all methods provides a more comprehensive view of anomalies.

- **Combination of Total Data, Daily, Weekly, and Monthly Rolling:**
  - **Result:** 13.2% anomaly detected. Including monthly analysis improves the anomaly detection percentage, offering a more robust overview.

## Rationale for Combining Methods

Combining results from different time periods (daily, weekly, monthly) allows for a more comprehensive and robust detection of anomalies in the data. Different methods capture various aspects of data changes, providing a fuller and more accurate picture of anomalies.
