---
type: Web Page
title: Deploy as Native Image – DuckDB
description: 'Overview The JDBC driver runs inside GraalVM Native Image executables.
  Graal Native Image compiles a Java application ahead of time into a standalone binary
  that starts in milliseconds and requires no JVM on the target machine, which suits
  command line tools, serverless functions, and small containers. Recent driver versions
  ship the JNI reachability metadata that native-image needs, and the build picks
  it up automatically from the class path. Two things remain for the application to
  configure: native access and the location of DuckDB''s shared library. Driver versions
  up to and including 1.5.5 do not ship this metadata. For those versions,…'
resource: https://duckdb.org/docs/current/clients/java/deploy_native_image
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
        
      

    
The JDBC driver runs inside [GraalVM Native Image](https://www.graalvm.org/latest/reference-manual/native-image/) executables. Graal Native Image compiles a Java application ahead of time into a standalone binary that starts in milliseconds and requires no JVM on the target machine, which suits command line tools, serverless functions, and small containers.

Recent driver versions ship the JNI reachability metadata that `native-image` needs, and the build picks it up automatically from the class path.

Two things remain for the application to configure: native access and the location of DuckDB's shared library.

  Driver versions up to and including 1.5.5 do not ship this metadata. For those versions, generate it by running the application once on the JVM with the [tracing agent](https://www.graalvm.org/latest/reference-manual/native-image/metadata/AutomaticMetadataCollection/):

```
java -agentlib:native-image-agent=config-output-dir=⟨config_dir⟩ -cp ⟨classpath⟩ ⟨MainClass⟩
```
Next, pass the directory to the build with `-H:ConfigurationFileDirectories=⟨config_dir⟩`.

## 
        
        [Requirements](#requirements)
        
      

    
GraalVM for JDK 22 or later is required. Older GraalVM releases initialize the driver's classes at image build time, which bakes a build machine path into the executable and fails at run time with `UnsatisfiedLinkError`.

Pass `--enable-native-access=ALL-UNNAMED` to `native-image`, or add it as a build argument in the [Native Build Tools](https://graalvm.github.io/native-build-tools/latest/index.html) Maven or Gradle plugin.

Load the driver explicitly before opening the first connection:

```
Class.forName("org.duckdb.DuckDBDriver");
```
Driver auto-registration through `ServiceLoader` is not always visible to Graal Native Image's closed world analysis, and the explicit load makes registration deterministic.

## 
        
        [Providing the Shared Library](#providing-the-shared-library)
        
      

    
DuckDB's engine is a native library bundled inside the driver JAR, one file per platform. Choose one of two ways to make it available to the executable.

### 
        
        [Option 1: Embed the Library in the Executable](#option-1-embed-the-library-in-the-executable)
        
      

    
Add a resource entry naming your platform's library, either in a configuration directory passed via `-H:ConfigurationFileDirectories` or under `META-INF/native-image` in your own project:

```
{ "resources": { "includes": [ { "pattern": "libduckdb_java\\.so_linux_amd64" } ] } }
```
The bundled library names are `libduckdb_java.so_linux_amd64`, `libduckdb_java.so_linux_arm64`, `libduckdb_java.so_osx_universal`, and `libduckdb_java.so_windows_amd64`.

Name the one for your target platform explicitly. A wildcard matching all of them adds roughly 260 MB to the executable.

This option produces a single self contained file, around 120 MB. The driver extracts the library to a temporary directory when the first connection opens, which adds up to a second of startup time and requires a writable temporary directory.

### 
        
        [Option 2: Ship the Library Next to the Executable](#option-2-ship-the-library-next-to-the-executable)
        
      

    
Build without any resource entry and place the shared library in the same directory as the executable. The file works under its bundled name, for example `libduckdb_java.so_linux_amd64`, or under the platform convention: `libduckdb_java.so` on Linux, `libduckdb_java.dylib` on macOS, `duckdb_java.dll` on Windows. The lookup is anchored to the executable rather than the working directory, so the program runs correctly from anywhere.

This option produces a small executable, under 20 MB for a simple application, with no extraction cost when connections open. The library can be extracted from the driver JAR, or taken from the `-nolib` distribution together with its separate library artifact.

## 
        
        [Building](#building)
        
      

    
A minimal build, with the driver JAR in the current directory:

```
javac -cp duckdb_jdbc-⟨version⟩.jar App.java
native-image --no-fallback --enable-native-access=ALL-UNNAMED \
    -cp duckdb_jdbc-⟨version⟩.jar:. -o app App
```
`--no-fallback` makes the build fail outright instead of producing an image that still requires a JVM. For Maven and Gradle projects, the [Native Build Tools](https://graalvm.github.io/native-build-tools/latest/index.html) plugins wrap the same build and run it during `mvn package` or `gradle nativeCompile`.

## 
        
        [Further Reading](#further-reading)
        
      

    
- [Troubleshoot](/docs/current/clients/java/troubleshoot.html) — the Native Image errors that indicate missing metadata or a missing shared library.
- [Define Connections](/docs/current/clients/java/connecting.html) — driver registration and connection configuration.
- [Java (JDBC) Client](/docs/current/clients/java/overview.html) — installing the driver from Maven Central.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/java/deploy_native_image
