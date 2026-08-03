---
type: Web Page
title: Known Issues – DuckDB
description: 'Incorrect Memory Values on Old Linux Distributions and WSL 2 On Windows
  Subsystem for Linux 2 (WSL2), when querying the max_memory or memory_limit from
  the duckdb_settings, the values may be inaccurate on certain Ubuntu versions (e.g.,
  20.04 and 24.04). The issue also occurs on older distributions such as Red Hat Enterprise
  Linux 8 (RHEL 8): Example: FROM duckdb_settings() WHERE name LIKE ''%mem%''; The
  output contains values larger than 1000 PiB: ┌──────────────┬────────────┬─────────────────────────────────────────────┬────────────┬─────────┐
  │ name │ value │ description │ input_type │ scope │ │ varchar │ varchar │ varchar
  │ varchar │ varchar │ ├──────────────┼────────────┼─────────────────────────────────────────────┼────────────┼─────────┤
  │ max_memory │ 1638.3 PiB │…'
resource: https://duckdb.org/docs/current/clients/cli/known_issues
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

Known Issues

					
## 
        
        [Incorrect Memory Values on Old Linux Distributions and WSL 2](#incorrect-memory-values-on-old-linux-distributions-and-wsl-2)
        
      

    
On Windows Subsystem for Linux 2 (WSL2), when querying the `max_memory` or `memory_limit` from the `duckdb_settings`, the values may be inaccurate on certain Ubuntu versions (e.g., 20.04 and 24.04). The issue also occurs on older distributions such as Red Hat Enterprise Linux 8 (RHEL 8):

Example:

```
FROM duckdb_settings() WHERE name LIKE '%mem%';
```
The output contains values larger than 1000 PiB:

```
┌──────────────┬────────────┬─────────────────────────────────────────────┬────────────┬─────────┐
│     name     │   value    │                 description                 │ input_type │  scope  │
│   varchar    │  varchar   │                   varchar                   │  varchar   │ varchar │
├──────────────┼────────────┼─────────────────────────────────────────────┼────────────┼─────────┤
│ max_memory   │ 1638.3 PiB │ The maximum memory of the system (e.g. 1GB) │ VARCHAR    │ GLOBAL  │
│ memory_limit │ 1638.3 PiB │ The maximum memory of the system (e.g. 1GB) │ VARCHAR    │ GLOBAL  │
└──────────────┴────────────┴─────────────────────────────────────────────┴────────────┴─────────┘
```
© 2026 DuckDB Foundation, Amsterdam NL

# Citations

1. Source page: https://duckdb.org/docs/current/clients/cli/known_issues
