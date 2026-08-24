---
type: Web Page
title: ODBC API on Linux – DuckDB
description: 'Driver Manager A driver manager is required to manage communication
  between applications and the ODBC driver. We tested and support unixODBC that is
  a complete ODBC driver manager for Linux. Users can install it from the command
  line: On Debian-based distributions (Ubuntu, Mint, etc.), run: sudo apt-get install
  unixodbc odbcinst On Fedora-based distributions (Amazon Linux, RHEL, CentOS, etc.),
  run: sudo yum install unixODBC Setting Up the Driver Download the ODBC Linux Asset
  corresponding to your architecture: [x86_64 (AMD64)](https://github.com/duckdb/duckdb-odbc/releases/download/v{%
  if site.current_duckdb_odbc_version != "" %}{{ site.current_duckdb_odbc_version
  }}{% else %}{{ site.lts_duckdb_odbc_version }}{% endif %}/duckdb_odbc-linux-amd64.zip)
  [arm64 (AArch64)](https://github.com/duckdb/duckdb-odbc/releases/download/v{% if
  site.current_duckdb_odbc_version != "" %}{{ site.current_duckdb_odbc_version }}{%…'
resource: https://duckdb.org/docs/current/clients/odbc/linux
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
        
        [Driver Manager](#driver-manager)
        
      

    
A driver manager is required to manage communication between applications and the ODBC driver.
We tested and support `unixODBC` that is a complete ODBC driver manager for Linux.
Users can install it from the command line:

On Debian-based distributions (Ubuntu, Mint, etc.), run:

```
sudo apt-get install unixodbc odbcinst
```
On Fedora-based distributions (Amazon Linux, RHEL, CentOS, etc.), run:

```
sudo yum install unixODBC
```
## 
        
        [Setting Up the Driver](#setting-up-the-driver)
        
      

    
1. 
    Download the ODBC Linux Asset corresponding to your architecture:
2. 
    The package contains the following files: 
  - `libduckdb_odbc.so` : the DuckDB driver.
  - `unixodbc_setup.sh` : a setup script to aid the configuration on Linux.
 To extract them, run: ```
mkdir duckdb_odbc && unzip duckdb_odbc-linux-amd64.zip -d duckdb_odbc
```
3. 
    The `unixodbc_setup.sh` script performs the configuration of the DuckDB ODBC Driver. It is based on the unixODBC package that provides some commands to handle the ODBC setup and test like`odbcinst` and`isql` .Run the following commands with either option `-u` or`-s` to configure DuckDB ODBC.The `-u` option based on the user home directory to setup the ODBC init files.```
./unixodbc_setup.sh -u
```
The `-s` option changes the system level files that will be visible for all users, because of that it requires root privileges.```
sudo ./unixodbc_setup.sh -s
```
The option `--help` shows the usage of`unixodbc_setup.sh` prints the help.```
./unixodbc_setup.sh --help
```
```
Usage: ./unixodbc_setup.sh <level> [options]
Example: ./unixodbc_setup.sh -u -db ~/database_path -D ~/driver_path/libduckdb_odbc.so
Level:
-s: System-level, using 'sudo' to configure DuckDB ODBC at the system-level, changing the files: /etc/odbc[inst].ini
-u: User-level, configuring the DuckDB ODBC at the user-level, changing the files: ~/.odbc[inst].ini.
Options:
-db database_path>: the DuckDB database file path, the default is ':memory:' if not provided.
-D driver_path: the driver file path (i.e., the path for libduckdb_odbc.so), the default is using the base script directory
```
4. 
    The ODBC setup on Linux is based on the `.odbc.ini` and`.odbcinst.ini` files.These files can be placed to the user home directory `/home/username` or in the system`/etc` directory.
The Driver Manager prioritizes the user configuration files over the system files.For the details of the configuration parameters, see the [ODBC configuration page](/docs/current/clients/odbc/configuration.html) .

# Citations

1. Source page: https://duckdb.org/docs/current/clients/odbc/linux
