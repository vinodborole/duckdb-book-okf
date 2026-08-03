---
type: Web Page
title: Friendly CLI – DuckDB
description: 'Along with our Friendly SQL, we provide friendly CLI features. Dark/Light
  Mode The CLI automatically detects whether the terminal is using a dark or light
  background and adjusts syntax highlighting colors accordingly. The mode can also
  be set manually using the .highlight_mode command: .highlight_mode dark .highlight_mode
  light To use a mix of colors suitable for both dark and light backgrounds: .highlight_mode
  mixed 8-Bit Colors Since DuckDB v1.5, the CLI supports 8-bit colors corresponding
  to Xterm system colors: .display_colors darkred1 red darkred2 red3 red4 red1 brightred
  indianred1 ... Dynamic Prompt The default prompts are the following: -- macOS /
  Linux {max_length:40}{color:38,5,208}{color:bold}{setting:current_database_and_schema}{color:reset}…'
resource: https://duckdb.org/docs/current/clients/cli/friendly_cli
timestamp: '2026-08-03T09:53:51.508916+00:00'
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
				 [Sitemap](/docs/sitemap)
- 
				 [Live Demo](https://shell.duckdb.org)

Friendly CLI

					
Along with our [Friendly SQL](/docs/current/sql/dialect/friendly_sql.html), we provide
**friendly CLI** features.

## 
        
        [Dark/Light Mode](#darklight-mode)
        
      

    
The CLI automatically detects whether the terminal is using a dark or light background and adjusts syntax highlighting colors accordingly. The mode can also be set manually using the `.highlight_mode` command:

```
.highlight_mode dark
```
```
.highlight_mode light
```
To use a mix of colors suitable for both dark and light backgrounds:

```
.highlight_mode mixed
```
## 
        
        [8-Bit Colors](#8-bit-colors)
        
      

    
Since DuckDB v1.5, the CLI supports 8-bit colors corresponding to [Xterm system colors](https://www.ditig.com/256-colors-cheat-sheet#xterm-system-colors):

```
.display_colors
```
```
darkred1 red darkred2 red3 red4 red1 brightred indianred1 ...
```
## 
        
        [Dynamic Prompt](#dynamic-prompt)
        
      

    
The default prompts are the following:

```
-- macOS / Linux
{max_length:40}{color:38,5,208}{color:bold}{setting:current_database_and_schema}{color:reset} D 
-- Windows
{max_length:40}{color:green}{color:bold}{setting:current_database_and_schema}{color:reset} D 
```
## 
        
        [Return the Result of the Last Query Using `_`](#return-the-result-of-the-last-query-using-_)
        
      

    
`_`
You can use the `_` (underscore) table to query the result of the last query:

```
SELECT 42 AS x;
```
```
┌───────┐
│   x   │
│ int32 │
├───────┤
│    42 │
└───────┘
```
```
FROM _;
```
```
┌───────┐
│   x   │
│ int32 │
├───────┤
│    42 │
└───────┘
```
If the last query did not return a result (e.g., because it performed an update operation), the CLI throws an error:

```
Binder Error:
Failed to query last result "_": no result available
```
© 2026 DuckDB Foundation, Amsterdam NL

# Citations

1. Source page: https://duckdb.org/docs/current/clients/cli/friendly_cli
