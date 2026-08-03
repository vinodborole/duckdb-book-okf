---
type: Web Page
title: Types API – DuckDB
description: The DuckDBPyType class represents a type instance of our data types.
  Converting from Other Types To make the API as easy to use as possible, we have
  added implicit conversions from existing type objects to a DuckDBPyType instance.
  This means that wherever a DuckDBPyType object is expected, it is also possible
  to provide any of the options listed below. Python Built-Ins The table below shows
  the mapping of Python Built-in types to DuckDB type. Built-in types DuckDB type
  bool BOOLEAN bytearray BLOB bytes BLOB float DOUBLE int BIGINT str VARCHAR Numpy
  DTypes The table below shows the mapping of Numpy…
resource: https://duckdb.org/docs/current/clients/python/types
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

The `DuckDBPyType` class represents a type instance of our [data types](/docs/current/sql/data_types/overview.html).

## 
        
        [Converting from Other Types](#converting-from-other-types)
        
      

    
To make the API as easy to use as possible, we have added implicit conversions from existing type objects to a DuckDBPyType instance. This means that wherever a DuckDBPyType object is expected, it is also possible to provide any of the options listed below.

### 
        
        [Python Built-Ins](#python-built-ins)
        
      

    
The table below shows the mapping of Python Built-in types to DuckDB type.

| Built-in types | DuckDB type | 
|---|---|
| bool | BOOLEAN | 
| bytearray | BLOB | 
| bytes | BLOB | 
| float | DOUBLE | 
| int | BIGINT | 
| str | VARCHAR | 

### 
        
        [Numpy DTypes](#numpy-dtypes)
        
      

    
The table below shows the mapping of Numpy DType to DuckDB type.

| Type | DuckDB type | 
|---|---|
| bool | BOOLEAN | 
| float32 | FLOAT | 
| float64 | DOUBLE | 
| int16 | SMALLINT | 
| int32 | INTEGER | 
| int64 | BIGINT | 
| int8 | TINYINT | 
| uint16 | USMALLINT | 
| uint32 | UINTEGER | 
| uint64 | UBIGINT | 
| uint8 | UTINYINT | 

### 
        
        [Nested Types](#nested-types)
        
      

    
      #### 
        
        [`list\[child_type\]`](#listchild_type)
        
      

    
`list[child_type]`
`list` type objects map to a `LIST` type of the child type.
Which can also be arbitrarily nested.

```
import duckdb.sqltypes
from typing import Union
duckdb.sqltypes.DuckDBPyType(list[dict[Union[str, int], str]])
```
```
MAP(UNION(u1 VARCHAR, u2 BIGINT), VARCHAR)[]
```
#### 
        
        [`dict\[key_type, value_type\]`](#dictkey_type-value_type)
        
      

    
`dict[key_type, value_type]`
`dict` type objects map to a `MAP` type of the key type and the value type.

```
import duckdb.sqltypes
print(duckdb.sqltypes.DuckDBPyType(dict[str, int]))
```
```
MAP(VARCHAR, BIGINT)
```
#### 
        
        [`{'a': field_one, 'b': field_two, ..., 'n': field_n}`](#a-field_one-b-field_two--n-field_n)
        
      

    
`dict` objects map to a `STRUCT` composed of the keys and values of the dict.

```
import duckdb.sqltypes
print(duckdb.sqltypes.DuckDBPyType({'a': str, 'b': int}))
```
```
STRUCT(a VARCHAR, b BIGINT)
```
#### 
        
        [`Union\[type_1, ... type_n\]`](#uniontype_1--type_n)
        
      

    
`Union[type_1, ... type_n]`
`typing.Union` objects map to a `UNION` type of the provided types.

```
import duckdb.sqltypes
from typing import Union
print(duckdb.sqltypes.DuckDBPyType(Union[int, str, bool, bytearray]))
```
```
UNION(u1 BIGINT, u2 VARCHAR, u3 BOOLEAN, u4 BLOB)
```
### 
        
        [Creation Functions](#creation-functions)
        
      

    
For the built-in types, you can use the constants defined in `duckdb.sqltypes`:

| DuckDB type | 
|---|
| BIGINT | 
| BIT | 
| BLOB | 
| BOOLEAN | 
| DATE | 
| DOUBLE | 
| FLOAT | 
| HUGEINT | 
| INTEGER | 
| INTERVAL | 
| SMALLINT | 
| SQLNULL | 
| TIME_TZ | 
| TIME | 
| TIMESTAMP_MS | 
| TIMESTAMP_NS | 
| TIMESTAMP_S | 
| TIMESTAMP_TZ | 
| TIMESTAMP | 
| TINYINT | 
| UBIGINT | 
| UHUGEINT | 
| UINTEGER | 
| USMALLINT | 
| UTINYINT | 
| UUID | 
| VARCHAR | 

For the complex types there are methods available on the `DuckDBPyConnection` object or the `duckdb` module.
Anywhere a `DuckDBPyType` is accepted, we will also accept one of the type objects that can implicitly convert to a `DuckDBPyType`.

#### 
        
        [`list_type` | `array_type`](#list_type--array_type)
        
      

    
`list_type` | `array_type`
Parameters:

- `child_type: DuckDBPyType`

#### 
        
        [`struct_type` | `row_type`](#struct_type--row_type)
        
      

    
`struct_type` | `row_type`
Parameters:

- `fields: Union[list[DuckDBPyType], dict[str, DuckDBPyType]]`

#### 
        
        [`map_type`](#map_type)
        
      

    
`map_type`
Parameters:

- `key_type: DuckDBPyType`
- `value_type: DuckDBPyType`

#### 
        
        [`decimal_type`](#decimal_type)
        
      

    
`decimal_type`
Parameters:

- `width: int`
- `scale: int`

#### 
        
        [`union_type`](#union_type)
        
      

    
`union_type`
Parameters:

- `members: Union[list[DuckDBPyType], dict[str, DuckDBPyType]]`

#### 
        
        [`string_type`](#string_type)
        
      

    
`string_type`
Parameters:

- `collation: Optional[str]`

# Citations

1. Source page: https://duckdb.org/docs/current/clients/python/types
