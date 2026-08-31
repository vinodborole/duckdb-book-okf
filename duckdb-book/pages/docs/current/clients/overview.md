---
type: Web Page
title: Client Overview – DuckDB
description: DuckDB is an in-process database system and offers client APIs (“drivers”)
  for several languages. Client API Maintainer Support tier Latest version C Core
  team {% include tooltip.html label="Primary" id="support_tier_primary" %} {% if
  site.current_duckdb_version != "" %}{{ site.current_duckdb_version }}{% else %}{{
  site.lts_duckdb_version }}{% endif %} CLI (command line interface) Core team {%
  include tooltip.html label="Primary" id="support_tier_primary" %} {% if site.current_duckdb_version
  != "" %}{{ site.current_duckdb_version }}{% else %}{{ site.lts_duckdb_version }}{%
  endif %} Java (JDBC) Core team {% include tooltip.html label="Primary" id="support_tier_primary"
  %} {% if site.current_duckdb_java_short_version != "" %}{{ site.current_duckdb_java_short_version
  }}{% else %}{{ site.lts_duckdb_java_short_version }}{% endif %} Go Core team {%
  include tooltip.html…
resource: https://duckdb.org/docs/current/clients/overview
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

DuckDB is an in-process database system and offers client APIs (“drivers”) for several languages.

| Client API | Maintainer | Support tier | Latest version | 
|---|---|---|---|
| [C](/docs/current/clients/c/overview.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=c) | 
| [CLI (command line interface)](/docs/current/clients/cli/overview.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=cli) | 
| [Java (JDBC)](/docs/current/clients/java/overview.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=java) | 
| [Go](/docs/current/clients/go.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=go) | 
| [Node.js (node-neo)](/docs/current/clients/node_neo/overview.html) | [Jeff Raymakers](https://github.com/jraymakers) | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=nodejs) | 
| [ODBC](/docs/current/clients/odbc/overview.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=odbc) | 
| [Python](/docs/current/clients/python/overview.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=python) | 
| [R](/docs/current/clients/r.html) | [Kirill Müller](https://github.com/krlmlr) | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=r) | 
| [Rust](/docs/current/clients/rust/overview.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](/install/?version=current&environment=rust) | 
| [WebAssembly (Wasm)](/docs/current/clients/wasm/overview.html) | Core team | PrimaryPrimary clients are the first to receive new features and are covered by community support. | [1.5.5](https://github.com/duckdb/duckdb-wasm#readme) | 
| [ADBC (Arrow)](/docs/current/clients/adbc.html) | Core team | SecondarySecondary clients receive new features but are not covered by community support. | [1.5.5](/docs/current/clients/adbc.html) | 
| [C# (.NET)](https://duckdb.net/) | [Giorgi](https://github.com/Giorgi) | SecondarySecondary clients receive new features but are not covered by community support. | [1.5.5](https://www.nuget.org/packages?q=Tags%3A%22DuckDB%22+Author%3A%22Giorgi%22&includeComputedFrameworks=true&prerel=true&sortby=relevance) | 
| [C++](/docs/current/clients/cpp.html) | Core team | SecondarySecondary clients receive new features but are not covered by community support. | [1.5.5](/install/?version=current&environment=c) | 

The table above lists the DuckDB clients with the primary and secondary [support tiers](#support-tiers).
For a list of tertiary clients, see the [“Tertiary Clients” page](/docs/current/clients/tertiary_clients/overview.html).

## 
        
        [Support Tiers](#support-tiers)
        
      

    
There are three tiers of support for clients.
Primary clients are the first to receive new features and are covered by [community support](https://ducklabs.com/community_support_policy).
Secondary clients receive new features but are not covered by community support.
Finally, there are no feature or support guarantees for tertiary clients.

  The DuckDB clients listed above are open-source and we welcome community contributions to these libraries. All primary and secondary clients are available under the MIT license. For tertiary clients, please consult the repository for the license.

## 
        
        [Compatibility](#compatibility)
        
      

    
All DuckDB clients support the same DuckDB SQL syntax and use the same on-disk [database format](/docs/current/internals/storage.html).
[DuckDB extensions](/docs/current/extensions/overview.html) are also portable between clients with some exceptions (see [Wasm extensions](/docs/current/clients/wasm/extensions.html#available-extensions)).

# Citations

1. Source page: https://duckdb.org/docs/current/clients/overview
