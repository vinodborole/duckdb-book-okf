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

The replacement scan API can be used to register a callback that is called when a table is read that does not exist in the catalog. For example, when a query such as `SELECT * FROM my_table` is executed and `my_table` does not exist, the replacement scan callback will be called with `my_table` as parameter. The replacement scan can then insert a table function with a specific parameter to replace the read of the table.

## API Reference Overview

```
void duckdb_add_replacement_scan(duckdb_database db, duckdb_replacement_callback_t replacement, void *extra_data, duckdb_delete_callback_t delete_callback);
void duckdb_replacement_scan_set_function_name(duckdb_replacement_scan_info info, const char *function_name);
void duckdb_replacement_scan_add_parameter(duckdb_replacement_scan_info info, duckdb_value parameter);
void duckdb_replacement_scan_set_error(duckdb_replacement_scan_info info, const char *error);
```
#### 
        
        `duckdb_add_replacement_scan`
        
      

    
Add a replacement scan definition to the specified database.

##### Syntax

```
void duckdb_add_replacement_scan(
  duckdb_database db,
  duckdb_replacement_callback_t replacement,
  void *extra_data,
  duckdb_delete_callback_t delete_callback
);
```
##### Parameters

- `db`: The database object to add the replacement scan to
- `replacement`: The replacement scan callback
- `extra_data`: Extra data that is passed back into the specified callback
- `delete_callback`: The delete callback to call on the extra data, if any

#### 
        
        `duckdb_replacement_scan_set_function_name`
        
      

    
Sets the replacement function name. If this function is called in the replacement callback, the replacement scan is performed. If it is not called, the replacement callback is not performed.

##### Syntax

```
void duckdb_replacement_scan_set_function_name(
  duckdb_replacement_scan_info info,
  const char *function_name
);
```
##### Parameters

- `info`: The info object
- `function_name`: The function name to substitute.

#### 
        
        `duckdb_replacement_scan_add_parameter`
        
      

    
Adds a parameter to the replacement scan function.

##### Syntax

```
void duckdb_replacement_scan_add_parameter(
  duckdb_replacement_scan_info info,
  duckdb_value parameter
);
```
##### Parameters

- `info`: The info object
- `parameter`: The parameter to add.

#### 
        
        `duckdb_replacement_scan_set_error`
        
      

    
Report that an error has occurred while executing the replacement scan.

##### Syntax

```
void duckdb_replacement_scan_set_error(
  duckdb_replacement_scan_info info,
  const char *error
);
```
##### Parameters

- `info`: The info object
- `error`: The error message

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/replacement_scans
