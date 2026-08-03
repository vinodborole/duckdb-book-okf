---
type: Web Page
title: Lakehouse Formats – DuckDB
description: Lakehouse formats, often referred to as open table formats, are specifications
  for storing data in object storage while maintaining some guarantees such as ACID
  transactions or keeping snapshot history. Over time, multiple lakehouse formats
  have emerged, each one with its own unique approach to managing its metadata (a.k.a.
  catalog). In this page, we will go over the support that DuckDB offers for some
  of these formats as well as some workarounds that you can use to still use DuckDB
  and get close to full interoperability with these formats. DuckDB Lakehouse Support
  Matrix DuckDB supports Iceberg, Delta, Lance and DuckLake as…
resource: https://duckdb.org/docs/current/lakehouse_formats
timestamp: '2026-08-03T09:53:51.508916+00:00'
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
				 [Sitemap](/docs/sitemap)
- 
				 [Live Demo](https://shell.duckdb.org)

Lakehouse formats, often referred to as open table formats, are specifications for storing data in object storage while maintaining some guarantees such as ACID transactions or keeping snapshot history. Over time, multiple lakehouse formats have emerged, each one with its own unique approach to managing its metadata (a.k.a. catalog). In this page, we will go over the support that DuckDB offers for some of these formats as well as some workarounds that you can use to still use DuckDB and get close to full interoperability with these formats.

## 
        
        [DuckDB Lakehouse Support Matrix](#duckdb-lakehouse-support-matrix)
        
      

    
DuckDB supports Iceberg, Delta, Lance and DuckLake as first-class citizens. The following matrix represents what DuckDB natively supports out of the box through core extensions.

|  | DuckLake | Iceberg | Delta | Lance | 
|---|---|---|---|---|
| Extension | [`ducklake`](https://ducklake.select/docs/stable/duckdb/introduction) | [`iceberg`](/docs/current/core_extensions/iceberg/overview.html) | [`delta`](/docs/current/core_extensions/delta.html) | [`lance`](/docs/current/core_extensions/lance.html) | 
| Read |  |  |  |  | 
| Write |  |  |  |  | 
| Deletes |  |  |  |  | 
| Updates |  |  |  |  | 
| Upserting |  |  |  |  | 
| Create table |  |  |  |  | 
| Create table with partitions |  |  |  |  | 
| Attaching to a catalog |  |  | * |  | 
| Rename table |  |  |  |  | 
| Rename columns |  |  |  |  | 
| Add/drop columns |  |  |  |  | 
| Alter column type |  |  |  |  | 
| Compaction and maintenance |  |  |  |  | 
| Encryption |  |  |  |  | 
| Manage table properties |  |  |  |  | 
| Time travel |  |  |  |  | 
| Query table changes |  |  |  |  | 

* Through the [`unity_catalog`](https://github.com/duckdb/unity_catalog) extension.

DuckDB aims to build native extensions with minimal dependencies. The `iceberg` extension for example, has no dependencies on third-party Iceberg libraries, which means all data and metadata operations are implemented natively in the DuckDB extension. For the `delta` extension, we use the [`delta-kernel-rs` project](https://github.com/delta-io/delta-kernel-rs), which is meant to be a lightweight platform for engines to build delta integrations that are as close to native as possible.

  **Why do native implementations matter?** Native implementations allow DuckDB to do more performance optimizations such as complex filter pushdowns (with file-level and row-group level pruning) and improve memory management.

# Citations

1. Source page: https://duckdb.org/docs/current/lakehouse_formats
