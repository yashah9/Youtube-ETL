# YouTube Data Analysis Project

## Overview
This project focuses on analyzing YouTube trending video data to provide actionable insights for marketing campaigns. By identifying key factors that influence likes and engagement, this project aids in optimizing marketing strategies for businesses. The project utilizes various AWS services for data storage, transformation, and visualization.

## Table of Contents
1. [Dataset](#dataset)
2. [Technologies Used](#technologies-used)
3. [Objectives](#objectives)
4. [Workflow and Steps](#workflow-and-steps)
   - [1. Data Storage](#1-data-storage)
   - [2. Data Transformation](#2-data-transformation)
   - [3. Data Analytics](#3-data-analytics)
5. [Insights (focused on US-based content)](#insights-focused-on-us-based-content)
6. [Marketing Use Case](#marketing-use-case)
7. [Limitations](#limitations)
   
## Dataset
- **Source**: [Kaggle - YouTube New](https://www.kaggle.com/datasets/datasnaek/youtube-new)
- **Description**: The dataset contains metadata on trending YouTube videos across multiple countries, including video titles, categories, tags, views, likes, dislikes, and comment status.

## Technologies Used
- **AWS S3**: Data storage.
- **AWS Glue**: Schema generation and ETL jobs.
- **AWS Lambda**: Testing data pipelines.
- **AWS Athena**: Querying data.
- **Amazon QuickSight**: Data visualization and dashboarding.

## Objectives
- Transform raw JSON data into an optimized format for analytics.
- Extract insights to identify:
  - Top-performing categories and channels.
  - Impact of specific words (tags) on video likes.
  - Trends in user engagement based on video content.

## Workflow and Steps

### 1. Data Storage
- **Initial Format**: The raw dataset in JSON format was uploaded to an Amazon S3 bucket.
- **Reason**: S3 provides scalable and durable storage for large datasets.

### 2. Data Transformation
- **Format Conversion**: The JSON dataset was converted to **Parquet** format.
  - **Why Parquet?**
    - More efficient for analytical queries.
    - Compatible with AWS Glue crawlers and Spark jobs.

- **AWS Glue**:
  - **Crawler**: Automatically generated a schema for the transformed Parquet files.
  - **ETL Job**: Processed and transformed data for analytics.
    
- **Testing Endpoints**: Used **AWS Lambda** functions to test and validate data transformation steps for integrity and correctness.

![cr](https://github.com/user-attachments/assets/c73d485b-ab47-4995-8555-5a141979c7e3)


### 3. Data Analytics
- **Amazon Athena**:
  - Queried the transformed Parquet files for preliminary analysis.
  - Extracted insights such as average likes, top tags, and category-wise performance.

- **Visualization**: Leveraged **Amazon QuickSight** for creating interactive dashboards. Key visualizations included:
  - **Likes by Category**: Identified which video categories generate the most likes.
  - **Views and Likes**: Highlighted the correlation between views and likes.
  - **Trending Channels**: Displayed channels with the highest number of trending videos.
  - **Impact of Tags**: Created a word cloud to show the most popular tags associated with high engagement.
![de-y](https://github.com/user-attachments/assets/1d1a9bd3-a28b-4847-976a-2d5a98aadec0)

## Insights (focused on US based content)
1. **Top Video Categories**:
   - Categories like *Entertainment*, *Music*, and *People & Blogs* had the highest likes and engagement.

2. **Impact of Tags**:
   - Words like *"tutorial"*, *"funny video"*, *"makeup"*, and *"music"* were consistently associated with high engagement.

3. **Comments Enabled vs Disabled**:
   - Videos with enabled comments showed slightly higher likes on average.

4. **Trending Channels**:
   - Channels such as *NBA*, *Screen Junkies*, and *Late Night Talk Shows* dominated the trending section.

---

## Marketing Use Case
The marketing team can:
- **Campaign Optimization**: Focus on creating content in top-performing categories.
- **Keyword Strategy**: Utilize popular tags like *"tutorial"* and *"funny"* to increase engagement.
- **Channel Partnerships**: Collaborate with trending channels for targeted campaigns.

---

## Limitations
- Dataset only includes trending videos, which may not represent all YouTube content.
- Insights are limited to the data provided and specific countries listed in the dataset.
