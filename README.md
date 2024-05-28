[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/1lXY_Wlg)

# Bat Tracking Data Analysis Project

## Overview
This project focuses on developing an ETL pipeline and an interactive visualization tool for analyzing bat tracking data. The goal is to assist coaches and analysts in assessing swing quality and understanding the physical factors impacting a player's performance.

## Conceptual Model

### Components and Data Flow
The conceptual model of this project involves several key components that work together to process, analyze, and visualize bat tracking data.

1. **Data Ingestion**
   - **Raw Data Source**: The bat tracking data, including location data for bat head and handle, ball position, and metadata (e.g., pitch speed, pitch type, exit velocity, launch angle).
   - **ETL Pipeline**: Extracts data from the raw source, transforms it into a structured format, and loads it into a database.

2. **Data Transformation and Storage**
   - **Transformation**: Data cleaning and processing steps to ensure quality and consistency (e.g., filling missing values, validating ranges).
   - **Data Storage**: Structured storage of transformed data in a relational database, designed for efficient querying and analysis.

3. **Analysis and Metric Calculation**
   - **Metric Calculation**: Calculation of key performance metrics from the structured data, such as bat speed, exit velocity, launch angle, and contact quality.

4. **Interactive Visualization**
   - **Web Application**: A user-friendly interface developed using a framework like React, Dash, or Shiny, allowing users to interact with the data.
   - **Visualization Tools**: Tools to compare swings, visualize metrics, and analyze pitch impact.

### Data Flow Diagram

```plaintext
Raw Data Source (Bat tracking data)
       |
       v
   ETL Pipeline
(Extract, Transform, Load)
       |
       v
Structured Data Storage (Database)
       |
       v
 Metric Calculation (Bat speed, Exit velocity, etc.)
       |
       v
Web Application (React/Dash/Shiny)
       |
       v
Interactive Visualization (Swing comparison, Metric visualization)

## Project Structure

- **ETL Pipeline**: Extracts, transforms, and loads tracking data.
- **Interactive Visualization Tool**: Allows coaches and analysts to compare swings and evaluate swing quality metrics.

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

## DAG Diagram

![DAG Diagram](path_to_dag_diagram.png)

## Data Model Diagram

![Data Model Diagram](path_to_data_model_diagram.png)

## Metrics

- **Bat Speed**: Calculated as the speed of the bat head over time.
- **Exit Velocity**: Speed of the ball after contact.
- **Launch Angle**: Angle at which the ball leaves the bat.
- **Contact Quality**: Derived from bat and ball positions at the contact frame.

## Data Quality Checks

- **Check 1**: Ensure all frames are present for each swing.
- **Check 2**: Validate the range and consistency of location coordinates for bat head, handle, and ball.

## Interactive Visualization Tool

The web application, built with [React/Dash/Shiny], provides the following features:
- **Swing Comparison**: Compare two swings side by side, displaying characteristics and metrics.
- **Swing Quality Metrics**: Visualize metrics such as bat speed, exit velocity, and launch angle.
- **Pitch Analysis**: Display information about the pitch and its impact on the swing.

![Screenshot](path_to_screenshot.png)

## Project Spec

### Expected Outputs
- Interactive visualizations for swing comparison and analysis.
- Swing quality metrics based on bat and ball tracking data.

### Queries
- Calculate bat speed, exit velocity, and launch angle.
- Identify frames where contact occurs and assess contact quality.

### Justifications
- **Datasets**: Provided tracking data offers detailed swing and pitch information.
- **Technologies**: React for the web app, Python for ETL and data analysis, PostgreSQL for data storage.
- **Data Model**: Relational model simplifies querying and aggregation of swing metrics.

### Steps Followed
1. **Data Extraction**: Extracted raw tracking data from provided datasets.
2. **Data Transformation**: Cleaned and transformed data into structured format.
3. **Data Loading**: Loaded transformed data into a PostgreSQL database.
4. **Metric Calculation**: Calculated swing quality metrics.
5. **Visualization Development**: Built an interactive web app for visualization.
6. **Testing and Validation**: Performed unit tests and validated metrics.

### Alternatives Considered
- **Streaming Data**: Not used due to batch nature of provided data.
- **NoSQL Database**: Considered but relational model was more suitable for this use case.

### Future Expansions
- **Increased Batch Size**: Optimize ETL pipeline to handle larger datasets.
- **Streaming Source**: Adapt ETL pipeline for real-time data processing.
- **Daily Reports**: Automate daily updates and report generation.
- **Exposing Results**: Build an API to share results with other data teams.

## Data Quality Checks

- **Check 1**: Ensure completeness of frame data for each swing.
- **Check 2**: Validate positional data ranges for consistency.

## ETL Code Quality

- **Modularity**: Code is divided into functions and classes.
- **Testing**: Unit tests are implemented.
- **Linting**: Code follows PEP8 guidelines.
- **Execution**: Code runs without errors.

## Project Scoping

The project aims to provide a non-trivial use case of swing analysis using bat tracking data, fulfilling both the hackathon and capstone project goals. The design and code satisfy end-to-end requirements, from data extraction to interactive visualization.

## Conclusion

This project demonstrates the integration of data engineering and data science to provide valuable insights into baseball swings. It showcases the development of a robust ETL pipeline, thorough data quality checks, and an interactive tool for coaches and analysts.

---

### Author
Alissa Del Toro
