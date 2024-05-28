[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/1lXY_Wlg)

# Bat Tracking Data Analysis Project

## Overview

This project was developed for a hackathon focused on analyzing bat tracking data to assess swing quality and understand factors impacting a player's performance. It also serves as a data engineering capstone project, demonstrating the creation of an ETL pipeline, data quality checks, and an interactive visualization tool.

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
