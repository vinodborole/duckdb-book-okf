---
type: Web Page
title: Relational API – DuckDB
description: 'The Relational API is an alternative API that can be used to incrementally
  construct queries. The API is centered around DuckDBPyRelation nodes. The relations
  can be seen as symbolic representations of SQL queries. Lazy Evaluation The relations
  do not hold any data – and nothing is executed – until a method that triggers execution
  is called. For example, we create a relation, which loads 1 billion rows: import
  duckdb duckdb_conn = duckdb.connect() rel = duckdb_conn.sql("from range(1_000_000_000)")
  At the moment of execution, rel does not hold any data and no data is retrieved
  from the database. By calling rel.show() or simply…'
resource: https://duckdb.org/docs/current/clients/python/relational_api
timestamp: '2026-08-03T09:53:51.508916+00:00'
---

The Relational API is an alternative API that can be used to incrementally construct queries. 
The API is centered around `DuckDBPyRelation` nodes. The relations can be seen as symbolic representations of SQL queries.

## 
        
        [Lazy Evaluation](#lazy-evaluation)
        
      

    
The relations do not hold any data – and nothing is executed – until [a method that triggers execution](#output) is called.

For example, we create a relation, which loads 1 billion rows:

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("from range(1_000_000_000)")
```
At the moment of execution, `rel` does not hold any data and no data is retrieved from the database.

By calling `rel.show()` or simply printing `rel` on the terminal, the first 10K rows are fetched.
If there are more than 10K rows, the output window will show >9999 rows (as the amount of rows in the relation is unknown).

By calling an [output](#output) method, the data is retrieved and stored in the specified format:

```
rel.to_table("example_rel")
# 100% ▕████████████████████████████████████████████████████████████▏ 
```
## 
        
        [Relation Creation](#relation-creation)
        
      

    
This section contains the details on how a relation is created.         The methods are [lazy evaluated](#lazy-evaluation).

| Name | Description | 
|---|---|
| [`from_arrow`](#from_arrow) | Create a relation object from an Arrow object | 
| [`from_csv_auto`](#from_csv_auto) | Create a relation object from the CSV file in 'name' | 
| [`from_df`](#from_df) | Create a relation object from the DataFrame in df | 
| [`from_parquet`](#from_parquet) | Create a relation object from the Parquet files | 
| [`from_query`](#from_query) | Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is. | 
| [`query`](#query) | Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is. | 
| [`read_csv`](#read_csv) | Create a relation object from the CSV file in 'name' | 
| [`read_json`](#read_json) | Create a relation object from the JSON file in 'name' | 
| [`read_parquet`](#read_parquet) | Create a relation object from the Parquet files | 
| [`sql`](#sql) | Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is. | 
| [`table`](#table) | Create a relation object for the named table | 
| [`table_function`](#table_function) | Create a relation object from the named table function with given parameters | 
| [`values`](#values) | Create a relation object from the passed values | 
| [`view`](#view) | Create a relation object for the named view | 

#### 
        
        [`from_arrow`](#from_arrow)
        
      

    
      `from_arrow`
##### 
        
        [Signature](#signature)
        
      

    
```
from_arrow(self: _duckdb.DuckDBPyConnection, arrow_object: object) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description)
        
      

    
Create a relation object from an Arrow object

##### 
        
        [Parameters](#parameters)
        
      

    
- 
    **arrow_object** : pyarrow.Table, pyarrow.RecordBatchArrow object to create a relation from

##### 
        
        [Example](#example)
        
      

    
```
import duckdb
import pyarrow as pa
ids = pa.array([1], type=pa.int8())
texts = pa.array(['a'], type=pa.string())
example_table = pa.table([ids, texts], names=["id", "text"])
duckdb_conn = duckdb.connect()
rel = duckdb_conn.from_arrow(example_table)
rel.show()
```
##### 
        
        [Result](#result)
        
      

    
```
┌──────┬─────────┐
│  id  │  text   │
│ int8 │ varchar │
├──────┼─────────┤
│    1 │ a       │
└──────┴─────────┘
```
#### 
        
        [`from_csv_auto`](#from_csv_auto)
        
      

    
      `from_csv_auto`
##### 
        
        [Signature](#signature-1)
        
      

    
```
from_csv_auto(self: _duckdb.DuckDBPyConnection, path_or_buffer: object, **kwargs) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-1)
        
      

    
Create a relation object from the CSV file in 'name'

**Aliases**: `read_csv`

##### 
        
        [Parameters](#parameters-1)
        
      

    
- 
    **path_or_buffer** : Union[str, StringIO, TextIOBase]Path to the CSV file or buffer to read from.
- 
    **header** : Optional[bool], Optional[int]Row number(s) to use as the column names, or None if no header.
- 
    **compression** : Optional[str]Compression type (e.g., 'gzip', 'bz2').
- 
    **sep** : Optional[str]Delimiter to use; defaults to comma.
- 
    **delimiter** : Optional[str]Alternative delimiter to use.
- 
    **dtype** : Optional[Dict[str, str]], Optional[List[str]]Data types for columns.
- 
    **na_values** : Optional[str], Optional[List[str]]Additional strings to recognize as NA/NaN.
- 
    **skiprows** : Optional[int]Number of rows to skip at the start.
- 
    **quotechar** : Optional[str]Character used to quote fields.
- 
    **escapechar** : Optional[str]Character used to escape delimiter or quote characters.
- 
    **encoding** : Optional[str]Encoding to use for UTF when reading/writing.
- 
    **parallel** : Optional[bool]Enable parallel reading.
- 
    **date_format** : Optional[str]Format to parse dates.
- 
    **timestamp_format** : Optional[str]Format to parse timestamps.
- 
    **sample_size** : Optional[int]Number of rows to sample for schema inference.
- 
    **all_varchar** : Optional[bool]Treat all columns as VARCHAR.
- 
    **normalize_names** : Optional[bool]Normalize column names to lowercase.
- 
    **null_padding** : Optional[bool]Enable null padding for rows with missing columns.
- 
    **names** : Optional[List[str]]List of column names to use.
- 
    **lineterminator** : Optional[str]Character to break lines on.
- 
    **columns** : Optional[Dict[str, str]]Column mapping for schema.
- 
    **auto_type_candidates** : Optional[List[str]]List of columns for automatic type inference.
- 
    **max_line_size** : Optional[int]Maximum line size in bytes.
- 
    **ignore_errors** : Optional[bool]Ignore parsing errors.
- 
    **store_rejects** : Optional[bool]Store rejected rows.
- 
    **rejects_table** : Optional[str]Table name to store rejected rows.
- 
    **rejects_scan** : Optional[str]Scan to use for rejects.
- 
    **rejects_limit** : Optional[int]Limit number of rejects stored.
- 
    **force_not_null** : Optional[List[str]]List of columns to force as NOT NULL.
- 
    **buffer_size** : Optional[int]Buffer size in bytes.
- 
    **decimal** : Optional[str]Character to recognize as decimal point.
- 
    **allow_quoted_nulls** : Optional[bool]Allow quoted NULL values.
- 
    **filename** : Optional[bool], Optional[str]Add filename column or specify filename.
- 
    **hive_partitioning** : Optional[bool]Enable Hive-style partitioning.
- 
    **union_by_name** : Optional[bool]Union files by column name instead of position.
- 
    **hive_types** : Optional[Dict[str, str]]Hive types for columns.
- 
    **hive_types_autocast** : Optional[bool]Automatically cast Hive types.
- 
    **connection** : DuckDBPyConnectionDuckDB connection to use.

##### 
        
        [Example](#example-1)
        
      

    
```
import csv
import duckdb
duckdb_conn = duckdb.connect()
with open('code_example.csv', 'w', newline='') as csvfile:
    fieldnames = ['id', 'text']
    writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerow({'id': '1', 'text': 'a'})
rel = duckdb_conn.from_csv_auto("code_example.csv")
rel.show()
```
##### 
        
        [Result](#result-1)
        
      

    
```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        [`from_df`](#from_df)
        
      

    
      `from_df`
##### 
        
        [Signature](#signature-2)
        
      

    
```
from_df(self: _duckdb.DuckDBPyConnection, df: pandas.DataFrame) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-2)
        
      

    
Create a relation object from the DataFrame in df

##### 
        
        [Parameters](#parameters-2)
        
      

    
- 
    **df** : pandas.DataFrameA pandas DataFrame to be converted into a DuckDB relation.

##### 
        
        [Example](#example-2)
        
      

    
```
import duckdb
import pandas as pd
df = pd.DataFrame(data = {'id': [1], "text":["a"]})
duckdb_conn = duckdb.connect()
rel = duckdb_conn.from_df(df)
rel.show()
```
##### 
        
        [Result](#result-2)
        
      

    
```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        [`from_parquet`](#from_parquet)
        
      

    
      `from_parquet`
##### 
        
        [Signature](#signature-3)
        
      

    
```
from_parquet(*args, **kwargs)
Overloaded function.
1. from_parquet(self: _duckdb.DuckDBPyConnection, file_glob: str, binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_glob
2. from_parquet(self: _duckdb.DuckDBPyConnection, file_globs: collections.abc.Sequence[str], binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_globs
```
##### 
        
        [Description](#description-3)
        
      

    
Create a relation object from the Parquet files

**Aliases**: `read_parquet`

##### 
        
        [Parameters](#parameters-3)
        
      

    
- 
    **file_glob** : strFile path or glob pattern pointing to Parquet files to be read.
- 
    **binary_as_string** : bool, default: FalseInterpret binary columns as strings instead of blobs.
- 
    **file_row_number** : bool, default: FalseAdd a column containing the row number within each file.
- 
    **filename** : bool, default: FalseAdd a column containing the name of the file each row came from.
- 
    **hive_partitioning** : bool, default: FalseEnable automatic detection of Hive-style partitions in file paths.
- 
    **union_by_name** : bool, default: FalseUnion Parquet files by matching column names instead of positions.
- 
    **compression** : objectOptional compression codec to use when reading the Parquet files.

##### 
        
        [Example](#example-3)
        
      

    
```
import duckdb
import pyarrow as pa
import pyarrow.parquet as pq
ids = pa.array([1], type=pa.int8())
texts = pa.array(['a'], type=pa.string())
example_table = pa.table([ids, texts], names=["id", "text"])
pq.write_table(example_table, "code_example.parquet")
duckdb_conn = duckdb.connect()
rel = duckdb_conn.from_parquet("code_example.parquet")
rel.show()
```
##### 
        
        [Result](#result-3)
        
      

    
```
┌──────┬─────────┐
│  id  │  text   │
│ int8 │ varchar │
├──────┼─────────┤
│    1 │ a       │
└──────┴─────────┘
```
#### 
        
        [`from_query`](#from_query)
        
      

    
      `from_query`
##### 
        
        [Signature](#signature-4)
        
      

    
```
from_query(self: _duckdb.DuckDBPyConnection, query: object, *, alias: str = '', params: object = None) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-4)
        
      

    
Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is.

  **Warning.** Passing `params` to this method is [discouraged](/docs/current/clients/python/known_issues.html#parameterized-queries-in-relational-api) due to significant performance overhead. Use [`execute()`](/docs/current/clients/python/dbapi.html#prepared-statements) for parameterized queries instead.

##### 
        
        [Parameters](#parameters-4)
        
      

    
- 
    **query** : objectThe SQL query or subquery to be executed and converted into a relation.
- 
    **alias** : str, default: ''Optional alias name to assign to the resulting relation.
- 
    **params** : objectOptional query parameters. **Discouraged** due to[significant performance overhead](/docs/current/clients/python/known_issues.html#parameterized-queries-in-relational-api) . Use[`execute()`](/docs/current/clients/python/dbapi.html#prepared-statements) for parameterized queries instead.

##### 
        
        [Example](#example-4)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.from_query("from range(1,2) tbl(id)")
rel.show()
```
##### 
        
        [Result](#result-4)
        
      

    
```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        [`query`](#query)
        
      

    
      `query`
##### 
        
        [Signature](#signature-5)
        
      

    
```
query(self: _duckdb.DuckDBPyConnection, query: object, *, alias: str = '', params: object = None) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-5)
        
      

    
Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is.

  **Warning.** Passing `params` to this method is [discouraged](/docs/current/clients/python/known_issues.html#parameterized-queries-in-relational-api) due to significant performance overhead. Use [`execute()`](/docs/current/clients/python/dbapi.html#prepared-statements) for parameterized queries instead.

**Aliases**: [`from_query`](#from_query), `sql`

##### 
        
        [Parameters](#parameters-5)
        
      

    
- 
    **query** : objectThe SQL query or subquery to be executed and converted into a relation.
- 
    **alias** : str, default: ''Optional alias name to assign to the resulting relation.
- 
    **params** : objectOptional query parameters. **Discouraged** due to[significant performance overhead](/docs/current/clients/python/known_issues.html#parameterized-queries-in-relational-api) . Use[`execute()`](/docs/current/clients/python/dbapi.html#prepared-statements) for parameterized queries instead.

##### 
        
        [Example](#example-5)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.query("from range(1,2) tbl(id)")
rel.show()
```
##### 
        
        [Result](#result-5)
        
      

    
```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        [`read_csv`](#read_csv)
        
      

    
      `read_csv`
##### 
        
        [Signature](#signature-6)
        
      

    
```
read_csv(self: _duckdb.DuckDBPyConnection, path_or_buffer: object, **kwargs) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-6)
        
      

    
Create a relation object from the CSV file in 'name'

**Aliases**: `from_csv_auto`

##### 
        
        [Parameters](#parameters-6)
        
      

    
- 
    **path_or_buffer** : Union[str, StringIO, TextIOBase]Path to the CSV file or buffer to read from.
- 
    **header** : Optional[bool], Optional[int]Row number(s) to use as the column names, or None if no header.
- 
    **compression** : Optional[str]Compression type (e.g., 'gzip', 'bz2').
- 
    **sep** : Optional[str]Delimiter to use; defaults to comma.
- 
    **delimiter** : Optional[str]Alternative delimiter to use.
- 
    **dtype** : Optional[Dict[str, str]], Optional[List[str]]Data types for columns.
- 
    **na_values** : Optional[str], Optional[List[str]]Additional strings to recognize as NA/NaN.
- 
    **skiprows** : Optional[int]Number of rows to skip at the start.
- 
    **quotechar** : Optional[str]Character used to quote fields.
- 
    **escapechar** : Optional[str]Character used to escape delimiter or quote characters.
- 
    **encoding** : Optional[str]Encoding to use for UTF when reading/writing.
- 
    **parallel** : Optional[bool]Enable parallel reading.
- 
    **date_format** : Optional[str]Format to parse dates.
- 
    **timestamp_format** : Optional[str]Format to parse timestamps.
- 
    **sample_size** : Optional[int]Number of rows to sample for schema inference.
- 
    **all_varchar** : Optional[bool]Treat all columns as VARCHAR.
- 
    **normalize_names** : Optional[bool]Normalize column names to lowercase.
- 
    **null_padding** : Optional[bool]Enable null padding for rows with missing columns.
- 
    **names** : Optional[List[str]]List of column names to use.
- 
    **lineterminator** : Optional[str]Character to break lines on.
- 
    **columns** : Optional[Dict[str, str]]Column mapping for schema.
- 
    **auto_type_candidates** : Optional[List[str]]List of columns for automatic type inference.
- 
    **max_line_size** : Optional[int]Maximum line size in bytes.
- 
    **ignore_errors** : Optional[bool]Ignore parsing errors.
- 
    **store_rejects** : Optional[bool]Store rejected rows.
- 
    **rejects_table** : Optional[str]Table name to store rejected rows.
- 
    **rejects_scan** : Optional[str]Scan to use for rejects.
- 
    **rejects_limit** : Optional[int]Limit number of rejects stored.
- 
    **force_not_null** : Optional[List[str]]List of columns to force as NOT NULL.
- 
    **buffer_size** : Optional[int]Buffer size in bytes.
- 
    **decimal** : Optional[str]Character to recognize as decimal point.
- 
    **allow_quoted_nulls** : Optional[bool]Allow quoted NULL values.
- 
    **filename** : Optional[bool], Optional[str]Add filename column or specify filename.
- 
    **hive_partitioning** : Optional[bool]Enable Hive-style partitioning.
- 
    **union_by_name** : Optional[bool]Union files by column name instead of position.
- 
    **hive_types** : Optional[Dict[str, str]]Hive types for columns.
- 
    **hive_types_autocast** : Optional[bool]Automatically cast Hive types.
- 
    **connection** : DuckDBPyConnectionDuckDB connection to use.

##### 
        
        [Example](#example-6)
        
      

    
```
import csv
import duckdb
duckdb_conn = duckdb.connect()
with open('code_example.csv', 'w', newline='') as csvfile:
    fieldnames = ['id', 'text']
    writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerow({'id': '1', 'text': 'a'})
rel = duckdb_conn.read_csv("code_example.csv")
rel.show()
```
##### 
        
        [Result](#result-6)
        
      

    
```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        [`read_json`](#read_json)
        
      

    
      `read_json`
##### 
        
        [Signature](#signature-7)
        
      

    
```
read_json(self: _duckdb.DuckDBPyConnection, path_or_buffer: object, *, columns: typing.Optional[object] = None, sample_size: typing.Optional[object] = None, maximum_depth: typing.Optional[object] = None, records: typing.Optional[str] = None, format: typing.Optional[str] = None, date_format: typing.Optional[object] = None, timestamp_format: typing.Optional[object] = None, compression: typing.Optional[object] = None, maximum_object_size: typing.Optional[object] = None, ignore_errors: typing.Optional[object] = None, convert_strings_to_integers: typing.Optional[object] = None, field_appearance_threshold: typing.Optional[object] = None, map_inference_threshold: typing.Optional[object] = None, maximum_sample_files: typing.Optional[object] = None, filename: typing.Optional[object] = None, hive_partitioning: typing.Optional[object] = None, union_by_name: typing.Optional[object] = None, hive_types: typing.Optional[object] = None, hive_types_autocast: typing.Optional[object] = None) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-7)
        
      

    
Create a relation object from the JSON file in 'name'

##### 
        
        [Parameters](#parameters-7)
        
      

    
- 
    **path_or_buffer** : objectFile path or file-like object containing JSON data to be read.
- 
    **columns** : objectOptional list of column names to project from the JSON data.
- 
    **sample_size** : objectNumber of rows to sample for inferring JSON schema.
- 
    **maximum_depth** : objectMaximum depth to which JSON objects should be parsed.
- 
    **records** : strFormat string specifying whether JSON is in records mode.
- 
    **format** : strFormat of the JSON data (e.g., 'auto', 'newline_delimited').
- 
    **date_format** : objectFormat string for parsing date fields.
- 
    **timestamp_format** : objectFormat string for parsing timestamp fields.
- 
    **compression** : objectCompression codec used on the JSON data (e.g., 'gzip').
- 
    **maximum_object_size** : objectMaximum size in bytes for individual JSON objects.
- 
    **ignore_errors** : objectIf True, skip over JSON records with parsing errors.
- 
    **convert_strings_to_integers** : objectIf True, attempt to convert strings to integers where appropriate.
- 
    **field_appearance_threshold** : objectThreshold for inferring optional fields in nested JSON.
- 
    **map_inference_threshold** : objectThreshold for inferring maps from JSON object patterns.
- 
    **maximum_sample_files** : objectMaximum number of files to sample for schema inference.
- 
    **filename** : objectIf True, include a column with the source filename for each row.
- 
    **hive_partitioning** : objectIf True, enable Hive partitioning based on directory structure.
- 
    **union_by_name** : objectIf True, align JSON columns by name instead of position.
- 
    **hive_types** : objectIf True, use Hive types from directory structure for schema.
- 
    **hive_types_autocast** : objectIf True, automatically cast data types to match Hive types.

##### 
        
        [Example](#example-7)
        
      

    
```
import duckdb
import json
with open("code_example.json", mode="w") as f:
    json.dump([{'id': 1, "text":"a"}], f)
    
duckdb_conn = duckdb.connect()
rel = duckdb_conn.read_json("code_example.json")
rel.show()
```
##### 
        
        [Result](#result-7)
        
      

    
```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        [`read_parquet`](#read_parquet)
        
      

    
      `read_parquet`
##### 
        
        [Signature](#signature-8)
        
      

    
```
read_parquet(*args, **kwargs)
Overloaded function.
1. read_parquet(self: _duckdb.DuckDBPyConnection, file_glob: str, binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_glob
2. read_parquet(self: _duckdb.DuckDBPyConnection, file_globs: collections.abc.Sequence[str], binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_globs
```
##### 
        
        [Description](#description-8)
        
      

    
Create a relation object from the Parquet files

**Aliases**: `from_parquet`

##### 
        
        [Parameters](#parameters-8)
        
      

    
- 
    **file_glob** : strFile path or glob pattern pointing to Parquet files to be read.
- 
    **binary_as_string** : bool, default: FalseInterpret binary columns as strings instead of blobs.
- 
    **file_row_number** : bool, default: FalseAdd a column containing the row number within each file.
- 
    **filename** : bool, default: FalseAdd a column containing the name of the file each row came from.
- 
    **hive_partitioning** : bool, default: FalseEnable automatic detection of Hive-style partitions in file paths.
- 
    **union_by_name** : bool, default: FalseUnion Parquet files by matching column names instead of positions.
- 
    **compression** : objectOptional compression codec to use when reading the Parquet files.

##### 
        
        [Example](#example-8)
        
      

    
```
import duckdb
import pyarrow as pa
import pyarrow.parquet as pq
ids = pa.array([1], type=pa.int8())
texts = pa.array(['a'], type=pa.string())
example_table = pa.table([ids, texts], names=["id", "text"])
pq.write_table(example_table, "code_example.parquet")
duckdb_conn = duckdb.connect()
rel = duckdb_conn.read_parquet("code_example.parquet")
rel.show()
```
##### 
        
        [Result](#result-8)
        
      

    
```
┌──────┬─────────┐
│  id  │  text   │
│ int8 │ varchar │
├──────┼─────────┤
│    1 │ a       │
└──────┴─────────┘
```
#### 
        
        [`sql`](#sql)
        
      

    
      `sql`
##### 
        
        [Signature](#signature-9)
        
      

    
```
sql(self: _duckdb.DuckDBPyConnection, query: object, *, alias: str = '', params: object = None) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-9)
        
      

    
Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is.

  **Warning.** Passing `params` to this method is [discouraged](/docs/current/clients/python/known_issues.html#parameterized-queries-in-relational-api) due to significant performance overhead. Use [`execute()`](/docs/current/clients/python/dbapi.html#prepared-statements) for parameterized queries instead.

**Aliases**: [`from_query`](#from_query), `query`

##### 
        
        [Parameters](#parameters-9)
        
      

    
- 
    **query** : objectThe SQL query or subquery to be executed and converted into a relation.
- 
    **alias** : str, default: ''Optional alias name to assign to the resulting relation.
- 
    **params** : objectOptional query parameters. **Discouraged** due to[significant performance overhead](/docs/current/clients/python/known_issues.html#parameterized-queries-in-relational-api) . Use[`execute()`](/docs/current/clients/python/dbapi.html#prepared-statements) for parameterized queries instead.

##### 
        
        [Example](#example-9)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("from range(1,2) tbl(id)")
rel.show()
```
##### 
        
        [Result](#result-9)
        
      

    
```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        [`table`](#table)
        
      

    
      `table`
##### 
        
        [Signature](#signature-10)
        
      

    
```
table(self: _duckdb.DuckDBPyConnection, table_name: str) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-10)
        
      

    
Create a relation object for the named table

##### 
        
        [Parameters](#parameters-10)
        
      

    
- 
    **table_name** : strName of the table to create a relation from.

##### 
        
        [Example](#example-10)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
duckdb_conn.sql("create table code_example as select * from range(1,2) tbl(id)")
rel = duckdb_conn.table("code_example")
rel.show()
```
##### 
        
        [Result](#result-10)
        
      

    
```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        [`table_function`](#table_function)
        
      

    
      `table_function`
##### 
        
        [Signature](#signature-11)
        
      

    
```
table_function(self: _duckdb.DuckDBPyConnection, name: str, parameters: object = None) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-11)
        
      

    
Create a relation object from the named table function with given parameters

##### 
        
        [Parameters](#parameters-11)
        
      

    
- 
    **name** : strName of the table function to call.
- 
    **parameters** : objectOptional parameters to pass to the table function.

##### 
        
        [Example](#example-11)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
duckdb_conn.sql("""
    create macro get_record_for(x) as table
    select x*range from range(1,2)
""")
rel = duckdb_conn.table_function(name="get_record_for", parameters=[1])
rel.show()
```
##### 
        
        [Result](#result-11)
        
      

    
```
┌───────────────┐
│ (1 * "range") │
│     int64     │
├───────────────┤
│             1 │
└───────────────┘
```
#### 
        
        [`values`](#values)
        
      

    
      `values`
##### 
        
        [Signature](#signature-12)
        
      

    
```
values(self: _duckdb.DuckDBPyConnection, *args) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-12)
        
      

    
Create a relation object from the passed values

##### 
        
        [Example](#example-12)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.values([1, 'a'])
rel.show()
```
##### 
        
        [Result](#result-12)
        
      

    
```
┌───────┬─────────┐
│ col0  │  col1   │
│ int32 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        [`view`](#view)
        
      

    
      `view`
##### 
        
        [Signature](#signature-13)
        
      

    
```
view(self: _duckdb.DuckDBPyConnection, view_name: str) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-13)
        
      

    
Create a relation object for the named view

##### 
        
        [Parameters](#parameters-12)
        
      

    
- 
    **view_name** : strName of the view to create a relation from.

##### 
        
        [Example](#example-13)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
duckdb_conn.sql("create table code_example as select * from range(1,2) tbl(id)")
rel = duckdb_conn.view("code_example")
rel.show()
```
##### 
        
        [Result](#result-13)
        
      

    
```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
## 
        
        [Relation Definition Details](#relation-definition-details)
        
      

    
This section contains the details on how to inspect a relation.

| Name | Description | 
|---|---|
| [`alias`](#alias) | Get the name of the current alias | 
| [`columns`](#columns) | Return a list containing the names of the columns of the relation. | 
| [`describe`](#describe) | Gives basic statistics (e.g., min, max) and if NULL exists for each column of the relation. | 
| [`description`](#description) | Return the description of the result | 
| [`dtypes`](#dtypes) | Return a list containing the types of the columns of the relation. | 
| [`explain`](#explain) | explain(self: _duckdb.DuckDBPyRelation, type: _duckdb.ExplainType = 'standard') -> str | 
| [`query`](#query-1) | Run the given SQL query in sql_query on the view named virtual_table_name that refers to the relation object | 
| [`set_alias`](#set_alias) | Rename the relation object to new alias | 
| [`shape`](#shape) | Tuple of # of rows, # of columns in relation. | 
| [`show`](#show) | Display a summary of the data | 
| [`sql_query`](#sql_query) | Get the SQL query that is equivalent to the relation | 
| [`type`](#type) | Get the type of the relation. | 
| [`types`](#types) | Return a list containing the types of the columns of the relation. | 

#### 
        
        [`alias`](#alias)
        
      

    
      `alias`
##### 
        
        [Description](#description-14)
        
      

    
Get the name of the current alias

##### 
        
        [Example](#example-14)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.alias
```
##### 
        
        [Result](#result-14)
        
      

    
```
unnamed_relation_43c808c247431be5
```
#### 
        
        [`columns`](#columns)
        
      

    
      `columns`
##### 
        
        [Description](#description-15)
        
      

    
Return a list containing the names of the columns of the relation.

##### 
        
        [Example](#example-15)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.columns
```
##### 
        
        [Result](#result-15)
        
      

    
```
 ['id', 'description', 'value', 'created_timestamp']
```
#### 
        
        [`describe`](#describe)
        
      

    
      `describe`
##### 
        
        [Signature](#signature-14)
        
      

    
```
describe(self: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-16)
        
      

    
Gives basic statistics (e.g., min, max) and if NULL exists for each column of the relation.

##### 
        
        [Example](#example-16)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.describe()
```
##### 
        
        [Result](#result-16)
        
      

    
```
┌─────────┬──────────────────────────────────────┬─────────────────┬────────────────────┬────────────────────────────┐
│  aggr   │                  id                  │   description   │       value        │     created_timestamp      │
│ varchar │               varchar                │     varchar     │       double       │          varchar           │
├─────────┼──────────────────────────────────────┼─────────────────┼────────────────────┼────────────────────────────┤
│ count   │ 9                                    │ 9               │                9.0 │ 9                          │
│ mean    │ NULL                                 │ NULL            │                5.0 │ NULL                       │
│ stddev  │ NULL                                 │ NULL            │ 2.7386127875258306 │ NULL                       │
│ min     │ 08fdcbf8-4e53-4290-9e81-423af263b518 │ value is even   │                1.0 │ 2025-04-09 15:41:20.642+02 │
│ max     │ fb10390e-fad5-4694-91cb-e82728cb6f9f │ value is uneven │                9.0 │ 2025-04-09 15:49:20.642+02 │
│ median  │ NULL                                 │ NULL            │                5.0 │ NULL                       │
└─────────┴──────────────────────────────────────┴─────────────────┴────────────────────┴────────────────────────────┘ 
```
#### 
        
        [`description`](#description-17)
        
      

    
      `description`
##### 
        
        [Description](#description-18)
        
      

    
Return the description of the result

##### 
        
        [Example](#example-17)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.description
```
##### 
        
        [Result](#result-17)
        
      

    
```
[('id', 'UUID', None, None, None, None, None),
 ('description', 'STRING', None, None, None, None, None),
 ('value', 'NUMBER', None, None, None, None, None),
 ('created_timestamp', 'DATETIME', None, None, None, None, None)]  
```
#### 
        
        [`dtypes`](#dtypes)
        
      

    
      `dtypes`
##### 
        
        [Description](#description-19)
        
      

    
Return a list containing the types of the columns of the relation.

**Aliases**: `types`

##### 
        
        [Example](#example-18)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.dtypes
```
##### 
        
        [Result](#result-18)
        
      

    
```
 [UUID, VARCHAR, BIGINT, TIMESTAMP WITH TIME ZONE]
```
#### 
        
        [`explain`](#explain)
        
      

    
      `explain`
##### 
        
        [Description](#description-20)
        
      

    
explain(self: _duckdb.DuckDBPyRelation, type: _duckdb.ExplainType = 'standard') -> str

##### 
        
        [Example](#example-19)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.explain()
```
##### 
        
        [Result](#result-19)
        
      

    
```
┌───────────────────────────┐
│         PROJECTION        │
│    ────────────────────   │
│             id            │
│        description        │
│           value           │
│     created_timestamp     │
│                           │
│          ~9 Rows          │
└─────────────┬─────────────┘
┌─────────────┴─────────────┐
│           RANGE           │
│    ────────────────────   │
│      Function: RANGE      │
│                           │
│          ~9 Rows          │
└───────────────────────────┘
```
#### 
        
        [`query`](#query-1)
        
      

    
      `query`
##### 
        
        [Signature](#signature-15)
        
      

    
```
query(self: _duckdb.DuckDBPyRelation, virtual_table_name: str, sql_query: str) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-21)
        
      

    
Run the given SQL query in sql_query on the view named virtual_table_name that refers to the relation object

##### 
        
        [Parameters](#parameters-13)
        
      

    
- 
    **virtual_table_name** : strThe name to assign to the current relation when referenced in the SQL query.
- 
    **sql_query** : strThe SQL query string that uses the virtual table name to query the relation.

##### 
        
        [Example](#example-20)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.query(virtual_table_name="rel_view", sql_query="from rel")
duckdb_conn.sql("show rel_view")
```
##### 
        
        [Result](#result-20)
        
      

    
```
┌───────────────────┬──────────────────────────┬─────────┬─────────┬─────────┬─────────┐
│    column_name    │       column_type        │  null   │   key   │ default │  extra  │
│      varchar      │         varchar          │ varchar │ varchar │ varchar │ varchar │
├───────────────────┼──────────────────────────┼─────────┼─────────┼─────────┼─────────┤
│ id                │ UUID                     │ YES     │ NULL    │ NULL    │ NULL    │
│ description       │ VARCHAR                  │ YES     │ NULL    │ NULL    │ NULL    │
│ value             │ BIGINT                   │ YES     │ NULL    │ NULL    │ NULL    │
│ created_timestamp │ TIMESTAMP WITH TIME ZONE │ YES     │ NULL    │ NULL    │ NULL    │
└───────────────────┴──────────────────────────┴─────────┴─────────┴─────────┴─────────┘
```
#### 
        
        [`set_alias`](#set_alias)
        
      

    
      `set_alias`
##### 
        
        [Signature](#signature-16)
        
      

    
```
set_alias(self: _duckdb.DuckDBPyRelation, alias: str) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-22)
        
      

    
Rename the relation object to new alias

##### 
        
        [Parameters](#parameters-14)
        
      

    
- 
    **alias** : strThe alias name to assign to the relation.

##### 
        
        [Example](#example-21)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.set_alias('abc').select('abc.id')
```
##### 
        
        [Result](#result-21)
        
      

    
```
In the SQL query, the alias will be `abc`
```
#### 
        
        [`shape`](#shape)
        
      

    
      `shape`
##### 
        
        [Description](#description-23)
        
      

    
Tuple of # of rows, # of columns in relation.

##### 
        
        [Example](#example-22)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.shape
```
##### 
        
        [Result](#result-22)
        
      

    
```
(9, 4)
```
#### 
        
        [`show`](#show)
        
      

    
      `show`
##### 
        
        [Signature](#signature-17)
        
      

    
```
show(self: _duckdb.DuckDBPyRelation, *, max_width: typing.Optional[typing.SupportsInt] = None, max_rows: typing.Optional[typing.SupportsInt] = None, max_col_width: typing.Optional[typing.SupportsInt] = None, null_value: typing.Optional[str] = None, render_mode: object = None) -> None
```
##### 
        
        [Description](#description-24)
        
      

    
Display a summary of the data

##### 
        
        [Parameters](#parameters-15)
        
      

    
- 
    **max_width** : intMaximum display width for the entire output in characters.
- 
    **max_rows** : intMaximum number of rows to display.
- 
    **max_col_width** : intMaximum number of characters to display per column.
- 
    **null_value** : strString to display in place of NULL values.
- 
    **render_mode** : objectRender mode for displaying the output.

##### 
        
        [Example](#example-23)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.show()
```
##### 
        
        [Result](#result-23)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 642ea3d7-793d-4867-a759-91c1226c25a0 │ value is uneven │     1 │ 2025-04-09 15:41:20.642+02 │
│ 6817dd31-297c-40a8-8e40-8521f00b2d08 │ value is even   │     2 │ 2025-04-09 15:42:20.642+02 │
│ 45143f9a-e16e-4e59-91b2-3a0800eed6d6 │ value is uneven │     3 │ 2025-04-09 15:43:20.642+02 │
│ fb10390e-fad5-4694-91cb-e82728cb6f9f │ value is even   │     4 │ 2025-04-09 15:44:20.642+02 │
│ 111ced5c-9155-418e-b087-c331b814db90 │ value is uneven │     5 │ 2025-04-09 15:45:20.642+02 │
│ 66a870a6-aef0-4085-87d5-5d1b35d21c66 │ value is even   │     6 │ 2025-04-09 15:46:20.642+02 │
│ a7e8e796-bca0-44cd-a269-1d71090fb5cc │ value is uneven │     7 │ 2025-04-09 15:47:20.642+02 │
│ 74908d48-7f2d-4bdd-9c92-1e7920b115b5 │ value is even   │     8 │ 2025-04-09 15:48:20.642+02 │
│ 08fdcbf8-4e53-4290-9e81-423af263b518 │ value is uneven │     9 │ 2025-04-09 15:49:20.642+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        [`sql_query`](#sql_query)
        
      

    
      `sql_query`
##### 
        
        [Signature](#signature-18)
        
      

    
```
sql_query(self: _duckdb.DuckDBPyRelation) -> str
```
##### 
        
        [Description](#description-25)
        
      

    
Get the SQL query that is equivalent to the relation

##### 
        
        [Example](#example-24)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.sql_query()
```
##### 
        
        [Result](#result-24)
        
      

    
```
SELECT 
    gen_random_uuid() AS id, 
    concat('value is ', CASE  WHEN ((mod("range", 2) = 0)) THEN ('even') ELSE 'uneven' END) AS description, 
    "range" AS "value", 
    (now() + CAST(concat("range", ' ', 'minutes') AS INTERVAL)) AS created_timestamp 
FROM "range"(1, 10)
```
#### 
        
        [`type`](#type)
        
      

    
      `type`
##### 
        
        [Description](#description-26)
        
      

    
Get the type of the relation.

##### 
        
        [Example](#example-25)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.type
```
##### 
        
        [Result](#result-25)
        
      

    
```
QUERY_RELATION
```
#### 
        
        [`types`](#types)
        
      

    
      `types`
##### 
        
        [Description](#description-27)
        
      

    
Return a list containing the types of the columns of the relation.

**Aliases**: `dtypes`

##### 
        
        [Example](#example-26)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.types
```
##### 
        
        [Result](#result-26)
        
      

    
```
[UUID, VARCHAR, BIGINT, TIMESTAMP WITH TIME ZONE]
```
## 
        
        [Transformation](#transformation)
        
      

    
This section contains the methods which can be used to chain queries.        The methods are [lazy evaluated](#lazy-evaluation).

| Name | Description | 
|---|---|
| [`aggregate`](#aggregate) | Compute the aggregate aggr_expr by the optional groups group_expr on the relation | 
| [`apply`](#apply) | Compute the function of a single column or a list of columns by the optional groups on the relation | 
| [`cross`](#cross) | Create cross/cartesian product of two relational objects | 
| [`except_`](#except_) | Create the set except of this relation object with another relation object in other_rel | 
| [`filter`](#filter) | Filter the relation object by the filter in filter_expr | 
| [`insert`](#insert) | Inserts the given values into the relation | 
| [`insert_into`](#insert_into) | Inserts the relation object into an existing table named table_name | 
| [`intersect`](#intersect) | Create the set intersection of this relation object with another relation object in other_rel | 
| [`join`](#join) | Join the relation object with another relation object in other_rel using the join condition expression in join_condition. Types supported are 'inner', 'left', 'right', 'outer', 'semi' and 'anti' | 
| [`limit`](#limit) | Only retrieve the first n rows from this relation object, starting at offset | 
| [`map`](#map) | Calls the passed function on the relation | 
| [`order`](#order) | Reorder the relation object by order_expr | 
| [`project`](#project) | Project the relation object by the projection in project_expr | 
| [`select`](#select) | Project the relation object by the projection in project_expr | 
| [`sort`](#sort) | Reorder the relation object by the provided expressions | 
| [`union`](#union) | Create the set union of this relation object with another relation object in other_rel | 
| [`update`](#update) | Update the given relation with the provided expressions | 

#### 
        
        [`aggregate`](#aggregate)
        
      

    
      `aggregate`
##### 
        
        [Signature](#signature-19)
        
      

    
```
aggregate(self: _duckdb.DuckDBPyRelation, aggr_expr: object, group_expr: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-28)
        
      

    
Compute the aggregate aggr_expr by the optional groups group_expr on the relation

##### 
        
        [Parameters](#parameters-16)
        
      

    
- 
    **aggr_expr** : str, list[Expression]The list of columns and aggregation functions.
- 
    **group_expr** : str, default: ''The list of columns to be included in `group_by` . If`None` ,`group by all` is applied.

##### 
        
        [Example](#example-27)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.aggregate('max(value)')
```
##### 
        
        [Result](#result-27)
        
      

    
```
┌──────────────┐
│ max("value") │
│    int64     │
├──────────────┤
│            9 │
└──────────────┘
        
```
#### 
        
        [`apply`](#apply)
        
      

    
      `apply`
##### 
        
        [Signature](#signature-20)
        
      

    
```
apply(self: _duckdb.DuckDBPyRelation, function_name: str, function_aggr: str, group_expr: str = '', function_parameter: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-29)
        
      

    
Compute the function of a single column or a list of columns by the optional groups on the relation

##### 
        
        [Parameters](#parameters-17)
        
      

    
- 
    **function_name** : strName of the function to apply over the relation.
- 
    **function_aggr** : strThe list of columns to apply the function over.
- 
    **group_expr** : str, default: ''Optional SQL expression for grouping.
- 
    **function_parameter** : str, default: ''Optional parameters to pass into the function.
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-28)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.apply(
    function_name="count", 
    function_aggr="id", 
    group_expr="description",
    projected_columns="description"
)
```
##### 
        
        [Result](#result-28)
        
      

    
```
┌─────────────────┬───────────┐
│   description   │ count(id) │
│     varchar     │   int64   │
├─────────────────┼───────────┤
│ value is uneven │         5 │
│ value is even   │         4 │
└─────────────────┴───────────┘
```
#### 
        
        [`cross`](#cross)
        
      

    
      `cross`
##### 
        
        [Signature](#signature-21)
        
      

    
```
cross(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-30)
        
      

    
Create cross/cartesian product of two relational objects

##### 
        
        [Parameters](#parameters-18)
        
      

    
- 
    **other_rel** : _duckdb.DuckDBPyRelationAnother relation to perform a cross product with.

##### 
        
        [Example](#example-29)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.cross(other_rel=rel.set_alias("other_rel"))
```
##### 
        
        [Result](#result-29)
        
      

    
```
┌─────────────────────────────┬─────────────────┬───────┬───────────────────────────┬──────────────────────────────────────┬─────────────────┬───────┬───────────────────────────┐
│             id              │   description   │ value │     created_timestamp     │                  id                  │   description   │ value │     created_timestamp     │
│            uuid             │     varchar     │ int64 │ timestamp with time zone  │                 uuid                 │     varchar     │ int64 │ timestamp with time zone  │
├─────────────────────────────┼─────────────────┼───────┼───────────────────────────┼──────────────────────────────────────┼─────────────────┼───────┼───────────────────────────┤
│ cb2b453f-1a06-4f5e-abe1-b…  │ value is uneven │     1 │ 2025-04-10 09:53:29.78+02 │ cb2b453f-1a06-4f5e-abe1-bfd413581bcf │ value is uneven │     1 │ 2025-04-10 09:53:29.78+02 │
...
```
#### 
        
        [`except_`](#except_)
        
      

    
      `except_`
##### 
        
        [Signature](#signature-22)
        
      

    
```
except_(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-31)
        
      

    
Create the set except of this relation object with another relation object in other_rel

##### 
        
        [Parameters](#parameters-19)
        
      

    
- 
    **other_rel** : _duckdb.DuckDBPyRelationThe relation to subtract from the current relation (set difference).

##### 
        
        [Example](#example-30)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.except_(other_rel=rel.set_alias("other_rel"))
```
##### 
        
        [Result](#result-30)
        
      

    
```
The relation query is executed twice, therefore generating different ids and timestamps:
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ f69ed6dd-a7fe-4de2-b6af-1c2418096d69 │ value is uneven │     3 │ 2025-04-10 11:43:05.711+02 │
│ 08ad11dc-a9c2-4aaa-9272-760b27ad1f5d │ value is uneven │     7 │ 2025-04-10 11:47:05.711+02 │
...
```
#### 
        
        [`filter`](#filter)
        
      

    
      `filter`
##### 
        
        [Signature](#signature-23)
        
      

    
```
filter(self: _duckdb.DuckDBPyRelation, filter_expr: object) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-32)
        
      

    
Filter the relation object by the filter in filter_expr

##### 
        
        [Parameters](#parameters-20)
        
      

    
- 
    **filter_expr** : str, ExpressionThe filter expression to apply over the relation.

##### 
        
        [Example](#example-31)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.filter("value = 2")
```
##### 
        
        [Result](#result-31)
        
      

    
```
┌──────────────────────────────────────┬───────────────┬───────┬───────────────────────────┐
│                  id                  │  description  │ value │     created_timestamp     │
│                 uuid                 │    varchar    │ int64 │ timestamp with time zone  │
├──────────────────────────────────────┼───────────────┼───────┼───────────────────────────┤
│ b0684ab7-fcbf-41c5-8e4a-a51bdde86926 │ value is even │     2 │ 2025-04-10 09:54:29.78+02 │
└──────────────────────────────────────┴───────────────┴───────┴───────────────────────────┘
```
#### 
        
        [`insert`](#insert)
        
      

    
      `insert`
##### 
        
        [Signature](#signature-24)
        
      

    
```
insert(self: _duckdb.DuckDBPyRelation, values: object) -> None
```
##### 
        
        [Description](#description-33)
        
      

    
Inserts the given values into the relation

##### 
        
        [Parameters](#parameters-21)
        
      

    
- 
    **values** : objectA tuple of values matching the relation column list, to be inserted.

##### 
        
        [Example](#example-32)
        
      

    
```
import duckdb
from datetime import datetime
from uuid import uuid4
duckdb_conn = duckdb.connect()
duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
).to_table("code_example")
rel = duckdb_conn.table("code_example")
rel.insert(
    (
        uuid4(), 
        'value is even',
        10, 
        datetime.now()
    )
)
rel.filter("value = 10")
```
##### 
        
        [Result](#result-32)
        
      

    
```
┌──────────────────────────────────────┬───────────────┬───────┬───────────────────────────────┐
│                  id                  │  description  │ value │       created_timestamp       │
│                 uuid                 │    varchar    │ int64 │   timestamp with time zone    │
├──────────────────────────────────────┼───────────────┼───────┼───────────────────────────────┤
│ c6dfab87-fae6-4213-8f76-1b96a8d179f6 │ value is even │    10 │ 2025-04-10 10:02:24.652218+02 │
└──────────────────────────────────────┴───────────────┴───────┴───────────────────────────────┘
```
#### 
        
        [`insert_into`](#insert_into)
        
      

    
      `insert_into`
##### 
        
        [Signature](#signature-25)
        
      

    
```
insert_into(self: _duckdb.DuckDBPyRelation, table_name: str) -> None
```
##### 
        
        [Description](#description-34)
        
      

    
Inserts the relation object into an existing table named table_name

##### 
        
        [Parameters](#parameters-22)
        
      

    
- 
    **table_name** : strThe table name to insert the data into. The relation must respect the column order of the table.

##### 
        
        [Example](#example-33)
        
      

    
```
import duckdb
from datetime import datetime
from uuid import uuid4
duckdb_conn = duckdb.connect()
duckdb_conn.sql("""
        select
            gen_random_uuid() as id,
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value,
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
).to_table("code_example")
rel = duckdb_conn.values(
    [
        uuid4(),
        'value is even',
        10,
        datetime.now()
    ]
)
rel.insert_into("code_example")
duckdb_conn.table("code_example").filter("value = 10")
```
##### 
        
        [Result](#result-33)
        
      

    
```
┌──────────────────────────────────────┬───────────────┬───────┬───────────────────────────────┐
│                  id                  │  description  │ value │       created_timestamp       │
│                 uuid                 │    varchar    │ int64 │   timestamp with time zone    │
├──────────────────────────────────────┼───────────────┼───────┼───────────────────────────────┤
│ 271c5ddd-c1d5-4638-b5a0-d8c7dc9e8220 │ value is even │    10 │ 2025-04-10 14:29:18.616379+02 │
└──────────────────────────────────────┴───────────────┴───────┴───────────────────────────────┘
```
#### 
        
        [`intersect`](#intersect)
        
      

    
      `intersect`
##### 
        
        [Signature](#signature-26)
        
      

    
```
intersect(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-35)
        
      

    
Create the set intersection of this relation object with another relation object in other_rel

##### 
        
        [Parameters](#parameters-23)
        
      

    
- 
    **other_rel** : _duckdb.DuckDBPyRelationThe relation to intersect with the current relation (set intersection).

##### 
        
        [Example](#example-34)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.intersect(other_rel=rel.set_alias("other_rel"))
```
##### 
        
        [Result](#result-34)
        
      

    
```
The relation query is executed once with `rel` and once with `other_rel`,
therefore generating different ids and timestamps:
┌──────┬─────────────┬───────┬──────────────────────────┐
│  id  │ description │ value │    created_timestamp     │
│ uuid │   varchar   │ int64 │ timestamp with time zone │
├──────┴─────────────┴───────┴──────────────────────────┤
│                        0 rows                         │
└───────────────────────────────────────────────────────┘
```
#### 
        
        [`join`](#join)
        
      

    
      `join`
##### 
        
        [Signature](#signature-27)
        
      

    
```
join(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation, condition: object, how: str = 'inner') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-36)
        
      

    
Join the relation object with another relation object in other_rel using the join condition expression in join_condition. Types supported are 'inner', 'left', 'right', 'outer', 'semi' and 'anti'

Depending on how the `condition` parameter is provided, the JOIN clause generated is:

- `USING`

```
import duckdb
duckdb_conn = duckdb.connect()
rel1 = duckdb_conn.sql("select range as id, concat('dummy 1', range) as text from range(1,10)")
rel2 = duckdb_conn.sql("select range as id, concat('dummy 2', range) as text from range(5,7)")
rel1.join(rel2, condition="id", how="inner").sql_query()
```
with following SQL:

```
SELECT * 
FROM (
        SELECT "range" AS id, 
            concat('dummy 1', "range") AS "text" 
        FROM "range"(1, 10)
    ) AS unnamed_relation_41bc15e744037078 
INNER JOIN (
        SELECT "range" AS id, 
        concat('dummy 2', "range") AS "text" 
        FROM "range"(5, 7)
    ) AS unnamed_relation_307e245965aa2c2b 
USING (id)
```
- `ON`

```
import duckdb
duckdb_conn = duckdb.connect()
rel1 = duckdb_conn.sql("select range as id, concat('dummy 1', range) as text from range(1,10)")
rel2 = duckdb_conn.sql("select range as id, concat('dummy 2', range) as text from range(5,7)")
rel1.join(rel2, condition=f"{rel1.alias}.id = {rel2.alias}.id", how="inner").sql_query()
```
with the following SQL:

```
SELECT * 
FROM (
        SELECT "range" AS id, 
            concat('dummy 1', "range") AS "text" 
        FROM "range"(1, 10)
    ) AS unnamed_relation_41bc15e744037078 
INNER JOIN (
        SELECT "range" AS id, 
        concat('dummy 2', "range") AS "text" 
        FROM "range"(5, 7)
    ) AS unnamed_relation_307e245965aa2c2b 
ON ((unnamed_relation_41bc15e744037078.id = unnamed_relation_307e245965aa2c2b.id))
```
  `NATURAL`, `POSITIONAL` and `ASOF` joins are not provided by the relational API.
`CROSS` joins are provided through the [cross method](#cross).

##### 
        
        [Parameters](#parameters-24)
        
      

    
- 
    **other_rel** : _duckdb.DuckDBPyRelationThe relation to join with the current relation.
- 
    **condition** : objectThe join condition, typically a SQL expression or the duplicated column name to join on.
- 
    **how** : str, default: 'inner'The type of join to perform: 'inner', 'left', 'right', 'outer', 'semi' and 'anti'.

##### 
        
        [Example](#example-35)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.set_alias("rel").join(
    other_rel=rel.set_alias("other_rel"), 
    condition="rel.id = other_rel.id",
    how="left"
)
rel.count("*")
```
##### 
        
        [Result](#result-35)
        
      

    
```
┌──────────────┐
│ count_star() │
│    int64     │
├──────────────┤
│            9 │
└──────────────┘
```
#### 
        
        [`limit`](#limit)
        
      

    
      `limit`
##### 
        
        [Signature](#signature-28)
        
      

    
```
limit(self: _duckdb.DuckDBPyRelation, n: typing.SupportsInt, offset: typing.SupportsInt = 0) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-37)
        
      

    
Only retrieve the first n rows from this relation object, starting at offset

##### 
        
        [Parameters](#parameters-25)
        
      

    
- 
    **n** : intThe maximum number of rows to return.
- 
    **offset** : int, default: 0The number of rows to skip before starting to return rows.

##### 
        
        [Example](#example-36)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.limit(1)
```
##### 
        
        [Result](#result-36)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 4135597b-29e7-4cb9-a443-41f3d54f25df │ value is uneven │     1 │ 2025-04-10 10:52:03.678+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        [`map`](#map)
        
      

    
      `map`
##### 
        
        [Signature](#signature-29)
        
      

    
```
map(self: _duckdb.DuckDBPyRelation, map_function: collections.abc.Callable, *, schema: typing.Optional[object] = None) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-38)
        
      

    
Calls the passed function on the relation

##### 
        
        [Parameters](#parameters-26)
        
      

    
- 
    **map_function** : CallableA Python function that takes a DataFrame and returns a transformed DataFrame.
- 
    **schema** : object, default: NoneOptional schema describing the structure of the output relation.

##### 
        
        [Example](#example-37)
        
      

    
```
import duckdb
from pandas import DataFrame
def multiply_by_2(df: DataFrame):
    df["id"] = df["id"] * 2
    return df
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("select range as id, 'dummy' as text from range(1,3)")
rel.map(multiply_by_2, schema={"id": int, "text": str})
```
##### 
        
        [Result](#result-37)
        
      

    
```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     2 │ dummy   │
│     4 │ dummy   │
└───────┴─────────┘
```
#### 
        
        [`order`](#order)
        
      

    
      `order`
##### 
        
        [Signature](#signature-30)
        
      

    
```
order(self: _duckdb.DuckDBPyRelation, order_expr: str) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-39)
        
      

    
Reorder the relation object by order_expr

##### 
        
        [Parameters](#parameters-27)
        
      

    
- 
    **order_expr** : strSQL expression defining the ordering of the result rows.

##### 
        
        [Example](#example-38)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.order("value desc").limit(1, offset=4)
```
##### 
        
        [Result](#result-38)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 55899131-e3d3-463c-a215-f65cb8aef3bf │ value is uneven │     5 │ 2025-04-10 10:56:03.678+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        [`project`](#project)
        
      

    
      `project`
##### 
        
        [Signature](#signature-31)
        
      

    
```
project(self: _duckdb.DuckDBPyRelation, *args, groups: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-40)
        
      

    
Project the relation object by the projection in project_expr

**Aliases**: `select`

##### 
        
        [Parameters](#parameters-28)
        
      

    
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .

##### 
        
        [Example](#example-39)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.project("description").limit(1)
```
##### 
        
        [Result](#result-39)
        
      

    
```
┌─────────────────┐
│   description   │
│     varchar     │
├─────────────────┤
│ value is uneven │
└─────────────────┘
```
#### 
        
        [`select`](#select)
        
      

    
      `select`
##### 
        
        [Signature](#signature-32)
        
      

    
```
select(self: _duckdb.DuckDBPyRelation, *args, groups: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-41)
        
      

    
Project the relation object by the projection in project_expr

**Aliases**: `project`

##### 
        
        [Parameters](#parameters-29)
        
      

    
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .

##### 
        
        [Example](#example-40)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.select("description").limit(1)
```
##### 
        
        [Result](#result-40)
        
      

    
```
┌─────────────────┐
│   description   │
│     varchar     │
├─────────────────┤
│ value is uneven │
└─────────────────┘
```
#### 
        
        [`sort`](#sort)
        
      

    
      `sort`
##### 
        
        [Signature](#signature-33)
        
      

    
```
sort(self: _duckdb.DuckDBPyRelation, *args) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-42)
        
      

    
Reorder the relation object by the provided expressions

##### 
        
        [Example](#example-41)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.sort("description")
```
##### 
        
        [Result](#result-41)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 5e0dfa8c-de4d-4ccd-8cff-450dabb86bde │ value is even   │     6 │ 2025-04-10 16:52:15.605+02 │
│ 95f1ad48-facf-4a84-a971-0a4fecce68c7 │ value is even   │     2 │ 2025-04-10 16:48:15.605+02 │
...
```
#### 
        
        [`union`](#union)
        
      

    
      `union`
##### 
        
        [Signature](#signature-34)
        
      

    
```
union(self: _duckdb.DuckDBPyRelation, union_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-43)
        
      

    
Create the set union of this relation object with another relation object in other_rel

  The union is `union all`. In order to retrieve distinct values, apply [distinct](#distinct).

##### 
        
        [Parameters](#parameters-30)
        
      

    
- 
    **union_rel** : _duckdb.DuckDBPyRelationThe relation to union with the current relation (set union).

##### 
        
        [Example](#example-42)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.union(union_rel=rel)
rel.count("*")
```
##### 
        
        [Result](#result-42)
        
      

    
```
┌──────────────┐
│ count_star() │
│    int64     │
├──────────────┤
│           18 │
└──────────────┘
```
#### 
        
        [`update`](#update)
        
      

    
      `update`
##### 
        
        [Signature](#signature-35)
        
      

    
```
update(self: _duckdb.DuckDBPyRelation, set: object, *, condition: object = None) -> None
```
##### 
        
        [Description](#description-44)
        
      

    
Update the given relation with the provided expressions

##### 
        
        [Parameters](#parameters-31)
        
      

    
- 
    **set** : objectMapping of columns to new values for the update operation.
- 
    **condition** : object, default: NoneOptional condition to filter which rows to update.

##### 
        
        [Example](#example-43)
        
      

    
```
import duckdb
from duckdb import ColumnExpression
duckdb_conn = duckdb.connect()
duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
).to_table("code_example")
rel = duckdb_conn.table("code_example")
rel.update(set={"description":None}, condition=ColumnExpression("value") == 1)
# the update is executed on the table, but not reflected on the relationship
# the relationship has to be recreated to retrieve the modified data
rel = duckdb_conn.table("code_example")
rel.show()
```
##### 
        
        [Result](#result-43)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 66dcaa14-f4a6-4a55-af3b-7f6aa23ab4ad │ NULL            │     1 │ 2025-04-10 16:54:49.317+02 │
│ c6a18a42-67fb-4c95-827b-c966f2f95b88 │ value is even   │     2 │ 2025-04-10 16:55:49.317+02 │
...
```
## 
        
        [Functions](#functions)
        
      

    
This section contains the functions which can be applied to a relation,         in order to get a (scalar) result. The functions are [lazy evaluated](#lazy-evaluation).

| Name | Description | 
|---|---|
| [`any_value`](#any_value) | Returns the first non-null value from a given expression | 
| [`arg_max`](#arg_max) | Finds the row with the maximum value for a value column and returns the value of that row for an argument column | 
| [`arg_min`](#arg_min) | Finds the row with the minimum value for a value column and returns the value of that row for an argument column | 
| [`avg`](#avg) | Computes the average of a given expression | 
| [`bit_and`](#bit_and) | Computes the bitwise AND of all bits present in a given expression | 
| [`bit_or`](#bit_or) | Computes the bitwise OR of all bits present in a given expression | 
| [`bit_xor`](#bit_xor) | Computes the bitwise XOR of all bits present in a given expression | 
| [`bitstring_agg`](#bitstring_agg) | Computes a bitstring with bits set for each distinct value in a given expression | 
| [`bool_and`](#bool_and) | Computes the logical AND of all values present in a given expression | 
| [`bool_or`](#bool_or) | Computes the logical OR of all values present in a given expression | 
| [`count`](#count) | Computes the number of elements present in a given expression | 
| [`cume_dist`](#cume_dist) | Computes the cumulative distribution within the partition | 
| [`dense_rank`](#dense_rank) | Computes the dense rank within the partition | 
| [`distinct`](#distinct) | Retrieve distinct rows from this relation object | 
| [`favg`](#favg) | Computes the average of all values present in a given expression using a more accurate floating point summation (Kahan Sum) | 
| [`first`](#first) | Returns the first value of a given expression | 
| [`first_value`](#first_value) | Computes the first value within the group or partition | 
| [`fsum`](#fsum) | Computes the sum of all values present in a given expression using a more accurate floating point summation (Kahan Sum) | 
| [`geomean`](#geomean) | Computes the geometric mean over all values present in a given expression | 
| [`histogram`](#histogram) | Computes the histogram over all values present in a given expression | 
| [`lag`](#lag) | Computes the lag within the partition | 
| [`last`](#last) | Returns the last value of a given expression | 
| [`last_value`](#last_value) | Computes the last value within the group or partition | 
| [`lead`](#lead) | Computes the lead within the partition | 
| [`list`](#list) | Returns a list containing all values present in a given expression | 
| [`max`](#max) | Returns the maximum value present in a given expression | 
| [`mean`](#mean) | Computes the average of a given expression | 
| [`median`](#median) | Computes the median over all values present in a given expression | 
| [`min`](#min) | Returns the minimum value present in a given expression | 
| [`mode`](#mode) | Computes the mode over all values present in a given expression | 
| [`n_tile`](#n_tile) | Divides the partition as equally as possible into num_buckets | 
| [`nth_value`](#nth_value) | Computes the nth value within the partition | 
| [`percent_rank`](#percent_rank) | Computes the relative rank within the partition | 
| [`product`](#product) | Returns the product of all values present in a given expression | 
| [`quantile`](#quantile) | Computes the exact quantile value for a given expression | 
| [`quantile_cont`](#quantile_cont) | Computes the interpolated quantile value for a given expression | 
| [`quantile_disc`](#quantile_disc) | Computes the exact quantile value for a given expression | 
| [`rank`](#rank) | Computes the rank within the partition | 
| [`rank_dense`](#rank_dense) | Computes the dense rank within the partition | 
| [`row_number`](#row_number) | Computes the row number within the partition | 
| [`select_dtypes`](#select_dtypes) | Select columns from the relation, by filtering based on type(s) | 
| [`select_types`](#select_types) | Select columns from the relation, by filtering based on type(s) | 
| [`std`](#std) | Computes the sample standard deviation for a given expression | 
| [`stddev`](#stddev) | Computes the sample standard deviation for a given expression | 
| [`stddev_pop`](#stddev_pop) | Computes the population standard deviation for a given expression | 
| [`stddev_samp`](#stddev_samp) | Computes the sample standard deviation for a given expression | 
| [`string_agg`](#string_agg) | Concatenates the values present in a given expression with a separator | 
| [`sum`](#sum) | Computes the sum of all values present in a given expression | 
| [`unique`](#unique) | Returns the distinct values in a column. | 
| [`value_counts`](#value_counts) | Computes the number of elements present in a given expression, also projecting the original expression | 
| [`var`](#var) | Computes the sample variance for a given expression | 
| [`var_pop`](#var_pop) | Computes the population variance for a given expression | 
| [`var_samp`](#var_samp) | Computes the sample variance for a given expression | 
| [`variance`](#variance) | Computes the sample variance for a given expression | 

#### 
        
        [`any_value`](#any_value)
        
      

    
      `any_value`
##### 
        
        [Signature](#signature-36)
        
      

    
```
any_value(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-45)
        
      

    
Returns the first non-null value from a given expression

##### 
        
        [Parameters](#parameters-32)
        
      

    
- 
    **column** : strThe column name from which to retrieve any value.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)` .
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-44)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.any_value('id')
```
##### 
        
        [Result](#result-44)
        
      

    
```
┌──────────────────────────────────────┐
│            any_value(id)             │
│                 uuid                 │
├──────────────────────────────────────┤
│ 642ea3d7-793d-4867-a759-91c1226c25a0 │
└──────────────────────────────────────┘
```
#### 
        
        [`arg_max`](#arg_max)
        
      

    
      `arg_max`
##### 
        
        [Signature](#signature-37)
        
      

    
```
arg_max(self: _duckdb.DuckDBPyRelation, arg_column: str, value_column: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-46)
        
      

    
Finds the row with the maximum value for a value column and returns the value of that row for an argument column

##### 
        
        [Parameters](#parameters-33)
        
      

    
- 
    **arg_column** : strThe column name for which to find the argument maximizing the value.
- 
    **value_column** : strThe column name containing values used to determine the maximum.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)` .
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-45)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.arg_max(arg_column="value", value_column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-45)
        
      

    
```
┌─────────────────┬───────────────────────────┐
│   description   │ arg_max("value", "value") │
│     varchar     │           int64           │
├─────────────────┼───────────────────────────┤
│ value is uneven │                         9 │
│ value is even   │                         8 │
└─────────────────┴───────────────────────────┘
```
#### 
        
        [`arg_min`](#arg_min)
        
      

    
      `arg_min`
##### 
        
        [Signature](#signature-38)
        
      

    
```
arg_min(self: _duckdb.DuckDBPyRelation, arg_column: str, value_column: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-47)
        
      

    
Finds the row with the minimum value for a value column and returns the value of that row for an argument column

##### 
        
        [Parameters](#parameters-34)
        
      

    
- 
    **arg_column** : strThe column name for which to find the argument minimizing the value.
- 
    **value_column** : strThe column name containing values used to determine the minimum.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-46)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.arg_min(arg_column="value", value_column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-46)
        
      

    
```
┌─────────────────┬───────────────────────────┐
│   description   │ arg_min("value", "value") │
│     varchar     │           int64           │
├─────────────────┼───────────────────────────┤
│ value is even   │                         2 │
│ value is uneven │                         1 │
└─────────────────┴───────────────────────────┘
```
#### 
        
        [`avg`](#avg)
        
      

    
      `avg`
##### 
        
        [Signature](#signature-39)
        
      

    
```
avg(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-48)
        
      

    
Computes the average of a given expression

##### 
        
        [Parameters](#parameters-35)
        
      

    
- 
    **column** : strThe column name to calculate the average on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-47)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.avg('value')
```
##### 
        
        [Result](#result-47)
        
      

    
```
┌──────────────┐
│ avg("value") │
│    double    │
├──────────────┤
│          5.0 │
└──────────────┘
 
```
#### 
        
        [`bit_and`](#bit_and)
        
      

    
      `bit_and`
##### 
        
        [Signature](#signature-40)
        
      

    
```
bit_and(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-49)
        
      

    
Computes the bitwise AND of all bits present in a given expression

##### 
        
        [Parameters](#parameters-36)
        
      

    
- 
    **column** : strThe column name to perform the bitwise AND aggregation on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-48)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.select("description, value::bit as value_bit")
rel.bit_and(column="value_bit", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-48)
        
      

    
```
┌─────────────────┬──────────────────────────────────────────────────────────────────┐
│   description   │                        bit_and(value_bit)                        │
│     varchar     │                               bit                                │
├─────────────────┼──────────────────────────────────────────────────────────────────┤
│ value is uneven │ 0000000000000000000000000000000000000000000000000000000000000001 │
│ value is even   │ 0000000000000000000000000000000000000000000000000000000000000000 │
└─────────────────┴──────────────────────────────────────────────────────────────────┘    
```
#### 
        
        [`bit_or`](#bit_or)
        
      

    
      `bit_or`
##### 
        
        [Signature](#signature-41)
        
      

    
```
bit_or(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-50)
        
      

    
Computes the bitwise OR of all bits present in a given expression

##### 
        
        [Parameters](#parameters-37)
        
      

    
- 
    **column** : strThe column name to perform the bitwise OR aggregation on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-49)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.select("description, value::bit as value_bit")
rel.bit_or(column="value_bit", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-49)
        
      

    
```
┌─────────────────┬──────────────────────────────────────────────────────────────────┐
│   description   │                        bit_or(value_bit)                         │
│     varchar     │                               bit                                │
├─────────────────┼──────────────────────────────────────────────────────────────────┤
│ value is uneven │ 0000000000000000000000000000000000000000000000000000000000001111 │
│ value is even   │ 0000000000000000000000000000000000000000000000000000000000001110 │
└─────────────────┴──────────────────────────────────────────────────────────────────┘    
```
#### 
        
        [`bit_xor`](#bit_xor)
        
      

    
      `bit_xor`
##### 
        
        [Signature](#signature-42)
        
      

    
```
bit_xor(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-51)
        
      

    
Computes the bitwise XOR of all bits present in a given expression

##### 
        
        [Parameters](#parameters-38)
        
      

    
- 
    **column** : strThe column name to perform the bitwise XOR aggregation on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-50)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.select("description, value::bit as value_bit")
rel.bit_xor(column="value_bit", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-50)
        
      

    
```
┌─────────────────┬──────────────────────────────────────────────────────────────────┐
│   description   │                        bit_xor(value_bit)                        │
│     varchar     │                               bit                                │
├─────────────────┼──────────────────────────────────────────────────────────────────┤
│ value is even   │ 0000000000000000000000000000000000000000000000000000000000001000 │
│ value is uneven │ 0000000000000000000000000000000000000000000000000000000000001001 │
└─────────────────┴──────────────────────────────────────────────────────────────────┘
```
#### 
        
        [`bitstring_agg`](#bitstring_agg)
        
      

    
      `bitstring_agg`
##### 
        
        [Signature](#signature-43)
        
      

    
```
bitstring_agg(self: _duckdb.DuckDBPyRelation, expression: str, min: typing.Optional[object] = None, max: typing.Optional[object] = None, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-52)
        
      

    
Computes a bitstring with bits set for each distinct value in a given expression

##### 
        
        [Parameters](#parameters-39)
        
      

    
- 
    **column** : strThe column name to aggregate as a bitstring.
- 
    **min** : object, default: NoneOptional minimum bitstring value for aggregation.
- 
    **max** : object, default: NoneOptional maximum bitstring value for aggregation.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-51)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.bitstring_agg(column="value", groups="description", projected_columns="description", min=1, max=9)
```
##### 
        
        [Result](#result-51)
        
      

    
```
┌─────────────────┬────────────────────────┐
│   description   │ bitstring_agg("value") │
│     varchar     │          bit           │
├─────────────────┼────────────────────────┤
│ value is uneven │ 101010101              │
│ value is even   │ 010101010              │
└─────────────────┴────────────────────────┘
```
#### 
        
        [`bool_and`](#bool_and)
        
      

    
      `bool_and`
##### 
        
        [Signature](#signature-44)
        
      

    
```
bool_and(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-53)
        
      

    
Computes the logical AND of all values present in a given expression

##### 
        
        [Parameters](#parameters-40)
        
      

    
- 
    **column** : strThe column name to perform the boolean AND aggregation on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-52)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.select("description, mod(value,2)::boolean as uneven")
rel.bool_and(column="uneven", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-52)
        
      

    
```
┌─────────────────┬──────────────────┐
│   description   │ bool_and(uneven) │
│     varchar     │     boolean      │
├─────────────────┼──────────────────┤
│ value is even   │ false            │
│ value is uneven │ true             │
└─────────────────┴──────────────────┘
```
#### 
        
        [`bool_or`](#bool_or)
        
      

    
      `bool_or`
##### 
        
        [Signature](#signature-45)
        
      

    
```
bool_or(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-54)
        
      

    
Computes the logical OR of all values present in a given expression

##### 
        
        [Parameters](#parameters-41)
        
      

    
- 
    **column** : strThe column name to perform the boolean OR aggregation on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-53)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel = rel.select("description, mod(value,2)::boolean as uneven")
rel.bool_or(column="uneven", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-53)
        
      

    
```
┌─────────────────┬─────────────────┐
│   description   │ bool_or(uneven) │
│     varchar     │     boolean     │
├─────────────────┼─────────────────┤
│ value is even   │ false           │
│ value is uneven │ true            │
└─────────────────┴─────────────────┘                
```
#### 
        
        [`count`](#count)
        
      

    
      `count`
##### 
        
        [Signature](#signature-46)
        
      

    
```
count(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-55)
        
      

    
Computes the number of elements present in a given expression

##### 
        
        [Parameters](#parameters-42)
        
      

    
- 
    **column** : strThe column name to perform count on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-54)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.count("id")
```
##### 
        
        [Result](#result-54)
        
      

    
```
┌───────────┐
│ count(id) │
│   int64   │
├───────────┤
│         9 │
└───────────┘
```
#### 
        
        [`cume_dist`](#cume_dist)
        
      

    
      `cume_dist`
##### 
        
        [Signature](#signature-47)
        
      

    
```
cume_dist(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-56)
        
      

    
Computes the cumulative distribution within the partition

##### 
        
        [Parameters](#parameters-43)
        
      

    
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-55)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.cume_dist(window_spec="over (partition by description order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-55)
        
      

    
```
┌─────────────────┬───────┬──────────────────────────────────────────────────────────────┐
│   description   │ value │ cume_dist() OVER (PARTITION BY description ORDER BY "value") │
│     varchar     │ int64 │                            double                            │
├─────────────────┼───────┼──────────────────────────────────────────────────────────────┤
│ value is uneven │     1 │                                                          0.2 │
│ value is uneven │     3 │                                                          0.4 │
│ value is uneven │     5 │                                                          0.6 │
│ value is uneven │     7 │                                                          0.8 │
│ value is uneven │     9 │                                                          1.0 │
│ value is even   │     2 │                                                         0.25 │
│ value is even   │     4 │                                                          0.5 │
│ value is even   │     6 │                                                         0.75 │
│ value is even   │     8 │                                                          1.0 │
└─────────────────┴───────┴──────────────────────────────────────────────────────────────┘
```
#### 
        
        [`dense_rank`](#dense_rank)
        
      

    
      `dense_rank`
##### 
        
        [Signature](#signature-48)
        
      

    
```
dense_rank(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-57)
        
      

    
Computes the dense rank within the partition

**Aliases**: `rank_dense`

##### 
        
        [Parameters](#parameters-44)
        
      

    
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-56)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
 rel.dense_rank(window_spec="over (partition by description order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-56)
        
      

    
```
┌─────────────────┬───────┬───────────────────────────────────────────────────────────────┐
│   description   │ value │ dense_rank() OVER (PARTITION BY description ORDER BY "value") │
│     varchar     │ int64 │                             int64                             │
├─────────────────┼───────┼───────────────────────────────────────────────────────────────┤
│ value is even   │     2 │                                                             1 │
│ value is even   │     4 │                                                             2 │
│ value is even   │     6 │                                                             3 │
│ value is even   │     8 │                                                             4 │
│ value is uneven │     1 │                                                             1 │
│ value is uneven │     3 │                                                             2 │
│ value is uneven │     5 │                                                             3 │
│ value is uneven │     7 │                                                             4 │
│ value is uneven │     9 │                                                             5 │
└─────────────────┴───────┴───────────────────────────────────────────────────────────────┘
```
#### 
        
        [`distinct`](#distinct)
        
      

    
      `distinct`
##### 
        
        [Signature](#signature-49)
        
      

    
```
distinct(self: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-58)
        
      

    
Retrieve distinct rows from this relation object

##### 
        
        [Example](#example-57)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("select range from range(1,4)")
rel = rel.union(union_rel=rel)
rel.distinct().order("range")
```
##### 
        
        [Result](#result-57)
        
      

    
```
┌───────┐
│ range │
│ int64 │
├───────┤
│     1 │
│     2 │
│     3 │
└───────┘
```
#### 
        
        [`favg`](#favg)
        
      

    
      `favg`
##### 
        
        [Signature](#signature-50)
        
      

    
```
favg(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-59)
        
      

    
Computes the average of all values present in a given expression using a more accurate floating point summation (Kahan Sum)

##### 
        
        [Parameters](#parameters-45)
        
      

    
- 
    **column** : strThe column name to calculate the average on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-58)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.favg(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-58)
        
      

    
```
┌─────────────────┬───────────────┐
│   description   │ favg("value") │
│     varchar     │    double     │
├─────────────────┼───────────────┤
│ value is uneven │           5.0 │
│ value is even   │           5.0 │
└─────────────────┴───────────────┘
```
#### 
        
        [`first`](#first)
        
      

    
      `first`
##### 
        
        [Signature](#signature-51)
        
      

    
```
first(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-60)
        
      

    
Returns the first value of a given expression

##### 
        
        [Parameters](#parameters-46)
        
      

    
- 
    **column** : strThe column name from which to retrieve the first value.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-59)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.first(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-59)
        
      

    
```
┌─────────────────┬──────────────────┐
│   description   │ "first"("value") │
│     varchar     │      int64       │
├─────────────────┼──────────────────┤
│ value is even   │                2 │
│ value is uneven │                1 │
└─────────────────┴──────────────────┘
```
#### 
        
        [`first_value`](#first_value)
        
      

    
      `first_value`
##### 
        
        [Signature](#signature-52)
        
      

    
```
first_value(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-61)
        
      

    
Computes the first value within the group or partition

##### 
        
        [Parameters](#parameters-47)
        
      

    
- 
    **column** : strThe column name from which to retrieve the first value.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-60)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.first_value(column="value", window_spec="over (partition by description order by value)", projected_columns="description").distinct()
```
##### 
        
        [Result](#result-60)
        
      

    
```
┌─────────────────┬───────────────────────────────────────────────────────────────────────┐
│   description   │ first_value("value") OVER (PARTITION BY description ORDER BY "value") │
│     varchar     │                                 int64                                 │
├─────────────────┼───────────────────────────────────────────────────────────────────────┤
│ value is even   │                                                                     2 │
│ value is uneven │                                                                     1 │
└─────────────────┴───────────────────────────────────────────────────────────────────────┘
```
#### 
        
        [`fsum`](#fsum)
        
      

    
      `fsum`
##### 
        
        [Signature](#signature-53)
        
      

    
```
fsum(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-62)
        
      

    
Computes the sum of all values present in a given expression using a more accurate floating point summation (Kahan Sum)

##### 
        
        [Parameters](#parameters-48)
        
      

    
- 
    **column** : strThe column name to calculate the sum on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-61)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.fsum(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-61)
        
      

    
```
┌─────────────────┬───────────────┐
│   description   │ fsum("value") │
│     varchar     │    double     │
├─────────────────┼───────────────┤
│ value is even   │          20.0 │
│ value is uneven │          25.0 │
└─────────────────┴───────────────┘
```
#### 
        
        [`geomean`](#geomean)
        
      

    
      `geomean`
##### 
        
        [Signature](#signature-54)
        
      

    
```
geomean(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-63)
        
      

    
Computes the geometric mean over all values present in a given expression

##### 
        
        [Parameters](#parameters-49)
        
      

    
- 
    **column** : strThe column name to calculate the geometric mean on.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-62)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.geomean(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-62)
        
      

    
```
┌─────────────────┬───────────────────┐
│   description   │ geomean("value")  │
│     varchar     │      double       │
├─────────────────┼───────────────────┤
│ value is uneven │ 3.936283427035351 │
│ value is even   │ 4.426727678801287 │
└─────────────────┴───────────────────┘
```
#### 
        
        [`histogram`](#histogram)
        
      

    
      `histogram`
##### 
        
        [Signature](#signature-55)
        
      

    
```
histogram(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-64)
        
      

    
Computes the histogram over all values present in a given expression

##### 
        
        [Parameters](#parameters-50)
        
      

    
- 
    **column** : strThe column name to calculate the histogram on.
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-63)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.histogram(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-63)
        
      

    
```
┌─────────────────┬───────────────────────────┐
│   description   │    histogram("value")     │
│     varchar     │   map(bigint, ubigint)    │
├─────────────────┼───────────────────────────┤
│ value is uneven │ {1=1, 3=1, 5=1, 7=1, 9=1} │
│ value is even   │ {2=1, 4=1, 6=1, 8=1}      │
└─────────────────┴───────────────────────────┘
```
#### 
        
        [`lag`](#lag)
        
      

    
      `lag`
##### 
        
        [Signature](#signature-56)
        
      

    
```
lag(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str, offset: typing.SupportsInt = 1, default_value: str = 'NULL', ignore_nulls: bool = False, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-65)
        
      

    
Computes the lag within the partition

##### 
        
        [Parameters](#parameters-51)
        
      

    
- 
    **column** : strThe column name to apply the lag function on.
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **offset** : int, default: 1The number of rows to lag behind.
- 
    **default_value** : str, default: 'NULL'The default value to return when the lag offset goes out of bounds.
- 
    **ignore_nulls** : bool, default: FalseWhether to ignore NULL values when computing the lag.
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-64)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.lag(column="description", window_spec="over (order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-64)
        
      

    
```
┌─────────────────┬───────┬───────────────────────────────────────────────────┐
│   description   │ value │ lag(description, 1, NULL) OVER (ORDER BY "value") │
│     varchar     │ int64 │                      varchar                      │
├─────────────────┼───────┼───────────────────────────────────────────────────┤
│ value is uneven │     1 │ NULL                                              │
│ value is even   │     2 │ value is uneven                                   │
│ value is uneven │     3 │ value is even                                     │
│ value is even   │     4 │ value is uneven                                   │
│ value is uneven │     5 │ value is even                                     │
│ value is even   │     6 │ value is uneven                                   │
│ value is uneven │     7 │ value is even                                     │
│ value is even   │     8 │ value is uneven                                   │
│ value is uneven │     9 │ value is even                                     │
└─────────────────┴───────┴───────────────────────────────────────────────────┘
```
#### 
        
        [`last`](#last)
        
      

    
      `last`
##### 
        
        [Signature](#signature-57)
        
      

    
```
last(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-66)
        
      

    
Returns the last value of a given expression

##### 
        
        [Parameters](#parameters-52)
        
      

    
- 
    **column** : strThe column name from which to retrieve the last value.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-65)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.last(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-65)
        
      

    
```
┌─────────────────┬─────────────────┐
│   description   │ "last"("value") │
│     varchar     │      int64      │
├─────────────────┼─────────────────┤
│ value is even   │               8 │
│ value is uneven │               9 │
└─────────────────┴─────────────────┘
```
#### 
        
        [`last_value`](#last_value)
        
      

    
      `last_value`
##### 
        
        [Signature](#signature-58)
        
      

    
```
last_value(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-67)
        
      

    
Computes the last value within the group or partition

##### 
        
        [Parameters](#parameters-53)
        
      

    
- 
    **column** : strThe column name from which to retrieve the last value within the window.
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-66)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.last_value(column="value", window_spec="over (order by description)", projected_columns="description").distinct()
```
##### 
        
        [Result](#result-66)
        
      

    
```
┌─────────────────┬─────────────────────────────────────────────────┐
│   description   │ last_value("value") OVER (ORDER BY description) │
│     varchar     │                      int64                      │
├─────────────────┼─────────────────────────────────────────────────┤
│ value is uneven │                                               9 │
│ value is even   │                                               8 │
└─────────────────┴─────────────────────────────────────────────────┘
```
#### 
        
        [`lead`](#lead)
        
      

    
      `lead`
##### 
        
        [Signature](#signature-59)
        
      

    
```
lead(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str, offset: typing.SupportsInt = 1, default_value: str = 'NULL', ignore_nulls: bool = False, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-68)
        
      

    
Computes the lead within the partition

##### 
        
        [Parameters](#parameters-54)
        
      

    
- 
    **column** : strThe column name to apply the lead function on.
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **offset** : int, default: 1The number of rows to lead ahead.
- 
    **default_value** : str, default: 'NULL'The default value to return when the lead offset goes out of bounds.
- 
    **ignore_nulls** : bool, default: FalseWhether to ignore NULL values when computing the lead.
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-67)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.lead(column="description", window_spec="over (order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-67)
        
      

    
```
┌─────────────────┬───────┬────────────────────────────────────────────────────┐
│   description   │ value │ lead(description, 1, NULL) OVER (ORDER BY "value") │
│     varchar     │ int64 │                      varchar                       │
├─────────────────┼───────┼────────────────────────────────────────────────────┤
│ value is uneven │     1 │ value is even                                      │
│ value is even   │     2 │ value is uneven                                    │
│ value is uneven │     3 │ value is even                                      │
│ value is even   │     4 │ value is uneven                                    │
│ value is uneven │     5 │ value is even                                      │
│ value is even   │     6 │ value is uneven                                    │
│ value is uneven │     7 │ value is even                                      │
│ value is even   │     8 │ value is uneven                                    │
│ value is uneven │     9 │ NULL                                               │
└─────────────────┴───────┴────────────────────────────────────────────────────┘
```
#### 
        
        [`list`](#list)
        
      

    
      `list`
##### 
        
        [Signature](#signature-60)
        
      

    
```
list(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-69)
        
      

    
Returns a list containing all values present in a given expression

##### 
        
        [Parameters](#parameters-55)
        
      

    
- 
    **column** : strThe column name to aggregate values into a list.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-68)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.list(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-68)
        
      

    
```
┌─────────────────┬─────────────────┐
│   description   │  list("value")  │
│     varchar     │     int64[]     │
├─────────────────┼─────────────────┤
│ value is even   │ [2, 4, 6, 8]    │
│ value is uneven │ [1, 3, 5, 7, 9] │
└─────────────────┴─────────────────┘
```
#### 
        
        [`max`](#max)
        
      

    
      `max`
##### 
        
        [Signature](#signature-61)
        
      

    
```
max(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-70)
        
      

    
Returns the maximum value present in a given expression

##### 
        
        [Parameters](#parameters-56)
        
      

    
- 
    **column** : strThe column name to calculate the maximum value of.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-69)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
 rel.max(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-69)
        
      

    
```
┌─────────────────┬──────────────┐
│   description   │ max("value") │
│     varchar     │    int64     │
├─────────────────┼──────────────┤
│ value is even   │            8 │
│ value is uneven │            9 │
└─────────────────┴──────────────┘
```
#### 
        
        [`mean`](#mean)
        
      

    
      `mean`
##### 
        
        [Signature](#signature-62)
        
      

    
```
mean(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-71)
        
      

    
Computes the average of a given expression

##### 
        
        [Parameters](#parameters-57)
        
      

    
- 
    **column** : strThe column name to calculate the mean value of.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-70)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.mean(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-70)
        
      

    
```
┌─────────────────┬──────────────┐
│   description   │ avg("value") │
│     varchar     │    double    │
├─────────────────┼──────────────┤
│ value is even   │          5.0 │
│ value is uneven │          5.0 │
└─────────────────┴──────────────┘
```
#### 
        
        [`median`](#median)
        
      

    
      `median`
##### 
        
        [Signature](#signature-63)
        
      

    
```
median(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-72)
        
      

    
Computes the median over all values present in a given expression

##### 
        
        [Parameters](#parameters-58)
        
      

    
- 
    **column** : strThe column name to calculate the median value of.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-71)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.median(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-71)
        
      

    
```
┌─────────────────┬─────────────────┐
│   description   │ median("value") │
│     varchar     │     double      │
├─────────────────┼─────────────────┤
│ value is even   │             5.0 │
│ value is uneven │             5.0 │
└─────────────────┴─────────────────┘
```
#### 
        
        [`min`](#min)
        
      

    
      `min`
##### 
        
        [Signature](#signature-64)
        
      

    
```
min(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-73)
        
      

    
Returns the minimum value present in a given expression

##### 
        
        [Parameters](#parameters-59)
        
      

    
- 
    **column** : strThe column name to calculate the min value of.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-72)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.min(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-72)
        
      

    
```
┌─────────────────┬──────────────┐
│   description   │ min("value") │
│     varchar     │    int64     │
├─────────────────┼──────────────┤
│ value is uneven │            1 │
│ value is even   │            2 │
└─────────────────┴──────────────┘
```
#### 
        
        [`mode`](#mode)
        
      

    
      `mode`
##### 
        
        [Signature](#signature-65)
        
      

    
```
mode(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-74)
        
      

    
Computes the mode over all values present in a given expression

##### 
        
        [Parameters](#parameters-60)
        
      

    
- 
    **column** : strThe column name to calculate the mode (most frequent value) of.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-73)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.mode(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-73)
        
      

    
```
┌─────────────────┬─────────────────┐
│   description   │ "mode"("value") │
│     varchar     │      int64      │
├─────────────────┼─────────────────┤
│ value is uneven │               1 │
│ value is even   │               2 │
└─────────────────┴─────────────────┘
```
#### 
        
        [`n_tile`](#n_tile)
        
      

    
      `n_tile`
##### 
        
        [Signature](#signature-66)
        
      

    
```
n_tile(self: _duckdb.DuckDBPyRelation, window_spec: str, num_buckets: typing.SupportsInt, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-75)
        
      

    
Divides the partition as equally as possible into num_buckets

##### 
        
        [Parameters](#parameters-61)
        
      

    
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **num_buckets** : intThe number of buckets to divide the rows into.
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-74)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.n_tile(window_spec="over (partition by description)", num_buckets=2, projected_columns="description, value")
```
##### 
        
        [Result](#result-74)
        
      

    
```
┌─────────────────┬───────┬──────────────────────────────────────────┐
│   description   │ value │ ntile(2) OVER (PARTITION BY description) │
│     varchar     │ int64 │                  int64                   │
├─────────────────┼───────┼──────────────────────────────────────────┤
│ value is uneven │     1 │                                        1 │
│ value is uneven │     3 │                                        1 │
│ value is uneven │     5 │                                        1 │
│ value is uneven │     7 │                                        2 │
│ value is uneven │     9 │                                        2 │
│ value is even   │     2 │                                        1 │
│ value is even   │     4 │                                        1 │
│ value is even   │     6 │                                        2 │
│ value is even   │     8 │                                        2 │
└─────────────────┴───────┴──────────────────────────────────────────┘
```
#### 
        
        [`nth_value`](#nth_value)
        
      

    
      `nth_value`
##### 
        
        [Signature](#signature-67)
        
      

    
```
nth_value(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str, offset: typing.SupportsInt, ignore_nulls: bool = False, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-76)
        
      

    
Computes the nth value within the partition

##### 
        
        [Parameters](#parameters-62)
        
      

    
- 
    **column** : strThe column name from which to retrieve the nth value within the window.
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **offset** : intThe position of the value to retrieve within the window (1-based index).
- 
    **ignore_nulls** : bool, default: FalseWhether to ignore NULL values when computing the nth value.
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-75)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.nth_value(column="value", window_spec="over (partition by description)", projected_columns="description", offset=1)
```
##### 
        
        [Result](#result-75)
        
      

    
```
┌─────────────────┬───────────────────────────────────────────────────────┐
│   description   │ nth_value("value", 1) OVER (PARTITION BY description) │
│     varchar     │                         int64                         │
├─────────────────┼───────────────────────────────────────────────────────┤
│ value is even   │                                                     2 │
│ value is even   │                                                     2 │
│ value is even   │                                                     2 │
│ value is even   │                                                     2 │
│ value is uneven │                                                     1 │
│ value is uneven │                                                     1 │
│ value is uneven │                                                     1 │
│ value is uneven │                                                     1 │
│ value is uneven │                                                     1 │
└─────────────────┴───────────────────────────────────────────────────────┘
```
#### 
        
        [`percent_rank`](#percent_rank)
        
      

    
      `percent_rank`
##### 
        
        [Signature](#signature-68)
        
      

    
```
percent_rank(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-77)
        
      

    
Computes the relative rank within the partition

##### 
        
        [Parameters](#parameters-63)
        
      

    
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-76)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.percent_rank(window_spec="over (partition by description order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-76)
        
      

    
```
┌─────────────────┬───────┬─────────────────────────────────────────────────────────────────┐
│   description   │ value │ percent_rank() OVER (PARTITION BY description ORDER BY "value") │
│     varchar     │ int64 │                             double                              │
├─────────────────┼───────┼─────────────────────────────────────────────────────────────────┤
│ value is even   │     2 │                                                             0.0 │
│ value is even   │     4 │                                              0.3333333333333333 │
│ value is even   │     6 │                                              0.6666666666666666 │
│ value is even   │     8 │                                                             1.0 │
│ value is uneven │     1 │                                                             0.0 │
│ value is uneven │     3 │                                                            0.25 │
│ value is uneven │     5 │                                                             0.5 │
│ value is uneven │     7 │                                                            0.75 │
│ value is uneven │     9 │                                                             1.0 │
└─────────────────┴───────┴─────────────────────────────────────────────────────────────────┘
```
#### 
        
        [`product`](#product)
        
      

    
      `product`
##### 
        
        [Signature](#signature-69)
        
      

    
```
product(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-78)
        
      

    
Returns the product of all values present in a given expression

##### 
        
        [Parameters](#parameters-64)
        
      

    
- 
    **column** : strThe column name to calculate the product of.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-77)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.product(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-77)
        
      

    
```
┌─────────────────┬──────────────────┐
│   description   │ product("value") │
│     varchar     │      double      │
├─────────────────┼──────────────────┤
│ value is uneven │            945.0 │
│ value is even   │            384.0 │
└─────────────────┴──────────────────┘
```
#### 
        
        [`quantile`](#quantile)
        
      

    
      `quantile`
##### 
        
        [Signature](#signature-70)
        
      

    
```
quantile(self: _duckdb.DuckDBPyRelation, expression: str, q: object = 0.5, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-79)
        
      

    
Computes the exact quantile value for a given expression

##### 
        
        [Parameters](#parameters-65)
        
      

    
- 
    **column** : strThe column name to compute the quantile for.
- 
    **q** : object, default: 0.5The quantile value to compute (e.g., 0.5 for median).
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-78)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.quantile(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-78)
        
      

    
```
┌─────────────────┬──────────────────────────────────┐
│   description   │ quantile_disc("value", 0.500000) │
│     varchar     │              int64               │
├─────────────────┼──────────────────────────────────┤
│ value is uneven │                                5 │
│ value is even   │                                4 │
└─────────────────┴──────────────────────────────────┘
```
#### 
        
        [`quantile_cont`](#quantile_cont)
        
      

    
      `quantile_cont`
##### 
        
        [Signature](#signature-71)
        
      

    
```
quantile_cont(self: _duckdb.DuckDBPyRelation, expression: str, q: object = 0.5, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-80)
        
      

    
Computes the interpolated quantile value for a given expression

##### 
        
        [Parameters](#parameters-66)
        
      

    
- 
    **column** : strThe column name to compute the continuous quantile for.
- 
    **q** : object, default: 0.5The quantile value to compute (e.g., 0.5 for median).
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-79)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.quantile_cont(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-79)
        
      

    
```
┌─────────────────┬──────────────────────────────────┐
│   description   │ quantile_cont("value", 0.500000) │
│     varchar     │              double              │
├─────────────────┼──────────────────────────────────┤
│ value is even   │                              5.0 │
│ value is uneven │                              5.0 │
└─────────────────┴──────────────────────────────────┘
```
#### 
        
        [`quantile_disc`](#quantile_disc)
        
      

    
      `quantile_disc`
##### 
        
        [Signature](#signature-72)
        
      

    
```
quantile_disc(self: _duckdb.DuckDBPyRelation, expression: str, q: object = 0.5, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-81)
        
      

    
Computes the exact quantile value for a given expression

##### 
        
        [Parameters](#parameters-67)
        
      

    
- 
    **column** : strThe column name to compute the discrete quantile for.
- 
    **q** : object, default: 0.5The quantile value to compute (e.g., 0.5 for median).
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-80)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.quantile_disc(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-80)
        
      

    
```
┌─────────────────┬──────────────────────────────────┐
│   description   │ quantile_disc("value", 0.500000) │
│     varchar     │              int64               │
├─────────────────┼──────────────────────────────────┤
│ value is even   │                                4 │
│ value is uneven │                                5 │
└─────────────────┴──────────────────────────────────┘
```
#### 
        
        [`rank`](#rank)
        
      

    
      `rank`
##### 
        
        [Signature](#signature-73)
        
      

    
```
rank(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-82)
        
      

    
Computes the rank within the partition

##### 
        
        [Parameters](#parameters-68)
        
      

    
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-81)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.rank(window_spec="over (partition by description order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-81)
        
      

    
```
┌─────────────────┬───────┬─────────────────────────────────────────────────────────┐
│   description   │ value │ rank() OVER (PARTITION BY description ORDER BY "value") │
│     varchar     │ int64 │                          int64                          │
├─────────────────┼───────┼─────────────────────────────────────────────────────────┤
│ value is uneven │     1 │                                                       1 │
│ value is uneven │     3 │                                                       2 │
│ value is uneven │     5 │                                                       3 │
│ value is uneven │     7 │                                                       4 │
│ value is uneven │     9 │                                                       5 │
│ value is even   │     2 │                                                       1 │
│ value is even   │     4 │                                                       2 │
│ value is even   │     6 │                                                       3 │
│ value is even   │     8 │                                                       4 │
└─────────────────┴───────┴─────────────────────────────────────────────────────────┘
```
#### 
        
        [`rank_dense`](#rank_dense)
        
      

    
      `rank_dense`
##### 
        
        [Signature](#signature-74)
        
      

    
```
rank_dense(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-83)
        
      

    
Computes the dense rank within the partition

**Aliases**: `dense_rank`

##### 
        
        [Parameters](#parameters-69)
        
      

    
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-82)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
 rel.rank_dense(window_spec="over (partition by description order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-82)
        
      

    
```
┌─────────────────┬───────┬───────────────────────────────────────────────────────────────┐
│   description   │ value │ dense_rank() OVER (PARTITION BY description ORDER BY "value") │
│     varchar     │ int64 │                             int64                             │
├─────────────────┼───────┼───────────────────────────────────────────────────────────────┤
│ value is uneven │     1 │                                                             1 │
│ value is uneven │     3 │                                                             2 │
│ value is uneven │     5 │                                                             3 │
│ value is uneven │     7 │                                                             4 │
│ value is uneven │     9 │                                                             5 │
│ value is even   │     2 │                                                             1 │
│ value is even   │     4 │                                                             2 │
│ value is even   │     6 │                                                             3 │
│ value is even   │     8 │                                                             4 │
└─────────────────┴───────┴───────────────────────────────────────────────────────────────┘
```
#### 
        
        [`row_number`](#row_number)
        
      

    
      `row_number`
##### 
        
        [Signature](#signature-75)
        
      

    
```
row_number(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-84)
        
      

    
Computes the row number within the partition

##### 
        
        [Parameters](#parameters-70)
        
      

    
- 
    **window_spec** : strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-83)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.row_number(window_spec="over (partition by description order by value)", projected_columns="description, value")
```
##### 
        
        [Result](#result-83)
        
      

    
```
┌─────────────────┬───────┬───────────────────────────────────────────────────────────────┐
│   description   │ value │ row_number() OVER (PARTITION BY description ORDER BY "value") │
│     varchar     │ int64 │                             int64                             │
├─────────────────┼───────┼───────────────────────────────────────────────────────────────┤
│ value is uneven │     1 │                                                             1 │
│ value is uneven │     3 │                                                             2 │
│ value is uneven │     5 │                                                             3 │
│ value is uneven │     7 │                                                             4 │
│ value is uneven │     9 │                                                             5 │
│ value is even   │     2 │                                                             1 │
│ value is even   │     4 │                                                             2 │
│ value is even   │     6 │                                                             3 │
│ value is even   │     8 │                                                             4 │
└─────────────────┴───────┴───────────────────────────────────────────────────────────────┘
```
#### 
        
        [`select_dtypes`](#select_dtypes)
        
      

    
      `select_dtypes`
##### 
        
        [Signature](#signature-76)
        
      

    
```
select_dtypes(self: _duckdb.DuckDBPyRelation, types: object) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-85)
        
      

    
Select columns from the relation, by filtering based on type(s)

**Aliases**: `select_types`

##### 
        
        [Parameters](#parameters-71)
        
      

    
- 
    **types** : objectData type(s) to select columns by. Can be a single type or a collection of types.

##### 
        
        [Example](#example-84)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.select_dtypes(types=[duckdb.sqltypes.VARCHAR]).distinct()
```
##### 
        
        [Result](#result-84)
        
      

    
```
┌─────────────────┐
│   description   │
│     varchar     │
├─────────────────┤
│ value is even   │
│ value is uneven │
└─────────────────┘
```
#### 
        
        [`select_types`](#select_types)
        
      

    
      `select_types`
##### 
        
        [Signature](#signature-77)
        
      

    
```
select_types(self: _duckdb.DuckDBPyRelation, types: object) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-86)
        
      

    
Select columns from the relation, by filtering based on type(s)

**Aliases**: `select_dtypes`

##### 
        
        [Parameters](#parameters-72)
        
      

    
- 
    **types** : objectData type(s) to select columns by. Can be a single type or a collection of types.

##### 
        
        [Example](#example-85)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.select_types(types=[duckdb.sqltypes.VARCHAR]).distinct()
```
##### 
        
        [Result](#result-85)
        
      

    
```
┌─────────────────┐
│   description   │
│     varchar     │
├─────────────────┤
│ value is even   │
│ value is uneven │
└─────────────────┘
```
#### 
        
        [`std`](#std)
        
      

    
      `std`
##### 
        
        [Signature](#signature-78)
        
      

    
```
std(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-87)
        
      

    
Computes the sample standard deviation for a given expression

**Aliases**: [`stddev`](#stddev), `stddev_samp`

##### 
        
        [Parameters](#parameters-73)
        
      

    
- 
    **column** : strThe column name to calculate the standard deviation for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-86)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.std(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-86)
        
      

    
```
┌─────────────────┬──────────────────────┐
│   description   │ stddev_samp("value") │
│     varchar     │        double        │
├─────────────────┼──────────────────────┤
│ value is uneven │   3.1622776601683795 │
│ value is even   │    2.581988897471611 │
└─────────────────┴──────────────────────┘
```
#### 
        
        [`stddev`](#stddev)
        
      

    
      `stddev`
##### 
        
        [Signature](#signature-79)
        
      

    
```
stddev(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-88)
        
      

    
Computes the sample standard deviation for a given expression

**Aliases**: [`std`](#std), `stddev_samp`

##### 
        
        [Parameters](#parameters-74)
        
      

    
- 
    **column** : strThe column name to calculate the standard deviation for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-87)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.stddev(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-87)
        
      

    
```
┌─────────────────┬──────────────────────┐
│   description   │ stddev_samp("value") │
│     varchar     │        double        │
├─────────────────┼──────────────────────┤
│ value is even   │    2.581988897471611 │
│ value is uneven │   3.1622776601683795 │
└─────────────────┴──────────────────────┘
```
#### 
        
        [`stddev_pop`](#stddev_pop)
        
      

    
      `stddev_pop`
##### 
        
        [Signature](#signature-80)
        
      

    
```
stddev_pop(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-89)
        
      

    
Computes the population standard deviation for a given expression

##### 
        
        [Parameters](#parameters-75)
        
      

    
- 
    **column** : strThe column name to calculate the standard deviation for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-88)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.stddev_pop(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-88)
        
      

    
```
┌─────────────────┬─────────────────────┐
│   description   │ stddev_pop("value") │
│     varchar     │       double        │
├─────────────────┼─────────────────────┤
│ value is even   │    2.23606797749979 │
│ value is uneven │  2.8284271247461903 │
└─────────────────┴─────────────────────┘
```
#### 
        
        [`stddev_samp`](#stddev_samp)
        
      

    
      `stddev_samp`
##### 
        
        [Signature](#signature-81)
        
      

    
```
stddev_samp(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-90)
        
      

    
Computes the sample standard deviation for a given expression

##### 
        
        [Parameters](#parameters-76)
        
      

    
- 
    **column** : strThe column name to calculate the standard deviation for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-89)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.stddev_samp(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-89)
        
      

    
```
┌─────────────────┬──────────────────────┐
│   description   │ stddev_samp("value") │
│     varchar     │        double        │
├─────────────────┼──────────────────────┤
│ value is even   │    2.581988897471611 │
│ value is uneven │   3.1622776601683795 │
└─────────────────┴──────────────────────┘
```
#### 
        
        [`string_agg`](#string_agg)
        
      

    
      `string_agg`
##### 
        
        [Signature](#signature-82)
        
      

    
```
string_agg(self: _duckdb.DuckDBPyRelation, expression: str, sep: str = ',', groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-91)
        
      

    
Concatenates the values present in a given expression with a separator

##### 
        
        [Parameters](#parameters-77)
        
      

    
- 
    **column** : strThe column name to concatenate values from.
- 
    **sep** : str, default: ','Separator string to use between concatenated values.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-90)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.string_agg(column="value", sep=",", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-90)
        
      

    
```
┌─────────────────┬──────────────────────────┐
│   description   │ string_agg("value", ',') │
│     varchar     │         varchar          │
├─────────────────┼──────────────────────────┤
│ value is even   │ 2,4,6,8                  │
│ value is uneven │ 1,3,5,7,9                │
└─────────────────┴──────────────────────────┘
```
#### 
        
        [`sum`](#sum)
        
      

    
      `sum`
##### 
        
        [Signature](#signature-83)
        
      

    
```
sum(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-92)
        
      

    
Computes the sum of all values present in a given expression

##### 
        
        [Parameters](#parameters-78)
        
      

    
- 
    **column** : strThe column name to calculate the sum for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-91)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.sum(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-91)
        
      

    
```
┌─────────────────┬──────────────┐
│   description   │ sum("value") │
│     varchar     │    int128    │
├─────────────────┼──────────────┤
│ value is even   │           20 │
│ value is uneven │           25 │
└─────────────────┴──────────────┘
```
#### 
        
        [`unique`](#unique)
        
      

    
      `unique`
##### 
        
        [Signature](#signature-84)
        
      

    
```
unique(self: _duckdb.DuckDBPyRelation, unique_aggr: str) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-93)
        
      

    
Returns the distinct values in a column.

##### 
        
        [Parameters](#parameters-79)
        
      

    
- 
    **unique_aggr** : strThe column to get the distinct values for.

##### 
        
        [Example](#example-92)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.unique(unique_aggr="description")
```
##### 
        
        [Result](#result-92)
        
      

    
```
┌─────────────────┐
│   description   │
│     varchar     │
├─────────────────┤
│ value is even   │
│ value is uneven │
└─────────────────┘
```
#### 
        
        [`value_counts`](#value_counts)
        
      

    
      `value_counts`
##### 
        
        [Signature](#signature-85)
        
      

    
```
value_counts(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-94)
        
      

    
Computes the number of elements present in a given expression, also projecting the original expression

##### 
        
        [Parameters](#parameters-80)
        
      

    
- 
    **column** : strThe column name to count values from.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .

##### 
        
        [Example](#example-93)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.value_counts(column="description", groups="description")
```
##### 
        
        [Result](#result-93)
        
      

    
```
┌─────────────────┬────────────────────┐
│   description   │ count(description) │
│     varchar     │       int64        │
├─────────────────┼────────────────────┤
│ value is uneven │                  5 │
│ value is even   │                  4 │
└─────────────────┴────────────────────┘
```
#### 
        
        [`var`](#var)
        
      

    
      `var`
##### 
        
        [Signature](#signature-86)
        
      

    
```
var(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-95)
        
      

    
Computes the sample variance for a given expression

##### 
        
        [Parameters](#parameters-81)
        
      

    
- 
    **column** : strThe column name to calculate the sample variance for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-94)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.var(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-94)
        
      

    
```
┌─────────────────┬───────────────────┐
│   description   │ var_samp("value") │
│     varchar     │      double       │
├─────────────────┼───────────────────┤
│ value is even   │ 6.666666666666667 │
│ value is uneven │              10.0 │
└─────────────────┴───────────────────┘
```
#### 
        
        [`var_pop`](#var_pop)
        
      

    
      `var_pop`
##### 
        
        [Signature](#signature-87)
        
      

    
```
var_pop(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-96)
        
      

    
Computes the population variance for a given expression

##### 
        
        [Parameters](#parameters-82)
        
      

    
- 
    **column** : strThe column name to calculate the population variance for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-95)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.var_pop(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-95)
        
      

    
```
┌─────────────────┬──────────────────┐
│   description   │ var_pop("value") │
│     varchar     │      double      │
├─────────────────┼──────────────────┤
│ value is even   │              5.0 │
│ value is uneven │              8.0 │
└─────────────────┴──────────────────┘
```
#### 
        
        [`var_samp`](#var_samp)
        
      

    
      `var_samp`
##### 
        
        [Signature](#signature-88)
        
      

    
```
var_samp(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-97)
        
      

    
Computes the sample variance for a given expression

##### 
        
        [Parameters](#parameters-83)
        
      

    
- 
    **column** : strThe column name to calculate the sample variance for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-96)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.var_samp(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-96)
        
      

    
```
┌─────────────────┬───────────────────┐
│   description   │ var_samp("value") │
│     varchar     │      double       │
├─────────────────┼───────────────────┤
│ value is even   │ 6.666666666666667 │
│ value is uneven │              10.0 │
└─────────────────┴───────────────────┘
```
#### 
        
        [`variance`](#variance)
        
      

    
      `variance`
##### 
        
        [Signature](#signature-89)
        
      

    
```
variance(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-98)
        
      

    
Computes the sample variance for a given expression

##### 
        
        [Parameters](#parameters-84)
        
      

    
- 
    **column** : strThe column name to calculate the sample variance for.
- 
    **groups** : str, default: ''Comma-separated list of columns to include in the `group by` .
- 
    **window_spec** : str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns** : str, default: ''Comma-separated list of columns to include in the result.

##### 
        
        [Example](#example-97)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.variance(column="value", groups="description", projected_columns="description")
```
##### 
        
        [Result](#result-97)
        
      

    
```
┌─────────────────┬───────────────────┐
│   description   │ var_samp("value") │
│     varchar     │      double       │
├─────────────────┼───────────────────┤
│ value is even   │ 6.666666666666667 │
│ value is uneven │              10.0 │
└─────────────────┴───────────────────┘
```
## 
        
        [Output](#output)
        
      

    
This section contains the functions which will trigger an SQL execution and retrieve the data.

| Name | Description | 
|---|---|
| [`arrow`](#arrow) | Alias of to_arrow_reader(). We recommend using to_arrow_reader() instead. | 
| [`close`](#close) | Closes the result | 
| [`create`](#create) | Creates a new table named table_name with the contents of the relation object | 
| [`create_view`](#create_view) | Creates a view named view_name that refers to the relation object | 
| [`df`](#df) | Execute and fetch all rows as a pandas DataFrame | 
| [`execute`](#execute) | Transform the relation into a result set | 
| [`fetch_arrow_reader`](#fetch_arrow_reader) | Execute and return an Arrow Record Batch Reader that yields all rows | 
| [`fetch_arrow_table`](#fetch_arrow_table) | Execute and fetch all rows as an Arrow Table | 
| [`fetch_df_chunk`](#fetch_df_chunk) | Execute and fetch a chunk of the rows | 
| [`fetch_record_batch`](#fetch_record_batch) | Execute and return an Arrow Record Batch Reader that yields all rows | 
| [`fetchall`](#fetchall) | Execute and fetch all rows as a list of tuples | 
| [`fetchdf`](#fetchdf) | Execute and fetch all rows as a pandas DataFrame | 
| [`fetchmany`](#fetchmany) | Execute and fetch the next set of rows as a list of tuples | 
| [`fetchnumpy`](#fetchnumpy) | Execute and fetch all rows as a Python dict mapping each column to one numpy arrays | 
| [`fetchone`](#fetchone) | Execute and fetch a single row as a tuple | 
| [`pl`](#pl) | Execute and fetch all rows as a Polars DataFrame | 
| [`tf`](#tf) | Fetch a result as dict of TensorFlow Tensors | 
| [`to_arrow_reader`](#to_arrow_reader) | Execute and return an Arrow Record Batch Reader that yields all rows | 
| [`to_arrow_table`](#to_arrow_table) | Execute and fetch all rows as an Arrow Table | 
| [`to_csv`](#to_csv) | Write the relation object to a CSV file in 'file_name' | 
| [`to_df`](#to_df) | Execute and fetch all rows as a pandas DataFrame | 
| [`to_parquet`](#to_parquet) | Write the relation object to a Parquet file in 'file_name' | 
| [`to_table`](#to_table) | Creates a new table named table_name with the contents of the relation object | 
| [`to_view`](#to_view) | Creates a view named view_name that refers to the relation object | 
| [`torch`](#torch) | Fetch a result as dict of PyTorch Tensors | 
| [`write_csv`](#write_csv) | Write the relation object to a CSV file in 'file_name' | 
| [`write_parquet`](#write_parquet) | Write the relation object to a Parquet file in 'file_name' | 

#### 
        
        [`arrow`](#arrow)
        
      

    
      `arrow`
##### 
        
        [Signature](#signature-90)
        
      

    
```
arrow(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000) -> pyarrow.lib.RecordBatchReader
```
##### 
        
        [Description](#description-99)
        
      

    
Alias of to_arrow_reader(). We recommend using to_arrow_reader() instead.

  We recommend using [`to_arrow_reader()`](#to_arrow_reader) instead.

**Aliases**: `to_arrow_reader`

##### 
        
        [Parameters](#parameters-85)
        
      

    
- 
    **batch_size** : int, default: 1000000The batch size for fetching the data.

##### 
        
        [Example](#example-98)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
pa_reader = rel.arrow(batch_size=1)
pa_reader.read_next_batch()
```
##### 
        
        [Result](#result-98)
        
      

    
```
pyarrow.RecordBatch
id: string
description: string
value: int64
created_timestamp: timestamp[us, tz=Europe/Amsterdam]
----
id: ["e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd"]
description: ["value is even"]
value: [2]
created_timestamp: [2025-04-10 09:25:51.259000Z]
```
#### 
        
        [`close`](#close)
        
      

    
      `close`
##### 
        
        [Signature](#signature-91)
        
      

    
```
close(self: _duckdb.DuckDBPyRelation) -> None
```
##### 
        
        [Description](#description-100)
        
      

    
Closes the result

#### 
        
        [`create`](#create)
        
      

    
      `create`
##### 
        
        [Signature](#signature-92)
        
      

    
```
create(self: _duckdb.DuckDBPyRelation, table_name: str) -> None
```
##### 
        
        [Description](#description-101)
        
      

    
Creates a new table named table_name with the contents of the relation object

**Aliases**: `to_table`

##### 
        
        [Parameters](#parameters-86)
        
      

    
- 
    **table_name** : strThe name of the table to be created. There shouldn't be any other table with the same name.

##### 
        
        [Example](#example-99)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.create("table_code_example")
duckdb_conn.table("table_code_example").limit(1)
```
##### 
        
        [Result](#result-99)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 3ac9e0ba-8390-4a02-ad72-33b1caea6354 │ value is uneven │     1 │ 2025-04-10 11:07:12.614+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        [`create_view`](#create_view)
        
      

    
      `create_view`
##### 
        
        [Signature](#signature-93)
        
      

    
```
create_view(self: _duckdb.DuckDBPyRelation, view_name: str, replace: bool = True) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-102)
        
      

    
Creates a view named view_name that refers to the relation object

**Aliases**: `to_view`

##### 
        
        [Parameters](#parameters-87)
        
      

    
- 
    **view_name** : strThe name of the view to be created.
- 
    **replace** : bool, default: TrueIf the view should be created with `CREATE OR REPLACE` . When set to`False` , there shouldn't be another view with the same`view_name` .

##### 
        
        [Example](#example-100)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.create_view("view_code_example", replace=True)
duckdb_conn.table("view_code_example").limit(1)
```
##### 
        
        [Result](#result-100)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 3ac9e0ba-8390-4a02-ad72-33b1caea6354 │ value is uneven │     1 │ 2025-04-10 11:07:12.614+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        [`df`](#df)
        
      

    
      `df`
##### 
        
        [Signature](#signature-94)
        
      

    
```
df(self: _duckdb.DuckDBPyRelation, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### 
        
        [Description](#description-103)
        
      

    
Execute and fetch all rows as a pandas DataFrame

##### 
        
        [Parameters](#parameters-88)
        
      

    
- 
    **date_as_object** : bool, default: FalseIf the date columns should be interpreted as Python date objects.

##### 
        
        [Example](#example-101)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.df()
```
##### 
        
        [Result](#result-101)
        
      

    
```
                                     id      description  value                created_timestamp
0  3ac9e0ba-8390-4a02-ad72-33b1caea6354  value is uneven      1 2025-04-10 11:07:12.614000+02:00
1  8b844392-1404-4bbc-b731-120f42c8ca27    value is even      2 2025-04-10 11:08:12.614000+02:00
2  ca5584ca-8e97-4fca-a295-ae3c16c32f5b  value is uneven      3 2025-04-10 11:09:12.614000+02:00
...
```
#### 
        
        [`execute`](#execute)
        
      

    
      `execute`
##### 
        
        [Signature](#signature-95)
        
      

    
```
execute(self: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-104)
        
      

    
Transform the relation into a result set

##### 
        
        [Example](#example-102)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.execute()
```
##### 
        
        [Result](#result-102)
        
      

    
```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 3ac9e0ba-8390-4a02-ad72-33b1caea6354 │ value is uneven │     1 │ 2025-04-10 11:07:12.614+02 │
│ 8b844392-1404-4bbc-b731-120f42c8ca27 │ value is even   │     2 │ 2025-04-10 11:08:12.614+02 │
│ ca5584ca-8e97-4fca-a295-ae3c16c32f5b │ value is uneven │     3 │ 2025-04-10 11:09:12.614+02 │
```
#### 
        
        [`fetch_arrow_reader`](#fetch_arrow_reader)
        
      

    
      `fetch_arrow_reader`
##### 
        
        [Signature](#signature-96)
        
      

    
```
fetch_arrow_reader(self: object, batch_size: typing.SupportsInt = 1000000) -> object
```
##### 
        
        [Description](#description-105)
        
      

    
Execute and return an Arrow Record Batch Reader that yields all rows

  Deprecated `fetch_arrow_reader()` is deprecated. Use [`to_arrow_reader()`](#to_arrow_reader) instead.

##### 
        
        [Parameters](#parameters-89)
        
      

    
- 
    **batch_size** : int, default: 1000000The batch size for fetching the data.

##### 
        
        [Example](#example-103)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
pa_reader = rel.fetch_arrow_reader(batch_size=1)
pa_reader.read_next_batch()
```
##### 
        
        [Result](#result-103)
        
      

    
```
pyarrow.RecordBatch
id: string
description: string
value: int64
created_timestamp: timestamp[us, tz=Europe/Amsterdam]
----
id: ["e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd"]
description: ["value is even"]
value: [2]
created_timestamp: [2025-04-10 09:25:51.259000Z]
```
#### 
        
        [`fetch_arrow_table`](#fetch_arrow_table)
        
      

    
      `fetch_arrow_table`
##### 
        
        [Signature](#signature-97)
        
      

    
```
fetch_arrow_table(self: object, batch_size: typing.SupportsInt = 1000000) -> object
```
##### 
        
        [Description](#description-106)
        
      

    
Execute and fetch all rows as an Arrow Table

  Deprecated `fetch_arrow_table()` is deprecated. Use [`to_arrow_table()`](#to_arrow_table) instead.

**Aliases**: [`arrow`](#arrow), `to_arrow_table`

##### 
        
        [Parameters](#parameters-90)
        
      

    
- 
    **batch_size** : int, default: 1000000The batch size for fetching the data.

##### 
        
        [Example](#example-104)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.fetch_arrow_table()
```
##### 
        
        [Result](#result-104)
        
      

    
```
pyarrow.Table
id: string
description: string
value: int64
created_timestamp: timestamp[us, tz=Europe/Amsterdam]
----
id: [["1587b4b0-3023-49fe-82cf-06303ca136ac","e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd","3f8ad67a-290f-4a22-b41b-0173b8e45afa","9a4e37ef-d8bd-46dd-ab01-51cf4973549f","12baa624-ebc9-45ae-b73e-6f4029e31d2d","56d41292-53cc-48be-a1b8-e1f5d6ca5581","1accca18-c950-47c1-9108-aef8afbd5249","56d8db75-72c4-4d40-90d2-a3c840579c37","e19f6201-8646-401c-b019-e37c42c39632"]]
description: [["value is uneven","value is even","value is uneven","value is even","value is uneven","value is even","value is uneven","value is even","value is uneven"]]
value: [[1,2,3,4,5,6,7,8,9]]
created_timestamp: [[2025-04-10 09:24:51.259000Z,2025-04-10 09:25:51.259000Z,2025-04-10 09:26:51.259000Z,2025-04-10 09:27:51.259000Z,2025-04-10 09:28:51.259000Z,2025-04-10 09:29:51.259000Z,2025-04-10 09:30:51.259000Z,2025-04-10 09:31:51.259000Z,2025-04-10 09:32:51.259000Z]]
```
#### 
        
        [`fetch_df_chunk`](#fetch_df_chunk)
        
      

    
      `fetch_df_chunk`
##### 
        
        [Signature](#signature-98)
        
      

    
```
fetch_df_chunk(self: _duckdb.DuckDBPyRelation, vectors_per_chunk: typing.SupportsInt = 1, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### 
        
        [Description](#description-107)
        
      

    
Execute and fetch a chunk of the rows

##### 
        
        [Parameters](#parameters-91)
        
      

    
- 
    **vectors_per_chunk** : int, default: 1Number of data chunks to be processed before converting to dataframe.
- 
    **date_as_object** : bool, default: FalseIf the date columns should be interpreted as Python date objects.

##### 
        
        [Example](#example-105)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.fetch_df_chunk()
```
##### 
        
        [Result](#result-105)
        
      

    
```
                                     id      description  value                created_timestamp
0  1587b4b0-3023-49fe-82cf-06303ca136ac  value is uneven      1 2025-04-10 11:24:51.259000+02:00
1  e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd    value is even      2 2025-04-10 11:25:51.259000+02:00
2  3f8ad67a-290f-4a22-b41b-0173b8e45afa  value is uneven      3 2025-04-10 11:26:51.259000+02:00
...
```
#### 
        
        [`fetch_record_batch`](#fetch_record_batch)
        
      

    
      `fetch_record_batch`
##### 
        
        [Signature](#signature-99)
        
      

    
```
fetch_record_batch(self: object, rows_per_batch: typing.SupportsInt = 1000000) -> object
```
##### 
        
        [Description](#description-108)
        
      

    
Execute and return an Arrow Record Batch Reader that yields all rows

  Deprecated `fetch_record_batch()` is deprecated. Use [`to_arrow_reader()`](#to_arrow_reader) instead.

**Aliases**: `record_batch`

##### 
        
        [Parameters](#parameters-92)
        
      

    
- 
    **rows_per_batch** : int, default: 1000000The number of rows per batch.

##### 
        
        [Example](#example-106)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
pa_reader = rel.fetch_record_batch(rows_per_batch=1)
pa_reader.read_next_batch()
```
##### 
        
        [Result](#result-106)
        
      

    
```
pyarrow.RecordBatch
id: string
description: string
value: int64
created_timestamp: timestamp[us, tz=Europe/Amsterdam]
----
id: ["908cf67c-a086-4b94-9017-2089a83e4a6c"]
description: ["value is uneven"]
value: [1]
created_timestamp: [2025-04-10 09:52:55.249000Z]
```
#### 
        
        [`fetchall`](#fetchall)
        
      

    
      `fetchall`
##### 
        
        [Signature](#signature-100)
        
      

    
```
fetchall(self: _duckdb.DuckDBPyRelation) -> list
```
##### 
        
        [Description](#description-109)
        
      

    
Execute and fetch all rows as a list of tuples

##### 
        
        [Example](#example-107)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.limit(1).fetchall()
```
##### 
        
        [Result](#result-107)
        
      

    
```
[(UUID('1587b4b0-3023-49fe-82cf-06303ca136ac'),
  'value is uneven',
  1,
  datetime.datetime(2025, 4, 10, 11, 24, 51, 259000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
```
#### 
        
        [`fetchdf`](#fetchdf)
        
      

    
      `fetchdf`
##### 
        
        [Signature](#signature-101)
        
      

    
```
fetchdf(self: _duckdb.DuckDBPyRelation, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### 
        
        [Description](#description-110)
        
      

    
Execute and fetch all rows as a pandas DataFrame

##### 
        
        [Parameters](#parameters-93)
        
      

    
- 
    **date_as_object** : bool, default: FalseIf the date columns should be interpreted as Python date objects.

##### 
        
        [Example](#example-108)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.fetchdf()
```
##### 
        
        [Result](#result-108)
        
      

    
```
                                     id      description  value                created_timestamp
0  1587b4b0-3023-49fe-82cf-06303ca136ac  value is uneven      1 2025-04-10 11:24:51.259000+02:00
1  e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd    value is even      2 2025-04-10 11:25:51.259000+02:00
2  3f8ad67a-290f-4a22-b41b-0173b8e45afa  value is uneven      3 2025-04-10 11:26:51.259000+02:00
...
```
#### 
        
        [`fetchmany`](#fetchmany)
        
      

    
      `fetchmany`
##### 
        
        [Signature](#signature-102)
        
      

    
```
fetchmany(self: _duckdb.DuckDBPyRelation, size: typing.SupportsInt = 1) -> list
```
##### 
        
        [Description](#description-111)
        
      

    
Execute and fetch the next set of rows as a list of tuples

  Warning Executing any operation during the retrieval of the data from an [aggregate](#aggregate) relation,
will close the result set.

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
      select 
          gen_random_uuid() as id, 
          concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
          range as value, 
          now() + concat(range,' ', 'minutes')::interval as created_timestamp
      from range(1, 10)
   """
)
agg_rel = rel.aggregate("value")
while res := agg_rel.fetchmany(size=1):
   print(res)
   rel.show()
```

##### 
        
        [Parameters](#parameters-94)
        
      

    
- 
    **size** : int, default: 1The number of records to be fetched.

##### 
        
        [Example](#example-109)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
while res := rel.fetchmany(size=1):
    print(res)
```
##### 
        
        [Result](#result-109)
        
      

    
```
[(UUID('cf4c5e32-d0aa-4699-a3ee-0092e900f263'), 'value is uneven', 1, datetime.datetime(2025, 4, 30, 16, 23, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('cec335ac-24ac-49a3-ae9a-bb35f71fc88d'), 'value is even', 2, datetime.datetime(2025, 4, 30, 16, 24, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('2423295d-9bb0-453c-a385-21bdacba03b6'), 'value is uneven', 3, datetime.datetime(2025, 4, 30, 16, 25, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('88806b21-192d-41e7-a293-c789aad636ba'), 'value is even', 4, datetime.datetime(2025, 4, 30, 16, 26, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('05837a28-dacf-4121-88a6-a374aefb8a07'), 'value is uneven', 5, datetime.datetime(2025, 4, 30, 16, 27, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('b9c1f7e9-6156-4554-b80e-67d3b5d810bb'), 'value is even', 6, datetime.datetime(2025, 4, 30, 16, 28, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('4709c7fa-d286-4864-bb48-69748b447157'), 'value is uneven', 7, datetime.datetime(2025, 4, 30, 16, 29, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('30e48457-b103-4fa5-95cf-1c7f0143335b'), 'value is even', 8, datetime.datetime(2025, 4, 30, 16, 30, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
[(UUID('036b7f4b-bd78-4ffb-a351-964d93f267b7'), 'value is uneven', 9, datetime.datetime(2025, 4, 30, 16, 31, 5, 310000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
```
#### 
        
        [`fetchnumpy`](#fetchnumpy)
        
      

    
      `fetchnumpy`
##### 
        
        [Signature](#signature-103)
        
      

    
```
fetchnumpy(self: _duckdb.DuckDBPyRelation) -> dict
```
##### 
        
        [Description](#description-112)
        
      

    
Execute and fetch all rows as a Python dict mapping each column to one numpy arrays

##### 
        
        [Example](#example-110)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.fetchnumpy()
```
##### 
        
        [Result](#result-110)
        
      

    
```
{'id': array([UUID('1587b4b0-3023-49fe-82cf-06303ca136ac'),
        UUID('e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd'),
        UUID('3f8ad67a-290f-4a22-b41b-0173b8e45afa'),
        UUID('9a4e37ef-d8bd-46dd-ab01-51cf4973549f'),
        UUID('12baa624-ebc9-45ae-b73e-6f4029e31d2d'),
        UUID('56d41292-53cc-48be-a1b8-e1f5d6ca5581'),
        UUID('1accca18-c950-47c1-9108-aef8afbd5249'),
        UUID('56d8db75-72c4-4d40-90d2-a3c840579c37'),
        UUID('e19f6201-8646-401c-b019-e37c42c39632')], dtype=object),
 'description': array(['value is uneven', 'value is even', 'value is uneven',
        'value is even', 'value is uneven', 'value is even',
        'value is uneven', 'value is even', 'value is uneven'],
       dtype=object),
 'value': array([1, 2, 3, 4, 5, 6, 7, 8, 9]),
 'created_timestamp': array(['2025-04-10T09:24:51.259000', '2025-04-10T09:25:51.259000',
        '2025-04-10T09:26:51.259000', '2025-04-10T09:27:51.259000',
        '2025-04-10T09:28:51.259000', '2025-04-10T09:29:51.259000',
        '2025-04-10T09:30:51.259000', '2025-04-10T09:31:51.259000',
        '2025-04-10T09:32:51.259000'], dtype='datetime64[us]')}
```
#### 
        
        [`fetchone`](#fetchone)
        
      

    
      `fetchone`
##### 
        
        [Signature](#signature-104)
        
      

    
```
fetchone(self: _duckdb.DuckDBPyRelation) -> typing.Optional[tuple]
```
##### 
        
        [Description](#description-113)
        
      

    
Execute and fetch a single row as a tuple

  Warning Executing any operation during the retrieval of the data from an [aggregate](#aggregate) relation,
will close the result set.

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
      select 
          gen_random_uuid() as id, 
          concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
          range as value, 
          now() + concat(range,' ', 'minutes')::interval as created_timestamp
      from range(1, 10)
   """
)
agg_rel = rel.aggregate("value")
while res := agg_rel.fetchone():
   print(res)
   rel.show()
```

##### 
        
        [Example](#example-111)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
while res := rel.fetchone():
    print(res)
```
##### 
        
        [Result](#result-111)
        
      

    
```
(UUID('fe036411-f4c7-4f52-9ddd-80cd2bb56613'), 'value is uneven', 1, datetime.datetime(2025, 4, 30, 12, 59, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('466c9b43-e9f0-4237-8f26-155f259a5b59'), 'value is even', 2, datetime.datetime(2025, 4, 30, 13, 0, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('5755cf16-a94f-41ef-a16d-21e856d71f9f'), 'value is uneven', 3, datetime.datetime(2025, 4, 30, 13, 1, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('05b52c93-bd68-45e1-b02a-a08d682c33d5'), 'value is even', 4, datetime.datetime(2025, 4, 30, 13, 2, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('cf61ef13-2840-4541-900d-f493767d7622'), 'value is uneven', 5, datetime.datetime(2025, 4, 30, 13, 3, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('033e7c68-e800-4ee8-9787-6cf50aabc27b'), 'value is even', 6, datetime.datetime(2025, 4, 30, 13, 4, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('8b8d6545-ff54-45d6-b69a-97edb63dfe43'), 'value is uneven', 7, datetime.datetime(2025, 4, 30, 13, 5, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('7da79dfe-b29c-462b-a414-9d5e3cc80139'), 'value is even', 8, datetime.datetime(2025, 4, 30, 13, 6, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
(UUID('f83ffff2-33b9-4f86-9d14-46974b546bab'), 'value is uneven', 9, datetime.datetime(2025, 4, 30, 13, 7, 8, 912000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))
```
#### 
        
        [`pl`](#pl)
        
      

    
      `pl`
##### 
        
        [Signature](#signature-105)
        
      

    
```
pl(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000, *, lazy: bool = False) -> duckdb::PolarsDataFrame
```
##### 
        
        [Description](#description-114)
        
      

    
Execute and fetch all rows as a Polars DataFrame

##### 
        
        [Parameters](#parameters-95)
        
      

    
- 
    **batch_size** : int, default: 1000000The number of records to be fetched per batch.

##### 
        
        [Example](#example-112)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.pl(batch_size=1)
```
##### 
        
        [Result](#result-112)
        
      

    
```
shape: (9, 4)
┌─────────────────────────────────┬─────────────────┬───────┬────────────────────────────────┐
│ id                              ┆ description     ┆ value ┆ created_timestamp              │
│ ---                             ┆ ---             ┆ ---   ┆ ---                            │
│ str                             ┆ str             ┆ i64   ┆ datetime[μs, Europe/Amsterdam] │
╞═════════════════════════════════╪═════════════════╪═══════╪════════════════════════════════╡
│ b2f92c3c-9372-49f3-897f-2c86fc… ┆ value is uneven ┆ 1     ┆ 2025-04-10 11:49:51.886 CEST   │
```
#### 
        
        [`tf`](#tf)
        
      

    
      `tf`
##### 
        
        [Signature](#signature-106)
        
      

    
```
tf(self: _duckdb.DuckDBPyRelation) -> dict
```
##### 
        
        [Description](#description-115)
        
      

    
Fetch a result as dict of TensorFlow Tensors

##### 
        
        [Example](#example-113)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.select("description, value").tf()
```
##### 
        
        [Result](#result-113)
        
      

    
```
{'description': <tf.Tensor: shape=(9,), dtype=string, numpy=
 array([b'value is uneven', b'value is even', b'value is uneven',
        b'value is even', b'value is uneven', b'value is even',
        b'value is uneven', b'value is even', b'value is uneven'],
       dtype=object)>,
 'value': <tf.Tensor: shape=(9,), dtype=int64, numpy=array([1, 2, 3, 4, 5, 6, 7, 8, 9])>}
```
#### 
        
        [`to_arrow_reader`](#to_arrow_reader)
        
      

    
      `to_arrow_reader`
##### 
        
        [Signature](#signature-107)
        
      

    
```
to_arrow_reader(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000) -> pyarrow.lib.RecordBatchReader
```
##### 
        
        [Description](#description-116)
        
      

    
Execute and return an Arrow Record Batch Reader that yields all rows

**Aliases**: `arrow`

##### 
        
        [Parameters](#parameters-96)
        
      

    
- 
    **batch_size** : int, default: 1000000The batch size for fetching the data.

##### 
        
        [Example](#example-114)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
pa_reader = rel.to_arrow_reader(batch_size=1)
pa_reader.read_next_batch()
```
##### 
        
        [Result](#result-114)
        
      

    
```
pyarrow.RecordBatch
id: string
description: string
value: int64
created_timestamp: timestamp[us, tz=Europe/Amsterdam]
----
id: ["e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd"]
description: ["value is even"]
value: [2]
created_timestamp: [2025-04-10 09:25:51.259000Z]
```
#### 
        
        [`to_arrow_table`](#to_arrow_table)
        
      

    
      `to_arrow_table`
##### 
        
        [Signature](#signature-108)
        
      

    
```
to_arrow_table(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000) -> pyarrow.lib.Table
```
##### 
        
        [Description](#description-117)
        
      

    
Execute and fetch all rows as an Arrow Table

**Aliases**: `fetch_arrow_table`

##### 
        
        [Parameters](#parameters-97)
        
      

    
- 
    **batch_size** : int, default: 1000000The batch size for fetching the data.

##### 
        
        [Example](#example-115)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.to_arrow_table()
```
##### 
        
        [Result](#result-115)
        
      

    
```
pyarrow.Table
id: string
description: string
value: int64
created_timestamp: timestamp[us, tz=Europe/Amsterdam]
----
id: [["86b2011d-3818-426f-a41e-7cd5c7321f79","07fa4f89-0bba-4049-9acd-c933332a66d5","f2f1479e-f582-4fe4-b82f-9b753b69634c","529d3c63-5961-4adb-b0a8-8249188fc82a","aa9eea7d-7fac-4dcf-8f32-4a0b5d64f864","4852aa32-03f2-40d3-8006-b8213904775a","c0127203-f2e3-4925-9810-655bc02a3c19","2a1356ba-5707-44d6-a492-abd0a67e5efb","800a1c24-231c-4dae-bd68-627654c8a110"]]
description: [["value is uneven","value is even","value is uneven","value is even","value is uneven","value is even","value is uneven","value is even","value is uneven"]]
value: [[1,2,3,4,5,6,7,8,9]]
created_timestamp: [[2025-04-10 09:54:24.015000Z,2025-04-10 09:55:24.015000Z,2025-04-10 09:56:24.015000Z,2025-04-10 09:57:24.015000Z,2025-04-10 09:58:24.015000Z,2025-04-10 09:59:24.015000Z,2025-04-10 10:00:24.015000Z,2025-04-10 10:01:24.015000Z,2025-04-10 10:02:24.015000Z]]
```
#### 
        
        [`to_csv`](#to_csv)
        
      

    
      `to_csv`
##### 
        
        [Signature](#signature-109)
        
      

    
```
to_csv(self: _duckdb.DuckDBPyRelation, file_name: str, *, sep: object = None, na_rep: object = None, header: object = None, quotechar: object = None, escapechar: object = None, date_format: object = None, timestamp_format: object = None, quoting: object = None, encoding: object = None, compression: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None) -> None
```
##### 
        
        [Description](#description-118)
        
      

    
Write the relation object to a CSV file in 'file_name'

**Aliases**: `write_csv`

##### 
        
        [Parameters](#parameters-98)
        
      

    
- 
    **file_name** : strThe name of the output CSV file.
- 
    **sep** : str, default: ','Field delimiter for the output file.
- 
    **na_rep** : str, default: ''Missing data representation.
- 
    **header** : bool, default: TrueWhether to write column headers.
- 
    **quotechar** : str, default: '"'Character used to quote fields containing special characters.
- 
    **escapechar** : str, default: NoneCharacter used to escape the delimiter if quoting is set to QUOTE_NONE.
- 
    **date_format** : str, default: NoneCustom format string for DATE values.
- 
    **timestamp_format** : str, default: NoneCustom format string for TIMESTAMP values.
- 
    **quoting** : int, default: csv.QUOTE_MINIMALControl field quoting behavior (e.g., QUOTE_MINIMAL, QUOTE_ALL).
- 
    **encoding** : str, default: 'utf-8'Character encoding for the output file.
- 
    **compression** : str, default: autoCompression type (e.g., 'gzip', 'bz2', 'zstd').
- 
    **overwrite** : bool, default: FalseWhen true, all existing files inside targeted directories will be removed (not supported on remote filesystems). Only has an effect when used with `partition_by` .
- 
    **per_thread_output** : bool, default: FalseWhen `true` , write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file** : bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes.
- 
    **partition_by** : list[str], default: NoneList of column names to partition output by (creates folder structure).
- 
    **write_partition_columns** : bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by` .

##### 
        
        [Example](#example-116)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.to_csv("code_example.csv")
```
##### 
        
        [Result](#result-116)
        
      

    
```
The data is exported to a CSV file, named code_example.csv
```
#### 
        
        [`to_df`](#to_df)
        
      

    
      `to_df`
##### 
        
        [Signature](#signature-110)
        
      

    
```
to_df(self: _duckdb.DuckDBPyRelation, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### 
        
        [Description](#description-119)
        
      

    
Execute and fetch all rows as a pandas DataFrame

##### 
        
        [Parameters](#parameters-99)
        
      

    
- 
    **date_as_object** : bool, default: FalseIf the date columns should be interpreted as Python date objects.

##### 
        
        [Example](#example-117)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.to_df()
```
##### 
        
        [Result](#result-117)
        
      

    
```
                                     id      description  value                created_timestamp
0  e1f79925-60fd-4ee2-ae67-5eff6b0543d1  value is uneven      1 2025-04-10 11:56:04.452000+02:00
1  caa619d4-d79c-4c00-b82e-9319b086b6f8    value is even      2 2025-04-10 11:57:04.452000+02:00
2  64c68032-99b9-4e8f-b4a3-6c522d5419b3  value is uneven      3 2025-04-10 11:58:04.452000+02:00
...
```
#### 
        
        [`to_parquet`](#to_parquet)
        
      

    
      `to_parquet`
##### 
        
        [Signature](#signature-111)
        
      

    
```
to_parquet(self: _duckdb.DuckDBPyRelation, file_name: str, *, compression: object = None, field_ids: object = None, row_group_size_bytes: object = None, row_group_size: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None, append: object = None, filename_pattern: object = None, file_size_bytes: object = None) -> None
```
##### 
        
        [Description](#description-120)
        
      

    
Write the relation object to a Parquet file in 'file_name'

**Aliases**: `write_parquet`

##### 
        
        [Parameters](#parameters-100)
        
      

    
- 
    **file_name** : strThe name of the output Parquet file.
- 
    **compression** : str, default: 'snappy'The compression format to use ( `uncompressed` ,`snappy` ,`gzip` ,`zstd` ,`brotli` ,`lz4` ,`lz4_raw` ).
- 
    **field_ids** : STRUCTThe field_id for each column. Pass auto to attempt to infer automatically.
- 
    **row_group_size_bytes** : int, default: row_group_size * 1024The target size of each row group. You can pass either a human-readable string, e.g., 2MB, or an integer, i.e., the number of bytes. This option is only used when you have issued `SET preserve_insertion_order = false;` , otherwise, it is ignored.
- 
    **row_group_size** : int, default: 122880The target size, i.e., number of rows, of each row group.
- 
    **overwrite** : bool, default: FalseIf True, overwrite the file if it exists.
- 
    **per_thread_output** : bool, default: FalseWhen `True` , write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file** : bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes.
- 
    **partition_by** : list[str], default: NoneList of column names to partition output by (creates folder structure).
- 
    **write_partition_columns** : bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by` .
- 
    **append** : bool, default: FalseWhen `True` , in the event a filename pattern is generated that already exists, the path will be regenerated to ensure no existing files are overwritten. Only has an effect when used with`partition_by` .

##### 
        
        [Example](#example-118)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.to_parquet("code_example.parquet")
```
##### 
        
        [Result](#result-118)
        
      

    
```
The data is exported to a Parquet file, named code_example.parquet
```
#### 
        
        [`to_table`](#to_table)
        
      

    
      `to_table`
##### 
        
        [Signature](#signature-112)
        
      

    
```
to_table(self: _duckdb.DuckDBPyRelation, table_name: str) -> None
```
##### 
        
        [Description](#description-121)
        
      

    
Creates a new table named table_name with the contents of the relation object

**Aliases**: `create`

##### 
        
        [Parameters](#parameters-101)
        
      

    
- 
    **table_name** : strThe name of the table to be created. There shouldn't be any other table with the same name.

##### 
        
        [Example](#example-119)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.to_table("table_code_example")
```
##### 
        
        [Result](#result-119)
        
      

    
```
A table, named table_code_example, is created with the data of the relation
```
#### 
        
        [`to_view`](#to_view)
        
      

    
      `to_view`
##### 
        
        [Signature](#signature-113)
        
      

    
```
to_view(self: _duckdb.DuckDBPyRelation, view_name: str, replace: bool = True) -> _duckdb.DuckDBPyRelation
```
##### 
        
        [Description](#description-122)
        
      

    
Creates a view named view_name that refers to the relation object

**Aliases**: `create_view`

##### 
        
        [Parameters](#parameters-102)
        
      

    
- 
    **view_name** : strThe name of the view to be created.
- 
    **replace** : bool, default: TrueIf the view should be created with `CREATE OR REPLACE` . When set to`False` , there shouldn't be another view with the same`view_name` .

##### 
        
        [Example](#example-120)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.to_view("view_code_example", replace=True)
```
##### 
        
        [Result](#result-120)
        
      

    
```
A view, named view_code_example, is created with the query definition of the relation
```
#### 
        
        [`torch`](#torch)
        
      

    
      `torch`
##### 
        
        [Signature](#signature-114)
        
      

    
```
torch(self: _duckdb.DuckDBPyRelation) -> dict
```
##### 
        
        [Description](#description-123)
        
      

    
Fetch a result as dict of PyTorch Tensors

##### 
        
        [Example](#example-121)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.select("value").torch()
```
##### 
        
        [Result](#result-121)
        
      

    
```
{'value': tensor([1, 2, 3, 4, 5, 6, 7, 8, 9])}
```
#### 
        
        [`write_csv`](#write_csv)
        
      

    
      `write_csv`
##### 
        
        [Signature](#signature-115)
        
      

    
```
write_csv(self: _duckdb.DuckDBPyRelation, file_name: str, *, sep: object = None, na_rep: object = None, header: object = None, quotechar: object = None, escapechar: object = None, date_format: object = None, timestamp_format: object = None, quoting: object = None, encoding: object = None, compression: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None) -> None
```
##### 
        
        [Description](#description-124)
        
      

    
Write the relation object to a CSV file in 'file_name'

**Aliases**: `to_csv`

##### 
        
        [Parameters](#parameters-103)
        
      

    
- 
    **file_name** : strThe name of the output CSV file.
- 
    **sep** : str, default: ','Field delimiter for the output file.
- 
    **na_rep** : str, default: ''Missing data representation.
- 
    **header** : bool, default: TrueWhether to write column headers.
- 
    **quotechar** : str, default: '"'Character used to quote fields containing special characters.
- 
    **escapechar** : str, default: NoneCharacter used to escape the delimiter if quoting is set to QUOTE_NONE.
- 
    **date_format** : str, default: NoneCustom format string for DATE values.
- 
    **timestamp_format** : str, default: NoneCustom format string for TIMESTAMP values.
- 
    **quoting** : int, default: csv.QUOTE_MINIMALControl field quoting behavior (e.g., QUOTE_MINIMAL, QUOTE_ALL).
- 
    **encoding** : str, default: 'utf-8'Character encoding for the output file.
- 
    **compression** : str, default: autoCompression type (e.g., 'gzip', 'bz2', 'zstd').
- 
    **overwrite** : bool, default: FalseWhen true, all existing files inside targeted directories will be removed (not supported on remote filesystems). Only has an effect when used with `partition_by` .
- 
    **per_thread_output** : bool, default: FalseWhen `true` , write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file** : bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes.
- 
    **partition_by** : list[str], default: NoneList of column names to partition output by (creates folder structure).
- 
    **write_partition_columns** : bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by` .

##### 
        
        [Example](#example-122)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.write_csv("code_example.csv")
```
##### 
        
        [Result](#result-122)
        
      

    
```
The data is exported to a CSV file, named code_example.csv
```
#### 
        
        [`write_parquet`](#write_parquet)
        
      

    
      `write_parquet`
##### 
        
        [Signature](#signature-116)
        
      

    
```
write_parquet(self: _duckdb.DuckDBPyRelation, file_name: str, *, compression: object = None, field_ids: object = None, row_group_size_bytes: object = None, row_group_size: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None, append: object = None, filename_pattern: object = None, file_size_bytes: object = None) -> None
```
##### 
        
        [Description](#description-125)
        
      

    
Write the relation object to a Parquet file in 'file_name'

**Aliases**: `to_parquet`

##### 
        
        [Parameters](#parameters-104)
        
      

    
- 
    **file_name** : strThe name of the output Parquet file.
- 
    **compression** : str, default: 'snappy'The compression format to use ( `uncompressed` ,`snappy` ,`gzip` ,`zstd` ,`brotli` ,`lz4` ,`lz4_raw` ).
- 
    **field_ids** : STRUCTThe field_id for each column. Pass auto to attempt to infer automatically.
- 
    **row_group_size_bytes** : int, default: row_group_size * 1024The target size of each row group. You can pass either a human-readable string, e.g., 2MB, or an integer, i.e., the number of bytes. This option is only used when you have issued `SET preserve_insertion_order = false;` , otherwise, it is ignored.
- 
    **row_group_size** : int, default: 122880The target size, i.e., number of rows, of each row group.
- 
    **overwrite** : bool, default: FalseIf True, overwrite the file if it exists.
- 
    **per_thread_output** : bool, default: FalseWhen `True` , write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file** : bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes.
- 
    **partition_by** : list[str], default: NoneList of column names to partition output by (creates folder structure).
- 
    **write_partition_columns** : bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by` .
- 
    **append** : bool, default: FalseWhen `True` , in the event a filename pattern is generated that already exists, the path will be regenerated to ensure no existing files are overwritten. Only has an effect when used with`partition_by` .

##### 
        
        [Example](#example-123)
        
      

    
```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("""
        select 
            gen_random_uuid() as id, 
            concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description,
            range as value, 
            now() + concat(range,' ', 'minutes')::interval as created_timestamp
        from range(1, 10)
    """
)
rel.write_parquet("code_example.parquet")
```
##### 
        
        [Result](#result-123)
        
      

    
```
The data is exported to a Parquet file, named code_example.parquet
```

# Citations

1. Source page: https://duckdb.org/docs/current/clients/python/relational_api
