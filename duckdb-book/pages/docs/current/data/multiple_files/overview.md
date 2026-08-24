---
type: Web Page
title: Reading Multiple Files – DuckDB
description: 'DuckDB can read multiple files of different types (CSV, Parquet, JSON
  files) at the same time using either the glob syntax, or by providing a list of
  files to read. See the combining schemas page for tips on reading files with different
  schemas. CSV Read all files with a name ending in .csv in the folder dir: SELECT
  * FROM ''dir/*.csv''; Read all files with a name ending in .csv, two directories
  deep: SELECT * FROM ''*/*/*.csv''; Read all files with a name ending in .csv, at
  any depth in the folder dir: SELECT * FROM ''dir/**/*.csv''; Read the CSV…'
resource: https://duckdb.org/docs/current/data/multiple_files/overview
timestamp: '2026-08-24T07:05:55.104476+00:00'
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
				 [Sitemap](/sitemap.html)
- 
				 [Live Demo](https://shell.duckdb.org)

DuckDB can read multiple files of different types (CSV, Parquet, JSON files) at the same time using either the glob syntax, or by providing a list of files to read.
See the [combining schemas](/docs/current/data/multiple_files/combining_schemas.html) page for tips on reading files with different schemas.

## 
        
        [CSV](#csv)
        
      

    
Read all files with a name ending in `.csv` in the folder `dir`:

```
SELECT *
FROM 'dir/*.csv';
```
Read all files with a name ending in `.csv`, two directories deep:

```
SELECT *
FROM '*/*/*.csv';
```
Read all files with a name ending in `.csv`, at any depth in the folder `dir`:

```
SELECT *
FROM 'dir/**/*.csv';
```
Read the CSV files `flights1.csv` and `flights2.csv`:

```
SELECT *
FROM read_csv(['flights1.csv', 'flights2.csv']);
```
Read the CSV files `flights1.csv` and `flights2.csv`, unifying schemas by name and outputting a `filename` column:

```
SELECT *
FROM read_csv(['flights1.csv', 'flights2.csv'], union_by_name = true, filename = true);
```
## 
        
        [Parquet](#parquet)
        
      

    
Read all files that match the glob pattern:

```
SELECT *
FROM 'test/*.parquet';
```
Read three Parquet files and treat them as a single table:

```
SELECT *
FROM read_parquet(['file1.parquet', 'file2.parquet', 'file3.parquet']);
```
Read all Parquet files from two specific folders:

```
SELECT *
FROM read_parquet(['folder1/*.parquet', 'folder2/*.parquet']);
```
Read all Parquet files that match the glob pattern at any depth:

```
SELECT *
FROM read_parquet('dir/**/*.parquet');
```
## 
        
        [Multi-File Reads and Globs](#multi-file-reads-and-globs)
        
      

    
DuckDB can also read a series of Parquet files and treat them as if they were a single table. Note that this only works if the Parquet files have the same schema. You can specify which Parquet files you want to read using a list parameter, glob pattern matching syntax, or a combination of both.

### 
        
        [List Parameter](#list-parameter)
        
      

    
The `read_parquet` function can accept a list of filenames as the input parameter.

Read three Parquet files and treat them as a single table:

```
SELECT *
FROM read_parquet(['file1.parquet', 'file2.parquet', 'file3.parquet']);
```
### 
        
        [Glob Syntax](#glob-syntax)
        
      

    
Any file name input to the `read_parquet` function can either be an exact filename, or use a glob syntax to read multiple files that match a pattern.

| Wildcard | Description | 
|---|---|
| `*` | Matches any number of any characters (including none) | 
| `**` | Matches any number of subdirectories (including none) | 
| `?` | Matches any single character | 
| `[abc]` | Matches one character given in the bracket | 
| `[a-z]` | Matches one character from the range given in the bracket | 

Note that the `?` wildcard in globs is not supported for reads over S3 due to HTTP encoding issues.

Here is an example that reads all the files that end with `.parquet` located in the `test` folder:

Read all files that match the glob pattern:

```
SELECT *
FROM read_parquet('test/*.parquet');
```
### 
        
        [List of Globs](#list-of-globs)
        
      

    
The glob syntax and the list input parameter can be combined to scan files that meet one of multiple patterns.

Read all Parquet files from 2 specific folders.

```
SELECT *
FROM read_parquet(['folder1/*.parquet', 'folder2/*.parquet']);
```
DuckDB can read multiple CSV files at the same time using either the glob syntax, or by providing a list of files to read.

## 
        
        [Filename](#filename)
        
      

    
The `filename` argument can be used to add an extra `filename` column to the result that indicates which row came from which file. For example:

```
SELECT *
FROM read_csv(['flights1.csv', 'flights2.csv'], union_by_name = true, filename = true);
```
| FlightDate | OriginCityName | DestCityName | UniqueCarrier | filename | 
|---|---|---|---|---|
| 1988-01-01 | New York, NY | Los Angeles, CA | NULL | flights1.csv | 
| 1988-01-02 | New York, NY | Los Angeles, CA | NULL | flights1.csv | 
| 1988-01-03 | New York, NY | Los Angeles, CA | AA | flights2.csv | 

  The `filename` argument also accepts a string (e.g., `filename = 'input_file'`). When provided, the string is used as the name of the added column. This is useful when the source data already contains a `filename` column and you want to avoid a name collision.

## 
        
        [Glob Function to Find Filenames](#glob-function-to-find-filenames)
        
      

    
The glob pattern matching syntax can also be used to search for filenames using the `glob` table function.
It accepts one parameter: the path to search (which may include glob patterns).

Search the current directory for all files.

```
SELECT *
FROM glob('*');
```
| file | 
|---|
| test.csv | 
| test.json | 
| test.parquet | 
| test2.csv | 
| test2.parquet | 
| todos.json |

# Citations

1. Source page: https://duckdb.org/docs/current/data/multiple_files/overview
