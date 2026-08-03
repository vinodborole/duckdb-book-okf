---
type: Web Page
title: Data Ingestion – DuckDB
description: 'This page contains examples for data ingestion to Python using DuckDB.
  First, import the DuckDB package: import duckdb Then, proceed with any of the following
  sections. CSV Files CSV files can be read using the read_csv function, called either
  from within Python or directly from within SQL. By default, the read_csv function
  attempts to auto-detect the CSV settings by sampling from the provided file. Read
  from a file using fully auto-detected settings: duckdb.read_csv("example.csv") Read
  multiple CSV files from a folder: duckdb.read_csv("folder/*.csv") Specify options
  on how the CSV is formatted internally: duckdb.read_csv("example.csv", header =
  False, sep = ",") Override types of…'
resource: https://duckdb.org/docs/current/clients/python/data_ingestion
timestamp: '2026-08-03T09:53:51.508916+00:00'
---

- 
				
					
					
					[Installation](/install/)
- Documentation
- 
							 [Getting Started](/docs/current/index)
- Connect
- Data Import and Export
- 
								 [Overview](/docs/current/data/overview)
- 
								 [Data Sources](/docs/current/data/data_sources)
- CSV Files
- JSON Files
- Multiple Files
- Parquet Files
- Partitioning
- 
								 [Appender](/docs/current/data/appender)
- 
								 [INSERT Statements](/docs/current/data/insert)
- 
							 [Lakehouse Formats](/docs/current/lakehouse_formats)
- Client APIs
- SQL
- 
								 [Introduction](/docs/current/sql/introduction)
- Statements
- Query Syntax
- Data Types
- 
									  [Overview](/docs/current/sql/data_types/overview) 
- 
									  [Array](/docs/current/sql/data_types/array) 
- 
									  [Bitstring](/docs/current/sql/data_types/bitstring) 
- 
									  [Blob](/docs/current/sql/data_types/blob) 
- 
									  [Boolean](/docs/current/sql/data_types/boolean) 
- 
									  [Date](/docs/current/sql/data_types/date) 
- 
									  [Enum](/docs/current/sql/data_types/enum) 
- 
									  [Geometry](/docs/current/sql/data_types/geometry) 
- 
									  [Interval](/docs/current/sql/data_types/interval) 
- 
									  [List](/docs/current/sql/data_types/list) 
- 
									  [Literal Types](/docs/current/sql/data_types/literal_types) 
- 
									  [Map](/docs/current/sql/data_types/map) 
- 
									  [NULL Values](/docs/current/sql/data_types/nulls) 
- 
									  [Numeric](/docs/current/sql/data_types/numeric) 
- 
									  [Struct](/docs/current/sql/data_types/struct) 
- 
									  [Text](/docs/current/sql/data_types/text) 
- 
									  [Time](/docs/current/sql/data_types/time) 
- 
									  [Timestamp](/docs/current/sql/data_types/timestamp) 
- 
									  [Time Zones](/docs/current/sql/data_types/timezones) 
- 
									  [Union](/docs/current/sql/data_types/union) 
- 
									  [Typecasting](/docs/current/sql/data_types/typecasting) 
- 
									  [Variant](/docs/current/sql/data_types/variant) 
- Expressions
- Functions
- 
								 [Constraints](/docs/current/sql/constraints)
- 
								 [Indexes](/docs/current/sql/indexes)
- Meta Queries
- DuckDB's SQL Dialect
- 
								 [PEG Parser](/docs/current/sql/peg_parser)
- 
								 [Samples](/docs/current/sql/samples)
- Configuration
- Extensions
- Core Extensions
- 
								 [Overview](/docs/current/core_extensions/overview)
- 
								 [AutoComplete](/docs/current/core_extensions/autocomplete)
- 
								 [Avro](/docs/current/core_extensions/avro)
- 
								 [AWS](/docs/current/core_extensions/aws)
- 
								 [Azure](/docs/current/core_extensions/azure)
- 
								 [Delta](/docs/current/core_extensions/delta)
- 
								 [DuckLake](/docs/current/core_extensions/ducklake)
- 
								 [Encodings](/docs/current/core_extensions/encodings)
- 
								 [Excel](/docs/current/core_extensions/excel)
- 
								 [Full Text Search](/docs/current/core_extensions/full_text_search)
- httpfs (HTTP and S3)
- Iceberg
- 
								 [ICU](/docs/current/core_extensions/icu)
- 
								 [inet](/docs/current/core_extensions/inet)
- 
								 [jemalloc](/docs/current/core_extensions/jemalloc)
- 
								 [Lance](/docs/current/core_extensions/lance)
- 
								 [MotherDuck](/docs/current/core_extensions/motherduck)
- 
								 [MySQL](/docs/current/core_extensions/mysql)
- ODBC
- 
								 [Quack](/docs/current/core_extensions/quack)
- PostgreSQL
- Spatial
- 
								 [SQLite](/docs/current/core_extensions/sqlite)
- 
								 [TPC-DS](/docs/current/core_extensions/tpcds)
- 
								 [TPC-H](/docs/current/core_extensions/tpch)
- 
								 [UI](/docs/current/core_extensions/ui)
- 
								 [Unity Catalog](/docs/current/core_extensions/unity_catalog)
- 
								 [Vortex](/docs/current/core_extensions/vortex)
- 
								 [VSS](/docs/current/core_extensions/vss)
- Quack Remote Protocol
- Guides
- 
								 [Overview](/docs/current/guides/overview)
- Data Viewers
- Database Integration
- File Formats
- Meta Queries
- Network and Cloud Storage
- ODBC
- Performance
- Python
- SQL Editors
- SQL Features
- Snippets
- Troubleshooting
- 
								 [Glossary of Terms](/docs/current/guides/glossary)
- 
								 [Browsing Offline](/docs/current/guides/offline-copy)
- Operations Manual
- 
								 [Overview](/docs/current/operations_manual/overview)
- DuckDB's Footprint
- Installing DuckDB
- Logging
- 
								 [User Agents](/docs/current/operations_manual/user_agents)
- Securing DuckDB
- 
								 [Non-Deterministic Behavior](/docs/current/operations_manual/non-deterministic_behavior)
- 
								 [Limits](/docs/current/operations_manual/limits)
- 
								 [DuckDB Docker Container](/docs/current/operations_manual/duckdb_docker)
- Development
- 
								 [DuckDB Repositories](/docs/current/dev/repositories)
- 
								 [Release Cycle](/docs/current/dev/release_cycle)
- 
								 [Metrics](/docs/current/dev/metrics)
- 
								 [Profiling](/docs/current/dev/profiling)
- Building DuckDB
- 
								 [Benchmark Suite](/docs/current/dev/benchmark)
- Testing
- Internals
- 
				 [Sitemap](/docs/sitemap)
- 
				 [Live Demo](https://shell.duckdb.org)

This page contains examples for data ingestion to Python using DuckDB. First, import the DuckDB package:

```
import duckdb
```
Then, proceed with any of the following sections.

## 
        
        [CSV Files](#csv-files)
        
      

    
CSV files can be read using the `read_csv` function, called either from within Python or directly from within SQL. By default, the `read_csv` function attempts to auto-detect the CSV settings by sampling from the provided file.

Read from a file using fully auto-detected settings:

```
duckdb.read_csv("example.csv")
```
Read multiple CSV files from a folder:

```
duckdb.read_csv("folder/*.csv")
```
Specify options on how the CSV is formatted internally:

```
duckdb.read_csv("example.csv", header = False, sep = ",")
```
Override types of the first two columns:

```
duckdb.read_csv("example.csv", dtype = ["int", "varchar"])
```
Directly read a CSV file from within SQL:

```
duckdb.sql("SELECT * FROM 'example.csv'")
```
Call `read_csv` from within SQL:

```
duckdb.sql("SELECT * FROM read_csv('example.csv')")
```
See the [CSV Import](/docs/current/data/csv/overview.html) page for more information.

## 
        
        [Parquet Files](#parquet-files)
        
      

    
Parquet files can be read using the `read_parquet` function, called either from within Python or directly from within SQL.

Read from a single Parquet file:

```
duckdb.read_parquet("example.parquet")
```
Read multiple Parquet files from a folder:

```
duckdb.read_parquet("folder/*.parquet")
```
Read a Parquet file over [https](/docs/current/core_extensions/httpfs/overview.html):

```
duckdb.read_parquet("https://some.url/some_file.parquet")
```
Read a list of Parquet files:

```
duckdb.read_parquet(["file1.parquet", "file2.parquet", "file3.parquet"])
```
Directly read a Parquet file from within SQL:

```
duckdb.sql("SELECT * FROM 'example.parquet'")
```
Call `read_parquet` from within SQL:

```
duckdb.sql("SELECT * FROM read_parquet('example.parquet')")
```
See the [Parquet Loading](/docs/current/data/parquet/overview.html) page for more information.

## 
        
        [JSON Files](#json-files)
        
      

    
JSON files can be read using the `read_json` function, called either from within Python or directly from within SQL. By default, the `read_json` function will automatically detect if a file contains newline-delimited JSON or regular JSON, and will detect the schema of the objects stored within the JSON file.

Read from a single JSON file:

```
duckdb.read_json("example.json")
```
Read multiple JSON files from a folder:

```
duckdb.read_json("folder/*.json")
```
Directly read a JSON file from within SQL:

```
duckdb.sql("SELECT * FROM 'example.json'")
```
Call `read_json` from within SQL:

```
duckdb.sql("SELECT * FROM read_json('example.json')")
```
## 
        
        [Directly Accessing DataFrames and Arrow Objects](#directly-accessing-dataframes-and-arrow-objects)
        
      

    
DuckDB is automatically able to query certain Python variables by referring to their variable name (as if it was a table).
These types include the following: Pandas DataFrame, Polars DataFrame, Polars LazyFrame, NumPy arrays, [relations](/docs/current/clients/python/relational_api.html) and Arrow objects.

Only variables that are visible to Python code at the location of the `sql()` or `execute()` call can be used in this manner.
Accessing these variables is made possible by [replacement scans](/docs/current/clients/c/replacement_scans.html). To disable replacement scans entirely, use:

```
SET python_enable_replacements = false;
```
DuckDB supports querying multiple types of Apache Arrow objects including [tables](https://arrow.apache.org/docs/python/generated/pyarrow.Table.html), [datasets](https://arrow.apache.org/docs/python/generated/pyarrow.dataset.Dataset.html), [RecordBatchReaders](https://arrow.apache.org/docs/python/generated/pyarrow.ipc.RecordBatchStreamReader.html) and [scanners](https://arrow.apache.org/docs/python/generated/pyarrow.dataset.Scanner.html). See the Python [guides](/docs/current/guides/overview.html#python-client) for more examples.

```
import duckdb
import pandas as pd
test_df = pd.DataFrame.from_dict({"i": [1, 2, 3, 4], "j": ["one", "two", "three", "four"]})
print(duckdb.sql("SELECT * FROM test_df").fetchall())
```
```
[(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]
```
DuckDB also supports “registering” a DataFrame or Arrow object as a virtual table, comparable to a SQL `VIEW`. This is useful when querying a DataFrame/Arrow object that is stored in another way (as a class variable, or a value in a dictionary). Below is a Pandas example:

If your Pandas DataFrame is stored in another location, here is an example of manually registering it:

```
import duckdb
import pandas as pd
my_dictionary = {}
my_dictionary["test_df"] = pd.DataFrame.from_dict({"i": [1, 2, 3, 4], "j": ["one", "two", "three", "four"]})
duckdb.register("test_df_view", my_dictionary["test_df"])
print(duckdb.sql("SELECT * FROM test_df_view").fetchall())
```
```
[(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]
```
You can also create a persistent table in DuckDB from the contents of the DataFrame (or the view):

```
# create a new table from the contents of a DataFrame
con.execute("CREATE TABLE test_df_table AS SELECT * FROM test_df")
# insert into an existing table from the contents of a DataFrame
con.execute("INSERT INTO test_df_table SELECT * FROM test_df")
```
The precedence of objects with the same name is as follows:

- Objects explicitly registered via `register()`
- Native DuckDB tables and views
- [Replacement scans](/docs/current/clients/c/replacement_scans.html)

### 
        
        [Pandas DataFrames – `object` Columns](#pandas-dataframes--object-columns)
        
      

    
`object` Columns
`pandas.DataFrame` columns of an `object` dtype require some special care, since this stores values of arbitrary type.
To convert these columns to DuckDB, we first go through an analyze phase before converting the values.
In this analyze phase a sample of all the rows of the column are analyzed to determine the target type.
This sample size is by default set to 1000.
If the type picked during the analyze step is incorrect, this will result in `Invalid Input Error: Failed to cast value`, in which case you will need to increase the sample size.
The sample size can be changed by setting the `pandas_analyze_sample` config option.

```
# example setting the sample size to 100k
duckdb.execute("SET GLOBAL pandas_analyze_sample = 100_000")
```

# Citations

1. Source page: https://duckdb.org/docs/current/clients/python/data_ingestion
