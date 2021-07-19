# Python-csv-to-postgre-loader
## Script to load csv data to a postgre database from a directory recursively.

### Dependencies
1. Python3
2. python-pip
3. python-virtualenv


### Requirements
1. Csv file name should be the same as the name of the table.
2. Csv columns must be ordered exactly the same as table columns.


### Installation

1. Clone the repository.
```
git clone git@github.com:Faustasm/Python-csv-to-postgre-loader.git
```
2. Create an ENV in the root directory.
```
cd Python-csv-to-postgre-loader
python -m venv ENV
```
3. Install requirements.
```
pip install -r requirements.txt
```
4. Edit `config.py` with details of the database, path to csv and optionally ignored files.
```
USER = "postgres"
PASS = "123"
HOST = "127.0.0.1"
PORT = 5432
DB_NAME = "example_db"
CSV_DIR = "example_data"
IGNORED_FILES = []

```
5. Run the script.
```
python import.py
```


### Full usage example

1. Clone the repository.
```
git clone git@github.com:Faustasm/Python-csv-to-postgre-loader.git
```

2. Create an ENV in the root directory.
```
cd Python-csv-to-postgre-loader
python -m venv ENV
```

3. Install requirements.
```
pip install -r requirements.txt
```

4. Edit `config.py` with details of the database, path to csv and optionally ignored files.
```
USER = "postgres"
PASS = "123"
HOST = "127.0.0.1"
PORT = 5432
DB_NAME = "example_db"
CSV_DIR = "example_data"
IGNORED_FILES = []

```

5. Create `example_db`.
```
psql -U postgres -h 127.0.0.1
CREATE DATABASE example_db;
\q
```

6. Create tables. From root directory run:
```
cd example_data
psql postgres -h 127.0.0.1 -d example_db -f example_db.sql
```

7. From root directory run:
```
python import.py
```
