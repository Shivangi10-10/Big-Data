# Advanced Big Data Project with Spark and Hadoop

This project analyzes student scores using Spark and Hadoop on Google Colab, showcasing various data processing, analytical, and visualization techniques. It includes advanced features such as monthly performance tracking, outlier detection, a custom performance metric, and recommendations based on performance, providing a comprehensive overview of student performance and areas for improvement.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Features](#features)
- [Project Setup](#project-setup)
- [Code Explanation](#code-explanation)
- [Insights from Visualizations](#insights-from-visualizations)

---

## Project Overview
This project involves analyzing student data across various subjects, using Spark to process and partition data for efficient handling of large datasets. The primary aim is to calculate statistics, detect outliers, measure consistency, and generate actionable recommendations. This project provides rich visual insights using Seaborn and Matplotlib.

### Key Objectives:
1. Calculate and visualize score distributions, averages, and top performers.
2. Detect score outliers to identify exceptional performances or underperforming areas.
3. Provide student-specific recommendations for improvement based on historical data.

## Technologies Used
- **Apache Spark**: For distributed data processing.
- **Google Colab**: For coding and running the project on a cloud-based environment.
- **Hadoop**: Integrated for storage management, handling large data partitions.
- **Pandas, Seaborn, and Matplotlib**: For data manipulation and visualization.
- **Python**: Primary programming language used.

## Features
### Base Features
- **Partitioned Data Storage**: Stores the student data by subject in a compressed format for optimized processing.
- **Score Calculations**: Calculates total scores and averages per student and per subject.
- **Data Visualizations**:
  - Total Score Distribution by Subject
  - Average Score per Student
  - Top Scores by Subject
  - Students with Top Scores in Each Subject
  - Correlation Heatmap for Class and Test Scores

### Advanced Features
1. **Monthly Performance Tracking**: Tracks and visualizes monthly trends for each subject if temporal data is available.
2. **Outlier Detection**: Detects significant deviations from average scores per subject.
3. **Consistency Score**: Measures how consistently a student performs within each subject.
4. **Recommendation System**: Suggests improvement areas for each student based on performance.

## Project Setup
### Prerequisites
- **Google Colab**: To run the code in a cloud environment.
- **PySpark**: Should be pre-installed in Google Colab; otherwise, install with `!pip install pyspark`.
- **Additional Libraries**: Pandas, Seaborn, Matplotlib.

### Instructions
1. Upload your dataset file (`CSV` format) containing student scores and subjects in Google Colab.
2. Run the code provided in `main.py`, ensuring the uploaded dataset has the columns: `Student`, `Subject`, `Class Score`, `Test Score`, and optionally `Date`.
3. Visualizations and insights will be generated automatically as per the code.

## Code Explanation
### 1. Data Loading and Partitioning
- The `load_csv` function uploads and reads the CSV file into a Spark DataFrame.
- Data is partitioned by subject and stored in a Parquet format with `gzip` compression for optimal storage and access speeds.

### 2. Data Processing and Calculations
- **Total Score**: Calculated as a sum of `ClassScore` and `TestScore`.
- **Statistics**: Aggregated metrics like average and maximum scores are calculated per student and subject.

### 3. Advanced Feature Implementations
- **Monthly Performance Tracking**: Aggregates monthly averages if the `Date` column is available.
- **Outlier Detection**: Uses standard deviation to detect significant deviations from average scores.
- **Consistency Score**: A custom metric that highlights the stability of a student's performance.
- **Recommendation System**: Generates actionable insights by identifying subjects where students score below the average.

### 4. Data Visualization
- Uses `Matplotlib` and `Seaborn` to create various plots:
  - **Histogram**: Distribution of total scores across subjects.
  - **Bar Plots**: Average score per student, top scores by subject.
  - **Scatter Plot**: Shows students with top scores in each subject.
  - **Box Plot**: Consistency score by subject.
  - **Heatmap**: Shows correlations among `ClassScore`, `TestScore`, and `TotScore`.

## Insights from Visualizations
- **Distribution Analysis**: Identify subjects with high or low score variance.
- **Student Averages**: Determine top-performing and underperforming students.
- **Top Scores by Subject**: Highlights subjects with the highest and lowest performance.
- **Consistency Scores**: Measures each student's reliability in scoring.
- **Recommendations**: Helps students and teachers focus on subjects needing improvement.

---


