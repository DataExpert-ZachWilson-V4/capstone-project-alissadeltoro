[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/1lXY_Wlg)

# Batting Metrics Anomaly Detection

## Overview
This project aims to identify anomalies in batting performance metrics to provide actionable insights for coaches and the front office of a baseball team. By detecting unusual patterns in player performance, the project helps in making informed decisions on player management, training focus, and game strategies.

## Problem Statement
In baseball, player performance can fluctuate due to various factors such as fatigue, injury, changes in technique, or external conditions. Identifying these anomalies early can prevent prolonged slumps, optimize player performance, and improve overall team strategy. This project seeks to detect such anomalies using advanced data analytics and machine learning techniques.

## Project Goals
1. **Anomaly Detection**: Implement advanced algorithms to detect anomalies in batting performance metrics.
2. **Real-Time Insights**: Provide real-time analysis and updates on player performance.
3. **Actionable Recommendations**: Generate actionable insights and recommendations for coaches and the front office.
4. **Comprehensive Visualization**: Develop interactive dashboards to visualize anomalies and performance trends.
  
## Conceptual Model

### Data Sources
To meet the project goals, we will utilize the following data sources:
1. **Statcast Data** (API, CSV): Detailed pitch-by-pitch data including player performance metrics.
2. **Weather Data** (API): Historical and real-time weather conditions affecting gameplay.
3. **Stadium Data** (CSV): Information about stadium conditions such as dimensions and turf type.
4. **Player Health Data** (Public CSV): Records of player injuries and health status.
5. **Social Media Sentiment Data** (API): Sentiment analysis of player and team mentions on social media platforms.

### Technical Stack
- Data Ingestion: Apache Kafka for real-time data streaming, APIs for data collection.
- Data Storage: Amazon S3 for raw data storage, PostgreSQL for relational data, Amazon Redshift for data warehousing.
- Data Processing: Apache Spark for ETL processes, Python for data manipulation and anomaly detection.
- Data Quality Checks: Great Expectations, dbt tests.
- Machine Learning: Scikit-learn, TensorFlow for anomaly detection algorithms.
- Visualization: Tableau, Streamlit for interactive dashboards.
- Version Control: GitHub for code and documentation.

### Components and Data Flow
The conceptual model of this project involves several key components that work together to process, analyze, and visualize batting data to detect anomalies.

1. **Data Collection**
   - **Raw Data Source**: The bat tracking data, including location data for bat head and handle, ball position, and metadata (e.g., pitch speed, pitch type, exit velocity, launch angle).
   - **ETL Pipeline**: Extracts data from the raw source, transforms it into a structured format, and loads it into a database.

2. **Data Transformation and Storage**
   - **Transformation**: Data cleaning and processing steps to ensure quality and consistency (e.g., filling missing values, validating ranges).
   - **Data Storage**: Structured storage of transformed data in a relational database, designed for efficient querying and analysis.

3. **Analysis and Metric Calculation**
   - **Metric Calculation**: Calculation of key performance metrics from the structured data, such as bat speed, exit velocity, launch angle, and contact quality.
      - **Bat Speed**: Calculated as the speed of the bat head over time.
      - **Exit Velocity**: Speed of the ball after contact.
      - **Launch Angle**: Angle at which the ball leaves the bat.
      - **Contact Quality**: Derived from bat and ball positions at the contact frame.

4. **Interactive Visualization**
   - **Web Application**: A user-friendly interface developed using a framework like React, Dash, or Shiny, allowing users to interact with the data.
      - **Swing Comparison**: Compare two swings side by side, displaying characteristics and metrics.
      - **Swing Quality Metrics**: Visualize metrics such as bat speed, exit velocity, and launch angle.
      - **Pitch Analysis**: Display information about the pitch and its impact on the swing.
   - **Visualization Tools**: Tools to compare swings, visualize metrics, and analyze pitch impact.

### Data Flow Diagram

```plaintext
                +---------------------+
                |   Data Collection   |
                +---------------------+
                          |
                          v
+------------------+   +----------------+   +----------------+   +---------------------+
|  Statcast Data   |   |  Weather Data  |   |  Stadium Data  |   |  Player Health Data |
+------------------+   +----------------+   +----------------+   +---------------------+
       |                     |                    |                      |
       v                     v                    v                      v
+------------------+   +----------------+   +----------------+   +---------------------+
|  Raw Data Store  |   |  Raw Data Store|   |  Raw Data Store|   |  Raw Data Store     |
+------------------+   +----------------+   +----------------+   +---------------------+
                          |                    |                      |
                          v                    v                      v
                   +------------------------------------------------------+
                   |               Data Integration Layer                |
                   +------------------------------------------------------+
                          |
                          v
                +---------------------+
                |    Data Warehouse   |
                +---------------------+
                          |
                          v
                +---------------------+
                |   Data Processing   |
                |      (ETL)          |
                +---------------------+
                          |
                          v
              +------------------------+
              |   Anomaly Detection    |
              +------------------------+
                          |
                          v
                +---------------------+
                |     Data Models     |
                +---------------------+
                          |
                          v
                +---------------------+
                |  Visualization Layer |
                +---------------------+
                          |
                          v
                +---------------------+
                |    Dashboards       |
                +---------------------+
                          |
                          v
                +---------------------+
                |  Actionable Insights|
                +---------------------+
```

## Schemas

### Raw Data Schema
The raw data consists of swing tracking data sampled at 30 frames per second, including:
- Bat head and handle positions
- Ball position
- Metadata (e.g., pitch speed, pitch type, exit velocity, launch angle)

### Transformed Data Schema
After transformation, the data is structured into relational tables:
- **Swings**: `swing_id`, `frame_number`, `bat_head_x`, `bat_head_y`, `bat_handle_x`, `bat_handle_y`, `ball_x`, `ball_y`
- **Metadata**: `swing_id`, `pitch_speed`, `pitch_type`, `exit_velocity`, `launch_angle`

## ETL Considerations

### DAG Diagram

[PLACEHOLDER]

### Data Model Diagram

[PLACEHOLDER]

## Data Quality Checks

- **Check 1**: Ensure completeness of frame data for each swing.
- **Check 2**: Ensure all frames are present for each swing.
- **Check 3**: Validate positional data ranges for consistency.
- **Check 4**: Validate the range and consistency of location coordinates for bat head, handle, and ball.

## ETL Code Quality

- **Modularity**: Code is divided into functions and classes.
- **Testing**: Unit tests are implemented.
- **Linting**: Code follows PEP8 guidelines.
- **Execution**: Code runs without errors.

## Conclusion

### Alternatives Considered
- **Streaming Data**: Not used due to batch nature of provided data.
- **NoSQL Database**: Considered but relational model was more suitable for this use case.

### Future Expansions
- **Increased Batch Size**: Optimize ETL pipeline to handle larger datasets.
- **Streaming Source**: Adapt ETL pipeline for real-time data processing.
- **Daily Reports**: Automate daily updates and report generation.
- **Exposing Results**: Build an API to share results with other data teams.

---

### Author
Alissa Del Toro
