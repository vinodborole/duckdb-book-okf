---
type: Web Page
title: Querying Parquet Metadata – DuckDB
description: 'Parquet Metadata The parquet_metadata function can be used to query
  the metadata contained within a Parquet file, which reveals various internal details
  of the Parquet file such as the statistics of the different columns. This can be
  useful for figuring out what kind of skipping is possible in Parquet files, or even
  to obtain a quick overview of what the different columns contain. The function supports
  glob patterns to query metadata across multiple files in parallel: SELECT * FROM
  parquet_metadata(''test.parquet''); SELECT * FROM parquet_metadata(''data/*.parquet'');
  Below is a table of the columns returned by parquet_metadata. Field Type file_name
  VARCHAR row_group_id BIGINT…'
resource: https://duckdb.org/docs/current/data/parquet/metadata
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

## 
        
        [Parquet Metadata](#parquet-metadata)
        
      

    
The `parquet_metadata` function can be used to query the metadata contained within a Parquet file, which reveals various internal details of the Parquet file such as the statistics of the different columns. This can be useful for figuring out what kind of skipping is possible in Parquet files, or even to obtain a quick overview of what the different columns contain. The function supports glob patterns to query metadata across multiple files in parallel:

```
SELECT *
FROM parquet_metadata('test.parquet');
```
```
SELECT *
FROM parquet_metadata('data/*.parquet');
```
Below is a table of the columns returned by `parquet_metadata`.

| Field | Type | 
|---|---|
| file_name | VARCHAR | 
| row_group_id | BIGINT | 
| row_group_num_rows | BIGINT | 
| row_group_num_columns | BIGINT | 
| row_group_bytes | BIGINT | 
| column_id | BIGINT | 
| file_offset | BIGINT | 
| num_values | BIGINT | 
| path_in_schema | VARCHAR | 
| type | VARCHAR | 
| stats_min | VARCHAR | 
| stats_max | VARCHAR | 
| stats_null_count | BIGINT | 
| stats_distinct_count | BIGINT | 
| stats_min_value | VARCHAR | 
| stats_max_value | VARCHAR | 
| compression | VARCHAR | 
| encodings | VARCHAR | 
| index_page_offset | BIGINT | 
| dictionary_page_offset | BIGINT | 
| data_page_offset | BIGINT | 
| total_compressed_size | BIGINT | 
| total_uncompressed_size | BIGINT | 
| key_value_metadata | MAP(BLOB, BLOB) | 
| bloom_filter_offset | BIGINT | 
| bloom_filter_length | BIGINT | 
| min_is_exact | BOOLEAN | 
| max_is_exact | BOOLEAN | 
| row_group_compressed_bytes | BIGINT | 

## 
        
        [Parquet Schema](#parquet-schema)
        
      

    
The `parquet_schema` function can be used to query the internal schema contained within a Parquet file. Note that this is the schema as it is contained within the metadata of the Parquet file. If you want to figure out the column names and types contained within a Parquet file it is easier to use `DESCRIBE`.

Fetch the column names and column types:

```
DESCRIBE SELECT * FROM 'test.parquet';
```
Fetch the internal schema of a Parquet file:

```
SELECT *
FROM parquet_schema('test.parquet');
```
Below is a table of the columns returned by `parquet_schema`.

| Field | Type | 
|---|---|
| file_name | VARCHAR | 
| name | VARCHAR | 
| type | VARCHAR | 
| type_length | VARCHAR | 
| repetition_type | VARCHAR | 
| num_children | BIGINT | 
| converted_type | VARCHAR | 
| scale | BIGINT | 
| precision | BIGINT | 
| field_id | BIGINT | 
| logical_type | VARCHAR | 

## 
        
        [Parquet File Metadata](#parquet-file-metadata)
        
      

    
The `parquet_file_metadata` function can be used to query file-level metadata such as the format version and the encryption algorithm used:

```
SELECT *
FROM parquet_file_metadata('test.parquet');
```
Below is a table of the columns returned by `parquet_file_metadata`.

| Field | Type | 
|---|---|
| file_name | VARCHAR | 
| created_by | VARCHAR | 
| num_rows | BIGINT | 
| num_row_groups | BIGINT | 
| format_version | BIGINT | 
| encryption_algorithm | VARCHAR | 
| footer_signing_key_metadata | VARCHAR | 
| file_size_bytes | UBIGINT | 
| footer_size | UBIGINT | 
| column_orders | VARCHAR[] | 

## 
        
        [Parquet Key-Value Metadata](#parquet-key-value-metadata)
        
      

    
The `parquet_kv_metadata` function can be used to query custom metadata defined as key-value pairs:

```
SELECT *
FROM parquet_kv_metadata('test.parquet');
```
Below is a table of the columns returned by `parquet_kv_metadata`.

| Field | Type | 
|---|---|
| file_name | VARCHAR | 
| key | BLOB | 
| value | BLOB | 

## 
        
        [Full Metadata](#full-metadata)
        
      

    
The `parquet_full_metadata` function returns all metadata for a Parquet file in a single row, combining the results of `parquet_file_metadata`, `parquet_metadata`, `parquet_schema`, and `parquet_kv_metadata` as nested struct arrays:

```
SELECT *
FROM parquet_full_metadata('test.parquet');
```
| Field | Type | 
|---|---|
| parquet_file_metadata | STRUCT(…)[] | 
| parquet_metadata | STRUCT(…)[] | 
| parquet_schema | STRUCT(…)[] | 
| parquet_kv_metadata | STRUCT(…)[] | 

Each struct array contains the same columns as the corresponding standalone function.

## 
        
        [Bloom Filters](#bloom-filters)
        
      

    
DuckDB [supports Bloom filters](/2025/03/07/parquet-bloom-filters-in-duckdb.html) for pruning the row groups that need to be read to answer highly selective queries.
Currently, Bloom filters are supported for the following types:

- Integer types: `TINYINT` ,`UTINYINT` ,`SMALLINT` ,`USMALLINT` ,`INTEGER` ,`UINTEGER` ,`BIGINT` ,`UBIGINT`
- Floating point types: `FLOAT` ,`DOUBLE`
- `VARCHAR`
- `BLOB`

The `parquet_bloom_probe(filename, column_name, value)` function shows which row groups can be excluded when filtering for a given value of a given column using the Bloom filter.
For example:

```
FROM parquet_bloom_probe('my_file.parquet', 'my_col', 500);
```
| file_name | row_group_id | bloom_filter_excludes | 
|---|---|---|
| my_file.parquet | 0 | true | 
| … | … | … | 
| my_file.parquet | 9 | false |

# Citations

1. Source page: https://duckdb.org/docs/current/data/parquet/metadata
