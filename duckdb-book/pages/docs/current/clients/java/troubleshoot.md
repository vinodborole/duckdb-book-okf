---
type: Web Page
title: Troubleshoot – DuckDB
description: 'Overview This page collects common issues encountered when using the
  DuckDB JDBC driver, together with their workarounds. If you run into a problem that
  is not covered here, search the driver''s issue tracker on GitHub. Driver Class
  Not Found This error occurs when the DuckDB JDBC driver is not on the application''s
  classpath, typically because the build tool has not resolved the dependency. If
  the Java application is unable to find the DuckDB driver, it may throw the following
  error: Exception in thread "main" java.sql.SQLException: No suitable driver found
  for jdbc:duckdb: at java.sql/java.sql.DriverManager.getConnection(DriverManager.java:706)
  at java.sql/java.sql.DriverManager.getConnection(DriverManager.java:252) ... And
  when trying to…'
resource: https://duckdb.org/docs/current/clients/java/troubleshoot
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

## 
        
        [Overview](#overview)
        
      

    
This page collects common issues encountered when using the DuckDB JDBC driver, together with their workarounds. If you run into a problem that is not covered here, search the [driver's issue tracker](https://github.com/duckdb/duckdb-java/issues) on GitHub.

## 
        
        [Driver Class Not Found](#driver-class-not-found)
        
      

    
This error occurs when the DuckDB JDBC driver is not on the application's classpath, typically because the build tool has not resolved the dependency. If the Java application is unable to find the DuckDB driver, it may throw the following error:

```
Exception in thread "main" java.sql.SQLException: No suitable driver found for jdbc:duckdb:
    at java.sql/java.sql.DriverManager.getConnection(DriverManager.java:706)
    at java.sql/java.sql.DriverManager.getConnection(DriverManager.java:252)
    ...
```
And when trying to load the class manually, it may result in this error:

```
Exception in thread "main" java.lang.ClassNotFoundException: org.duckdb.DuckDBDriver
    at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
    at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
    at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:520)
    at java.base/java.lang.Class.forName0(Native Method)
    at java.base/java.lang.Class.forName(Class.java:375)
    ...
```
These errors stem from the DuckDB [Maven](https://maven.apache.org/)/[Gradle](https://gradle.org/) dependency not being detected. To ensure that it is detected, force refresh the Maven configuration in your IDE.

## 
        
        [Parquet String Column Returns a Blob](#parquet-string-column-returns-a-blob)
        
      

    
Parquet files written by some legacy writers do not set the `UTF8` flag on string columns, so DuckDB reads them as `BLOB`. `ResultSet.getObject()` then returns a `DuckDBBlobResult` and `ResultSet.getString()` returns the bytes rendered as an escaped string rather than the expected text. Enable the [`binary_as_string`](/docs/current/data/parquet/overview.html) setting to read these columns as `VARCHAR`:

```
try (Statement stmt = conn.createStatement()) {
    stmt.execute("SET binary_as_string = true;");
}
```
The same option can be passed to `read_parquet` directly, for example `read_parquet('file.parquet', binary_as_string = true)`.

This behavior is tracked in [duckdb-java issue #113](https://github.com/duckdb/duckdb-java/issues/113).

## 
        
        [Native Image: `NoSuchMethodError` When Opening a Connection](#native-image-nosuchmethoderror-when-opening-a-connection)
        
      

    
`NoSuchMethodError` When Opening a Connection
In a [GraalVM Native Image](/docs/current/clients/java/deploy_native_image.html) executable, opening the first connection may fail with:

```
Exception in thread "main" java.lang.ExceptionInInitializerError
    ...
Caused by: java.lang.NoSuchMethodError: ⟨class and method⟩
    at com.oracle.svm.core.jni.functions.JNIFunctions$Support.getMethodID(JNIFunctions.java)
    ...
```
The driver resolves its entire JNI surface eagerly when its native library initializes, so a single class, method, or field missing from the reachability metadata fails the whole initialization. This indicates that the metadata compiled into the image is missing or older than the driver: upgrade to a driver version that ships its own metadata, or regenerate the metadata with the tracing agent against the exact driver version in use.

The error is sometimes wrapped in a misleading message:

```
java.lang.UnsatisfiedLinkError: Unsupported JNI version 0xffffffff, required by ⟨path⟩/libduckdb_java.⟨suffix⟩
```
This is what the library's `JNI_OnLoad` reports when an internal lookup failed, and the cause is the same missing metadata, not a JNI version problem.

## 
        
        [Native Image: `UnsatisfiedLinkError: Can't load library`](#native-image-unsatisfiedlinkerror-cant-load-library)
        
      

    
`UnsatisfiedLinkError: Can't load library`
In a Native Image executable, the first connection may fail with:

```
java.lang.UnsatisfiedLinkError: Can't load library: duckdb_java | java.library.path = [.]
    ...
Caused by: java.io.FileNotFoundException: DuckDB JNI library not found, path: '⟨path⟩/libduckdb_java.⟨suffix⟩'
```
The shared library was neither embedded in the executable nor found next to it. Either add a resource entry for your platform's library or place the library file beside the executable. Both options are described on the [Deploy as Native Image](/docs/current/clients/java/deploy_native_image.html) page.

## 
        
        [Warning about a Restricted Method in `java.lang.System`](#warning-about-a-restricted-method-in-javalangsystem)
        
      

    
`java.lang.System`
On JDK 24 and later, loading the driver prints:

```
WARNING: A restricted method in java.lang.System has been called
WARNING: java.lang.System::load has been called by org.duckdb.DuckDBNative ...
WARNING: Use --enable-native-access=ALL-UNNAMED to avoid a warning for callers in this module
```
This is the JDK's [native access integrity check](https://openjdk.org/jeps/472) and is harmless. Silence it by running the JVM with `--enable-native-access=ALL-UNNAMED`, or the module name of the driver if you place it on the module path. Future JDK releases will turn this warning into an error, so adding the flag is recommended.

## 
        
        [Further Reading](#further-reading)
        
      

    
- [Deploy as Native Image](/docs/current/clients/java/deploy_native_image.html) — building standalone executables with GraalVM, including both ways to provide the shared library.
- [Java (JDBC) Client](/docs/current/clients/java/overview.html) — installing the driver from Maven Central, the fix for the driver-not-found errors above.
- [Define Connections](/docs/current/clients/java/connecting.html) — driver registration, configuration options, and instance behavior behind many connection-time errors.
- [Parquet Files](/docs/current/data/parquet/overview.html) — the`binary_as_string` setting and other options for reading Parquet string columns correctly.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/java/troubleshoot
