---
type: Web Page
title: Java (JDBC) Client – DuckDB
description: Installation To use the DuckDB Java (JDBC) client, visit the Java installation
  page. The latest stable version of the DuckDB Java (JDBC) client is {% if site.current_duckdb_java_short_version
  != "" %}{{ site.current_duckdb_java_short_version }}{% else %}{{ site.lts_duckdb_java_short_version
  }}{% endif %}. The DuckDB Java (JDBC) client lets Java applications query DuckDB
  through the standard JDBC API, extended with DuckDB-specific features for bulk loading,
  Apache Arrow interchange, user-defined functions, and profiling. The driver also
  supports ahead-of-time compilation with GraalVM Native Image. This page covers installation;
  the other pages in this section cover connecting and each feature in detail. Installation
  The DuckDB Java JDBC API…
resource: https://duckdb.org/docs/current/clients/java/overview
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

  Installation To use the DuckDB Java (JDBC) client, visit the [Java installation page](/install/?environment=java).

The latest stable version of the DuckDB Java (JDBC) client is 1.5.5.

The DuckDB Java (JDBC) client lets Java applications query DuckDB through the standard JDBC API, extended with DuckDB-specific features for bulk loading, [Apache Arrow](https://arrow.apache.org/) interchange, user-defined functions, and profiling. The driver also supports ahead-of-time compilation with [GraalVM Native Image](/docs/current/clients/java/deploy_native_image.html).

This page covers installation; the other pages in this section cover connecting and each feature in detail.

## 
        
        [Installation](#installation)
        
      

    
The DuckDB Java JDBC API can be installed from [Maven Central](https://search.maven.org/artifact/org.duckdb/duckdb_jdbc). Please see the [installation page](/install/?environment=java) for details.

  Tip To try features before they reach a stable release, preview (nightly) builds of the JDBC driver are published as `SNAPSHOT` versions to DuckDB's snapshot repository at `https://duckdb-staging.duckdb.org/duckdb/duckdb-java/maven`. This is an object storage repository with no browseable web page; it is consumed directly by Maven. Add the repository to your build and depend on a `duckdb_jdbc` `SNAPSHOT` version. See the [preview builds page](/install/preview.html) for a full Maven example.

## 
        
        [Basic API Usage](#basic-api-usage)
        
      

    
DuckDB's JDBC API implements the main parts of the standard Java Database Connectivity (JDBC) API, version 4.1. Describing JDBC is beyond the scope of this page, see the [official documentation](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html) for details. Below we focus on the DuckDB-specific parts.

Refer to the externally hosted [API Reference](https://javadoc.io/doc/org.duckdb/duckdb_jdbc) for more information about our extensions to the JDBC specification, or the [Arrow Methods](/docs/current/clients/java/result_handling.html#arrow-methods).

### 
        
        [Opening a Connection](#opening-a-connection)
        
      

    
In JDBC, database connections are created through the standard `java.sql.DriverManager` class, using the `jdbc:duckdb:` JDBC URL prefix:

```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;
Connection conn = DriverManager.getConnection("jdbc:duckdb:");
```
Used on its own, `jdbc:duckdb:` opens an in-memory database. Appending a file name, for example `jdbc:duckdb:/tmp/my_database`, opens a persistent database instead.

To confirm that the driver is on the classpath and a connection can be opened, run a trivial query:

```
try (Statement stmt = conn.createStatement();
     ResultSet rs = stmt.executeQuery("SELECT 42")) {
    rs.next();
    System.out.println(rs.getInt(1)); // prints 42
}
```
[Define Connections](/docs/current/clients/java/connecting.html) covers the connection lifecycle in full: the URL forms the driver accepts, DuckDB and driver configuration options, read-only mode, instance caching, threading, and shutdown.

## 
        
        [Further Reading](#further-reading)
        
      

    
- [Define Connections](/docs/current/clients/java/connecting.html) — the JDBC URL forms, configuration options, instance caching, threading, and connection shutdown.
- [Run Queries](/docs/current/clients/java/querying.html) — sending queries with`Statement` and`PreparedStatement` , and reading DuckDB's nested types.
- [Import Data](/docs/current/clients/java/data_import.html) — bulk-loading data with the Appender and the JDBC batch writer.
- [Handle Results](/docs/current/clients/java/result_handling.html) — Apache Arrow interchange, result streaming, and chunked results.
- [Deploy as Native Image](/docs/current/clients/java/deploy_native_image.html) — building standalone executables with GraalVM Native Image.
- [Clients Overview](/docs/current/clients/overview.html) — the other client APIs DuckDB provides alongside JDBC.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/java/overview
