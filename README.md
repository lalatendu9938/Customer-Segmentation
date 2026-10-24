Customer Segmentation and Prediction

A Capstone Project for the Enerzcloud Data Analyst Trainee Program

Business Objective

In the highly competitive e-commerce landscape, a one-size-fits-all marketing strategy is inefficient and often wastes resources. The objective of this project is to analyze historical purchasing behavior to categorize customers into distinct behavioral segments. By leveraging machine learning, the business can move away from generic campaigns and instead deploy highly targeted retention, cross-selling, and VIP-engagement strategies that maximize Customer Lifetime Value (CLV) and Return on Investment (ROI).

Dataset

This project utilizes the Online Retail Dataset, a standard transactional dataset containing records for a UK-based and registered non-store online retail network.

Initial Size: ~62,500+ raw transaction records.

Key Features Utilized: InvoiceNo, Quantity, InvoiceDate, UnitPrice, and CustomerID.

Methodology

The project pipeline was built using Python (Pandas, Scikit-Learn, Matplotlib, Seaborn) and consists of three main phases:

Data Cleaning:

Filtered out transactions missing CustomerIDs (anonymous purchases).

Removed returned or canceled orders (transactions where Quantity < 0).

Eliminated free items or errors (transactions where UnitPrice <= 0).

Feature Engineering (RFM Model):

Grouped transaction line-items by customer to calculate three critical metrics:

Recency: Days since the customer's last purchase.

Frequency: Total number of distinct orders placed.

Monetary: Total lifetime spend (Quantity × UnitPrice).

Machine Learning (K-Means Clustering):

Scaled the engineered RFM features using StandardScaler to normalize the variance across features.

Applied the K-Means Clustering algorithm (with k=4) to group customers based on mathematical similarities in their purchasing habits.

Key Findings & Customer Personas

The K-Means model successfully segmented the customer base into four highly actionable personas:

👑 Cluster 0: The VIPs

High-frequency buyers with massive lifetime spend.

Action: Deploy white-glove retention strategies, early product access, and dedicated account managers.

⚠️ Cluster 1: At-Risk / Casual Buyers

The largest segment. They have low lifetime spend and high recency (inactive recently).

Action: Launch automated win-back email campaigns with time-sensitive discount codes.

🐳 Cluster 2: The Wholesale 'Whale'

Massive single-purchase outliers (e.g., $77,000 in one order), indicating B2B or wholesale buyers.

Action: Route directly to a B2B sales team for bulk contract negotiations.

🛍️ Cluster 3: Recent Actives

Engaged customers who purchased very recently with a healthy average spend.

Action: Target with immediate cross-sell campaigns and product bundles to push them toward VIP status.

Visualizations

The core visual output of this analysis is a Scatter Plot mapping Frequency vs. Monetary Value.

The visualization clearly illustrates the behavioral boundaries of the four customer clusters.

Note: The axes in the final visualization were capped to exclude the extreme B2B outlier ("Whale"), allowing for a clear view of the density and distribution of the core consumer base.

Repository Structure

Copy_of_Intitled2.ipynb: The primary Jupyter Notebook containing all data cleaning, feature engineering, modeling, and visualization code.

E-commerce Customer Segmentation.pptx-1.pptx: A comprehensive business report summarizing the technical methodology and strategic recommendations.

PHOTO-2026-10-24-13-08-03.jpg: The generated scatter plot visualizing the distinct customer clusters.

(Note: The raw data.csv is excluded from the repository due to GitHub file size constraints.)

How to Run

Clone this repository to your local machine.

Download the Online Retail Dataset from Kaggle or the UCI Machine Learning Repository and place the CSV file in the root directory (rename to data.csv).

Open Copy_of_Intitled2.ipynb using Jupyter Notebook or Google Colab.

Run all cells sequentially to reproduce the data cleaning pipeline, train the K-Means model, and generate the visualizations.
