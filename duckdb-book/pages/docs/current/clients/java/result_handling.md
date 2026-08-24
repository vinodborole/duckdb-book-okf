---
type: Web Page
title: Handle Results – DuckDB
description: Overview Beyond the standard JDBC ResultSet, the DuckDB driver can hand
  results to Apache Arrow, stream large results instead of materializing them, and
  expose raw columnar data chunks. This page covers each of these result-handling
  options. Arrow Methods The DuckDB result set integrates with Apache Arrow through
  the Java Arrow bindings. A DuckDBResultSet can export its rows as an Arrow stream
  for consumption by Arrow-based tools, and an Arrow stream produced elsewhere can
  be registered on a connection and queried as a DuckDB table. Refer to the API Reference
  for the type signatures. Arrow Export The following example exports an…
resource: https://duckdb.org/docs/current/clients/java/result_handling
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
        
        [Overview](#overview)
        
      

    
Beyond the standard JDBC `ResultSet`, the DuckDB driver can hand results to [Apache Arrow](https://arrow.apache.org/), stream large results instead of materializing them, and expose raw columnar data chunks. This page covers each of these result-handling options.

## 
        
        [Arrow Methods](#arrow-methods)
        
      

    
The DuckDB result set integrates with [Apache Arrow](https://arrow.apache.org/) through the [Java Arrow bindings](https://arrow.apache.org/docs/java/). A `DuckDBResultSet` can export its rows as an Arrow stream for consumption by Arrow-based tools, and an Arrow stream produced elsewhere can be registered on a connection and queried as a DuckDB table. Refer to the [API Reference](<https://javadoc.io/doc/org.duckdb/duckdb_jdbc/latest/org/duckdb/DuckDBResultSet.html#arrowExportStream(java.lang.Object,long)>) for the type signatures.

### 
        
        [Arrow Export](#arrow-export)
        
      

    
The following example exports an Arrow stream from a query result and consumes it using the Java Arrow bindings. Each batch is loaded in turn, and its vectors are read from the `VectorSchemaRoot`.

```
import org.apache.arrow.memory.RootAllocator;
import org.apache.arrow.vector.ipc.ArrowReader;
import org.duckdb.DuckDBResultSet;
try (var conn = DriverManager.getConnection("jdbc:duckdb:");
    var stmt = conn.prepareStatement("SELECT * FROM generate_series(2000)");
    var resultset = (DuckDBResultSet) stmt.executeQuery();
    var allocator = new RootAllocator()) {
    try (var reader = (ArrowReader) resultset.arrowExportStream(allocator, 256)) {
        while (reader.loadNextBatch()) {
            System.out.println(reader.getVectorSchemaRoot().getVector("generate_series"));
        }
    }
}
```
### 
        
        [Arrow Import](#arrow-import)
        
      

    
The following example consumes an Arrow stream produced by the Java Arrow bindings and registers it on a DuckDB connection with `registerArrowStream()`. Once registered, the stream is addressed by the name passed to that method and can be queried like any other table.

```
import org.apache.arrow.c.ArrowArrayStream;
import org.apache.arrow.c.Data;
import org.apache.arrow.memory.RootAllocator;
import org.apache.arrow.vector.ipc.ArrowStreamReader;
import org.duckdb.DuckDBConnection;
import org.duckdb.DuckDBResultSet;
// Arrow binding
try (var allocator = new RootAllocator();
     ArrowStreamReader reader = null; // should not be null of course
     var arrow_array_stream = ArrowArrayStream.allocateNew(allocator)) {
    Data.exportArrayStream(allocator, reader, arrow_array_stream);
    // DuckDB setup
    try (var conn = (DuckDBConnection) DriverManager.getConnection("jdbc:duckdb:")) {
        conn.registerArrowStream("asdf", arrow_array_stream);
        // run a query
        try (var stmt = conn.createStatement();
             var rs = (DuckDBResultSet) stmt.executeQuery("SELECT count(*) FROM asdf")) {
            while (rs.next()) {
                System.out.println(rs.getInt(1));
            }
        }
    }
}
```
## 
        
        [Streaming Results](#streaming-results)
        
      

    
Result streaming is opt-in in the JDBC driver. Enable it by setting the `jdbc_stream_results` config to `true` before running a query. The easiest way to do that is to pass it in the `Properties` object.

```
Properties props = new Properties();
props.setProperty(DuckDBDriver.JDBC_STREAM_RESULTS, String.valueOf(true));
Connection conn = DriverManager.getConnection("jdbc:duckdb:", props);
```
## 
        
        [Chunked Results](#chunked-results)
        
      

    
The JDBC driver can return a query result as a lazily fetched sequence of columnar data chunks via the `org.duckdb.DuckDBChunkedResult` class.
This exposes the C API's `duckdb_fetch_chunk` function to Java and avoids the per-row overhead required by the JDBC `ResultSet` interface.
Chunk contents are read through the same `DuckDBDataChunkReader` API that is used by [user-defined functions](/docs/current/clients/java/functions.html).

Call `query()` on a `DuckDBPreparedStatement` to obtain a `DuckDBChunkedResult`, then advance through the chunks with `nextChunk()` and read each column vector by index.

Example:

```
import java.sql.DriverManager;
import org.duckdb.DuckDBConnection;
import org.duckdb.DuckDBPreparedStatement;
import org.duckdb.DuckDBChunkedResult;
import org.duckdb.DuckDBDataChunkReader;
import org.duckdb.DuckDBReadableVector;
try (DuckDBConnection conn = DriverManager
        .getConnection("jdbc:duckdb:")
        .unwrap(DuckDBConnection.class);
     DuckDBPreparedStatement ps = conn.prepare("SELECT ? AS col1")) {
    // statement parameters are 1-based
    ps.setInt(1, 42);
    try (DuckDBChunkedResult res = ps.query()) {
        // advance to the next chunk, returns true on success
        while (res.nextChunk()) {
            // get the current chunk from the result
            DuckDBDataChunkReader chunk = res.chunk();
            // iterate over the chunk columns, all indices are 0-based
            for (long col = 0; col < chunk.columnCount(); col++) {
                // get a vector for the specified column
                DuckDBReadableVector vector = chunk.vector(col);
                // iterate over the vector rows
                for (long row = 0; row < chunk.rowCount(); row++) {
                    int val = vector.getInt(row);
                    System.out.println(val);
                }
            }
        }
    }
}
```
Statement parameters remain 1-based, following the JDBC convention, while chunk columns and rows are 0-based, matching the C API and the user-defined function interfaces.

  The chunked result API currently supports basic data types only. Composite types such as `LIST` and `STRUCT` are not yet readable through this interface. The `query()` method is available on prepared statements only; there is no `query(String)` overload.

## 
        
        [Further Reading](#further-reading)
        
      

    
- [Run Queries](/docs/current/clients/java/querying.html) — sending the queries whose results this page reads, and the standard`ResultSet` accessors.
- [Define Functions](/docs/current/clients/java/functions.html) — the`DuckDBDataChunkReader` API shared with chunked results is also used to write user-defined functions.
- [Define Connections](/docs/current/clients/java/connecting.html) — the`jdbc_stream_results` option that enables result streaming.
- [C API](/docs/current/clients/c/api.html) — the`duckdb_fetch_chunk` function that the chunked result API exposes to Java.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/java/result_handling
