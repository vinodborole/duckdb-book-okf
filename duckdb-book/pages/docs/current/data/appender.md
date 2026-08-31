---
type: Web Page
title: Appender – DuckDB
description: The Appender can be used to load bulk data into a DuckDB database. It
  is available in the C, C++, Go, Java, Julia, Node.js, and Rust clients. This page
  describes how the Appender behaves across clients and shows a minimal example in
  each of them. For the full API of a given client, follow the links under Client
  APIs. How It Works An Appender is tied to a single connection and always appends
  to a single table in the database file, using that connection's transaction context.
  Values added to the Appender are cached before being inserted into the database,
  for…
resource: https://duckdb.org/docs/current/data/appender
timestamp: '2026-08-31T13:09:59.989662+00:00'
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
				 [Sitemap](/sitemap.html)
- 
				 [Live Demo](https://shell.duckdb.org)

The Appender can be used to load bulk data into a DuckDB database. It is available in the C, C++, Go, Java, Julia, Node.js, and Rust clients. This page describes how the Appender behaves across clients and shows a minimal example in each of them. For the full API of a given client, follow the links under [Client APIs](#client-apis).

## 
        
        [How It Works](#how-it-works)
        
      

    
An Appender is tied to a single connection and always appends to a single table in the database file, using that connection's transaction context.

Values added to the Appender are cached before being inserted into the database, for performance reasons. That means that, while appending, the rows might not be immediately visible in the system. The cache is flushed automatically when the Appender is closed or goes out of scope, and it can also be flushed manually. Once the Appender has been flushed or closed, all of its data has been written to the database.

Constraints such as `NOT NULL`, `PRIMARY KEY`, and `UNIQUE` are checked when the cache is flushed rather than as each row is added, so a row can be accepted but later fail at flush time. See [Handling Constraint Violations](#handling-constraint-violations).

## 
        
        [Creating an Appender](#creating-an-appender)
        
      

    
Each client creates an Appender from a connection and a target table, adds rows, and then flushes. The examples below insert into a table with an integer and a string column.

### 
        
        [C++](#c)
        
      

    
The `AppendRow` function is the easiest way of appending data. It uses recursive templates to allow you to put all the values of a single row within one function call:

```
DuckDB db;
Connection con(db);
con.Query("CREATE TABLE people (id INTEGER, name VARCHAR)");
Appender appender(con, "people");
appender.AppendRow(1, "Mark");
```
Rows can also be individually constructed using the `BeginRow`, `EndRow`, and `Append` methods. This is done internally by `AppendRow`, and hence has the same performance characteristics:

```
appender.BeginRow();
appender.Append<int32_t>(2);
appender.Append<string>("Hannes");
appender.EndRow();
```
For more information, see the [C++ client](/docs/current/clients/cpp.html).

### 
        
        [Java (JDBC)](#java-jdbc)
        
      

    
An appender is created from a `DuckDBConnection` with `createAppender()`, and rows are built with `beginRow()`, `append()`, and `endRow()`. Using try-with-resources flushes and closes it at the end of the scope:

```
try (var appender = conn.createAppender(DuckDBConnection.DEFAULT_SCHEMA, "tbl")) {
    appender.beginRow();
    appender.append(10);
    appender.append("hello");
    appender.endRow();
}
```
For more information, see the [Java Appender API](/docs/current/clients/java/data_import.html#appender).

### 
        
        [Go](#go)
        
      

    
Obtain an appender by supplying a connection to `NewAppenderFromConn()`, then add rows with `AppendRow()`:

```
appender, err := NewAppenderFromConn(conn, "", "test")
defer appender.Close()
err = appender.AppendRow(1, "hello")
// Optional, if you want to access the appended rows immediately.
err = appender.Flush()
```
For more information, see the [Go Appender API](/docs/current/clients/go.html#appender).

### 
        
        [Rust](#rust)
        
      

    
Create an appender from a `Connection` with `appender()`, then push rows built with the `params!` macro:

```
let mut app = conn.appender("foo")?;
app.append_row(params![1, "hello"])?;
app.flush()?;
```
For more information, see the [Rust Appender API](/docs/current/clients/rust/data_import.html#appender).

### 
        
        [C](#c-1)
        
      

    
For more information, see the [C Appender API](/docs/current/clients/c/appender.html).

## 
        
        [Date, Time and Timestamps](#date-time-and-timestamps)
        
      

    
While numbers and strings are rather self-explanatory, dates, times, and timestamps require some explanation. In the C++ API, they can be directly appended using the methods provided by `duckdb::Date`, `duckdb::Time` or `duckdb::Timestamp`. They can also be appended using the internal `duckdb::Value` type, however, this adds some additional overheads and should be avoided if possible.

Below is a short example:

```
con.Query("CREATE TABLE dates (d DATE, t TIME, ts TIMESTAMP)");
Appender appender(con, "dates");
// construct the values using the Date/Time/Timestamp types
// (this is the most efficient approach)
appender.AppendRow(
    Date::FromDate(1992, 1, 1),
    Time::FromTime(1, 1, 1, 0),
    Timestamp::FromDatetime(Date::FromDate(1992, 1, 1), Time::FromTime(1, 1, 1, 0))
);
// construct duckdb::Value objects
appender.AppendRow(
    Value::DATE(1992, 1, 1),
    Value::TIME(1, 1, 1, 0),
    Value::TIMESTAMP(1992, 1, 1, 1, 1, 1, 0)
);
```
## 
        
        [Commit Frequency](#commit-frequency)
        
      

    
By default, the appender performs commits every 204,800 rows.
You can change this by explicitly using [transactions](/docs/current/sql/statements/transactions.html) and surrounding your batches of appended rows by `BEGIN TRANSACTION` and `COMMIT` statements.

## 
        
        [Handling Constraint Violations](#handling-constraint-violations)
        
      

    
If the Appender encounters a `PRIMARY KEY` conflict or a `UNIQUE` constraint violation, it fails and returns the following error:

```
Constraint Error:
PRIMARY KEY or UNIQUE constraint violated: duplicate key "..."
```
In this case, the entire append operation fails and no rows are inserted.

## 
        
        [Client APIs](#client-apis)
        
      

    
Each client's documentation covers its full Appender API, including constructors for non-default schemas and catalogs and any client-specific features:

# Citations

1. Source page: https://duckdb.org/docs/current/data/appender
