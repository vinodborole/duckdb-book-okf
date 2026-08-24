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
timestamp: '2026-08-24T07:05:55.104476+00:00'
---

- 
				
					
					
					[Installation](/install)
- Documentation
- 
							 [Getting Started](/docs/lts/index)
- Connect
- Data Import and Export
- 
								 [Overview](/docs/lts/data/overview)
- 
								 [Data Sources](/docs/lts/data/data_sources)
- CSV Files
- JSON Files
- Multiple Files
- Parquet Files
- Partitioning
- 
								 [Appender](/docs/lts/data/appender)
- 
								 [INSERT Statements](/docs/lts/data/insert)
- 
							 [Lakehouse Formats](/docs/lts/lakehouse_formats)
- Client APIs
- 
								 [Overview](/docs/lts/clients/overview)
- 
								 [Tertiary Clients](/docs/lts/clients/tertiary)
- 
								 [ADBC](/docs/lts/clients/adbc)
- C
- 
								 [C++](/docs/lts/clients/cpp)
- CLI
- 
								 [Dart](/docs/lts/clients/dart)
- 
								 [Go](/docs/lts/clients/go)
- Java (JDBC)
- 
								 [Julia](/docs/lts/clients/julia)
- Node.js (Deprecated)
- Node.js (Neo)
- ODBC
- 
								 [PHP](/docs/lts/clients/php)
- Python
- 
								 [R](/docs/lts/clients/r)
- 
								 [Rust](/docs/lts/clients/rust)
- 
								 [Swift](/docs/lts/clients/swift)
- Wasm
- SQL
- 
								 [Introduction](/docs/lts/sql/introduction)
- Statements
- Query Syntax
- Data Types
- 
									  [Overview](/docs/lts/sql/data_types/overview) 
- 
									  [Array](/docs/lts/sql/data_types/array) 
- 
									  [Bitstring](/docs/lts/sql/data_types/bitstring) 
- 
									  [Blob](/docs/lts/sql/data_types/blob) 
- 
									  [Boolean](/docs/lts/sql/data_types/boolean) 
- 
									  [Date](/docs/lts/sql/data_types/date) 
- 
									  [Enum](/docs/lts/sql/data_types/enum) 
- 
									  [Interval](/docs/lts/sql/data_types/interval) 
- 
									  [List](/docs/lts/sql/data_types/list) 
- 
									  [Literal Types](/docs/lts/sql/data_types/literal_types) 
- 
									  [Map](/docs/lts/sql/data_types/map) 
- 
									  [NULL Values](/docs/lts/sql/data_types/nulls) 
- 
									  [Numeric](/docs/lts/sql/data_types/numeric) 
- 
									  [Struct](/docs/lts/sql/data_types/struct) 
- 
									  [Text](/docs/lts/sql/data_types/text) 
- 
									  [Time](/docs/lts/sql/data_types/time) 
- 
									  [Timestamp](/docs/lts/sql/data_types/timestamp) 
- 
									  [Time Zones](/docs/lts/sql/data_types/timezones) 
- 
									  [Union](/docs/lts/sql/data_types/union) 
- 
									  [Typecasting](/docs/lts/sql/data_types/typecasting) 
- Expressions
- Functions
- 
								 [Constraints](/docs/lts/sql/constraints)
- 
								 [Indexes](/docs/lts/sql/indexes)
- Meta Queries
- DuckDB's SQL Dialect
- 
								 [Samples](/docs/lts/sql/samples)
- Configuration
- Extensions
- Core Extensions
- 
								 [Overview](/docs/lts/core_extensions/overview)
- 
								 [AutoComplete](/docs/lts/core_extensions/autocomplete)
- 
								 [Avro](/docs/lts/core_extensions/avro)
- 
								 [AWS](/docs/lts/core_extensions/aws)
- 
								 [Azure](/docs/lts/core_extensions/azure)
- 
								 [Delta](/docs/lts/core_extensions/delta)
- 
								 [DuckLake](/docs/lts/core_extensions/ducklake)
- 
								 [Encodings](/docs/lts/core_extensions/encodings)
- 
								 [Excel](/docs/lts/core_extensions/excel)
- 
								 [Full Text Search](/docs/lts/core_extensions/full_text_search)
- httpfs (HTTP and S3)
- Iceberg
- 
								 [ICU](/docs/lts/core_extensions/icu)
- 
								 [inet](/docs/lts/core_extensions/inet)
- 
								 [jemalloc](/docs/lts/core_extensions/jemalloc)
- 
								 [Lance](/docs/lts/core_extensions/lance)
- 
								 [MySQL](/docs/lts/core_extensions/mysql)
- 
								 [PostgreSQL](/docs/lts/core_extensions/postgres)
- Spatial
- 
								 [SQLite](/docs/lts/core_extensions/sqlite)
- 
								 [TPC-DS](/docs/lts/core_extensions/tpcds)
- 
								 [TPC-H](/docs/lts/core_extensions/tpch)
- 
								 [UI](/docs/lts/core_extensions/ui)
- 
								 [Unity Catalog](/docs/lts/core_extensions/unity_catalog)
- 
								 [Vortex](/docs/lts/core_extensions/vortex)
- 
								 [VSS](/docs/lts/core_extensions/vss)
- Guides
- 
								 [Overview](/docs/lts/guides/overview)
- Data Viewers
- Database Integration
- File Formats
- Network and Cloud Storage
- Meta Queries
- ODBC
- Performance
- Python
- SQL Editors
- SQL Features
- Snippets
- Troubleshooting
- 
								 [Glossary of Terms](/docs/lts/guides/glossary)
- 
								 [Browsing Offline](/docs/lts/guides/offline-copy)
- Operations Manual
- 
								 [Overview](/docs/lts/operations_manual/overview)
- DuckDB's Footprint
- Installing DuckDB
- Logging
- Securing DuckDB
- 
								 [Non-Deterministic Behavior](/docs/lts/operations_manual/non-deterministic_behavior)
- 
								 [Limits](/docs/lts/operations_manual/limits)
- 
								 [DuckDB Docker Container](/docs/lts/operations_manual/duckdb_docker)
- Development
- 
								 [DuckDB Repositories](/docs/lts/dev/repositories)
- 
								 [Release Cycle](/docs/lts/dev/release_cycle)
- 
								 [Profiling](/docs/lts/dev/profiling)
- Building DuckDB
- 
								 [Benchmark Suite](/docs/lts/dev/benchmark)
- Testing
- Internals
- 
				 [Sitemap](/sitemap.html)
- 
				 [Live Demo](https://shell.duckdb.org)

## 
        
        [Handling Concurrency](#handling-concurrency)
        
      

    
DuckDB has two configurable options for concurrency:

1. One process can both read and write to the database.
2. Multiple processes can read from the database, but no processes can write ([`access_mode = 'READ_ONLY'`](/docs/lts/configuration/overview.html#configuration-reference) ).

When using option 1, DuckDB supports multiple writer threads using a combination of [MVCC (Multi-Version Concurrency Control)](https://en.wikipedia.org/wiki/Multiversion_concurrency_control) and optimistic concurrency control (see [Concurrency within a Single Process](#concurrency-within-a-single-process)), but all within that single writer process. The reason for this concurrency model is to allow for the caching of data in RAM for faster analytical queries, rather than going back and forth to disk during each query. It also allows the caching of functions pointers, the database catalog, and other items so that subsequent queries on the same connection are faster.

  DuckDB is optimized for bulk operations, so executing many small transactions is not a primary design goal.

## 
        
        [Concurrency within a Single Process](#concurrency-within-a-single-process)
        
      

    
DuckDB supports concurrency within a single process according to the following rules. As long as there are no write conflicts, multiple concurrent writes will succeed. Appends will never conflict, even on the same table. Multiple threads can also simultaneously update separate tables or separate subsets of the same table. Optimistic concurrency control comes into play when two threads attempt to edit (update or delete) the same row at the same time. In that situation, the second thread to attempt the edit will fail with a conflict error.

## 
        
        [Writing to DuckDB from Multiple Processes](#writing-to-duckdb-from-multiple-processes)
        
      

    
Writing to DuckDB from multiple processes is not supported automatically and is not a primary design goal (see [Handling Concurrency](#handling-concurrency)).

If multiple processes must write to the same file, several design patterns are possible, but would need to be implemented in application logic. For example, each process could acquire a cross-process mutex lock, then open the database in read/write mode and close it when the query is complete. Instead of using a mutex lock, each process could instead retry the connection if another process is already connected to the database (being sure to close the connection upon query completion). Another alternative would be to do multi-process transactions on a MySQL, PostgreSQL, or SQLite database, and use DuckDB's [MySQL](/docs/lts/core_extensions/mysql.html), [PostgreSQL](/docs/lts/core_extensions/postgres.html), or [SQLite](/docs/lts/core_extensions/sqlite.html) extensions to execute analytical queries on that data periodically.

Additional options include writing data to Parquet files and using DuckDB's ability to [read multiple Parquet files](/docs/lts/data/parquet/overview.html), taking a similar approach with [CSV files](/docs/lts/data/csv/overview.html), or creating a web server to receive requests and manage reads and writes to DuckDB.

## 
        
        [Optimistic Concurrency Control](#optimistic-concurrency-control)
        
      

    
DuckDB uses [optimistic concurrency control](https://en.wikipedia.org/wiki/Optimistic_concurrency_control), an approach generally considered to be the best fit for read-intensive analytical database systems as it speeds up read query processing. As a result any transactions that modify the same rows at the same time will cause a transaction conflict error:

```
Transaction conflict: cannot update a table that has been altered!
```
  Tip A common workaround when a transaction conflict is encountered is to rerun the transaction.

# Citations

1. Source page: https://duckdb.org/docs/lts/connect/concurrency
