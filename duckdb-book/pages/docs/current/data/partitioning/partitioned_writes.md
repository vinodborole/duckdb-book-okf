---
type: Web Page
title: Partitioned Writes – DuckDB
description: 'Examples Write a table to a Hive partitioned dataset of Parquet files:
  COPY orders TO ''orders'' (FORMAT parquet, PARTITION_BY (year, month)); Write a
  table to a Hive partitioned dataset of CSV files, allowing overwrites: COPY orders
  TO ''orders'' (FORMAT csv, PARTITION_BY (year, month), OVERWRITE_OR_IGNORE); Write
  a table to a Hive partitioned dataset of GZIP-compressed CSV files, setting explicit
  data files'' extension: COPY orders TO ''orders'' (FORMAT csv, PARTITION_BY (year,
  month), COMPRESSION gzip, FILE_EXTENSION ''csv.gz''); Partitioned Writes When the
  PARTITION_BY clause is specified for the COPY statement, the files are written in
  a Hive partitioned folder hierarchy. The target is the…'
resource: https://duckdb.org/docs/current/data/partitioning/partitioned_writes
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

## 
        
        [Examples](#examples)
        
      

    
Write a table to a Hive partitioned dataset of Parquet files:

```
COPY orders TO 'orders'
(FORMAT parquet, PARTITION_BY (year, month));
```
Write a table to a Hive partitioned dataset of CSV files, allowing overwrites:

```
COPY orders TO 'orders'
(FORMAT csv, PARTITION_BY (year, month), OVERWRITE_OR_IGNORE);
```
Write a table to a Hive partitioned dataset of GZIP-compressed CSV files, setting explicit data files' extension:

```
COPY orders TO 'orders'
(FORMAT csv, PARTITION_BY (year, month), COMPRESSION gzip, FILE_EXTENSION 'csv.gz');
```
## 
        
        [Partitioned Writes](#partitioned-writes)
        
      

    
When the `PARTITION_BY` clause is specified for the [`COPY` statement](/docs/current/sql/statements/copy.html), the files are written in a [Hive partitioned](/docs/current/data/partitioning/hive_partitioning.html) folder hierarchy. The target is the name of the root directory (in the example above: `orders`). The files are written in-order in the file hierarchy. Currently, one file is written per thread to each directory.

```
orders
├── year=2021
│    ├── month=1
│    │   ├── data_1.parquet
│    │   └── data_2.parquet
│    └── month=2
│        └── data_1.parquet
└── year=2022
     ├── month=11
     │   ├── data_1.parquet
     │   └── data_2.parquet
     └── month=12
         └── data_1.parquet
```
The values of the partitions are automatically extracted from the data. Note that it can be very expensive to write a larger number of partitions as many files will be created. The ideal partition count depends on how large your dataset is.

To limit the maximum number of files the system can keep open before flushing to disk when writing using `PARTITION_BY`, use the `partitioned_write_max_open_files` configuration option (default: 100):

```
SET partitioned_write_max_open_files = 10;
```
  Bestpractice Writing data into many small partitions is expensive. It is generally recommended to have at least `100 MB` of data per partition.

### 
        
        [Filename Pattern](#filename-pattern)
        
      

    
By default, files will be named `data_0.parquet` or `data_0.csv`. With the flag `FILENAME_PATTERN` a pattern with `{i}` or `{uuid}` can be defined to create specific filenames:

- `{i}` will be replaced by an index.
- `{uuid}` will be replaced by a 128 bits long UUID.

Write a table to a Hive partitioned dataset of .parquet files, with an index in the filename:

```
COPY orders TO 'orders'
(FORMAT parquet, PARTITION_BY (year, month), OVERWRITE_OR_IGNORE, FILENAME_PATTERN 'orders_{i}');
```
Write a table to a Hive partitioned dataset of .parquet files, with unique filenames:

```
COPY orders TO 'orders'
(FORMAT parquet, PARTITION_BY (year, month), OVERWRITE_OR_IGNORE, FILENAME_PATTERN 'file_{uuid}');
```
### 
        
        [Overwriting](#overwriting)
        
      

    
By default the partitioned write will not allow overwriting existing directories.
On a local file system, the `OVERWRITE` and `OVERWRITE_OR_IGNORE` options remove the existing directories.
On remote file systems, overwriting is not supported.

### 
        
        [Appending](#appending)
        
      

    
To append to an existing Hive partitioned directory structure, use the `APPEND` option:

```
COPY orders TO 'orders'
(FORMAT parquet, PARTITION_BY (year, month), APPEND);
```
Using the `APPEND` option results in a behavior similar to the `OVERWRITE_OR_IGNORE, FILENAME_PATTERN '{uuid}'` options,
but DuckDB performs an extra check for whether the file already exists and then regenerates the UUID in the rare event that it does (to avoid clashes).

### 
        
        [Handling Slashes in Columns](#handling-slashes-in-columns)
        
      

    
To handle slashes in column names, use Percent-Encoding implemented by the [`url_encode` function](/docs/current/sql/functions/text.html#url_encodestring).

# Citations

1. Source page: https://duckdb.org/docs/current/data/partitioning/partitioned_writes
