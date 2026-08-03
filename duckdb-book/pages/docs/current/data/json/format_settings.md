---
type: Web Page
title: JSON Format Settings – DuckDB
description: 'The JSON extension can attempt to determine the format of a JSON file
  when setting format to auto. Here are some example JSON files and the corresponding
  format settings that should be used. In each of the below cases, the format setting
  was not needed, as DuckDB was able to infer it correctly, but it is included for
  illustrative purposes. A query of this shape would work in each case: SELECT * FROM
  filename.json; Format: newline_delimited With format = ''newline_delimited'' newline-delimited
  JSON can be parsed. Each line is a JSON. We use the example file records.json with
  the following content:…'
resource: https://duckdb.org/docs/current/data/json/format_settings
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

The JSON extension can attempt to determine the format of a JSON file when setting `format` to `auto`.
Here are some example JSON files and the corresponding `format` settings that should be used.

In each of the below cases, the `format` setting was not needed, as DuckDB was able to infer it correctly, but it is included for illustrative purposes.
A query of this shape would work in each case:

```
SELECT *
FROM filename.json;
```
## 
        
        [Format: `newline_delimited`](#format-newline_delimited)
        
      

    
`newline_delimited`
With `format = 'newline_delimited'` newline-delimited JSON can be parsed.
Each line is a JSON.

We use the example file [`records.json`](/data/records.json) with the following content:

```
{"key1":"value1", "key2": "value1"}
{"key1":"value2", "key2": "value2"}
{"key1":"value3", "key2": "value3"}
```
```
SELECT *
FROM read_json('records.json', format = 'newline_delimited');
```
| key1 | key2 | 
|---|---|
| value1 | value1 | 
| value2 | value2 | 
| value3 | value3 | 

## 
        
        [Format: `array`](#format-array)
        
      

    
`array`
If the JSON file contains a JSON array of objects (pretty-printed or not), `array_of_objects` may be used.
To demonstrate its use, we use the example file [`records-in-array.json`](/data/records-in-array.json):

```
[
    {"key1":"value1", "key2": "value1"},
    {"key1":"value2", "key2": "value2"},
    {"key1":"value3", "key2": "value3"}
]
```
```
SELECT *
FROM read_json('records-in-array.json', format = 'array');
```
| key1 | key2 | 
|---|---|
| value1 | value1 | 
| value2 | value2 | 
| value3 | value3 | 

## 
        
        [Format: `unstructured`](#format-unstructured)
        
      

    
`unstructured`
If the JSON file contains JSON that is not newline-delimited or an array, `unstructured` may be used.
To demonstrate its use, we use the example file [`unstructured.json`](/data/unstructured.json):

```
{
    "key1":"value1",
    "key2":"value1"
}
{
    "key1":"value2",
    "key2":"value2"
}
{
    "key1":"value3",
    "key2":"value3"
}
```
```
SELECT *
FROM read_json('unstructured.json', format = 'unstructured');
```
| key1 | key2 | 
|---|---|
| value1 | value1 | 
| value2 | value2 | 
| value3 | value3 | 

## 
        
        [`records` Options](#records-options)
        
      

    
`records` Options
The JSON extension can attempt to determine whether a JSON file contains records when setting `records = auto`.
When `records = true`, the JSON extension expects JSON objects, and will unpack the fields of JSON objects into individual columns.

Continuing with the same example file, [`records.json`](/data/records.json):

```
{"key1":"value1", "key2": "value1"}
{"key1":"value2", "key2": "value2"}
{"key1":"value3", "key2": "value3"}
```
```
SELECT *
FROM read_json('records.json', records = true);
```
| key1 | key2 | 
|---|---|
| value1 | value1 | 
| value2 | value2 | 
| value3 | value3 | 

When `records = false`, the JSON extension will not unpack the top-level objects, and create `STRUCT`s instead:

```
SELECT *
FROM read_json('records.json', records = false);
```
| json | 
|---|
| {'key1': value1, 'key2': value1} | 
| {'key1': value2, 'key2': value2} | 
| {'key1': value3, 'key2': value3} | 

This is especially useful if we have non-object JSON, for example, [`arrays.json`](/data/arrays.json):

```
[1, 2, 3]
[4, 5, 6]
[7, 8, 9]
```
```
SELECT *
FROM read_json('arrays.json', records = false);
```
| json | 
|---|
| [1, 2, 3] | 
| [4, 5, 6] | 
| [7, 8, 9] |

# Citations

1. Source page: https://duckdb.org/docs/current/data/json/format_settings
