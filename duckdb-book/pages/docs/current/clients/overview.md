---
type: Web Page
title: Client Overview – DuckDB
description: DuckDB is an in-process database system and offers client APIs (“drivers”)
  for several languages. Client API Maintainer Support tier Latest version C Core
  team {% include tooltip.html label="Primary" id="support_tier_primary" %} {% if
  site.current_duckdb_version != "" %}{{ site.current_duckdb_version }}{% else %}{{
  site.lts_duckdb_version }}{% endif %} Command Line Interface (CLI) Core team {%
  include tooltip.html label="Primary" id="support_tier_primary" %} {% if site.current_duckdb_version
  != "" %}{{ site.current_duckdb_version }}{% else %}{{ site.lts_duckdb_version }}{%
  endif %} Java (JDBC) Core team {% include tooltip.html label="Primary" id="support_tier_primary"
  %} {% if site.current_duckdb_java_short_version != "" %}{{ site.current_duckdb_java_short_version
  }}{% else %}{{ site.lts_duckdb_java_short_version }}{% endif %} Go Core team {%
  include tooltip.html…
resource: https://duckdb.org/docs/current/clients/overview
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

DuckDB is an in-process database system and offers client APIs (“drivers”) for several languages.

| Client API | Maintainer | Support tier | Latest version | 
|---|---|---|---|
| C | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| Command Line Interface (CLI) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| Java (JDBC) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| Go | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| Node.js (node-neo) | Jeff Raymakers | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| ODBC | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| Python | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| R | Kirill Müller | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| Rust | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| WebAssembly (Wasm) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | 1.5.4 | 
| ADBC (Arrow) | Core team | SecondarySecondary clients receive new features but are not covered by community support. | 1.5.4 | 
| C# (.NET) | Giorgi | SecondarySecondary clients receive new features but are not covered by community support. | 1.5.3 | 
| C++ | Core team | SecondarySecondary clients receive new features but are not covered by community support. | 1.5.4 | 

The table above lists the DuckDB clients with the primary and secondary support tiers. For a list of tertiary clients, see the “Tertiary Clients” page.

## Support Tiers

There are three tiers of support for clients. Primary clients are the first to receive new features and are covered by community support. Secondary clients receive new features but are not covered by community support. Finally, there are no feature or support guarantees for tertiary clients.

The DuckDB clients listed above are open-source and we welcome community contributions to these libraries. All primary and secondary clients are available under the MIT license. For tertiary clients, please consult the repository for the license.

## Compatibility

All DuckDB clients support the same DuckDB SQL syntax and use the same on-disk database format. DuckDB extensions are also portable between clients with some exceptions (see Wasm extensions).

# Citations

1. Source page: https://duckdb.org/docs/current/clients/overview
