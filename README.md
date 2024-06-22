# Book Recommendations with ALS on PySpark

This repository contains an implementation of the Alternating Least Squares (ALS) algorithm using PySpark on a Google Cloud services. The project focuses on generating collaborative book recommendations based on user ratings data .

## Repository Description

The project involves the following steps:
1. Loading book ratings data from a CSV file stored in a GCS bucket.
2. Storing the loaded data into a BigQuery table using a PySpark cluster.
3. Training an ALS model on the book ratings data to generate recommendations.
4. Evaluating the model using the Root Mean Squared Error (RMSE) metric.

## Files

### `csv_to_bigquery.ipynb`

This notebook performs the following tasks:
- Loads a CSV file containing book ratings data from a GCS bucket.
- Uses a PySpark cluster to process the data.
- Stores the processed data into a BigQuery table.

### `als_recommendation.ipynb`

This notebook performs the following tasks:
- Initiates a Spark session with BigQuery configuration.
- Loads data from the previously created BigQuery table into a DataFrame.
- Uses the ALS algorithm to train a recommendation model on the book ratings data.
- Calculates the RMSE score to evaluate the model's performance.

## Setup and Usage

### Prerequisites

- Google Cloud Platform (GCP) account
- Google Cloud Storage (GCS) bucket
- Google BigQuery
- Google Cloud SDK
- PySpark cluster created on GCP

### Steps

1. **Clone the Repository**

    ```
    git clone https://github.com/zygmuntz/goodbooks-10k.git
    ```

2. **Upload the CSV file to GCS**

    Upload the ratings.csv file to a GCS bucket. 

3. **Configure Google Cloud SDK**

    Install google cloud SDK and Authenticate your GCP account:

    ```bash
    gcloud auth login
    gcloud config set project your-gcp-project-id
    ```

4. **Run `csv_to_bigquery.ipynb`**

    Open the notebook on pyspark cluster and follow the instructions to load the CSV file from GCS and store the data in a BigQuery table.

5. **Run `als_recommendation.ipynb`**

    Open the notebook on pyspark cluster and follow the instructions to initiate a Spark session, load data from BigQuery, train the ALS model, and evaluate its performance.
