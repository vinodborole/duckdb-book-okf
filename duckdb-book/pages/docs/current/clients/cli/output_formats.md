---
type: Web Page
title: Output Formats – DuckDB
description: The .mode dot command may be used to change the appearance of the tables
  returned in the terminal output. In addition to customizing the appearance, these
  modes have additional benefits. This can be useful for presenting DuckDB output
  elsewhere by redirecting the terminal output to a file. Using the insert mode will
  build a series of SQL statements that can be used to insert the data at a later
  point. The markdown mode is particularly useful for building documentation and the
  latex mode is useful for writing academic papers. Warning Unicode handling in Windows
  Terminal When long results are displayed…
resource: https://duckdb.org/docs/current/clients/cli/output_formats
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

The `.mode` dot command may be used to change the appearance of the tables returned in the terminal output. In addition to customizing the appearance, these modes have additional benefits. This can be useful for presenting DuckDB output elsewhere by redirecting the terminal output to a file. Using the `insert` mode will build a series of SQL statements that can be used to insert the data at a later point.
The `markdown` mode is particularly useful for building documentation and the `latex` mode is useful for writing academic papers.

Warning Unicode handling in Windows Terminal

When long results are displayed in Windows Terminal the more system utility is used by default to provide the scrolling through the results. This utility has incomplete support of Unicode, depending on the output data, in some cases it can display Unicode characters in garbled form.

We suggest using the third-party less utility instead, that is installed by default along with the Git for Windows installation. It can be enabled the following way:

`.pager '"C:\Program Files\Git\usr\bin\less.exe" -R'`

## List of Output Formats

| Mode | Description | 
|---|---|
| `ascii` | Columns/rows delimited by 0x1F and 0x1E | 
| `box` | Tables using unicode box-drawing characters | 
| `csv` | Comma-separated values | 
| `column` | Output in columns (See `.width`) | 
| `duckbox` | Tables with extensive features (default) | 
| `html` | HTML `<table>`code | 
| `insert TABLE` | SQL insert statements for `TABLE` | 
| `json` | Results in a JSON array | 
| `jsonlines` | Results in a NDJSON | 
| `latex` | LaTeX tabular environment code | 
| `line` | One value per line | 
| `list` | Values delimited by `|` | 
| `markdown` | Markdown table format | 
| `quote` | Escape answers as for SQL | 
| `table` | ASCII-art table | 
| `tabs` | Tab-separated values | 
| `tcl` | TCL list elements | 
| `trash` | No output | 

## Changing the Output Format

Use the vanilla `.mode` dot command to query the appearance currently in use.

```
.mode
```
```
current output mode: duckbox
```
Use the `.mode` dot command with an argument to set the output format.

```
.mode markdown
SELECT 'quacking intensifies' AS incoming_ducks;
```
```
|    incoming_ducks    |
|----------------------|
| quacking intensifies |
```
The output appearance can also be adjusted with the `.separator` command. If using an export mode that relies on a separator (`csv` or `tabs` for example), the separator will be reset when the mode is changed. For example, `.mode csv` will set the separator to a comma (`,`). Using `.separator "|"` will then convert the output to be pipe-separated.

```
.mode csv
SELECT 1 AS col_1, 2 AS col_2
UNION ALL
SELECT 10 AS col1, 20 AS col_2;
```
```
col_1,col_2
1,2
10,20
```
```
.separator "|"
SELECT 1 AS col_1, 2 AS col_2
UNION ALL
SELECT 10 AS col1, 20 AS col_2;
```
```
col_1|col_2
1|2
10|20
```
## Paging

The CLI supports paging for large result sets using the `.pager` command. When enabled, results that exceed the terminal size are displayed in a pager (such as `less`) for easier navigation.

The pager has three modes:

- `automatic`(default) – The pager is triggered when the result exceeds the row or column threshold.
- `on`– The pager is always used for output.
- `off`– The pager is disabled.

```
.pager on
```
```
.pager off
```
```
.pager automatic
```
In automatic mode, the thresholds for triggering the pager can be configured:

```
.pager set_row_threshold 50
.pager set_column_threshold 5
```
A custom pager command can be set by passing it as an argument:

```
.pager less -RS
```
The default pager command can also be configured via the `DUCKDB_PAGER` or `PAGER` environment variables.

## 
        
        `duckbox` Mode
        
      

    
By default, DuckDB renders query results in `duckbox` mode, which is a feature-rich ASCII-art style output format.

The duckbox mode supports the `large_number_rendering` option, which allows human-readable rendering of large numbers. It has three levels:

- `off`– All numbers are printed using regular formatting.
- `footer`(default) – Large numbers are augmented with the human-readable format. Only applies to single-row results.
- `all`- All large numbers are replaced with the human-readable format.

See the following examples:

```
.large_number_rendering off
SELECT pi() * 1_000_000_000 AS x;
```
```
┌───────────────────┐
│         x         │
│      double       │
├───────────────────┤
│ 3141592653.589793 │
└───────────────────┘
```
```
.large_number_rendering footer
SELECT pi() * 1_000_000_000 AS x;
```
```
┌───────────────────┐
│         x         │
│      double       │
├───────────────────┤
│ 3141592653.589793 │
│  (3.14 billion)   │
└───────────────────┘
```
```
.large_number_rendering all
SELECT pi() * 1_000_000_000 AS x;
```
```
┌──────────────┐
│      x       │
│    double    │
├──────────────┤
│ 3.14 billion │
└──────────────┘
```

# Citations

1. Source page: https://duckdb.org/docs/current/clients/cli/output_formats
