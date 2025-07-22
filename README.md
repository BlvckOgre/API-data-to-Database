# API data to Database
## Overview 
This project is to build a simple ETL pipeline to fetch real-time data from an open source API and store that data into a database. For this case we have used Yelp FUSION API as the open source API available and for database we used Postgres. 

## Config File
```
[KEYS]
CLIENT_KEY=<YOUR CLIENT KEY>
API_KEY=<YOUR API KEY>


[DATABASE]
host=<HOST NAME>
database=<DB NAME>
username=<USER NAME>
password=<PASSWORD>
port=<PORT>

```


## Files
```
auth.py - Contains configuration variable for making HTTP Request

businesssearch.py - Contains class to handle results returned from the search request

databasedriver.py - Contains Connection detials to Postgres database and executing queries

queries.py - Contains queries to create schema and tables in postgres and insert statement format

request.py - Contains class to handle making request to the API

driver.py - Entry point for the application, contains parsing command line arguments and control the program flow.
```

## How to Run
`python driver.py --term food --location Montreal --price 4` 


## Results
![RESULTS](https://github.com/san089/Udacity-Data-Engineering-Projects/blob/master/Data_Api_to_Postgres/Results.PNG)



# 📡 API to PostgreSQL ETL Pipeline

A lightweight ETL pipeline to extract data from the **Yelp Fusion API** and load it into a **PostgreSQL** database. This project demonstrates a basic data engineering workflow using Python, API integration, and relational databases.

---

## 🚀 Features

- Extracts real-time business data from the Yelp Fusion API  
- Transforms API response into structured format  
- Loads data into PostgreSQL  
- Easily configurable via an `.ini` file  
- CLI interface for flexible querying  

---

## 🧰 Technologies Used

- Python 3.8+
- Yelp Fusion API
- PostgreSQL
- `psycopg2`, `requests`, `configparser`, `argparse`

---

## 🗂️ Project Structure

```bash
.
├── auth.py               # API key configuration
├── businesssearch.py     # API response handling
├── databasedriver.py     # PostgreSQL DB connection + query execution
├── queries.py            # SQL schema and insert queries
├── request.py            # API request logic
├── driver.py             # Main entry point
├── config.ini            # API and DB credentials
└── README.md             # Project documentation

---

## ⚙️ Configuration
Create a file named config.ini in the project root with the following structure:

``` bash

[KEYS]
CLIENT_KEY = your_client_key
API_KEY = your_api_key

[DATABASE]
host     = your_db_host
database = your_db_name
username = your_db_user
password = your_db_password
port     = 5432

```

## 🧪 How to Run

Install required packages (you can use a virtual environment):

```bash

pip install -r requirements.txt

```
Run the ETL pipeline from the command line:

```bash

python driver.py --term food --location Montreal --price 4

```

| Argument     | Description                 |
| ------------ | --------------------------- |
| `--term`     | Search keyword (e.g., food) |
| `--location` | Location (e.g., Montreal)   |
| `--price`    | Price level (1-4, optional) |

---

## 🖼️ Sample Output
Data is inserted into PostgreSQL and can be queried directly.

📌 To-Do / Enhancements

* Add Docker support

* Implement logging

* Add unit tests

* Support for incremental updates

* Save raw API responses for audit

