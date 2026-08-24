---
type: Web Page
title: Hive Partitioning – DuckDB
description: 'Examples Read data from a Hive partitioned dataset: SELECT * FROM read_parquet(''orders/*/*/*.parquet'',
  hive_partitioning = true); Write a table to a Hive partitioned dataset: COPY orders
  TO ''orders'' (FORMAT parquet, PARTITION_BY (year, month)); Note that the PARTITION_BY
  options cannot use expressions. You can produce columns on the fly using the following
  syntax: COPY (SELECT *, year(timestamp) AS year, month(timestamp) AS month FROM
  services) TO ''test'' (PARTITION_BY (year, month)); When reading, the partition
  columns are read from the directory structure and can be included or excluded depending
  on the hive_partitioning parameter. FROM read_parquet(''test/*/*/*.parquet'', hive_partitioning
  = false); -- will not include year, month…'
resource: https://duckdb.org/docs/current/data/partitioning/hive_partitioning
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
        
      

    
Read data from a Hive partitioned dataset:

```
SELECT *
FROM read_parquet('orders/*/*/*.parquet', hive_partitioning = true);
```
Write a table to a Hive partitioned dataset:

```
COPY orders
TO 'orders' (FORMAT parquet, PARTITION_BY (year, month));
```
Note that the `PARTITION_BY` options cannot use expressions. You can produce columns on the fly using the following syntax:

```
COPY (SELECT *, year(timestamp) AS year, month(timestamp) AS month FROM services)
TO 'test' (PARTITION_BY (year, month));
```
When reading, the partition columns are read from the directory structure and
can be included or excluded depending on the `hive_partitioning` parameter.

```
FROM read_parquet('test/*/*/*.parquet', hive_partitioning = false); -- will not include year, month columns
FROM read_parquet('test/*/*/*.parquet', hive_partitioning = true);  -- will include year, month partition columns
```
## 
        
        [Hive Partitioning](#hive-partitioning)
        
      

    
Hive partitioning is a [partitioning strategy](<https://en.wikipedia.org/wiki/Partition_(database)>) that is used to split a table into multiple files based on **partition keys**. The files are organized into folders. Within each folder, the **partition key** has a value that is determined by the name of the folder.

Below is an example of a Hive partitioned file hierarchy. The files are partitioned on two keys (`year` and `month`).

```
orders
├── year=2021
│    ├── month=1
│    │   ├── file1.parquet
│    │   └── file2.parquet
│    └── month=2
│        └── file3.parquet
└── year=2022
     ├── month=11
     │   ├── file4.parquet
     │   └── file5.parquet
     └── month=12
         └── file6.parquet
```
Files stored in this hierarchy can be read using the `hive_partitioning` flag.

```
SELECT *
FROM read_parquet('orders/*/*/*.parquet', hive_partitioning = true);
```
When we specify the `hive_partitioning` flag, the values of the columns will be read from the directories.

### 
        
        [Filter Pushdown](#filter-pushdown)
        
      

    
Filters on the partition keys are automatically pushed down into the files. This way the system skips reading files that are not necessary to answer a query. For example, consider the following query on the above dataset:

```
SELECT *
FROM read_parquet('orders/*/*/*.parquet', hive_partitioning = true)
WHERE year = 2022
  AND month = 11;
```
When executing this query, only the following files will be read:

```
orders
└── year=2022
     └── month=11
         ├── file4.parquet
         └── file5.parquet
```
### 
        
        [Auto-detection](#auto-detection)
        
      

    
By default the system tries to infer if the provided files are in a hive partitioned hierarchy. And if so, the `hive_partitioning` flag is enabled automatically. The auto-detection will look at the names of the folders and search for a `'key' = 'value'` pattern. This behavior can be overridden by using the `hive_partitioning` configuration option:

```
SET hive_partitioning = false;
```
### 
        
        [Hive Types](#hive-types)
        
      

    
`hive_types` is a way to specify the logical types of the hive partitions in a struct:

```
SELECT *
FROM read_parquet(
    'dir/**/*.parquet',
    hive_partitioning = true,
    hive_types = {'release': DATE, 'orders': BIGINT}
);
```
`hive_types` will be auto-detected for the following types: `DATE`, `TIMESTAMP` and `BIGINT`. To switch off the auto-detection, the flag `hive_types_autocast = 0` can be set.

### 
        
        [Writing Partitioned Files](#writing-partitioned-files)
        
      

    
See the [Partitioned Writes](/docs/current/data/partitioning/partitioned_writes.html) section.

# Citations

1. Source page: https://duckdb.org/docs/current/data/partitioning/hive_partitioning
