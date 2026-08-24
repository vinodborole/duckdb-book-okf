---
type: Web Page
title: SQL to/from JSON – DuckDB
description: DuckDB provides functions to serialize and deserialize SELECT statements
  between SQL and JSON, as well as executing JSON serialized statements. Function
  Type Description json_deserialize_sql(json) Scalar Deserialize one or many json
  serialized statements back to an equivalent SQL string. json_execute_serialized_sql(varchar)
  Table Execute json serialized statements and return the resulting rows. Only one
  statement at a time is supported for now. json_serialize_sql(varchar, skip_default
  := boolean, skip_empty := boolean, skip_null := boolean, format := boolean) Scalar
  Serialize a set of semicolon-separated (;) select statements to an equivalent list
  of json serialized statements. PRAGMA json_execute_serialized_sql(varchar) Pragma
  Pragma version of the json_execute_serialized_sql function. The json_serialize_sql(varchar)…
resource: https://duckdb.org/docs/current/data/json/sql_to_and_from_json
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

DuckDB provides functions to serialize and deserialize `SELECT` statements between SQL and JSON, as well as executing JSON serialized statements.

| Function | Type | Description | 
|---|---|---|
| `json_deserialize_sql(json)` | Scalar | Deserialize one or many `json` serialized statements back to an equivalent SQL string. | 
| `json_execute_serialized_sql(varchar)` | Table | Execute `json` serialized statements and return the resulting rows. Only one statement at a time is supported for now. | 
| `json_serialize_sql(varchar, skip_default := boolean, skip_empty := boolean, skip_null := boolean, format := boolean)` | Scalar | Serialize a set of semicolon-separated ( `;` ) select statements to an equivalent list of`json` serialized statements. | 
| `PRAGMA json_execute_serialized_sql(varchar)` | Pragma | Pragma version of the `json_execute_serialized_sql` function. | 

The `json_serialize_sql(varchar)` function takes three optional parameters, `skip_empty`, `skip_null` and `format` that can be used to control the output of the serialized statements.

If you run the `json_execute_serialized_sql(varchar)` table function inside of a transaction the serialized statements will not be able to see any transaction local changes. This is because the statements are executed in a separate query context. You can use the `PRAGMA json_execute_serialized_sql(varchar)` pragma version to execute the statements in the same query context as the pragma, although with the limitation that the serialized JSON must be provided as a constant string, i.e., you cannot do `PRAGMA json_execute_serialized_sql(json_serialize_sql(...))`.

Note that these functions do not preserve syntactic sugar such as `FROM * SELECT ...`, so a statement round-tripped through `json_deserialize_sql(json_serialize_sql(...))` may not be identical to the original statement, but should always be semantically equivalent and produce the same output.

## 
        
        [Examples](#examples)
        
      

    
Simple example:

```
SELECT json_serialize_sql('SELECT 2');
```
```
{"error":false,"statements":[{"node":{"type":"SELECT_NODE","modifiers":[],"cte_map":{"map":[]},"select_list":[{"class":"CONSTANT","type":"VALUE_CONSTANT","alias":"","query_location":7,"value":{"type":{"id":"INTEGER","type_info":null},"is_null":false,"value":2}}],"from_table":{"type":"EMPTY","alias":"","sample":null,"query_location":18446744073709551615},"where_clause":null,"group_expressions":[],"group_sets":[],"aggregate_handling":"STANDARD_HANDLING","having":null,"sample":null,"qualify":null},"named_param_map":[]}]}
```
Example with multiple statements and skip options:

```
SELECT json_serialize_sql('SELECT 1 + 2; SELECT a + b FROM tbl1', skip_empty := true, skip_null := true);
```
```
{"error":false,"statements":[{"node":{"type":"SELECT_NODE","select_list":[{"class":"FUNCTION","type":"FUNCTION","query_location":9,"function_name":"+","children":[{"class":"CONSTANT","type":"VALUE_CONSTANT","query_location":7,"value":{"type":{"id":"INTEGER"},"is_null":false,"value":1}},{"class":"CONSTANT","type":"VALUE_CONSTANT","query_location":11,"value":{"type":{"id":"INTEGER"},"is_null":false,"value":2}}],"order_bys":{"type":"ORDER_MODIFIER"},"distinct":false,"is_operator":true,"export_state":false}],"from_table":{"type":"EMPTY","query_location":18446744073709551615},"aggregate_handling":"STANDARD_HANDLING"}},{"node":{"type":"SELECT_NODE","select_list":[{"class":"FUNCTION","type":"FUNCTION","query_location":23,"function_name":"+","children":[{"class":"COLUMN_REF","type":"COLUMN_REF","query_location":21,"column_names":["a"]},{"class":"COLUMN_REF","type":"COLUMN_REF","query_location":25,"column_names":["b"]}],"order_bys":{"type":"ORDER_MODIFIER"},"distinct":false,"is_operator":true,"export_state":false}],"from_table":{"type":"BASE_TABLE","query_location":32,"table_name":"tbl1"},"aggregate_handling":"STANDARD_HANDLING"}}]}
```
Skip the default values in the AST (e.g., `"distinct":false`):

```
SELECT json_serialize_sql('SELECT 1 + 2; SELECT a + b FROM tbl1', skip_default := true, skip_empty := true, skip_null := true);
```
```
{"error":false,"statements":[{"node":{"type":"SELECT_NODE","select_list":[{"class":"FUNCTION","type":"FUNCTION","query_location":9,"function_name":"+","children":[{"class":"CONSTANT","type":"VALUE_CONSTANT","query_location":7,"value":{"type":{"id":"INTEGER"},"is_null":false,"value":1}},{"class":"CONSTANT","type":"VALUE_CONSTANT","query_location":11,"value":{"type":{"id":"INTEGER"},"is_null":false,"value":2}}],"order_bys":{"type":"ORDER_MODIFIER"},"is_operator":true}],"from_table":{"type":"EMPTY"},"aggregate_handling":"STANDARD_HANDLING"}},{"node":{"type":"SELECT_NODE","select_list":[{"class":"FUNCTION","type":"FUNCTION","query_location":23,"function_name":"+","children":[{"class":"COLUMN_REF","type":"COLUMN_REF","query_location":21,"column_names":["a"]},{"class":"COLUMN_REF","type":"COLUMN_REF","query_location":25,"column_names":["b"]}],"order_bys":{"type":"ORDER_MODIFIER"},"is_operator":true}],"from_table":{"type":"BASE_TABLE","query_location":32,"table_name":"tbl1"},"aggregate_handling":"STANDARD_HANDLING"}}]}
```
Example with a syntax error:

```
SELECT json_serialize_sql('TOTALLY NOT VALID SQL');
```
```
{"error":true,"error_type":"parser","error_message":"syntax error at or near \"TOTALLY\"","error_subtype":"SYNTAX_ERROR","position":"0"}
```
Example with deserialize:

```
SELECT json_deserialize_sql(json_serialize_sql('SELECT 1 + 2'));
```
```
SELECT (1 + 2)
```
Example with deserialize and syntax sugar, which is lost during the transformation:

```
SELECT json_deserialize_sql(json_serialize_sql('FROM x SELECT 1 + 2'));
```
```
SELECT (1 + 2) FROM x
```
Example with execute:

```
SELECT * FROM json_execute_serialized_sql(json_serialize_sql('SELECT 1 + 2'));
```
```
3
```
Example with error:

```
SELECT * FROM json_execute_serialized_sql(json_serialize_sql('TOTALLY NOT VALID SQL'));
```
```
Parser Error:
Error parsing json: parser: syntax error at or near "TOTALLY"
```

# Citations

1. Source page: https://duckdb.org/docs/current/data/json/sql_to_and_from_json
