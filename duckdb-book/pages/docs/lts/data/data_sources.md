---
type: Web Page
title: Data Sources – DuckDB
description: 'DuckDB sources several data sources, including file formats, network
  protocols and database systems: AWS S3 buckets and storage with S3-compatible API
  Azure Blob Storage Blob files Cloudflare R2 CSV Delta Lake Excel httpfs Iceberg
  JSON MySQL Parquet PostgreSQL SQLite Text files'
resource: https://duckdb.org/docs/lts/data/data_sources
timestamp: '2026-07-07T12:26:08.924159+00:00'
---

Search Shortcut cmd + k | ctrl + k
		

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

  
  
  Documentation
  
    
    
  
    
    
      
        
        
      
        
        
      
        
        
          / Data Import and Export
          
          
          
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
          
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
    
  
  

Data Sources

				DuckDB sources several data sources, including file formats, network protocols and database systems:

- AWS S3 buckets and storage with S3-compatible API
- Azure Blob Storage
- Blob files
- Cloudflare R2
- CSV
- Delta Lake
- Excel
- httpfs
- Iceberg
- JSON
- MySQL
- Parquet
- PostgreSQL
- SQLite
- Text files

##### About this page

© 2026 DuckDB Foundation, Amsterdam NL

# Citations

1. Source page: https://duckdb.org/docs/lts/data/data_sources
