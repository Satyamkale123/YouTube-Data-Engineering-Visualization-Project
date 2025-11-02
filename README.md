# YouTube Data Engineering & Visualization Project

This project demonstrates an **end-to-end cloud-based data pipeline** for processing and visualizing **YouTube video data**. The pipeline leverages **AWS services** for data processing, and **Power BI** for interactive visualizations. The dataset used for this project is based on YouTube’s **daily trending video statistics** across multiple regions.

## Overview

The goal of this project is to process large-scale, structured and semi-structured YouTube data, perform analysis, and present key insights using **Power BI**. The pipeline starts from **data ingestion**, followed by **data cleaning**, **ETL (Extract, Transform, Load)** processes, and ends with **visualizations** to help stakeholders make data-driven decisions.

### **Key Insights:**
- **Most Popular Regions**: Identifying the regions with the highest engagement.
- **Top Video Categories**: Analyzing which video categories (e.g., Music, Entertainment) dominate by region.
- **Trends Over Time**: Analyzing growth in views and engagement across different regions and categories.
- **Engagement Analysis**: Understanding which regions or categories have the highest engagement (likes per view).

---

## Architecture Diagram

![Architecture Diagram](architecture.jpeg)

### **Key Components:**
- **Data Ingestion**: YouTube dataset from Kaggle, uploaded to AWS **S3** (raw layer).
- **ETL Pipeline**: AWS **Glue** for transforming raw data and **AWS Lambda** for processing and cleaning data.
- **Data Querying**: AWS **Athena** for querying the data stored in S3 (in Parquet format).
- **Data Visualization**: **Power BI** to create interactive dashboards and insights based on the processed data.

---

## Tech Stack

### **AWS Services**:
1. **S3 (Simple Storage Service)**:
   - Used to store raw and processed YouTube data (CSV and Parquet files).
   - Organized by region (CA, DE, FR, etc.) for easy access.

2. **AWS Lambda**:
   - Used for **real-time data transformation**. Lambda functions read JSON data from S3, process it, and store it back in S3 in a cleansed Parquet format.

3. **AWS Glue**:
   - Used for **ETL (Extract, Transform, Load)** operations. It transforms raw data into structured formats and updates the **AWS Glue Catalog**.

4. **AWS Athena**:
   - Serverless query service that allows querying **S3**-stored data without loading it into databases.
   - **SQL queries** are used to extract meaningful insights from the data.

5. **Power BI**:
   - Used to create interactive dashboards. Connects directly to **AWS Athena** to query the cloud data and visualize it in real-time.

---

## How the Pipeline Works

1. **Data Ingestion**:
   - Data is sourced from the **YouTube Trending Data** dataset available on **Kaggle**. The raw data is uploaded to **AWS S3** in CSV format for multiple regions (Canada, US, Germany, etc.).

2. **Data Cleaning and Transformation**:
   - AWS **Glue** crawlers scan the raw data in **S3** and register it in the **AWS Glue Data Catalog**.
   - AWS **Lambda** functions are used to clean and transform raw JSON files into **Parquet format** for better query performance and storage efficiency.

3. **Data Querying**:
   - The cleaned and transformed data is stored in **S3**. We use **AWS Athena** to run **SQL queries** directly on the Parquet files in **S3**.

4. **Data Visualization**:
   - Data from **AWS Athena** is then connected to **Power BI** to create **interactive dashboards**. The dashboards provide insights into the **engagement** and **viewership** trends for YouTube videos across regions and categories.



## Instructions

1. **Set up AWS Services**:
   - Follow the architecture diagram to set up **AWS S3**, **Glue**, **Lambda**, and **Athena**.
   - Upload the raw data to **S3** and configure the **Glue Crawler** to read and register the data.
   - Set up **AWS Lambda** functions to clean the raw JSON data and store it in Parquet format.

2. **Run AWS Glue Jobs**:
   - Use **AWS Glue** for transforming raw data into structured formats.
   - Use **AWS Athena** to query the processed data.

3. **Power BI Setup**:
   - Connect **Power BI** to **AWS Athena** to fetch the transformed data.
   - Build dashboards using the aggregated data (e.g., Total Views by Region, Likes vs Dislikes).

---

## Dashboard Link

- **Link to Power BI Dashboard** (if published to Power BI Service or shared online):
  
  [Power BI YouTube Dashboard](link_to_dashboard)

---

## Conclusion

This project demonstrates the full scope of working with cloud-based data engineering and analytics. By using **AWS services** and **Power BI**, we've created a **scalable, real-time data pipeline** that processes YouTube video data and provides valuable insights into global video engagement trends.

---

### **Key Takeaways **:
- **Data Engineering**: Showcased skills in **AWS Lambda**, **Glue**, **Athena**, and **S3** for cloud-based data processing and storage.
- **Data Analysis**: Used **Power BI** to create interactive dashboards that offer **insights** into **video engagement** and **viewership** trends across regions.
- **Cloud Integration**: Demonstrated the ability to integrate AWS services with data visualization tools to provide actionable business insights.

Feel free to **clone the repository**, follow the instructions, and explore how the data pipeline is built and visualized.

---

### **Future Enhancements**:
- Add more regions or countries to analyze.
- Incorporate **Machine Learning models** to predict video trends based on historical data.
- Integrate **real-time data processing** using AWS **Kinesis** for live video analytics.

---

This **README** should help recruiters understand the **entire workflow** and **technologies used** in your project, while also providing them a detailed view of how the data pipeline is built and visualized.


