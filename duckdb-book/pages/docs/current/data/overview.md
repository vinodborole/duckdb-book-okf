---
type: Web Page
title: Importing Data – DuckDB
description: The first step to using a database system is to insert data into that
  system. DuckDB can directly connect to many popular data sources and offers several
  data ingestion methods that allow you to easily and efficiently fill up the database.
  On this page, we provide an overview of these methods so you can select which one
  is best suited for your use case. INSERT Statements INSERT statements are the standard
  way of loading data into a database system. They are suitable for quick prototyping,
  but should be avoided for bulk loading as they have significant per-row overhead.
  INSERT INTO…
resource: https://duckdb.org/docs/current/data/overview
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

The first step to using a database system is to insert data into that system.
DuckDB can directly connect to [many popular data sources](/docs/current/data/data_sources.html) and offers several data ingestion methods that allow you to easily and efficiently fill up the database.
On this page, we provide an overview of these methods so you can select which one is best suited for your use case.

## 
        
        [`INSERT` Statements](#insert-statements)
        
      

    
`INSERT` Statements
`INSERT` statements are the standard way of loading data into a database system. They are suitable for quick prototyping, but should be avoided for bulk loading as they have significant per-row overhead.

```
INSERT INTO people VALUES (1, 'Mark');
```
For a more detailed description, see the [page on the `INSERT` statement](/docs/current/data/insert.html).

## 
        
        [File Loading: Relative Paths](#file-loading-relative-paths)
        
      

    
Use the configuration option [`file_search_path`](/docs/current/configuration/overview.html#local-configuration-options) to configure to which “root directories” relative paths are expanded on.
If `file_search_path` is not set, the working directory is used as the basis for relative paths.

## 
        
        [File Formats](#file-formats)
        
      

    
      ### 
        
        [CSV Loading](#csv-loading)
        
      

    
Data can be efficiently loaded from CSV files using several methods. The simplest is to use the CSV file's name:

```
SELECT * FROM 'test.csv';
```
Alternatively, use the [`read_csv` function](/docs/current/data/csv/overview.html) to pass along options:

```
SELECT * FROM read_csv('test.csv', header = false);
```
Or use the [`COPY` statement](/docs/current/sql/statements/copy.html#copy--from):

```
COPY tbl FROM 'test.csv' (HEADER false);
```
It is also possible to read data directly from **compressed CSV files** (e.g., compressed with [gzip](https://www.gzip.org/)):

```
SELECT * FROM 'test.csv.gz';
```
DuckDB can create a table from the loaded data using the [`CREATE TABLE ... AS SELECT` statement](/docs/current/sql/statements/create_table.html#create-table--as-select-ctas):

```
CREATE TABLE test AS
    SELECT * FROM 'test.csv';
```
For more details, see the [page on CSV loading](/docs/current/data/csv/overview.html).

### 
        
        [Parquet Loading](#parquet-loading)
        
      

    
Parquet files can be efficiently loaded and queried using their filename:

```
SELECT * FROM 'test.parquet';
```
Alternatively, use the [`read_parquet` function](/docs/current/data/parquet/overview.html):

```
SELECT * FROM read_parquet('test.parquet');
```
Or use the [`COPY` statement](/docs/current/sql/statements/copy.html#copy--from):

```
COPY tbl FROM 'test.parquet';
```
For more details, see the [page on Parquet loading](/docs/current/data/parquet/overview.html).

### 
        
        [JSON Loading](#json-loading)
        
      

    
JSON files can be efficiently loaded and queried using their filename:

```
SELECT * FROM 'test.json';
```
Alternatively, use the [`read_json` function](/docs/current/data/json/overview.html):

```
SELECT * FROM read_json('test.json');
```
Or use the [`COPY` statement](/docs/current/sql/statements/copy.html#copy--from):

```
COPY tbl FROM 'test.json';
```
For more details, see the [page on JSON loading](/docs/current/data/json/overview.html).

### 
        
        [Returning the Filename](#returning-the-filename)
        
      

    
Since DuckDB v1.3.0, the CSV, JSON and Parquet readers support the `filename` virtual column:

```
COPY (FROM (VALUES (42), (43)) t(x)) TO 'test.parquet';
SELECT *, filename FROM 'test.parquet';
```
## 
        
        [Appender](#appender)
        
      

    
In several APIs (C, C++, Go, Java and Rust), the [Appender](/docs/current/data/appender.html) can be used as an alternative for bulk data loading.
This class can be used to efficiently add rows to the database system without using SQL statements.

# Citations

1. Source page: https://duckdb.org/docs/current/data/overview
