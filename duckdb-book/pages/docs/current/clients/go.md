---
type: Web Page
title: Go Client – DuckDB
description: 'Installation To use the DuckDB Go client, visit the Go installation
  page. The latest stable version of the DuckDB Go client is {% if site.current_duckdb_go_version
  != "" %}{{ site.current_duckdb_go_version }}{% else %}{{ site.lts_duckdb_go_version
  }}{% endif %}. The DuckDB Go client, duckdb-go, allows using DuckDB via the database/sql
  interface. For examples on how to use this interface, see the official documentation
  and tutorial. Installation To install the duckdb-go client, run: go get github.com/duckdb/duckdb-go/v2
  Importing To import the DuckDB Go package, add the following entries to your imports:
  import ( "database/sql" _ "github.com/duckdb/duckdb-go/v2" ) Appender The DuckDB
  Go client supports the DuckDB…'
resource: https://duckdb.org/docs/current/clients/go
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

Installation To use the DuckDB Go client, visit the Go installation page.

The latest stable version of the DuckDB Go client is 1.5.4.

The DuckDB Go client, `duckdb-go`, allows using DuckDB via the `database/sql` interface.
For examples on how to use this interface, see the official documentation and tutorial.

## Installation

To install the `duckdb-go` client, run:

```
go get github.com/duckdb/duckdb-go/v2
```
## Importing

To import the DuckDB Go package, add the following entries to your imports:

```
import (
	"database/sql"
	_ "github.com/duckdb/duckdb-go/v2"
)
```
## Appender

The DuckDB Go client supports the DuckDB Appender API for bulk inserts. You can obtain a new Appender by supplying a DuckDB connection to `NewAppenderFromConn()`. For example:

```
connector, err := duckdb.NewConnector("test.db", nil)
if err != nil {
	...
}
conn, err := connector.Connect(context.Background())
if err != nil {
	...
}
defer conn.Close()
// Retrieve appender from connection (note that you have to create the table 'test' beforehand).
appender, err := NewAppenderFromConn(conn, "", "test")
if err != nil {
	...
}
defer appender.Close()
err = appender.AppendRow(...)
if err != nil {
	...
}
// Optional, if you want to access the appended rows immediately.
err = appender.Flush()
if err != nil {
	...
}
```
## Examples

### Simple Example

An example for using the Go API is as follows:

```
package main
import (
	"database/sql"
	"errors"
	"fmt"
	"log"
	_ "github.com/duckdb/duckdb-go/v2"
)
func main() {
	db, err := sql.Open("duckdb", "")
	if err != nil {
		log.Fatal(err)
	}
	defer db.Close()
	_, err = db.Exec(`CREATE TABLE people (id INTEGER, name VARCHAR)`)
	if err != nil {
		log.Fatal(err)
	}
	_, err = db.Exec(`INSERT INTO people VALUES (42, 'John')`)
	if err != nil {
		log.Fatal(err)
	}
	var (
		id   int
		name string
	)
	row := db.QueryRow(`SELECT id, name FROM people`)
	err = row.Scan(&id, &name)
	if errors.Is(err, sql.ErrNoRows) {
		log.Println("no rows")
	} else if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("id: %d, name: %s\n", id, name)
}
```
### More Examples

For more examples, see the examples in the `duckdb-go` repository.

## Acknowledgements

We would like to thank Marc Boeker for the initial implementation of the DuckDB Go client.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/go
