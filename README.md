# week-8-project-assignment-on-data-pipelines-with-Neo4j

Google colab link: https://colab.research.google.com/drive/10fsM2SgMjdfPSGGreQNW8RFqcnJSpWgh?usp=sharing#scrollTo=RgkR-c6o9PyI

## Data Pipeline with Neo4j

This data pipeline extracts subscription data from Neo4j, transforms it using pandas, and loads it into a Postgres database.

## Setup Dependencies
The following dependencies are required to run the data pipeline:

Python 3.6+ 

neo4j library for Python

pandas library for Python

psycopg2 library for Python


## Environment Variables

Before running the data pipeline, you must set the following environment variables:


NEO4J_URI: The URI of the Neo4j database.

NEO4J_USER: The username to connect to the Neo4j database.

NEO4J_PASSWORD: The password to connect to the Neo4j database.

PG_HOST: The hostname or IP address of the Postgres database.

PG_PORT: The port number of the Postgres database.

PG_DATABASE: The name of the Postgres database.

PG_USER: The username to connect to the Postgres database.

PG_PASSWORD: The password to connect to the Postgres database.

## Neo4j Schema

The Neo4j database used in this data pipeline has the following schema:


## Customer nodes with properties:

id: A unique identifier for the customer.

Service nodes with properties:

id: A unique identifier for the service.

name: The name of the service.

## Subscription nodes with properties:

id: A unique identifier for the subscription.

start_date: The start date of the subscription.

end_date: The end date of the subscription.

price: The price of the subscription.

Customer nodes are connected to Subscription nodes with a HAS_SUBSCRIPTION relationship.

Subscription nodes are connected to Service nodes with a USES relationship.

## Transformations


The data is transformed using the following steps:


The start_date and end_date columns are converted to datetime format.

Rows where either start_date or end_date is NaT are removed.

Rows with NaN values are dropped.

A new column duration_days is created which contains the duration of the subscription in days.

## Postgres Schema


The data is loaded into a Postgres table named customer_service with the following schema:


customer_id: A unique identifier for the customer.

start_date: The start date of the subscription.

end_date: The end date of the subscription.

price: The price of the subscription.

service_id: A unique identifier for the service.

service_name: The name of the service.

duration_days: The duration of the subscription in days.

## Running the Data Pipeline

To run the data pipeline, follow these steps:

Set the environment variables listed above.

Run the main() function in the Data Pipelines with Neo4j Project.ipynb file.
