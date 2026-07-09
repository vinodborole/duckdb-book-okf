---
type: Web Page
title: Connect – DuckDB
description: Connect or Create a Database To use DuckDB, you must first create a connection
  to a database. The exact syntax varies between the client APIs but it typically
  involves passing an argument to configure persistence. Persistence DuckDB can operate
  in both persistent mode, where the data is saved to disk, and in in-memory mode,
  where the entire dataset is stored in the main memory. Tip Both persistent and in-memory
  databases use spilling to disk to facilitate larger-than-memory workloads (i.e.,
  out-of-core-processing). Persistent Database To create or open a persistent database,
  set the path of the database file, e.g., my_database.duckdb, when creating…
resource: https://duckdb.org/docs/lts/connect/overview
timestamp: '2026-07-09T12:17:10.843759+00:00'
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
- 
									 [Overview](/docs/lts/data/json/overview)
- 
									 [Creating JSON](/docs/lts/data/json/creating_json)
- 
									 [Loading JSON](/docs/lts/data/json/loading_json)
- 
									 [Writing JSON](/docs/lts/data/json/writing_json)
- 
									 [JSON Type](/docs/lts/data/json/json_type)
- 
									 [JSON Functions](/docs/lts/data/json/json_functions)
- 
									 [Format Settings](/docs/lts/data/json/format_settings)
- 
									 [Installing and Loading](/docs/lts/data/json/installing_and_loading)
- 
									 [SQL to / from JSON](/docs/lts/data/json/sql_to_and_from_json)
- 
									 [Caveats](/docs/lts/data/json/caveats)
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
									 [Overview](/docs/lts/clients/c/overview)
- 
									 [Startup](/docs/lts/clients/c/connect)
- 
									 [Configuration](/docs/lts/clients/c/config)
- 
									 [Query](/docs/lts/clients/c/query)
- 
									 [Data Chunks](/docs/lts/clients/c/data_chunk)
- 
									 [Vectors](/docs/lts/clients/c/vector)
- 
									 [Values](/docs/lts/clients/c/value)
- 
									 [Types](/docs/lts/clients/c/types)
- 
									 [Prepared Statements](/docs/lts/clients/c/prepared)
- 
									 [Appender](/docs/lts/clients/c/appender)
- 
									 [Table Functions](/docs/lts/clients/c/table_functions)
- 
									 [Replacement Scans](/docs/lts/clients/c/replacement_scans)
- 
									 [API Reference](/docs/lts/clients/c/api)
- 
								 [C++](/docs/lts/clients/cpp)
- CLI
- 
									 [Overview](/docs/lts/clients/cli/overview)
- 
									 [Arguments](/docs/lts/clients/cli/arguments)
- 
									 [Dot Commands](/docs/lts/clients/cli/dot_commands)
- 
									 [Output Formats](/docs/lts/clients/cli/output_formats)
- 
									 [Editing](/docs/lts/clients/cli/editing)
- 
									 [Safe Mode](/docs/lts/clients/cli/safe_mode)
- 
									 [Autocomplete](/docs/lts/clients/cli/autocomplete)
- 
									 [Syntax Highlighting](/docs/lts/clients/cli/syntax_highlighting)
- 
									 [Known Issues](/docs/lts/clients/cli/known_issues)
- 
								 [Dart](/docs/lts/clients/dart)
- 
								 [Go](/docs/lts/clients/go)
- 
								 [Java (JDBC)](/docs/lts/clients/java)
- 
								 [Julia](/docs/lts/clients/julia)
- Node.js (Deprecated)
- Node.js (Neo)
- ODBC
- 
								 [PHP](/docs/lts/clients/php)
- Python
- 
									 [Overview](/docs/lts/clients/python/overview)
- 
									 [Data Ingestion](/docs/lts/clients/python/data_ingestion)
- 
									 [Conversion between DuckDB and Python](/docs/lts/clients/python/conversion)
- 
									 [DB API](/docs/lts/clients/python/dbapi)
- 
									 [Relational API](/docs/lts/clients/python/relational_api)
- 
									 [Function API](/docs/lts/clients/python/function)
- 
									 [Types API](/docs/lts/clients/python/types)
- 
									 [Expression API](/docs/lts/clients/python/expression)
- 
									 [Spark API](/docs/lts/clients/python/spark_api)
- 
									 [API Reference](/docs/lts/clients/python/reference)
- 
									 [Known Python Issues](/docs/lts/clients/python/known_issues)
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
- 
									 [Overview](/docs/lts/sql/statements/overview)
- 
									 [ANALYZE](/docs/lts/sql/statements/analyze)
- 
									 [ALTER TABLE](/docs/lts/sql/statements/alter_table)
- 
									 [ALTER VIEW](/docs/lts/sql/statements/alter_view)
- 
									 [ATTACH and DETACH](/docs/lts/sql/statements/attach)
- 
									 [CALL](/docs/lts/sql/statements/call)
- 
									 [CHECKPOINT](/docs/lts/sql/statements/checkpoint)
- 
									 [COMMENT ON](/docs/lts/sql/statements/comment_on)
- 
									 [COPY](/docs/lts/sql/statements/copy)
- 
									 [CREATE INDEX](/docs/lts/sql/statements/create_index)
- 
									 [CREATE MACRO](/docs/lts/sql/statements/create_macro)
- 
									 [CREATE SCHEMA](/docs/lts/sql/statements/create_schema)
- 
									 [CREATE SECRET](/docs/lts/sql/statements/create_secret)
- 
									 [CREATE SEQUENCE](/docs/lts/sql/statements/create_sequence)
- 
									 [CREATE TABLE](/docs/lts/sql/statements/create_table)
- 
									 [CREATE VIEW](/docs/lts/sql/statements/create_view)
- 
									 [CREATE TYPE](/docs/lts/sql/statements/create_type)
- 
									 [DELETE](/docs/lts/sql/statements/delete)
- 
									 [DESCRIBE](/docs/lts/sql/statements/describe)
- 
									 [DROP](/docs/lts/sql/statements/drop)
- 
									 [EXPORT and IMPORT DATABASE](/docs/lts/sql/statements/export)
- 
									 [INSERT](/docs/lts/sql/statements/insert)
- 
									 [LOAD / INSTALL](/docs/lts/sql/statements/load_and_install)
- 
									 [MERGE INTO](/docs/lts/sql/statements/merge_into)
- 
									 [PIVOT](/docs/lts/sql/statements/pivot)
- 
									 [Profiling](/docs/lts/sql/statements/profiling)
- 
									 [SELECT](/docs/lts/sql/statements/select)
- 
									 [SET / RESET](/docs/lts/sql/statements/set)
- 
									 [SET VARIABLE](/docs/lts/sql/statements/set_variable)
- 
									 [SHOW and SHOW DATABASES](/docs/lts/sql/statements/show)
- 
									 [SUMMARIZE](/docs/lts/sql/statements/summarize)
- 
									 [Transaction Management](/docs/lts/sql/statements/transactions)
- 
									 [UNPIVOT](/docs/lts/sql/statements/unpivot)
- 
									 [UPDATE](/docs/lts/sql/statements/update)
- 
									 [USE](/docs/lts/sql/statements/use)
- 
									 [VACUUM](/docs/lts/sql/statements/vacuum)
- Query Syntax
- 
									 [SELECT](/docs/lts/sql/query_syntax/select)
- 
									 [FROM and JOIN](/docs/lts/sql/query_syntax/from)
- 
									 [WHERE](/docs/lts/sql/query_syntax/where)
- 
									 [GROUP BY](/docs/lts/sql/query_syntax/groupby)
- 
									 [GROUPING SETS](/docs/lts/sql/query_syntax/grouping_sets)
- 
									 [HAVING](/docs/lts/sql/query_syntax/having)
- 
									 [ORDER BY](/docs/lts/sql/query_syntax/orderby)
- 
									 [LIMIT and OFFSET](/docs/lts/sql/query_syntax/limit)
- 
									 [SAMPLE](/docs/lts/sql/query_syntax/sample)
- 
									 [Unnesting](/docs/lts/sql/query_syntax/unnest)
- 
									 [WITH](/docs/lts/sql/query_syntax/with)
- 
									 [WINDOW](/docs/lts/sql/query_syntax/window)
- 
									 [QUALIFY](/docs/lts/sql/query_syntax/qualify)
- 
									 [VALUES](/docs/lts/sql/query_syntax/values)
- 
									 [FILTER](/docs/lts/sql/query_syntax/filter)
- 
									 [Set Operations](/docs/lts/sql/query_syntax/setops)
- 
									 [Prepared Statements](/docs/lts/sql/query_syntax/prepared_statements)
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
- 
									 [Overview](/docs/lts/sql/expressions/overview)
- 
									 [CASE Expression](/docs/lts/sql/expressions/case)
- 
									 [Casting](/docs/lts/sql/expressions/cast)
- 
									 [Collations](/docs/lts/sql/expressions/collations)
- 
									 [Comparisons](/docs/lts/sql/expressions/comparison_operators)
- 
									 [IN Operator](/docs/lts/sql/expressions/in)
- 
									 [Logical Operators](/docs/lts/sql/expressions/logical_operators)
- 
									 [Star Expression](/docs/lts/sql/expressions/star)
- 
									 [Subqueries](/docs/lts/sql/expressions/subqueries)
- 
									 [TRY](/docs/lts/sql/expressions/try)
- Functions
- 
									 [Overview](/docs/lts/sql/functions/overview)
- 
									 [Aggregate Functions](/docs/lts/sql/functions/aggregates)
- 
									 [Array Functions](/docs/lts/sql/functions/array)
- 
									 [Bitstring Functions](/docs/lts/sql/functions/bitstring)
- 
									 [Blob Functions](/docs/lts/sql/functions/blob)
- 
									 [Date Format Functions](/docs/lts/sql/functions/dateformat)
- 
									 [Date Functions](/docs/lts/sql/functions/date)
- 
									 [Date Part Functions](/docs/lts/sql/functions/datepart)
- 
									 [Enum Functions](/docs/lts/sql/functions/enum)
- 
									 [Interval Functions](/docs/lts/sql/functions/interval)
- 
									 [Lambda Functions](/docs/lts/sql/functions/lambda)
- 
									 [List Functions](/docs/lts/sql/functions/list)
- 
									 [Map Functions](/docs/lts/sql/functions/map)
- 
									 [Nested Functions](/docs/lts/sql/functions/nested)
- 
									 [Numeric Functions](/docs/lts/sql/functions/numeric)
- 
									 [Pattern Matching](/docs/lts/sql/functions/pattern_matching)
- 
									 [Regular Expressions](/docs/lts/sql/functions/regular_expressions)
- 
									 [Struct Functions](/docs/lts/sql/functions/struct)
- 
									 [Text Functions](/docs/lts/sql/functions/text)
- 
									 [Time Functions](/docs/lts/sql/functions/time)
- 
									 [Timestamp Functions](/docs/lts/sql/functions/timestamp)
- 
									 [Timestamp with Time Zone Functions](/docs/lts/sql/functions/timestamptz)
- 
									 [Union Functions](/docs/lts/sql/functions/union)
- 
									 [Utility Functions](/docs/lts/sql/functions/utility)
- 
									 [Window Functions](/docs/lts/sql/functions/window_functions)
- 
								 [Constraints](/docs/lts/sql/constraints)
- 
								 [Indexes](/docs/lts/sql/indexes)
- Meta Queries
- DuckDB's SQL Dialect
- 
									 [Overview](/docs/lts/sql/dialect/overview)
- 
									 [Indexing](/docs/lts/sql/dialect/indexing)
- 
									 [Friendly SQL](/docs/lts/sql/dialect/friendly_sql)
- 
									 [Keywords and Identifiers](/docs/lts/sql/dialect/keywords_and_identifiers)
- 
									 [Order Preservation](/docs/lts/sql/dialect/order_preservation)
- 
									 [PostgreSQL Compatibility](/docs/lts/sql/dialect/postgresql_compatibility)
- 
									 [SQL Quirks](/docs/lts/sql/dialect/sql_quirks)
- 
								 [Samples](/docs/lts/sql/samples)
- Configuration
- Extensions
- 
								 [Overview](/docs/lts/extensions/overview)
- 
								 [Installing Extensions](/docs/lts/extensions/installing_extensions)
- 
								 [Advanced Installation Methods](/docs/lts/extensions/advanced_installation_methods)
- 
								 [Distributing Extensions](/docs/lts/extensions/extension_distribution)
- 
								 [Versioning of Extensions](/docs/lts/extensions/versioning_of_extensions)
- 
								 [Troubleshooting of Extensions](/docs/lts/extensions/troubleshooting)
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
									 [Overview](/docs/lts/core_extensions/iceberg/overview)
- 
									 [Iceberg REST Catalogs](/docs/lts/core_extensions/iceberg/iceberg_rest_catalogs)
- 
									 [Amazon S3 Tables](/docs/lts/core_extensions/iceberg/amazon_s3_tables)
- 
									 [Amazon SageMaker Lakehouse (AWS Glue)](/docs/lts/core_extensions/iceberg/amazon_sagemaker_lakehouse)
- 
									 [Troubleshooting](/docs/lts/core_extensions/iceberg/troubleshooting)
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
- 
									 [Overview](/docs/lts/guides/file_formats/overview)
- 
									 [CSV Import](/docs/lts/guides/file_formats/csv_import)
- 
									 [CSV Export](/docs/lts/guides/file_formats/csv_export)
- 
									 [Directly Reading Files](/docs/lts/guides/file_formats/read_file)
- 
									 [Excel Import](/docs/lts/guides/file_formats/excel_import)
- 
									 [Excel Export](/docs/lts/guides/file_formats/excel_export)
- 
									 [JSON Import](/docs/lts/guides/file_formats/json_import)
- 
									 [JSON Export](/docs/lts/guides/file_formats/json_export)
- 
									 [Parquet Import](/docs/lts/guides/file_formats/parquet_import)
- 
									 [Parquet Export](/docs/lts/guides/file_formats/parquet_export)
- 
									 [Querying Parquet Files](/docs/lts/guides/file_formats/query_parquet)
- 
									 [File Access with the file: Protocol](/docs/lts/guides/file_formats/file_access)
- Network and Cloud Storage
- 
									 [Overview](/docs/lts/guides/network_cloud_storage/overview)
- 
									 [HTTP Parquet Import](/docs/lts/guides/network_cloud_storage/http_import)
- 
									 [S3 Parquet Import](/docs/lts/guides/network_cloud_storage/s3_import)
- 
									 [S3 Parquet Export](/docs/lts/guides/network_cloud_storage/s3_export)
- 
									 [S3 Iceberg Import](/docs/lts/guides/network_cloud_storage/s3_iceberg_import)
- 
									 [S3 Express One](/docs/lts/guides/network_cloud_storage/s3_express_one)
- 
									 [GCS Import](/docs/lts/guides/network_cloud_storage/gcs_import)
- 
									 [Cloudflare R2 Import](/docs/lts/guides/network_cloud_storage/cloudflare_r2_import)
- 
									 [DuckDB over HTTPS / S3](/docs/lts/guides/network_cloud_storage/duckdb_over_https_or_s3)
- 
									 [Fastly Object Storage Import](/docs/lts/guides/network_cloud_storage/fastly_object_storage_import)
- 
									 [Tigris Import](/docs/lts/guides/network_cloud_storage/tigris_import)
- Meta Queries
- 
									 [Describe Table](/docs/lts/guides/meta/describe)
- 
									 [EXPLAIN: Inspect Query Plans](/docs/lts/guides/meta/explain)
- 
									 [EXPLAIN ANALYZE: Profile Queries](/docs/lts/guides/meta/explain_analyze)
- 
									 [List Tables](/docs/lts/guides/meta/list_tables)
- 
									 [Summarize](/docs/lts/guides/meta/summarize)
- 
									 [DuckDB Environment](/docs/lts/guides/meta/duckdb_environment)
- ODBC
- Performance
- 
									 [Overview](/docs/lts/guides/performance/overview)
- 
									 [Environment](/docs/lts/guides/performance/environment)
- 
									 [Import](/docs/lts/guides/performance/import)
- 
									 [Schema](/docs/lts/guides/performance/schema)
- 
									 [Indexing](/docs/lts/guides/performance/indexing)
- 
									 [Join Operations](/docs/lts/guides/performance/join_operations)
- 
									 [File Formats](/docs/lts/guides/performance/file_formats)
- 
									 [How to Tune Workloads](/docs/lts/guides/performance/how_to_tune_workloads)
- 
									 [My Workload Is Slow](/docs/lts/guides/performance/my_workload_is_slow)
- 
									 [Benchmarks](/docs/lts/guides/performance/benchmarks)
- 
									 [Working with Huge Databases](/docs/lts/guides/performance/working_with_huge_databases)
- Python
- 
									 [Installation](/docs/lts/guides/python/install)
- 
									 [Executing SQL](/docs/lts/guides/python/execute_sql)
- 
									 [Jupyter Notebooks](/docs/lts/guides/python/jupyter)
- 
									 [marimo Notebooks](/docs/lts/guides/python/marimo)
- 
									 [SQL on Pandas](/docs/lts/guides/python/sql_on_pandas)
- 
									 [Import from Pandas](/docs/lts/guides/python/import_pandas)
- 
									 [Export to Pandas](/docs/lts/guides/python/export_pandas)
- 
									 [Import from Numpy](/docs/lts/guides/python/import_numpy)
- 
									 [Export to Numpy](/docs/lts/guides/python/export_numpy)
- 
									 [SQL on Arrow](/docs/lts/guides/python/sql_on_arrow)
- 
									 [Import from Arrow](/docs/lts/guides/python/import_arrow)
- 
									 [Export to Arrow](/docs/lts/guides/python/export_arrow)
- 
									 [Relational API on Pandas](/docs/lts/guides/python/relational_api_pandas)
- 
									 [Multiple Python Threads](/docs/lts/guides/python/multiple_threads)
- 
									 [Integration with Ibis](/docs/lts/guides/python/ibis)
- 
									 [Integration with Polars](/docs/lts/guides/python/polars)
- 
									 [Using fsspec Filesystems](/docs/lts/guides/python/filesystems)
- SQL Editors
- SQL Features
- 
									 [AsOf Join](/docs/lts/guides/sql_features/asof_join)
- 
									 [Full-Text Search](/docs/lts/guides/sql_features/full_text_search)
- 
									 [Graph Queries](/docs/lts/guides/sql_features/graph_queries)
- 
									 [query and query_table Functions](/docs/lts/guides/sql_features/query_and_query_table_functions)
- 
									 [Merge Statement for SCD Type 2](/docs/lts/guides/sql_features/merge)
- 
									 [Timestamp Issues](/docs/lts/guides/sql_features/timestamps)
- Snippets
- 
									 [Creating Synthetic Data](/docs/lts/guides/snippets/create_synthetic_data)
- 
									 [Dutch Railway Datasets](/docs/lts/guides/snippets/dutch_railway_datasets)
- 
									 [Sharing Macros](/docs/lts/guides/snippets/sharing_macros)
- 
									 [Analyzing a Git Repository](/docs/lts/guides/snippets/analyze_git_repository)
- 
									 [Importing Duckbox Tables](/docs/lts/guides/snippets/importing_duckbox_tables)
- 
									 [Copying an In-Memory Database to a File](/docs/lts/guides/snippets/copy_in-memory_database_to_file)
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
									 [Overview](/docs/lts/dev/building/overview)
- 
									 [Build Configuration](/docs/lts/dev/building/build_configuration)
- 
									 [Building Extensions](/docs/lts/dev/building/building_extensions)
- 
									 [Android](/docs/lts/dev/building/android)
- 
									 [Linux](/docs/lts/dev/building/linux)
- 
									 [macOS](/docs/lts/dev/building/macos)
- 
									 [Raspberry Pi](/docs/lts/dev/building/raspberry_pi)
- 
									 [Windows](/docs/lts/dev/building/windows)
- 
									 [Python](/docs/lts/dev/building/python)
- 
									 [R](/docs/lts/dev/building/r)
- 
									 [Troubleshooting](/docs/lts/dev/building/troubleshooting)
- 
									 [Unofficial and Unsupported Platforms](/docs/lts/dev/building/unofficial_and_unsupported_platforms)
- 
								 [Benchmark Suite](/docs/lts/dev/benchmark)
- Testing
- Internals
- 
				 [Sitemap](/docs/sitemap)
- 
				 [Live Demo](https://shell.duckdb.org)

## 
        
        [Connect or Create a Database](#connect-or-create-a-database)
        
      

    
To use DuckDB, you must first create a connection to a database. The exact syntax varies between the [client APIs](/docs/lts/clients/overview.html) but it typically involves passing an argument to configure persistence.

## 
        
        [Persistence](#persistence)
        
      

    
DuckDB can operate in both persistent mode, where the data is saved to disk, and in in-memory mode, where the entire dataset is stored in the main memory.

Tip Both persistent and in-memory databases use spilling to disk to facilitate larger-than-memory workloads (i.e., out-of-core-processing).

### 
        
        [Persistent Database](#persistent-database)
        
      

    
To create or open a persistent database, set the path of the database file, e.g., `my_database.duckdb`, when creating the connection.
This path can point to an existing database or to a file that does not yet exist and DuckDB will open or create a database at that location as needed.
The file may have an arbitrary extension, but `.db` or `.duckdb` are two common choices with `.ddb` also used sometimes.

Starting with v0.10, DuckDB's storage format is [backwards-compatible](/docs/lts/internals/storage.html#backward-compatibility), i.e., DuckDB is able to read database files produced by an older version of DuckDB.
For example, DuckDB v0.10 can read and operate on files created by the previous DuckDB version, v0.9.
For more details on DuckDB's storage format, see the [storage page](/docs/lts/internals/storage.html).

### 
        
        [In-Memory Database](#in-memory-database)
        
      

    
DuckDB can operate in in-memory mode. In most clients, this can be activated by passing the special value `:memory:` as the database file or omitting the database file argument. In in-memory mode, no data is persisted to disk, therefore, all data is lost when the process finishes.

# Citations

1. Source page: https://duckdb.org/docs/lts/connect/overview
