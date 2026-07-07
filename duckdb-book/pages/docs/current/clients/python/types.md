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
timestamp: '2026-07-07T12:26:08.924159+00:00'
---

- Installation
- Documentation
- Getting Started
- Connect
- Data Import and Export
- Overview
- Data Sources
- CSV Files
- JSON Files
- Overview
- Creating JSON
- Loading JSON
- Writing JSON
- JSON Type
- JSON Functions
- Format Settings
- Installing and Loading
- SQL to / from JSON
- Caveats
- Multiple Files
- Parquet Files
- Partitioning
- Appender
- INSERT Statements
- Lakehouse Formats
- Client APIs
- Overview
- ADBC
- C
- Overview
- Startup
- Configuration
- Query
- Data Chunks
- Vectors
- Values
- Types
- Prepared Statements
- Appender
- Table Functions
- Replacement Scans
- API Reference
- C++
- CLI
- Overview
- Arguments
- Dot Commands
- Output Formats
- Editing
- Friendly CLI
- Safe Mode
- Autocomplete
- Syntax Highlighting
- Known Issues
- Go
- Java (JDBC)
- Node.js (Neo)
- ODBC
- Python
- Overview
- Data Ingestion
- Conversion between DuckDB and Python
- DB API
- Relational API
- Function API
- Types API
- Expression API
- Spark API
- API Reference
- Known Python Issues
- R
- Rust
- Wasm
- Tertiary Clients
- SQL
- Introduction
- Statements
- Overview
- ANALYZE
- ALTER TABLE
- ALTER VIEW
- ATTACH and DETACH
- CALL
- CHECKPOINT
- COMMENT ON
- COPY
- CREATE INDEX
- CREATE MACRO
- CREATE SCHEMA
- CREATE SECRET
- CREATE SEQUENCE
- CREATE TABLE
- CREATE VIEW
- CREATE TYPE
- DELETE
- DESCRIBE
- DROP
- EXPORT and IMPORT DATABASE
- INSERT
- LOAD / INSTALL
- MERGE INTO
- PIVOT
- Profiling
- SELECT
- SET / RESET
- SET VARIABLE
- SHOW and SHOW DATABASES
- SUMMARIZE
- Transaction Management
- UNPIVOT
- UPDATE
- USE
- VACUUM
- Query Syntax
- SELECT
- FROM and JOIN
- WHERE
- GROUP BY
- GROUPING SETS
- HAVING
- ORDER BY
- LIMIT and OFFSET
- SAMPLE
- Unnesting
- WITH
- WINDOW
- QUALIFY
- VALUES
- FILTER
- Set Operations
- Prepared Statements
- Data Types
- Overview
- Array
- Bitstring
- Blob
- Boolean
- Date
- Enum
- Geometry
- Interval
- List
- Literal Types
- Map
- NULL Values
- Numeric
- Struct
- Text
- Time
- Timestamp
- Time Zones
- Union
- Typecasting
- Variant
- Expressions
- Overview
- CASE Expression
- Casting
- Collations
- Comparisons
- IN Operator
- Logical Operators
- Star Expression
- Subqueries
- TRY
- Functions
- Overview
- Aggregate Functions
- Array Functions
- Bitstring Functions
- Blob Functions
- Date Format Functions
- Date Functions
- Date Part Functions
- Enum Functions
- Geometry Functions
- Interval Functions
- Lambda Functions
- List Functions
- Map Functions
- Nested Functions
- Numeric Functions
- Pattern Matching
- Regular Expressions
- Struct Functions
- Text Functions
- Time Functions
- Timestamp Functions
- Timestamp with Time Zone Functions
- Union Functions
- Utility Functions
- Window Functions
- Constraints
- Indexes
- Meta Queries
- DuckDB's SQL Dialect
- Overview
- Indexing
- Friendly SQL
- Keywords and Identifiers
- Order Preservation
- PostgreSQL Compatibility
- SQL Quirks
- PEG Parser
- Samples
- Configuration
- Extensions
- Overview
- Installing Extensions
- Advanced Installation Methods
- Distributing Extensions
- Versioning of Extensions
- Troubleshooting of Extensions
- Core Extensions
- Overview
- AutoComplete
- Avro
- AWS
- Azure
- Delta
- DuckLake
- Encodings
- Excel
- Full Text Search
- httpfs (HTTP and S3)
- Iceberg
- Overview
- Writing to Iceberg
- Iceberg REST Catalogs
- Functions and Settings Reference
- Amazon S3 Tables
- Amazon SageMaker Lakehouse (AWS Glue)
- Troubleshooting
- ICU
- inet
- jemalloc
- Lance
- MotherDuck
- MySQL
- ODBC
- Quack
- PostgreSQL
- Spatial
- SQLite
- TPC-DS
- TPC-H
- UI
- Unity Catalog
- Vortex
- VSS
- Quack Remote Protocol
- Guides
- Overview
- Data Viewers
- Database Integration
- File Formats
- Overview
- CSV Import
- CSV Export
- Directly Reading Files
- Directly Reading DuckDB Databases
- Excel Import
- Excel Export
- JSON Import
- JSON Export
- Parquet Import
- Parquet Export
- Querying Parquet Files
- File Access with the file: Protocol
- Meta Queries
- Describe Table
- EXPLAIN: Inspect Query Plans
- EXPLAIN ANALYZE: Profile Queries
- List Tables
- Summarize
- DuckDB Environment
- Network and Cloud Storage
- Overview
- HTTP Parquet Import
- S3 Parquet Import
- S3 Parquet Export
- S3 Iceberg Import
- S3 Express One
- GCS Import
- Cloudflare R2 Import
- DuckDB over HTTPS / S3
- Fastly Object Storage Import
- Tigris Import
- ODBC
- Performance
- Overview
- Environment
- Import
- Schema
- Indexing
- Join Operations
- File Formats
- How to Tune Workloads
- My Workload Is Slow
- Out-of-Memory Issues
- Benchmarks
- Working with Huge Databases
- Python
- Installation
- Executing SQL
- Jupyter Notebooks
- marimo Notebooks
- SQL on Pandas
- Import from Pandas
- Export to Pandas
- Import from Numpy
- Export to Numpy
- SQL on Arrow
- Import from Arrow
- Export to Arrow
- Relational API on Pandas
- Multiple Python Threads
- Integration with Ibis
- Integration with Polars
- Using fsspec Filesystems
- SQL Editors
- SQL Features
- AsOf Join
- Full-Text Search
- Graph Queries
- query and query_table Functions
- Merge Statement for SCD Type 2
- Timestamp Issues
- Snippets
- Creating Synthetic Data
- Dutch Railway Datasets
- Sharing Macros
- Analyzing a Git Repository
- Importing Duckbox Tables
- Copying an In-Memory Database to a File
- Troubleshooting
- Glossary of Terms
- Browsing Offline
- Operations Manual
- Overview
- DuckDB's Footprint
- Installing DuckDB
- Logging
- User Agents
- Securing DuckDB
- Non-Deterministic Behavior
- Limits
- DuckDB Docker Container
- Development
- DuckDB Repositories
- Release Cycle
- Metrics
- Profiling
- Building DuckDB
- Overview
- Build Configuration
- Building Extensions
- Android
- Linux
- macOS
- Raspberry Pi
- Windows
- Python
- R
- Troubleshooting
- Unofficial and Unsupported Platforms
- Benchmark Suite
- Testing
- Internals
- Sitemap
- Live Demo

The `DuckDBPyType` class represents a type instance of our data types.

## Converting from Other Types

To make the API as easy to use as possible, we have added implicit conversions from existing type objects to a DuckDBPyType instance. This means that wherever a DuckDBPyType object is expected, it is also possible to provide any of the options listed below.

### Python Built-Ins

The table below shows the mapping of Python Built-in types to DuckDB type.

| Built-in types | DuckDB type | 
|---|---|
| bool | BOOLEAN | 
| bytearray | BLOB | 
| bytes | BLOB | 
| float | DOUBLE | 
| int | BIGINT | 
| str | VARCHAR | 

### Numpy DTypes

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

### Nested Types

#### 
        
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
        
        `{'a': field_one, 'b': field_two, ..., 'n': field_n}`
        
      

    
`dict` objects map to a `STRUCT` composed of the keys and values of the dict.

```
import duckdb.sqltypes
print(duckdb.sqltypes.DuckDBPyType({'a': str, 'b': int}))
```
```
STRUCT(a VARCHAR, b BIGINT)
```
#### 
        
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
### Creation Functions

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
        
        `list_type` | `array_type`
        
      

    
Parameters:

- `child_type: DuckDBPyType`

#### 
        
        `struct_type` | `row_type`
        
      

    
Parameters:

- `fields: Union[list[DuckDBPyType], dict[str, DuckDBPyType]]`

#### 
        
        `map_type`
        
      

    
Parameters:

- `key_type: DuckDBPyType`
- `value_type: DuckDBPyType`

#### 
        
        `decimal_type`
        
      

    
Parameters:

- `width: int`
- `scale: int`

#### 
        
        `union_type`
        
      

    
Parameters:

- `members: Union[list[DuckDBPyType], dict[str, DuckDBPyType]]`

#### 
        
        `string_type`
        
      

    
Parameters:

- `collation: Optional[str]`

# Citations

1. Source page: https://duckdb.org/docs/current/clients/python/types
