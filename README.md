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

```

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

