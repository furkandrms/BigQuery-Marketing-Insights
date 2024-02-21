# Analysis and Model Development with Marketing Data from BigQuery

## Introduction
This project focuses on analyzing user activities on an e-commerce platform, leveraging data from BigQuery to enhance user engagement and sales. It employs data analysis, machine learning, and visualization to understand user behavior and develop predictive models.

## Data Columns Overview
Key data columns include:
- `user_pseudo_id`: Unique user identifier.
- `event_timestamp`: Event logging time in microseconds (UTC).
- `country`, `region`: User's location based on IP.
- `device_category`, `device_operating_system`: Device and OS information.
- `event_name`: Type of user event (e.g., `page_view`, `purchase`).

## Importing Libraries and Dataset
### Setup
Use Google Colab for a seamless experience with BigQuery:
```python
from google.colab import auth
from google.cloud import bigquery
from google.colab import data_table

auth.authenticate_user()
project_id = 'your_project_id'
client = bigquery.Client(project=project_id)

data_table.enable_dataframe_formatter()
```

### Loading Data from BigQuery
```python
query = """
SELECT *
FROM `your_project_id.your_dataset.your_table`
WHERE date BETWEEN '2023-01-01' AND '2023-12-31'
"""
df = client.query(query).to_dataframe()
```

## Data Cleaning and Processing
Initial steps include handling missing values, converting timestamps, and identifying unique values for analysis.

## Data Visualization
Insights into user demographics, device usage, and engagement patterns are visualized using libraries such as Matplotlib, Seaborn, and Plotly.

## Analysis and Modeling
The project includes user segmentation using K-Means, LTV prediction with neural networks, and traffic source analysis via classification models.

## Insights and Recommendations
Findings from the analysis inform recommendations for improving user engagement and tailoring marketing strategies.

## Presentation
Additionally, stakeholders are encouraged to review the presentation file included in the repository for a comprehensive overview of the project findings and visual insights.

## Conclusion
This project demonstrates the value of BigQuery data in understanding e-commerce user behavior and optimizing marketing efforts for better engagement and sales.

---
