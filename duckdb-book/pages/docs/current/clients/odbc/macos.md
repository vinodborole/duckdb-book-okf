---
type: Web Page
title: ODBC API on macOS – DuckDB
description: 'A driver manager is required to manage communication between applications
  and the ODBC driver. DuckDB supports unixODBC, which is a complete ODBC driver manager
  for macOS and Linux. Users can install it from the command line via Homebrew: brew
  install unixodbc DuckDB releases a universal [ODBC driver for macOS](https://github.com/duckdb/duckdb-odbc/releases/download/v{%
  if site.current_duckdb_odbc_version != "" %}{{ site.current_duckdb_odbc_version
  }}{% else %}{{ site.lts_duckdb_odbc_version }}{% endif %}/duckdb_odbc-osx-universal.zip)
  (supporting both Intel and Apple Silicon CPUs). To download it, run: wget https://github.com/duckdb/duckdb-odbc/releases/download/v{%
  if site.current_duckdb_odbc_version != "" %}{{ site.current_duckdb_odbc_version
  }}{% else %}{{ site.lts_duckdb_odbc_version }}{% endif %}/duckdb_odbc-osx-universal.zip
  The archive contains the libduckdb_odbc.dylib artifact. To extract it to a directory,…'
resource: https://duckdb.org/docs/current/clients/odbc/macos
timestamp: '2026-08-24T07:05:55.104476+00:00'
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

1. 
    A driver manager is required to manage communication between applications and the ODBC driver. DuckDB supports `unixODBC` , which is a complete ODBC driver manager for macOS and Linux. Users can install it from the command line via[Homebrew](https://brew.sh/) :```
brew install unixodbc
```
2. 
    
    DuckDB releases a universal [ODBC driver for macOS](https://github.com/duckdb/duckdb-odbc/releases/download/v1.5.5.0/duckdb_odbc-osx-universal.zip) (supporting both Intel and Apple Silicon CPUs). To download it, run:```
wget https://github.com/duckdb/duckdb-odbc/releases/download/v1.5.5.0/duckdb_odbc-osx-universal.zip
```
3. 
    The archive contains the `libduckdb_odbc.dylib` artifact. To extract it to a directory, run:```
mkdir duckdb_odbc && unzip duckdb_odbc-osx-universal.zip -d duckdb_odbc
```
4. 
    There are two ways to configure the ODBC driver, either by initializing via the configuration files, or by connecting with [`SQLDriverConnect`](https://learn.microsoft.com/en-us/sql/odbc/reference/syntax/sqldriverconnect-function?view=sql-server-ver16) .
A combination of the two is also possible.Furthermore, the ODBC driver supports all the [configuration options](/docs/current/configuration/overview.html) included in DuckDB.If a configuration is set in both the connection string passed to `SQLDriverConnect` and in the`odbc.ini` file,
the one passed to`SQLDriverConnect` will take precedence.For the details of the configuration parameters, see the [ODBC configuration page](/docs/current/clients/odbc/configuration.html) .
5. 
    After the configuration, to validate the installation, it is possible to use an ODBC client. unixODBC uses a command line tool called `isql` .Use the DSN defined in `odbc.ini` as a parameter of`isql` .```
isql DuckDB
```
```
+---------------------------------------+
| Connected!                            |
|                                       |
| sql-statement                         |
| help [tablename]                      |
| echo [string]                         |
| quit                                  |
|                                       |
+---------------------------------------+
```
```
SQL> SELECT 42;
```
```
+------------+
| 42         |
+------------+
| 42         |
+------------+
SQLRowCount returns -1
1 rows fetched
```

# Citations

1. Source page: https://duckdb.org/docs/current/clients/odbc/macos
