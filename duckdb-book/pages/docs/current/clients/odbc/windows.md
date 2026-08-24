---
type: Web Page
title: ODBC API on Windows – DuckDB
description: 'Setup Using the DuckDB ODBC API on Windows requires the following steps:
  Microsoft Windows requires an ODBC Driver Manager to manage communication between
  applications and the ODBC drivers. The Driver Manager on Windows is provided in
  a DLL file odbccp32.dll, and other files and tools. For detailed information check
  out the Common ODBC Component Files. DuckDB releases the ODBC driver as an asset.
  For Windows, download it from the [Windows ODBC asset (x86_64/AMD64)](https://github.com/duckdb/duckdb-odbc/releases/download/v{%
  if site.current_duckdb_odbc_version != "" %}{{ site.current_duckdb_odbc_version
  }}{% else %}{{ site.lts_duckdb_odbc_version }}{% endif %}/duckdb_odbc-windows-amd64.zip).
  The archive contains the following artifacts: duckdb_odbc.dll: the DuckDB driver
  compiled for Windows. duckdb_odbc_setup.dll:…'
resource: https://duckdb.org/docs/current/clients/odbc/windows
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
        
        [Setup](#setup)
        
      

    
Using the DuckDB ODBC API on Windows requires the following steps:

1. 
    Microsoft Windows requires an ODBC Driver Manager to manage communication between applications and the ODBC drivers. The Driver Manager on Windows is provided in a DLL file `odbccp32.dll` , and other files and tools.
For detailed information check out the[Common ODBC Component Files](<https://docs.microsoft.com/en-us/previous-versions/windows/desktop/odbc/dn170563(v=vs.85)>) .
2. 
    
    DuckDB releases the ODBC driver as an asset. For Windows, download it from the [Windows ODBC asset (x86_64/AMD64)](https://github.com/duckdb/duckdb-odbc/releases/download/v1.5.5.0/duckdb_odbc-windows-amd64.zip) .
3. 
    The archive contains the following artifacts: 
  - `duckdb_odbc.dll` : the DuckDB driver compiled for Windows.
  - `duckdb_odbc_setup.dll` : a setup DLL used by the Windows ODBC Data Source Administrator tool.
  - `odbc_install.exe` : an installation script to aid the configuration on Windows.
 Decompress the archive to a directory (e.g., `duckdb_odbc` ).
4. 
    The `odbc_install.exe` binary performs the configuration of the DuckDB ODBC Driver on Windows. It depends on the`Odbccp32.dll` that provides functions to configure the ODBC registry entries.Inside the permanent directory (e.g., `duckdb_odbc` ), double-click on the`odbc_install.exe` .Windows administrator privileges are required. In case of a non-administrator, a User Account Control prompt will occur.
5. `odbc_install.exe` adds a default DSN configuration into the ODBC registries with a default database`:memory:` .

### 
        
        [DSN Windows Setup](#dsn-windows-setup)
        
      

    
After the installation, it is possible to change the default DSN configuration or add a new one using the Windows ODBC Data Source Administrator tool `odbcad32.exe`.

It also can be launched through the Windows start:

### 
        
        [Default DuckDB DSN](#default-duckdb-dsn)
        
      

    
The newly installed DSN is visible on the ***System DSN*** in the Windows ODBC Data Source Administrator tool:

### 
        
        [Changing DuckDB DSN](#changing-duckdb-dsn)
        
      

    
When selecting the default DSN (i.e., `DuckDB`) or adding a new configuration, the following setup window will display:

This window allows you to set the DSN and the database file path associated with that DSN.

## 
        
        [More Detailed Windows Setup](#more-detailed-windows-setup)
        
      

    
There are two ways to configure the ODBC driver, either by altering the registry keys as detailed below,
or by connecting with [`SQLDriverConnect`](https://learn.microsoft.com/en-us/sql/odbc/reference/syntax/sqldriverconnect-function?view=sql-server-ver16).
A combination of the two is also possible.

Furthermore, the ODBC driver supports all the [configuration options](/docs/current/configuration/overview.html)
included in DuckDB.

  If a configuration is set in both the connection string passed to `SQLDriverConnect` and in the `odbc.ini` file,
the one passed to `SQLDriverConnect` will take precedence.

For the details of the configuration parameters, see the [ODBC configuration page](/docs/current/clients/odbc/configuration.html).

### 
        
        [Registry Keys](#registry-keys)
        
      

    
The ODBC setup on Windows is based on registry keys (see [Registry Entries for ODBC Components](https://docs.microsoft.com/en-us/sql/odbc/reference/install/registry-entries-for-odbc-components?view=sql-server-ver15)).
The ODBC entries can be placed at the current user registry key (`HKCU`) or the system registry key (`HKLM`).

We have tested and used the system entries based on `HKLM->SOFTWARE->ODBC`.
The `odbc_install.exe` changes this entry that has two subkeys: `ODBC.INI` and `ODBCINST.INI`.

The `ODBC.INI` is where users usually insert DSN registry entries for the drivers.

For example, the DSN registry for DuckDB would look like this:

The `ODBCINST.INI` contains one entry for each ODBC driver and other keys predefined for [Windows ODBC configuration](https://docs.microsoft.com/en-us/sql/odbc/reference/install/registry-entries-for-odbc-components?view=sql-server-ver15).

### 
        
        [Updating the ODBC Driver](#updating-the-odbc-driver)
        
      

    
When a new version of the ODBC driver is released, installing the new version will overwrite the existing one.
However, the installer doesn't always update the version number in the registry.
To ensure the correct version is used,
check that `HKEY_LOCAL_MACHINE\SOFTWARE\ODBC\ODBCINST.INI\DuckDB Driver` has the most recent version,
and `HKEY_LOCAL_MACHINE\SOFTWARE\ODBC\ODBC.INI\DuckDB\Driver` has the correct path to the new driver.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/odbc/windows
