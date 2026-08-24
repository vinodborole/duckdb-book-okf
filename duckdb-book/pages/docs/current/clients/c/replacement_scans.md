---
type: Web Page
title: Replacement Scans – DuckDB
description: The replacement scan API can be used to register a callback that is called
  when a table is read that does not exist in the catalog. For example, when a query
  such as SELECT * FROM my_table is executed and my_table does not exist, the replacement
  scan callback will be called with my_table as parameter. The replacement scan can
  then insert a table function with a specific parameter to replace the read of the
  table. API Reference Overview void duckdb_add_replacement_scan(duckdb_database db,
  duckdb_replacement_callback_t replacement, void *extra_data, duckdb_delete_callback_t
  delete_callback); void duckdb_replacement_scan_set_function_name(duckdb_replacement_scan_info
  info, const char *function_name); void duckdb_replacement_scan_add_parameter(duckdb_replacement_scan_info
  info, duckdb_value parameter); void duckdb_replacement_scan_set_error(duckdb_replacement_scan_info…
resource: https://duckdb.org/docs/current/clients/c/replacement_scans
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

The replacement scan API can be used to register a callback that is called when a table is read that does not exist in the catalog. For example, when a query such as `SELECT * FROM my_table` is executed and `my_table` does not exist, the replacement scan callback will be called with `my_table` as parameter. The replacement scan can then insert a table function with a specific parameter to replace the read of the table.

## 
        
        [API Reference Overview](#api-reference-overview)
        
      

    
`void` [duckdb_add_replacement_scan](#duckdb_add_replacement_scan)(duckdb_database db, duckdb_replacement_callback_t replacement, void *extra_data, duckdb_delete_callback_t delete_callback);
void [duckdb_replacement_scan_set_function_name](#duckdb_replacement_scan_set_function_name)(duckdb_replacement_scan_info info, const char *function_name);
void [duckdb_replacement_scan_add_parameter](#duckdb_replacement_scan_add_parameter)(duckdb_replacement_scan_info info, duckdb_value parameter);
void [duckdb_replacement_scan_set_error](#duckdb_replacement_scan_set_error)(duckdb_replacement_scan_info info, const char *error);
#### 
        
        [`duckdb_add_replacement_scan`](#duckdb_add_replacement_scan)
        
      

    
`duckdb_add_replacement_scan`
Add a replacement scan definition to the specified database.

##### 
        
        [Syntax](#syntax)
        
      

    
```
void duckdb_add_replacement_scan(
  duckdb_database db,
  duckdb_replacement_callback_t replacement,
  void *extra_data,
  duckdb_delete_callback_t delete_callback
);
```
##### 
        
        [Parameters](#parameters)
        
      

    
- `db` : The database object to add the replacement scan to
- `replacement` : The replacement scan callback
- `extra_data` : Extra data that is passed back into the specified callback
- `delete_callback` : The delete callback to call on the extra data, if any

#### 
        
        [`duckdb_replacement_scan_set_function_name`](#duckdb_replacement_scan_set_function_name)
        
      

    
`duckdb_replacement_scan_set_function_name`
Sets the replacement function name. If this function is called in the replacement callback, the replacement scan is performed. If it is not called, the replacement callback is not performed.

##### 
        
        [Syntax](#syntax-1)
        
      

    
```
void duckdb_replacement_scan_set_function_name(
  duckdb_replacement_scan_info info,
  const char *function_name
);
```
##### 
        
        [Parameters](#parameters-1)
        
      

    
- `info` : The info object
- `function_name` : The function name to substitute.

#### 
        
        [`duckdb_replacement_scan_add_parameter`](#duckdb_replacement_scan_add_parameter)
        
      

    
`duckdb_replacement_scan_add_parameter`
Adds a parameter to the replacement scan function.

##### 
        
        [Syntax](#syntax-2)
        
      

    
```
void duckdb_replacement_scan_add_parameter(
  duckdb_replacement_scan_info info,
  duckdb_value parameter
);
```
##### 
        
        [Parameters](#parameters-2)
        
      

    
- `info` : The info object
- `parameter` : The parameter to add.

#### 
        
        [`duckdb_replacement_scan_set_error`](#duckdb_replacement_scan_set_error)
        
      

    
`duckdb_replacement_scan_set_error`
Report that an error has occurred while executing the replacement scan.

##### 
        
        [Syntax](#syntax-3)
        
      

    
```
void duckdb_replacement_scan_set_error(
  duckdb_replacement_scan_info info,
  const char *error
);
```
##### 
        
        [Parameters](#parameters-3)
        
      

    
- `info` : The info object
- `error` : The error message

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/replacement_scans
