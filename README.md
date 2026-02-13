Project Goal

In this phase of my research project, I operationalized an end-to-end machine learning pipeline in BigQuery to predict whether a website visitor is likely to complete a transaction. The workflow includes: data extraction → feature engineering → model training → evaluation → prediction & insight extraction using BigQuery ML (BQML).

This approach is intentional for my research because it demonstrates a production-realistic setup: the model is trained directly in the data warehouse (no export required), which reduces data movement, improves governance, and supports scalable analytics.

Task 1 — Explore and Prepare the Dataset (Training View)
Dataset Source

I used the public dataset available in:
bigquery-public-data.google_analytics_sample.ga_sessions_*

This dataset provides session-level Google Analytics data that is ideal for binary classification (purchase vs no purchase).

Feature Engineering Strategy

I transformed raw session data into a clean supervised learning format, where:

label = 1 if a transaction occurred, else 0

os = visitor operating system (categorical)

is_mobile = device type indicator (boolean)

country = visitor country (categorical)

pageviews = engagement proxy (numeric)

Training Data Query (with Explanation)
