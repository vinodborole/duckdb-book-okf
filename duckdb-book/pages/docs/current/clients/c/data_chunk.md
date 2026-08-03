---
type: Web Page
title: Data Chunks – DuckDB
description: Data chunks represent a horizontal slice of a table. They hold a number
  of vectors, that can each hold up to the VECTOR_SIZE rows. The vector size can be
  obtained through the duckdb_vector_size function and is configurable, but is usually
  set to 2048. Data chunks and vectors are what DuckDB uses natively to store and
  represent data. For this reason, the data chunk interface is the most efficient
  way of interfacing with DuckDB. Be aware, however, that correctly interfacing with
  DuckDB using the data chunk API does require knowledge of DuckDB's internal vector
  format. Data chunks can be used in…
resource: https://duckdb.org/docs/current/clients/c/data_chunk
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

Data chunks represent a horizontal slice of a table. They hold a number of [vectors](/docs/current/clients/c/vector.html), that can each hold up to the `VECTOR_SIZE` rows. The vector size can be obtained through the `duckdb_vector_size` function and is configurable, but is usually set to `2048`.

Data chunks and vectors are what DuckDB uses natively to store and represent data. For this reason, the data chunk interface is the most efficient way of interfacing with DuckDB. Be aware, however, that correctly interfacing with DuckDB using the data chunk API does require knowledge of DuckDB's internal vector format.

Data chunks can be used in two manners:

- **Reading Data** : Data chunks can be obtained from query results using the`duckdb_fetch_chunk` method, or as input to a user-defined function. In this case, the[vector methods](/docs/current/clients/c/vector.html) can be used to read individual values.
- **Writing Data** : Data chunks can be created using`duckdb_create_data_chunk` . The data chunk can then be filled with values and used in`duckdb_append_data_chunk` to write data to the database.

The primary manner of interfacing with data chunks is by obtaining the internal vectors of the data chunk using the `duckdb_data_chunk_get_vector` method. Afterwards, the [vector methods](/docs/current/clients/c/vector.html) can be used to read from or write to the individual vectors.

## 
        
        [API Reference Overview](#api-reference-overview)
        
      

    
`duckdb_data_chunk` [duckdb_create_data_chunk](#duckdb_create_data_chunk)(duckdb_logical_type *types, idx_t column_count);
void [duckdb_destroy_data_chunk](#duckdb_destroy_data_chunk)(duckdb_data_chunk *chunk);
void [duckdb_data_chunk_reset](#duckdb_data_chunk_reset)(duckdb_data_chunk chunk);
idx_t [duckdb_data_chunk_get_column_count](#duckdb_data_chunk_get_column_count)(duckdb_data_chunk chunk);
duckdb_vector [duckdb_data_chunk_get_vector](#duckdb_data_chunk_get_vector)(duckdb_data_chunk chunk, idx_t col_idx);
idx_t [duckdb_data_chunk_get_size](#duckdb_data_chunk_get_size)(duckdb_data_chunk chunk);
void [duckdb_data_chunk_set_size](#duckdb_data_chunk_set_size)(duckdb_data_chunk chunk, idx_t size);
#### 
        
        [`duckdb_create_data_chunk`](#duckdb_create_data_chunk)
        
      

    
`duckdb_create_data_chunk`
Creates an empty data chunk with the specified column types.
The result must be destroyed with `duckdb_destroy_data_chunk`.

##### 
        
        [Syntax](#syntax)
        
      

    
```
duckdb_data_chunk duckdb_create_data_chunk(
  duckdb_logical_type *types,
  idx_t column_count
);
```
##### 
        
        [Parameters](#parameters)
        
      

    
- `types` : An array of column types. Column types cannot contain ANY and INVALID types.
- `column_count` : The number of columns.

##### 
        
        [Return Value](#return-value)
        
      

    
The data chunk.

#### 
        
        [`duckdb_destroy_data_chunk`](#duckdb_destroy_data_chunk)
        
      

    
`duckdb_destroy_data_chunk`
Destroys the data chunk and de-allocates all memory allocated for that chunk.

##### 
        
        [Syntax](#syntax-1)
        
      

    
```
void duckdb_destroy_data_chunk(
  duckdb_data_chunk *chunk
);
```
##### 
        
        [Parameters](#parameters-1)
        
      

    
- `chunk` : The data chunk to destroy.

#### 
        
        [`duckdb_data_chunk_reset`](#duckdb_data_chunk_reset)
        
      

    
`duckdb_data_chunk_reset`
Resets a data chunk, clearing the validity masks and setting the cardinality of the data chunk to 0.
After calling this method, you must call `duckdb_vector_get_validity` and `duckdb_vector_get_data` to obtain current
data and validity pointers

##### 
        
        [Syntax](#syntax-2)
        
      

    
```
void duckdb_data_chunk_reset(
  duckdb_data_chunk chunk
);
```
##### 
        
        [Parameters](#parameters-2)
        
      

    
- `chunk` : The data chunk to reset.

#### 
        
        [`duckdb_data_chunk_get_column_count`](#duckdb_data_chunk_get_column_count)
        
      

    
`duckdb_data_chunk_get_column_count`
Retrieves the number of columns in a data chunk.

##### 
        
        [Syntax](#syntax-3)
        
      

    
```
idx_t duckdb_data_chunk_get_column_count(
  duckdb_data_chunk chunk
);
```
##### 
        
        [Parameters](#parameters-3)
        
      

    
- `chunk` : The data chunk to get the data from

##### 
        
        [Return Value](#return-value-1)
        
      

    
The number of columns in the data chunk

#### 
        
        [`duckdb_data_chunk_get_vector`](#duckdb_data_chunk_get_vector)
        
      

    
`duckdb_data_chunk_get_vector`
Retrieves the vector at the specified column index in the data chunk.

The pointer to the vector is valid for as long as the chunk is alive. It does NOT need to be destroyed.

##### 
        
        [Syntax](#syntax-4)
        
      

    
```
duckdb_vector duckdb_data_chunk_get_vector(
  duckdb_data_chunk chunk,
  idx_t col_idx
);
```
##### 
        
        [Parameters](#parameters-4)
        
      

    
- `chunk` : The data chunk to get the data from

##### 
        
        [Return Value](#return-value-2)
        
      

    
The vector

#### 
        
        [`duckdb_data_chunk_get_size`](#duckdb_data_chunk_get_size)
        
      

    
`duckdb_data_chunk_get_size`
Retrieves the current number of tuples in a data chunk.

##### 
        
        [Syntax](#syntax-5)
        
      

    
```
idx_t duckdb_data_chunk_get_size(
  duckdb_data_chunk chunk
);
```
##### 
        
        [Parameters](#parameters-5)
        
      

    
- `chunk` : The data chunk to get the data from

##### 
        
        [Return Value](#return-value-3)
        
      

    
The number of tuples in the data chunk

#### 
        
        [`duckdb_data_chunk_set_size`](#duckdb_data_chunk_set_size)
        
      

    
`duckdb_data_chunk_set_size`
Sets the current number of tuples in a data chunk.

##### 
        
        [Syntax](#syntax-6)
        
      

    
```
void duckdb_data_chunk_set_size(
  duckdb_data_chunk chunk,
  idx_t size
);
```
##### 
        
        [Parameters](#parameters-6)
        
      

    
- `chunk` : The data chunk to set the size in
- `size` : The number of tuples in the data chunk

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/data_chunk
