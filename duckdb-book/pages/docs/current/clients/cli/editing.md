---
type: Web Page
title: Editing – DuckDB
description: The linenoise-based CLI editor is available for macOS, Linux and Windows.
  DuckDB's CLI uses a line-editing library based on linenoise, which has shortcuts
  that are based on Emacs mode of readline. Below is a list of available commands.
  You can also view these shortcuts from within the CLI using .help shortcuts. Moving
  Key Action Left Move back a character Right Move forward a character Up Move up
  a line. When on the first line, move to previous history entry Down Move down a
  line. When on last line, move to next history entry Home Move to beginning of buffer
  End…
resource: https://duckdb.org/docs/current/clients/cli/editing
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

  
  
  Documentation
  
    
    
  
    
    
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
          / Client APIs
          
          
          
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
                / CLI
                
                
                
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                    
                    
                  
                
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
              
              
            
          
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
        
        
      
    
  
  

Editing

				The linenoise-based CLI editor is available for macOS, Linux and Windows.

DuckDB's CLI uses a line-editing library based on linenoise, which has shortcuts that are based on Emacs mode of readline. Below is a list of available commands. You can also view these shortcuts from within the CLI using `.help shortcuts`.

## Moving

| Key | Action | 
|---|---|
| `Left` | Move back a character | 
| `Right` | Move forward a character | 
| `Up` | Move up a line. When on the first line, move to previous history entry | 
| `Down` | Move down a line. When on last line, move to next history entry | 
| `Home` | Move to beginning of buffer | 
| `End` | Move to end of buffer | 
| `Ctrl`+`Left` | Move back a word | 
| `Ctrl`+`Right` | Move forward a word | 
| `Ctrl`+`A` | Move to beginning of buffer | 
| `Ctrl`+`B` | Move back a character | 
| `Ctrl`+`E` | Move to end of buffer | 
| `Ctrl`+`F` | Move forward a character | 
| `Alt`+`Left` | Move back a word | 
| `Alt`+`Right` | Move forward a word | 

## History

| Key | Action | 
|---|---|
| `Ctrl`+`P` | Move to previous history entry | 
| `Ctrl`+`N` | Move to next history entry | 
| `Ctrl`+`R` | Search the history | 
| `Ctrl`+`S` | Search the history | 
| `Alt`+`<` | Move to first history entry | 
| `Alt`+`>` | Move to last history entry | 
| `Alt`+`N` | Search the history | 
| `Alt`+`P` | Search the history | 

## Changing Text

| Key | Action | 
|---|---|
| `Backspace` | Delete previous character | 
| `Delete` | Delete next character | 
| `Ctrl`+`D` | Delete next character. When buffer is empty, end editing | 
| `Ctrl`+`H` | Delete previous character | 
| `Ctrl`+`K` | Delete everything after the cursor | 
| `Ctrl`+`T` | Swap current and next character | 
| `Ctrl`+`U` | Delete all text | 
| `Ctrl`+`W` | Delete previous word | 
| `Alt`+`C` | Convert next word to titlecase | 
| `Alt`+`D` | Delete next word | 
| `Alt`+`L` | Convert next word to lowercase | 
| `Alt`+`R` | Delete all text | 
| `Alt`+`T` | Swap current and next word | 
| `Alt`+`U` | Convert next word to uppercase | 
| `Alt`+`Backspace` | Delete previous word | 
| `Alt`+`\` | Delete spaces around cursor | 

## Completing

| Key | Action | 
|---|---|
| `Tab` | Autocomplete. When autocompleting, cycle to next entry | 
| `Shift`+`Tab` | When autocompleting, cycle to previous entry | 
| `Esc`+`Esc` | When autocompleting, revert autocompletion | 

## Miscellaneous

| Key | Action | 
|---|---|
| `Enter` | Execute query. If query is not complete, insert a newline at the end of the buffer | 
| `Ctrl`+`J` | Execute query. If query is not complete, insert a newline at the end of the buffer | 
| `Ctrl`+`C` | Cancel editing of current query | 
| `Ctrl`+`G` | Cancel editing of current query | 
| `Ctrl`+`L` | Clear screen | 
| `Ctrl`+`O` | Cancel editing of current query | 
| `Ctrl`+`X` | Insert a newline after the cursor | 
| `Ctrl`+`Q`, then click | Move cursor to mouse click position | 
| `Ctrl`+`Z` | Suspend CLI and return to shell, use `fg`to re-open | 

## External Editor Mode

Use `.edit` or `\e` to open a query in an external text editor.

- When entered alone, it opens the previous command for editing.
- When used inside a multi-line command, it opens the current command in the editor.

The editor is taken from the first set environment variable among `DUCKDB_EDITOR`, `EDITOR` or `VISUAL` (in that order). If none are set, `vi` is used.

## Using Read-Line

If you prefer, you can use `rlwrap` to use read-line directly with the shell. Then, use `Shift`+`Enter` to insert a newline and `Enter` to execute the query:

```
rlwrap --substitute-prompt="D " duckdb -batch
```
##### About this page

© 2026 DuckDB Foundation, Amsterdam NL

# Citations

1. Source page: https://duckdb.org/docs/current/clients/cli/editing
