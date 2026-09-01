
# Credit Card Customer Segmentation

## Project Description
This project focuses on segmenting credit card customers into distinct behavioral groups based on their transaction patterns and other financial metrics. By identifying these segments, businesses can deliver targeted offerings, manage risk more effectively, and enhance customer satisfaction through personalized services.

## Problem Statement / Project Objective
The primary objective of this project is to segment credit card customers into actionable groups, allowing for strategic marketing, risk management, and credit policy adjustments based on customer behavior.

## Project Type and Methodology
The project is a clustering analysis. It employs an unsupervised learning approach, specifically using KMeans Clustering, combined with Principal Component Analysis (PCA) for dimensionality reduction. Anomaly detection with Isolation Forest is used to identify and remove outlier customers to refine cluster formation.

## Dataset Description
- **Total Rows**: 8950
- **Total Columns**: 18
- **Missing Data Handling**: Missing values in "MINIMUM_PAYMENTS" and "CREDIT_LIMIT" columns were filled with their respective medians.

The dataset includes customer IDs and various financial metrics such as balance, purchases, cash advances, and payment frequencies.

## Installation and Dependencies
This project requires Python and packages like `pandas`, `numpy`, `seaborn`, `matplotlib`, `plotly`, `scikit-learn`, and `scipy`. Ensure all dependencies are installed when running in a new environment.

## Usage / How to Run the Project
To run the analysis:
1. Load the dataset provided as `CC GENERAL.csv`.
2. Execute the Jupyter Notebook `credit_card.ipynb`, which includes code cells for data preprocessing, clustering, and visualization.

## Data Preprocessing and Feature Engineering
- Missing values were filled with the median of each column.
- Derived additional features:
  - `cash_advance_ratio`, `oneoff_ratio`, `installment_ratio`, and `balance_to_limit`.
- Applied log transformation to normalize dataset distributions before applying PCA.

## Models or Algorithms Used
- **Dimensionality Reduction**: Principal Component Analysis (PCA) to capture 95% variance with 6 components.
- **Clustering**: KMeans with 3 clusters was applied, optimized for business interpretability and actionable marketing strategies.
- **Anomaly Detection**: Isolation Forest to identify and exclude anomalies, improving clustering precision.

## Validation and Evaluation Approach
- Clustering validation employed silhouette scores, where different `k` values (2-10) were evaluated.
- PCA examines variance explained by principal components to ensure crucial features are retained.

## Key Findings and Insights
Three unique customer segments were identified:
- **Cluster 2**: Cash-Advance-Dependent Revolvers—high-risk, high-revenue customers needing credit monitoring.
- **Cluster 0**: One-Off Big-Ticket Spenders—candidates for installment plan promotion.
- **Cluster 1**: Disciplined Low-Balance Payers—low risk, good candidates for credit limit increases.

## Project Structure
The repository includes:
- `credit_card.ipynb`: Main notebook for the analysis.
- `anomalies.csv`: Output file containing detected anomalies.
- `.vscode/settings.json`: VS Code configuration.
- `notebook_readme_agent.py`: Supporting script for notebook execution.

## Limitations and Possible Improvements
- The analysis could be further refined by exploring additional clustering algorithms (e.g., DBSCAN) for potentially better customer groupings.
- Expanding feature engineering based on deeper domain expertise could provide a more nuanced model.

If more specific metrics or outputs are desired, review the notebook code cells and outputs sections for detailed operations performed and results obtained.

