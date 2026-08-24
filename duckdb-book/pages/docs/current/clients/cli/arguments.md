---
type: Web Page
title: Command Line Arguments – DuckDB
description: 'The table below summarizes DuckDB''s command line options. To list all
  command line options, use the command: duckdb -help For a list of dot commands available
  in the CLI shell, see the Dot Commands page. Argument Description   -append Append
  the database to the end of the file   -ascii Set output mode to ascii   -bail Stop
  after hitting an error   -batch Force batch I/O   -box Set output mode to box  
  -column Set output mode to column   -cmd COMMAND Run COMMAND before reading stdin
    -c COMMAND Run COMMAND and exit   -csv Set output…'
resource: https://duckdb.org/docs/current/clients/cli/arguments
timestamp: '2026-08-24T07:05:55.104476+00:00'
---

Search Shortcut cmd + k | ctrl + k
		

	
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

Command Line Arguments

					
The table below summarizes DuckDB's command line options. To list all command line options, use the command:

```
duckdb -help
```
For a list of dot commands available in the CLI shell, see the [Dot Commands page](/docs/current/clients/cli/dot_commands.html).

| Argument | Description |  | 
|---|---|---|
| `-append` | Append the database to the end of the file |  | 
| `-ascii` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`ascii` |  | 
| `-bail` | Stop after hitting an error |  | 
| `-batch` | Force batch I/O |  | 
| `-box` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`box` |  | 
| `-column` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`column` |  | 
| `-cmd COMMAND` | Run `COMMAND` before reading`stdin` |  | 
| `-c COMMAND` | Run `COMMAND` and exit |  | 
| `-csv` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`csv` |  | 
| `-echo` | Print commands before execution |  | 
| `-f FILENAME` | Run the script in `FILENAME` and exit. Note that the`~/.duckdbrc` is read and executed first (if it exists) |  | 
| `-init FILENAME` | Run the script in `FILENAME` upon startup (instead of`~/.duckdbrc` ) |  | 
| `-header` | Turn headers on |  | 
| `-help` | Show this message |  | 
| `-html` | Set [output mode](/docs/current/clients/cli/output_formats.html) to HTML |  | 
| `-interactive` | Force interactive I/O |  | 
| `-json` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`json` |  | 
| `-line` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`line` |  | 
| `-list` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`list` |  | 
| `-markdown` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`markdown` |  | 
| `-newline SEP` | Set output row separator. Default: `\n` |  | 
| `-nofollow` | Refuse to open symbolic links to database files |  | 
| `-noheader` | Turn headers off |  | 
| `-no-stdin` | Exit after processing options instead of reading stdin |  | 
| `-nullvalue TEXT` | Set text string for `NULL` values. Default:`NULL` |  | 
| `-quote` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`quote` |  | 
| `-readonly` | Open the database read-only. This option also supports attaching to remote databases via HTTPS |  | 
| `-s COMMAND` | Run `COMMAND` and exit |  | 
| `-separator SEP` | Set output column separator to `SEP` . Default: ` | ` | 
| `-storage-version VER` | Database [storage compatibility version](/docs/current/internals/storage.html#storag-version_table) to use. To use the latest storage version, pass`-storage-version latest` |  | 
| `-table` | Set [output mode](/docs/current/clients/cli/output_formats.html) to`table` |  | 
| `-ui` | Loads and starts the [DuckDB UI](/docs/current/core_extensions/ui.html) . If the UI is not yet installed, it installs the`ui` extension |  | 
| `-unsigned` | Allow loading of [unsigned extensions](/docs/current/extensions/overview.html#unsigned-extensions) . This option is intended to be used for developing extensions. Consult the[Securing DuckDB page](/docs/current/operations_manual/securing_duckdb/securing_extensions.html) for guidelines on how to set up DuckDB in a secure manner |  | 
| `-version` | Show DuckDB version |  | 

## 
        
        [Passing a Sequence of Arguments](#passing-a-sequence-of-arguments)
        
      

    
Note that the CLI arguments are processed in order, similarly to the behavior of the SQLite CLI. For example:

```
duckdb -csv -c 'SELECT 42 AS hello' -json -c 'SELECT 84 AS world'
```
Returns the following:

```
hello
42
[{"world":84}]
```
© 2026 DuckDB Foundation, Amsterdam NL

# Citations

1. Source page: https://duckdb.org/docs/current/clients/cli/arguments
