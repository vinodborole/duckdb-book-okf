---
type: Web Page
title: Parquet Tips – DuckDB
description: 'Below is a collection of tips to help when dealing with Parquet files.
  Tips for Reading Parquet Files Use union_by_name When Loading Files with Different
  Schemas The union_by_name option can be used to unify the schema of files that have
  different or missing columns. For files that do not have certain columns, NULL values
  are filled in: SELECT * FROM read_parquet(''flights*.parquet'', union_by_name =
  true); Tips for Writing Parquet Files Using a glob pattern upon read or a Hive partitioning
  structure are good ways to transparently handle multiple files. Enabling PER_THREAD_OUTPUT
  If the final number of Parquet files is not important,…'
resource: https://duckdb.org/docs/current/data/parquet/tips
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

Below is a collection of tips to help when dealing with Parquet files.

## 
        
        [Tips for Reading Parquet Files](#tips-for-reading-parquet-files)
        
      

    
      ### 
        
        [Use `union_by_name` When Loading Files with Different Schemas](#use-union_by_name-when-loading-files-with-different-schemas)
        
      

    
`union_by_name` When Loading Files with Different Schemas
The `union_by_name` option can be used to unify the schema of files that have different or missing columns. For files that do not have certain columns, `NULL` values are filled in:

```
SELECT *
FROM read_parquet('flights*.parquet', union_by_name = true);
```
## 
        
        [Tips for Writing Parquet Files](#tips-for-writing-parquet-files)
        
      

    
Using a [glob pattern](/docs/current/data/multiple_files/overview.html#glob-syntax) upon read or a [Hive partitioning](/docs/current/data/partitioning/hive_partitioning.html) structure are good ways to transparently handle multiple files.

### 
        
        [Enabling `PER_THREAD_OUTPUT`](#enabling-per_thread_output)
        
      

    
`PER_THREAD_OUTPUT`
If the final number of Parquet files is not important, writing one file per thread can significantly improve performance:

```
COPY
    (FROM generate_series(10_000_000))
    TO 'test.parquet'
    (FORMAT parquet, PER_THREAD_OUTPUT);
```
### 
        
        [Selecting a `ROW_GROUP_SIZE`](#selecting-a-row_group_size)
        
      

    
`ROW_GROUP_SIZE`
The `ROW_GROUP_SIZE` parameter specifies the minimum number of rows in a Parquet row group, with a minimum value equal to DuckDB's vector size, 2,048, and a default of 122,880.
A Parquet row group is a partition of rows, consisting of a column chunk for each column in the dataset.

Compression algorithms are only applied per row group, so the larger the row group size, the more opportunities to compress the data.
On the other hand, larger row group sizes mean that each thread keeps more data in memory before flushing when streaming results.
Another argument for smaller row group sizes is that DuckDB can read Parquet row groups in parallel even within the same file and uses predicate pushdown to only scan the row groups whose metadata ranges match the `WHERE` clause of the query. However, there is some overhead associated with reading the metadata in each group.

A good rule of thumb is to ensure that the number of row groups per file is at least as large as the number of CPU threads used to query that file. More row groups beyond the thread count would improve the speed of highly selective queries, but slow down queries that must scan the whole file like aggregations.

To write a query to a Parquet file with a different row group size, run:

```
COPY
    (FROM generate_series(100_000))
    TO 'row-groups.parquet'
    (FORMAT parquet, ROW_GROUP_SIZE 100_000);
```
### 
        
        [The `ROW_GROUPS_PER_FILE` Option](#the-row_groups_per_file-option)
        
      

    
`ROW_GROUPS_PER_FILE` Option
The `ROW_GROUPS_PER_FILE` parameter creates a new Parquet file if the current one has a specified number of row groups.

```
COPY
    (FROM generate_series(100_000))
    TO 'output-directory'
    (FORMAT parquet, ROW_GROUP_SIZE 20_000, ROW_GROUPS_PER_FILE 2);
```
  If multiple threads are active, the number of row groups in a file may slightly exceed the specified number of row groups to limit the amount of locking – similarly to the behavior of [`FILE_SIZE_BYTES`](../../sql/statements/copy#copy--to-options).
However, if `PER_THREAD_OUTPUT` is set, only one thread writes to each file, and it becomes accurate again.

### 
        
        [Sorting Rows to Improve Row Group Pruning](#sorting-rows-to-improve-row-group-pruning)
        
      

    
DuckDB writes per-column statistics, including min/max values, for every row group, and as described above the reader uses these to skip row groups that cannot match a query’s `WHERE` clause.
Sorting the data on the columns that you filter on most often before writing makes these min/max ranges tight and non-overlapping between row groups, so that highly selective queries on those columns scan far fewer row groups:

```
COPY
    (FROM 'events.parquet' ORDER BY event_time)
    TO 'events-sorted.parquet'
    (FORMAT parquet);
```
This pairs well with a `ROW_GROUP_SIZE` that keeps each row group focused on a narrow range of the sort key.

See the [Performance Guide on “File Formats”](/docs/current/guides/performance/file_formats.html#parquet-file-sizes) for more tips.

# Citations

1. Source page: https://duckdb.org/docs/current/data/parquet/tips
