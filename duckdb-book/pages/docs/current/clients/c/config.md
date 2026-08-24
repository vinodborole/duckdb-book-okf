---
type: Web Page
title: Configuration – DuckDB
description: Configuration options can be provided to change different settings of
  the database system. Note that many of these settings can be changed later on using
  PRAGMA statements as well. The configuration object should be created, filled with
  values and passed to duckdb_open_ext. Example duckdb_database db; duckdb_config
  config; // create the configuration object if (duckdb_create_config(&config) ==
  DuckDBError) { // handle error } // set some configuration options duckdb_set_config(config,
  "access_mode", "READ_WRITE"); // or READ_ONLY duckdb_set_config(config, "threads",
  "8"); duckdb_set_config(config, "max_memory", "8GB"); duckdb_set_config(config,
  "default_order", "DESC"); // open the database using the configuration if (duckdb_open_ext(NULL,
  &db, config, NULL) == DuckDBError) { // handle error }…
resource: https://duckdb.org/docs/current/clients/c/config
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

Configuration options can be provided to change different settings of the database system. Note that many of these
settings can be changed later on using [`PRAGMA` statements](../../configuration/pragmas) as well. The configuration object
should be created, filled with values and passed to `duckdb_open_ext`.

## 
        
        [Example](#example)
        
      

    
```
duckdb_database db;
duckdb_config config;
// create the configuration object
if (duckdb_create_config(&config) == DuckDBError) {
    // handle error
}
// set some configuration options
duckdb_set_config(config, "access_mode", "READ_WRITE"); // or READ_ONLY
duckdb_set_config(config, "threads", "8");
duckdb_set_config(config, "max_memory", "8GB");
duckdb_set_config(config, "default_order", "DESC");
// open the database using the configuration
if (duckdb_open_ext(NULL, &db, config, NULL) == DuckDBError) {
    // handle error
}
// cleanup the configuration object
duckdb_destroy_config(&config);
// run queries...
// cleanup
duckdb_close(&db);
```
## 
        
        [API Reference Overview](#api-reference-overview)
        
      

    
`duckdb_state` [duckdb_create_config](#duckdb_create_config)(duckdb_config *out_config);
size_t [duckdb_config_count](#duckdb_config_count)();
duckdb_state [duckdb_get_config_flag](#duckdb_get_config_flag)(size_t index, const char **out_name, const char **out_description);
duckdb_state [duckdb_set_config](#duckdb_set_config)(duckdb_config config, const char *name, const char *option);
void [duckdb_destroy_config](#duckdb_destroy_config)(duckdb_config *config);
#### 
        
        [`duckdb_create_config`](#duckdb_create_config)
        
      

    
`duckdb_create_config`
Initializes an empty configuration object that can be used to provide start-up options for the DuckDB instance
through `duckdb_open_ext`.
The duckdb_config must be destroyed using 'duckdb_destroy_config'

This will always succeed unless there is a malloc failure.

Note that `duckdb_destroy_config` should always be called on the resulting config, even if the function returns
`DuckDBError`.

##### 
        
        [Syntax](#syntax)
        
      

    
```
duckdb_state duckdb_create_config(
  duckdb_config *out_config
);
```
##### 
        
        [Parameters](#parameters)
        
      

    
- `out_config` : The result configuration object.

##### 
        
        [Return Value](#return-value)
        
      

    
`DuckDBSuccess` on success or `DuckDBError` on failure.

#### 
        
        [`duckdb_config_count`](#duckdb_config_count)
        
      

    
`duckdb_config_count`
This returns the total amount of configuration options available for usage with `duckdb_get_config_flag`.

This should not be called in a loop as it internally loops over all the options.

##### 
        
        [Return Value](#return-value-1)
        
      

    
The amount of config options available.

##### 
        
        [Syntax](#syntax-1)
        
      

    
```
size_t duckdb_config_count(
  
);
```
#### 
        
        [`duckdb_get_config_flag`](#duckdb_get_config_flag)
        
      

    
`duckdb_get_config_flag`
Obtains a human-readable name and description of a specific configuration option. This can be used to e.g.
display configuration options. This will succeed unless `index` is out of range (i.e., `>= duckdb_config_count`).

The result name or description MUST NOT be freed.

##### 
        
        [Syntax](#syntax-2)
        
      

    
```
duckdb_state duckdb_get_config_flag(
  size_t index,
  const char **out_name,
  const char **out_description
);
```
##### 
        
        [Parameters](#parameters-1)
        
      

    
- `index` : The index of the configuration option (between 0 and`duckdb_config_count` )
- `out_name` : A name of the configuration flag.
- `out_description` : A description of the configuration flag.

##### 
        
        [Return Value](#return-value-2)
        
      

    
`DuckDBSuccess` on success or `DuckDBError` on failure.

#### 
        
        [`duckdb_set_config`](#duckdb_set_config)
        
      

    
`duckdb_set_config`
Sets the specified option for the specified configuration. The configuration option is indicated by name.
To obtain a list of config options, see `duckdb_get_config_flag`.

In the source code, configuration options are defined in `config.cpp`.

This can fail if either the name is invalid, or if the value provided for the option is invalid.

##### 
        
        [Syntax](#syntax-3)
        
      

    
```
duckdb_state duckdb_set_config(
  duckdb_config config,
  const char *name,
  const char *option
);
```
##### 
        
        [Parameters](#parameters-2)
        
      

    
- `config` : The configuration object to set the option on.
- `name` : The name of the configuration flag to set.
- `option` : The value to set the configuration flag to.

##### 
        
        [Return Value](#return-value-3)
        
      

    
`DuckDBSuccess` on success or `DuckDBError` on failure.

#### 
        
        [`duckdb_destroy_config`](#duckdb_destroy_config)
        
      

    
`duckdb_destroy_config`
Destroys the specified configuration object and de-allocates all memory allocated for the object.

##### 
        
        [Syntax](#syntax-4)
        
      

    
```
void duckdb_destroy_config(
  duckdb_config *config
);
```
##### 
        
        [Parameters](#parameters-3)
        
      

    
- `config` : The configuration object to destroy.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/config
