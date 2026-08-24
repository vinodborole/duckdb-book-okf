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
resource: https://duckdb.org/docs/lts/data/overview
timestamp: '2026-08-24T07:05:55.104476+00:00'
---

- 
				
					
					
					[Installation](/install)
- Documentation
- 
							 [Getting Started](/docs/lts/index)
- Connect
- Data Import and Export
- 
								 [Overview](/docs/lts/data/overview)
- 
								 [Data Sources](/docs/lts/data/data_sources)
- CSV Files
- JSON Files
- Multiple Files
- Parquet Files
- Partitioning
- 
								 [Appender](/docs/lts/data/appender)
- 
								 [INSERT Statements](/docs/lts/data/insert)
- 
							 [Lakehouse Formats](/docs/lts/lakehouse_formats)
- Client APIs
- 
								 [Overview](/docs/lts/clients/overview)
- 
								 [Tertiary Clients](/docs/lts/clients/tertiary)
- 
								 [ADBC](/docs/lts/clients/adbc)
- C
- 
								 [C++](/docs/lts/clients/cpp)
- CLI
- 
								 [Dart](/docs/lts/clients/dart)
- 
								 [Go](/docs/lts/clients/go)
- Java (JDBC)
- 
								 [Julia](/docs/lts/clients/julia)
- Node.js (Deprecated)
- Node.js (Neo)
- ODBC
- 
								 [PHP](/docs/lts/clients/php)
- Python
- 
								 [R](/docs/lts/clients/r)
- 
								 [Rust](/docs/lts/clients/rust)
- 
								 [Swift](/docs/lts/clients/swift)
- Wasm
- SQL
- 
								 [Introduction](/docs/lts/sql/introduction)
- Statements
- Query Syntax
- Data Types
- 
									  [Overview](/docs/lts/sql/data_types/overview) 
- 
									  [Array](/docs/lts/sql/data_types/array) 
- 
									  [Bitstring](/docs/lts/sql/data_types/bitstring) 
- 
									  [Blob](/docs/lts/sql/data_types/blob) 
- 
									  [Boolean](/docs/lts/sql/data_types/boolean) 
- 
									  [Date](/docs/lts/sql/data_types/date) 
- 
									  [Enum](/docs/lts/sql/data_types/enum) 
- 
									  [Interval](/docs/lts/sql/data_types/interval) 
- 
									  [List](/docs/lts/sql/data_types/list) 
- 
									  [Literal Types](/docs/lts/sql/data_types/literal_types) 
- 
									  [Map](/docs/lts/sql/data_types/map) 
- 
									  [NULL Values](/docs/lts/sql/data_types/nulls) 
- 
									  [Numeric](/docs/lts/sql/data_types/numeric) 
- 
									  [Struct](/docs/lts/sql/data_types/struct) 
- 
									  [Text](/docs/lts/sql/data_types/text) 
- 
									  [Time](/docs/lts/sql/data_types/time) 
- 
									  [Timestamp](/docs/lts/sql/data_types/timestamp) 
- 
									  [Time Zones](/docs/lts/sql/data_types/timezones) 
- 
									  [Union](/docs/lts/sql/data_types/union) 
- 
									  [Typecasting](/docs/lts/sql/data_types/typecasting) 
- Expressions
- Functions
- 
								 [Constraints](/docs/lts/sql/constraints)
- 
								 [Indexes](/docs/lts/sql/indexes)
- Meta Queries
- DuckDB's SQL Dialect
- 
								 [Samples](/docs/lts/sql/samples)
- Configuration
- Extensions
- Core Extensions
- 
								 [Overview](/docs/lts/core_extensions/overview)
- 
								 [AutoComplete](/docs/lts/core_extensions/autocomplete)
- 
								 [Avro](/docs/lts/core_extensions/avro)
- 
								 [AWS](/docs/lts/core_extensions/aws)
- 
								 [Azure](/docs/lts/core_extensions/azure)
- 
								 [Delta](/docs/lts/core_extensions/delta)
- 
								 [DuckLake](/docs/lts/core_extensions/ducklake)
- 
								 [Encodings](/docs/lts/core_extensions/encodings)
- 
								 [Excel](/docs/lts/core_extensions/excel)
- 
								 [Full Text Search](/docs/lts/core_extensions/full_text_search)
- httpfs (HTTP and S3)
- Iceberg
- 
								 [ICU](/docs/lts/core_extensions/icu)
- 
								 [inet](/docs/lts/core_extensions/inet)
- 
								 [jemalloc](/docs/lts/core_extensions/jemalloc)
- 
								 [Lance](/docs/lts/core_extensions/lance)
- 
								 [MySQL](/docs/lts/core_extensions/mysql)
- 
								 [PostgreSQL](/docs/lts/core_extensions/postgres)
- Spatial
- 
								 [SQLite](/docs/lts/core_extensions/sqlite)
- 
								 [TPC-DS](/docs/lts/core_extensions/tpcds)
- 
								 [TPC-H](/docs/lts/core_extensions/tpch)
- 
								 [UI](/docs/lts/core_extensions/ui)
- 
								 [Unity Catalog](/docs/lts/core_extensions/unity_catalog)
- 
								 [Vortex](/docs/lts/core_extensions/vortex)
- 
								 [VSS](/docs/lts/core_extensions/vss)
- Guides
- 
								 [Overview](/docs/lts/guides/overview)
- Data Viewers
- Database Integration
- File Formats
- Network and Cloud Storage
- Meta Queries
- ODBC
- Performance
- Python
- SQL Editors
- SQL Features
- Snippets
- Troubleshooting
- 
								 [Glossary of Terms](/docs/lts/guides/glossary)
- 
								 [Browsing Offline](/docs/lts/guides/offline-copy)
- Operations Manual
- 
								 [Overview](/docs/lts/operations_manual/overview)
- DuckDB's Footprint
- Installing DuckDB
- Logging
- Securing DuckDB
- 
								 [Non-Deterministic Behavior](/docs/lts/operations_manual/non-deterministic_behavior)
- 
								 [Limits](/docs/lts/operations_manual/limits)
- 
								 [DuckDB Docker Container](/docs/lts/operations_manual/duckdb_docker)
- Development
- 
								 [DuckDB Repositories](/docs/lts/dev/repositories)
- 
								 [Release Cycle](/docs/lts/dev/release_cycle)
- 
								 [Profiling](/docs/lts/dev/profiling)
- Building DuckDB
- 
								 [Benchmark Suite](/docs/lts/dev/benchmark)
- Testing
- Internals
- 
				 [Sitemap](/sitemap.html)
- 
				 [Live Demo](https://shell.duckdb.org)

The first step to using a database system is to insert data into that system.
DuckDB can directly connect to [many popular data sources](/docs/lts/data/data_sources.html) and offers several data ingestion methods that allow you to easily and efficiently fill up the database.
On this page, we provide an overview of these methods so you can select which one is best suited for your use case.

## 
        
        [`INSERT` Statements](#insert-statements)
        
      

    
`INSERT` Statements
`INSERT` statements are the standard way of loading data into a database system. They are suitable for quick prototyping, but should be avoided for bulk loading as they have significant per-row overhead.

```
INSERT INTO people VALUES (1, 'Mark');
```
For a more detailed description, see the [page on the `INSERT` statement](/docs/lts/data/insert.html).

## 
        
        [File Loading: Relative Paths](#file-loading-relative-paths)
        
      

    
Use the configuration option [`file_search_path`](/docs/lts/configuration/overview.html#local-configuration-options) to configure to which “root directories” relative paths are expanded on.
If `file_search_path` is not set, the working directory is used as the basis for relative paths.

## 
        
        [File Formats](#file-formats)
        
      

    
      ### 
        
        [CSV Loading](#csv-loading)
        
      

    
Data can be efficiently loaded from CSV files using several methods. The simplest is to use the CSV file's name:

```
SELECT * FROM 'test.csv';
```
Alternatively, use the [`read_csv` function](/docs/lts/data/csv/overview.html) to pass along options:

```
SELECT * FROM read_csv('test.csv', header = false);
```
Or use the [`COPY` statement](/docs/lts/sql/statements/copy.html#copy--from):

```
COPY tbl FROM 'test.csv' (HEADER false);
```
It is also possible to read data directly from **compressed CSV files** (e.g., compressed with [gzip](https://www.gzip.org/)):

```
SELECT * FROM 'test.csv.gz';
```
DuckDB can create a table from the loaded data using the [`CREATE TABLE ... AS SELECT` statement](/docs/lts/sql/statements/create_table.html#create-table--as-select-ctas):

```
CREATE TABLE test AS
    SELECT * FROM 'test.csv';
```
For more details, see the [page on CSV loading](/docs/lts/data/csv/overview.html).

### 
        
        [Parquet Loading](#parquet-loading)
        
      

    
Parquet files can be efficiently loaded and queried using their filename:

```
SELECT * FROM 'test.parquet';
```
Alternatively, use the [`read_parquet` function](/docs/lts/data/parquet/overview.html):

```
SELECT * FROM read_parquet('test.parquet');
```
Or use the [`COPY` statement](/docs/lts/sql/statements/copy.html#copy--from):

```
COPY tbl FROM 'test.parquet';
```
For more details, see the [page on Parquet loading](/docs/lts/data/parquet/overview.html).

### 
        
        [JSON Loading](#json-loading)
        
      

    
JSON files can be efficiently loaded and queried using their filename:

```
SELECT * FROM 'test.json';
```
Alternatively, use the [`read_json_auto` function](/docs/lts/data/json/overview.html):

```
SELECT * FROM read_json_auto('test.json');
```
Or use the [`COPY` statement](/docs/lts/sql/statements/copy.html#copy--from):

```
COPY tbl FROM 'test.json';
```
For more details, see the [page on JSON loading](/docs/lts/data/json/overview.html).

### 
        
        [Returning the Filename](#returning-the-filename)
        
      

    
Since DuckDB v1.3.0, the CSV, JSON and Parquet readers support the `filename` virtual column:

```
COPY (FROM (VALUES (42), (43)) t(x)) TO 'test.parquet';
SELECT *, filename FROM 'test.parquet';
```
## 
        
        [Appender](#appender)
        
      

    
In several APIs (C, C++, Go, Java and Rust), the [Appender](/docs/lts/data/appender.html) can be used as an alternative for bulk data loading.
This class can be used to efficiently add rows to the database system without using SQL statements.

# Citations

1. Source page: https://duckdb.org/docs/lts/data/overview
