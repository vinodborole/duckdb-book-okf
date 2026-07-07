---
type: Web Page
title: Concurrency – DuckDB
description: 'Handling Concurrency DuckDB has two configurable options for concurrency:
  One process can both read and write to the database. Multiple processes can read
  from the database, but no processes can write (access_mode = ''READ_ONLY''). When
  using option 1, DuckDB supports multiple writer threads using a combination of MVCC
  (Multi-Version Concurrency Control) and optimistic concurrency control (see Concurrency
  within a Single Process), but all within that single writer process. The reason
  for this concurrency model is to allow for the caching of data in RAM for faster
  analytical queries, rather than going back and forth to disk during each query.
  It…'
resource: https://duckdb.org/docs/lts/connect/concurrency
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
- Tertiary Clients
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
- Safe Mode
- Autocomplete
- Syntax Highlighting
- Known Issues
- Dart
- Go
- Java (JDBC)
- Julia
- Node.js (Deprecated)
- Node.js (Neo)
- ODBC
- PHP
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
- Swift
- Wasm
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
- Iceberg REST Catalogs
- Amazon S3 Tables
- Amazon SageMaker Lakehouse (AWS Glue)
- Troubleshooting
- ICU
- inet
- jemalloc
- Lance
- MySQL
- PostgreSQL
- Spatial
- SQLite
- TPC-DS
- TPC-H
- UI
- Unity Catalog
- Vortex
- VSS
- Guides
- Overview
- Data Viewers
- Database Integration
- File Formats
- Overview
- CSV Import
- CSV Export
- Directly Reading Files
- Excel Import
- Excel Export
- JSON Import
- JSON Export
- Parquet Import
- Parquet Export
- Querying Parquet Files
- File Access with the file: Protocol
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
- Meta Queries
- Describe Table
- EXPLAIN: Inspect Query Plans
- EXPLAIN ANALYZE: Profile Queries
- List Tables
- Summarize
- DuckDB Environment
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
- Securing DuckDB
- Non-Deterministic Behavior
- Limits
- DuckDB Docker Container
- Development
- DuckDB Repositories
- Release Cycle
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

## Handling Concurrency

DuckDB has two configurable options for concurrency:

- One process can both read and write to the database.
- Multiple processes can read from the database, but no processes can write (`access_mode = 'READ_ONLY'`).

When using option 1, DuckDB supports multiple writer threads using a combination of MVCC (Multi-Version Concurrency Control) and optimistic concurrency control (see Concurrency within a Single Process), but all within that single writer process. The reason for this concurrency model is to allow for the caching of data in RAM for faster analytical queries, rather than going back and forth to disk during each query. It also allows the caching of functions pointers, the database catalog, and other items so that subsequent queries on the same connection are faster.

DuckDB is optimized for bulk operations, so executing many small transactions is not a primary design goal.

## Concurrency within a Single Process

DuckDB supports concurrency within a single process according to the following rules. As long as there are no write conflicts, multiple concurrent writes will succeed. Appends will never conflict, even on the same table. Multiple threads can also simultaneously update separate tables or separate subsets of the same table. Optimistic concurrency control comes into play when two threads attempt to edit (update or delete) the same row at the same time. In that situation, the second thread to attempt the edit will fail with a conflict error.

## Writing to DuckDB from Multiple Processes

Writing to DuckDB from multiple processes is not supported automatically and is not a primary design goal (see Handling Concurrency).

If multiple processes must write to the same file, several design patterns are possible, but would need to be implemented in application logic. For example, each process could acquire a cross-process mutex lock, then open the database in read/write mode and close it when the query is complete. Instead of using a mutex lock, each process could instead retry the connection if another process is already connected to the database (being sure to close the connection upon query completion). Another alternative would be to do multi-process transactions on a MySQL, PostgreSQL, or SQLite database, and use DuckDB's MySQL, PostgreSQL, or SQLite extensions to execute analytical queries on that data periodically.

Additional options include writing data to Parquet files and using DuckDB's ability to read multiple Parquet files, taking a similar approach with CSV files, or creating a web server to receive requests and manage reads and writes to DuckDB.

## Optimistic Concurrency Control

DuckDB uses optimistic concurrency control, an approach generally considered to be the best fit for read-intensive analytical database systems as it speeds up read query processing. As a result any transactions that modify the same rows at the same time will cause a transaction conflict error:

```
Transaction conflict: cannot update a table that has been altered!
```
Tip A common workaround when a transaction conflict is encountered is to rerun the transaction.

# Citations

1. Source page: https://duckdb.org/docs/lts/connect/concurrency
