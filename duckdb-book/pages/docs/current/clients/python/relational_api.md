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
timestamp: '2026-07-07T12:26:08.924159+00:00'
---

The Relational API is an alternative API that can be used to incrementally construct queries. 
The API is centered around `DuckDBPyRelation` nodes. The relations can be seen as symbolic representations of SQL queries.

## Lazy Evaluation

The relations do not hold any data – and nothing is executed – until a method that triggers execution is called.

For example, we create a relation, which loads 1 billion rows:

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("from range(1_000_000_000)")
```
At the moment of execution, `rel` does not hold any data and no data is retrieved from the database.

By calling `rel.show()` or simply printing `rel` on the terminal, the first 10K rows are fetched.
If there are more than 10K rows, the output window will show >9999 rows (as the amount of rows in the relation is unknown).

By calling an output method, the data is retrieved and stored in the specified format:

```
rel.to_table("example_rel")
# 100% ▕████████████████████████████████████████████████████████████▏ 
```
## Relation Creation

This section contains the details on how a relation is created. The methods are lazy evaluated.

| Name | Description | 
|---|---|
| `from_arrow` | Create a relation object from an Arrow object | 
| `from_csv_auto` | Create a relation object from the CSV file in 'name' | 
| `from_df` | Create a relation object from the DataFrame in df | 
| `from_parquet` | Create a relation object from the Parquet files | 
| `from_query` | Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is. | 
| `query` | Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is. | 
| `read_csv` | Create a relation object from the CSV file in 'name' | 
| `read_json` | Create a relation object from the JSON file in 'name' | 
| `read_parquet` | Create a relation object from the Parquet files | 
| `sql` | Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is. | 
| `table` | Create a relation object for the named table | 
| `table_function` | Create a relation object from the named table function with given parameters | 
| `values` | Create a relation object from the passed values | 
| `view` | Create a relation object for the named view | 

#### 
        
        `from_arrow`
        
      

    
      ##### Signature

```
from_arrow(self: _duckdb.DuckDBPyConnection, arrow_object: object) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object from an Arrow object

##### Parameters

- 
    **arrow_object**: pyarrow.Table, pyarrow.RecordBatchArrow object to create a relation from 

##### Example

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
##### Result

```
┌──────┬─────────┐
│  id  │  text   │
│ int8 │ varchar │
├──────┼─────────┤
│    1 │ a       │
└──────┴─────────┘
```
#### 
        
        `from_csv_auto`
        
      

    
      ##### Signature

```
from_csv_auto(self: _duckdb.DuckDBPyConnection, path_or_buffer: object, **kwargs) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object from the CSV file in 'name'

**Aliases**: `read_csv`

##### Parameters

- 
    **path_or_buffer**: Union[str, StringIO, TextIOBase]Path to the CSV file or buffer to read from. 
- 
    **header**: Optional[bool], Optional[int]Row number(s) to use as the column names, or None if no header. 
- 
    **compression**: Optional[str]Compression type (e.g., 'gzip', 'bz2'). 
- 
    **sep**: Optional[str]Delimiter to use; defaults to comma. 
- 
    **delimiter**: Optional[str]Alternative delimiter to use. 
- 
    **dtype**: Optional[Dict[str, str]], Optional[List[str]]Data types for columns. 
- 
    **na_values**: Optional[str], Optional[List[str]]Additional strings to recognize as NA/NaN. 
- 
    **skiprows**: Optional[int]Number of rows to skip at the start. 
- 
    **quotechar**: Optional[str]Character used to quote fields. 
- 
    **escapechar**: Optional[str]Character used to escape delimiter or quote characters. 
- 
    **encoding**: Optional[str]Encoding to use for UTF when reading/writing. 
- 
    **parallel**: Optional[bool]Enable parallel reading. 
- 
    **date_format**: Optional[str]Format to parse dates. 
- 
    **timestamp_format**: Optional[str]Format to parse timestamps. 
- 
    **sample_size**: Optional[int]Number of rows to sample for schema inference. 
- 
    **all_varchar**: Optional[bool]Treat all columns as VARCHAR. 
- 
    **normalize_names**: Optional[bool]Normalize column names to lowercase. 
- 
    **null_padding**: Optional[bool]Enable null padding for rows with missing columns. 
- 
    **names**: Optional[List[str]]List of column names to use. 
- 
    **lineterminator**: Optional[str]Character to break lines on. 
- 
    **columns**: Optional[Dict[str, str]]Column mapping for schema. 
- 
    **auto_type_candidates**: Optional[List[str]]List of columns for automatic type inference. 
- 
    **max_line_size**: Optional[int]Maximum line size in bytes. 
- 
    **ignore_errors**: Optional[bool]Ignore parsing errors. 
- 
    **store_rejects**: Optional[bool]Store rejected rows. 
- 
    **rejects_table**: Optional[str]Table name to store rejected rows. 
- 
    **rejects_scan**: Optional[str]Scan to use for rejects. 
- 
    **rejects_limit**: Optional[int]Limit number of rejects stored. 
- 
    **force_not_null**: Optional[List[str]]List of columns to force as NOT NULL. 
- 
    **buffer_size**: Optional[int]Buffer size in bytes. 
- 
    **decimal**: Optional[str]Character to recognize as decimal point. 
- 
    **allow_quoted_nulls**: Optional[bool]Allow quoted NULL values. 
- 
    **filename**: Optional[bool], Optional[str]Add filename column or specify filename. 
- 
    **hive_partitioning**: Optional[bool]Enable Hive-style partitioning. 
- 
    **union_by_name**: Optional[bool]Union files by column name instead of position. 
- 
    **hive_types**: Optional[Dict[str, str]]Hive types for columns. 
- 
    **hive_types_autocast**: Optional[bool]Automatically cast Hive types. 
- 
    **connection**: DuckDBPyConnectionDuckDB connection to use. 

##### Example

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
##### Result

```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        `from_df`
        
      

    
      ##### Signature

```
from_df(self: _duckdb.DuckDBPyConnection, df: pandas.DataFrame) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object from the DataFrame in df

##### Parameters

- 
    **df**: pandas.DataFrameA pandas DataFrame to be converted into a DuckDB relation. 

##### Example

```
import duckdb
import pandas as pd
df = pd.DataFrame(data = {'id': [1], "text":["a"]})
duckdb_conn = duckdb.connect()
rel = duckdb_conn.from_df(df)
rel.show()
```
##### Result

```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        `from_parquet`
        
      

    
      ##### Signature

```
from_parquet(*args, **kwargs)
Overloaded function.
1. from_parquet(self: _duckdb.DuckDBPyConnection, file_glob: str, binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_glob
2. from_parquet(self: _duckdb.DuckDBPyConnection, file_globs: collections.abc.Sequence[str], binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_globs
```
##### Description

Create a relation object from the Parquet files

**Aliases**: `read_parquet`

##### Parameters

- 
    **file_glob**: strFile path or glob pattern pointing to Parquet files to be read. 
- 
    **binary_as_string**: bool, default: FalseInterpret binary columns as strings instead of blobs. 
- 
    **file_row_number**: bool, default: FalseAdd a column containing the row number within each file. 
- 
    **filename**: bool, default: FalseAdd a column containing the name of the file each row came from. 
- 
    **hive_partitioning**: bool, default: FalseEnable automatic detection of Hive-style partitions in file paths. 
- 
    **union_by_name**: bool, default: FalseUnion Parquet files by matching column names instead of positions. 
- 
    **compression**: objectOptional compression codec to use when reading the Parquet files. 

##### Example

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
##### Result

```
┌──────┬─────────┐
│  id  │  text   │
│ int8 │ varchar │
├──────┼─────────┤
│    1 │ a       │
└──────┴─────────┘
```
#### 
        
        `from_query`
        
      

    
      ##### Signature

```
from_query(self: _duckdb.DuckDBPyConnection, query: object, *, alias: str = '', params: object = None) -> _duckdb.DuckDBPyRelation
```
##### Description

Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is.

Warning.Passing`params`to this method is discouraged due to significant performance overhead. Use`execute()`for parameterized queries instead.

##### Parameters

- 
    **query**: objectThe SQL query or subquery to be executed and converted into a relation. 
- 
    **alias**: str, default: ''Optional alias name to assign to the resulting relation. 
- 
    **params**: objectOptional query parameters. **Discouraged**due to significant performance overhead. Use`execute()`for parameterized queries instead.

##### Example

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.from_query("from range(1,2) tbl(id)")
rel.show()
```
##### Result

```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        `query`
        
      

    
      ##### Signature

```
query(self: _duckdb.DuckDBPyConnection, query: object, *, alias: str = '', params: object = None) -> _duckdb.DuckDBPyRelation
```
##### Description

Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is.

Warning.Passing`params`to this method is discouraged due to significant performance overhead. Use`execute()`for parameterized queries instead.

**Aliases**: `from_query`, `sql`

##### Parameters

- 
    **query**: objectThe SQL query or subquery to be executed and converted into a relation. 
- 
    **alias**: str, default: ''Optional alias name to assign to the resulting relation. 
- 
    **params**: objectOptional query parameters. **Discouraged**due to significant performance overhead. Use`execute()`for parameterized queries instead.

##### Example

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.query("from range(1,2) tbl(id)")
rel.show()
```
##### Result

```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        `read_csv`
        
      

    
      ##### Signature

```
read_csv(self: _duckdb.DuckDBPyConnection, path_or_buffer: object, **kwargs) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object from the CSV file in 'name'

**Aliases**: `from_csv_auto`

##### Parameters

- 
    **path_or_buffer**: Union[str, StringIO, TextIOBase]Path to the CSV file or buffer to read from. 
- 
    **header**: Optional[bool], Optional[int]Row number(s) to use as the column names, or None if no header. 
- 
    **compression**: Optional[str]Compression type (e.g., 'gzip', 'bz2'). 
- 
    **sep**: Optional[str]Delimiter to use; defaults to comma. 
- 
    **delimiter**: Optional[str]Alternative delimiter to use. 
- 
    **dtype**: Optional[Dict[str, str]], Optional[List[str]]Data types for columns. 
- 
    **na_values**: Optional[str], Optional[List[str]]Additional strings to recognize as NA/NaN. 
- 
    **skiprows**: Optional[int]Number of rows to skip at the start. 
- 
    **quotechar**: Optional[str]Character used to quote fields. 
- 
    **escapechar**: Optional[str]Character used to escape delimiter or quote characters. 
- 
    **encoding**: Optional[str]Encoding to use for UTF when reading/writing. 
- 
    **parallel**: Optional[bool]Enable parallel reading. 
- 
    **date_format**: Optional[str]Format to parse dates. 
- 
    **timestamp_format**: Optional[str]Format to parse timestamps. 
- 
    **sample_size**: Optional[int]Number of rows to sample for schema inference. 
- 
    **all_varchar**: Optional[bool]Treat all columns as VARCHAR. 
- 
    **normalize_names**: Optional[bool]Normalize column names to lowercase. 
- 
    **null_padding**: Optional[bool]Enable null padding for rows with missing columns. 
- 
    **names**: Optional[List[str]]List of column names to use. 
- 
    **lineterminator**: Optional[str]Character to break lines on. 
- 
    **columns**: Optional[Dict[str, str]]Column mapping for schema. 
- 
    **auto_type_candidates**: Optional[List[str]]List of columns for automatic type inference. 
- 
    **max_line_size**: Optional[int]Maximum line size in bytes. 
- 
    **ignore_errors**: Optional[bool]Ignore parsing errors. 
- 
    **store_rejects**: Optional[bool]Store rejected rows. 
- 
    **rejects_table**: Optional[str]Table name to store rejected rows. 
- 
    **rejects_scan**: Optional[str]Scan to use for rejects. 
- 
    **rejects_limit**: Optional[int]Limit number of rejects stored. 
- 
    **force_not_null**: Optional[List[str]]List of columns to force as NOT NULL. 
- 
    **buffer_size**: Optional[int]Buffer size in bytes. 
- 
    **decimal**: Optional[str]Character to recognize as decimal point. 
- 
    **allow_quoted_nulls**: Optional[bool]Allow quoted NULL values. 
- 
    **filename**: Optional[bool], Optional[str]Add filename column or specify filename. 
- 
    **hive_partitioning**: Optional[bool]Enable Hive-style partitioning. 
- 
    **union_by_name**: Optional[bool]Union files by column name instead of position. 
- 
    **hive_types**: Optional[Dict[str, str]]Hive types for columns. 
- 
    **hive_types_autocast**: Optional[bool]Automatically cast Hive types. 
- 
    **connection**: DuckDBPyConnectionDuckDB connection to use. 

##### Example

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
##### Result

```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        `read_json`
        
      

    
      ##### Signature

```
read_json(self: _duckdb.DuckDBPyConnection, path_or_buffer: object, *, columns: typing.Optional[object] = None, sample_size: typing.Optional[object] = None, maximum_depth: typing.Optional[object] = None, records: typing.Optional[str] = None, format: typing.Optional[str] = None, date_format: typing.Optional[object] = None, timestamp_format: typing.Optional[object] = None, compression: typing.Optional[object] = None, maximum_object_size: typing.Optional[object] = None, ignore_errors: typing.Optional[object] = None, convert_strings_to_integers: typing.Optional[object] = None, field_appearance_threshold: typing.Optional[object] = None, map_inference_threshold: typing.Optional[object] = None, maximum_sample_files: typing.Optional[object] = None, filename: typing.Optional[object] = None, hive_partitioning: typing.Optional[object] = None, union_by_name: typing.Optional[object] = None, hive_types: typing.Optional[object] = None, hive_types_autocast: typing.Optional[object] = None) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object from the JSON file in 'name'

##### Parameters

- 
    **path_or_buffer**: objectFile path or file-like object containing JSON data to be read. 
- 
    **columns**: objectOptional list of column names to project from the JSON data. 
- 
    **sample_size**: objectNumber of rows to sample for inferring JSON schema. 
- 
    **maximum_depth**: objectMaximum depth to which JSON objects should be parsed. 
- 
    **records**: strFormat string specifying whether JSON is in records mode. 
- 
    **format**: strFormat of the JSON data (e.g., 'auto', 'newline_delimited'). 
- 
    **date_format**: objectFormat string for parsing date fields. 
- 
    **timestamp_format**: objectFormat string for parsing timestamp fields. 
- 
    **compression**: objectCompression codec used on the JSON data (e.g., 'gzip'). 
- 
    **maximum_object_size**: objectMaximum size in bytes for individual JSON objects. 
- 
    **ignore_errors**: objectIf True, skip over JSON records with parsing errors. 
- 
    **convert_strings_to_integers**: objectIf True, attempt to convert strings to integers where appropriate. 
- 
    **field_appearance_threshold**: objectThreshold for inferring optional fields in nested JSON. 
- 
    **map_inference_threshold**: objectThreshold for inferring maps from JSON object patterns. 
- 
    **maximum_sample_files**: objectMaximum number of files to sample for schema inference. 
- 
    **filename**: objectIf True, include a column with the source filename for each row. 
- 
    **hive_partitioning**: objectIf True, enable Hive partitioning based on directory structure. 
- 
    **union_by_name**: objectIf True, align JSON columns by name instead of position. 
- 
    **hive_types**: objectIf True, use Hive types from directory structure for schema. 
- 
    **hive_types_autocast**: objectIf True, automatically cast data types to match Hive types. 

##### Example

```
import duckdb
import json
with open("code_example.json", mode="w") as f:
    json.dump([{'id': 1, "text":"a"}], f)
    
duckdb_conn = duckdb.connect()
rel = duckdb_conn.read_json("code_example.json")
rel.show()
```
##### Result

```
┌───────┬─────────┐
│  id   │  text   │
│ int64 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        `read_parquet`
        
      

    
      ##### Signature

```
read_parquet(*args, **kwargs)
Overloaded function.
1. read_parquet(self: _duckdb.DuckDBPyConnection, file_glob: str, binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_glob
2. read_parquet(self: _duckdb.DuckDBPyConnection, file_globs: collections.abc.Sequence[str], binary_as_string: bool = False, *, file_row_number: bool = False, filename: bool = False, hive_partitioning: bool = False, union_by_name: bool = False, compression: object = None) -> _duckdb.DuckDBPyRelation
Create a relation object from the Parquet files in file_globs
```
##### Description

Create a relation object from the Parquet files

**Aliases**: `from_parquet`

##### Parameters

- 
    **file_glob**: strFile path or glob pattern pointing to Parquet files to be read. 
- 
    **binary_as_string**: bool, default: FalseInterpret binary columns as strings instead of blobs. 
- 
    **file_row_number**: bool, default: FalseAdd a column containing the row number within each file. 
- 
    **filename**: bool, default: FalseAdd a column containing the name of the file each row came from. 
- 
    **hive_partitioning**: bool, default: FalseEnable automatic detection of Hive-style partitions in file paths. 
- 
    **union_by_name**: bool, default: FalseUnion Parquet files by matching column names instead of positions. 
- 
    **compression**: objectOptional compression codec to use when reading the Parquet files. 

##### Example

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
##### Result

```
┌──────┬─────────┐
│  id  │  text   │
│ int8 │ varchar │
├──────┼─────────┤
│    1 │ a       │
└──────┴─────────┘
```
#### 
        
        `sql`
        
      

    
      ##### Signature

```
sql(self: _duckdb.DuckDBPyConnection, query: object, *, alias: str = '', params: object = None) -> _duckdb.DuckDBPyRelation
```
##### Description

Run a SQL query. If it is a SELECT statement, create a relation object from the given SQL query, otherwise run the query as-is.

Warning.Passing`params`to this method is discouraged due to significant performance overhead. Use`execute()`for parameterized queries instead.

**Aliases**: `from_query`, `query`

##### Parameters

- 
    **query**: objectThe SQL query or subquery to be executed and converted into a relation. 
- 
    **alias**: str, default: ''Optional alias name to assign to the resulting relation. 
- 
    **params**: objectOptional query parameters. **Discouraged**due to significant performance overhead. Use`execute()`for parameterized queries instead.

##### Example

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("from range(1,2) tbl(id)")
rel.show()
```
##### Result

```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        `table`
        
      

    
      ##### Signature

```
table(self: _duckdb.DuckDBPyConnection, table_name: str) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object for the named table

##### Parameters

- 
    **table_name**: strName of the table to create a relation from. 

##### Example

```
import duckdb
duckdb_conn = duckdb.connect()
duckdb_conn.sql("create table code_example as select * from range(1,2) tbl(id)")
rel = duckdb_conn.table("code_example")
rel.show()
```
##### Result

```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
#### 
        
        `table_function`
        
      

    
      ##### Signature

```
table_function(self: _duckdb.DuckDBPyConnection, name: str, parameters: object = None) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object from the named table function with given parameters

##### Parameters

- 
    **name**: strName of the table function to call. 
- 
    **parameters**: objectOptional parameters to pass to the table function. 

##### Example

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
##### Result

```
┌───────────────┐
│ (1 * "range") │
│     int64     │
├───────────────┤
│             1 │
└───────────────┘
```
#### 
        
        `values`
        
      

    
      ##### Signature

```
values(self: _duckdb.DuckDBPyConnection, *args) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object from the passed values

##### Example

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.values([1, 'a'])
rel.show()
```
##### Result

```
┌───────┬─────────┐
│ col0  │  col1   │
│ int32 │ varchar │
├───────┼─────────┤
│     1 │ a       │
└───────┴─────────┘
```
#### 
        
        `view`
        
      

    
      ##### Signature

```
view(self: _duckdb.DuckDBPyConnection, view_name: str) -> _duckdb.DuckDBPyRelation
```
##### Description

Create a relation object for the named view

##### Parameters

- 
    **view_name**: strName of the view to create a relation from. 

##### Example

```
import duckdb
duckdb_conn = duckdb.connect()
duckdb_conn.sql("create table code_example as select * from range(1,2) tbl(id)")
rel = duckdb_conn.view("code_example")
rel.show()
```
##### Result

```
┌───────┐
│  id   │
│ int64 │
├───────┤
│     1 │
└───────┘
```
## Relation Definition Details

This section contains the details on how to inspect a relation.

| Name | Description | 
|---|---|
| `alias` | Get the name of the current alias | 
| `columns` | Return a list containing the names of the columns of the relation. | 
| `describe` | Gives basic statistics (e.g., min, max) and if NULL exists for each column of the relation. | 
| `description` | Return the description of the result | 
| `dtypes` | Return a list containing the types of the columns of the relation. | 
| `explain` | explain(self: _duckdb.DuckDBPyRelation, type: _duckdb.ExplainType = 'standard') -> str | 
| `query` | Run the given SQL query in sql_query on the view named virtual_table_name that refers to the relation object | 
| `set_alias` | Rename the relation object to new alias | 
| `shape` | Tuple of # of rows, # of columns in relation. | 
| `show` | Display a summary of the data | 
| `sql_query` | Get the SQL query that is equivalent to the relation | 
| `type` | Get the type of the relation. | 
| `types` | Return a list containing the types of the columns of the relation. | 

#### 
        
        `alias`
        
      

    
      ##### Description

Get the name of the current alias

##### Example

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
##### Result

```
unnamed_relation_43c808c247431be5
```
#### 
        
        `columns`
        
      

    
      ##### Description

Return a list containing the names of the columns of the relation.

##### Example

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
##### Result

```
 ['id', 'description', 'value', 'created_timestamp']
```
#### 
        
        `describe`
        
      

    
      ##### Signature

```
describe(self: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### Description

Gives basic statistics (e.g., min, max) and if NULL exists for each column of the relation.

##### Example

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
##### Result

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
        
        `description`
        
      

    
      ##### Description

Return the description of the result

##### Example

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
##### Result

```
[('id', 'UUID', None, None, None, None, None),
 ('description', 'STRING', None, None, None, None, None),
 ('value', 'NUMBER', None, None, None, None, None),
 ('created_timestamp', 'DATETIME', None, None, None, None, None)]  
```
#### 
        
        `dtypes`
        
      

    
      ##### Description

Return a list containing the types of the columns of the relation.

**Aliases**: `types`

##### Example

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
##### Result

```
 [UUID, VARCHAR, BIGINT, TIMESTAMP WITH TIME ZONE]
```
#### 
        
        `explain`
        
      

    
      ##### Description

explain(self: _duckdb.DuckDBPyRelation, type: _duckdb.ExplainType = 'standard') -> str

##### Example

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
##### Result

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
        
        `query`
        
      

    
      ##### Signature

```
query(self: _duckdb.DuckDBPyRelation, virtual_table_name: str, sql_query: str) -> _duckdb.DuckDBPyRelation
```
##### Description

Run the given SQL query in sql_query on the view named virtual_table_name that refers to the relation object

##### Parameters

- 
    **virtual_table_name**: strThe name to assign to the current relation when referenced in the SQL query. 
- 
    **sql_query**: strThe SQL query string that uses the virtual table name to query the relation. 

##### Example

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
##### Result

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
        
        `set_alias`
        
      

    
      ##### Signature

```
set_alias(self: _duckdb.DuckDBPyRelation, alias: str) -> _duckdb.DuckDBPyRelation
```
##### Description

Rename the relation object to new alias

##### Parameters

- 
    **alias**: strThe alias name to assign to the relation. 

##### Example

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
##### Result

```
In the SQL query, the alias will be `abc`
```
#### 
        
        `shape`
        
      

    
      ##### Description

Tuple of # of rows, # of columns in relation.

##### Example

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
##### Result

```
(9, 4)
```
#### 
        
        `show`
        
      

    
      ##### Signature

```
show(self: _duckdb.DuckDBPyRelation, *, max_width: typing.Optional[typing.SupportsInt] = None, max_rows: typing.Optional[typing.SupportsInt] = None, max_col_width: typing.Optional[typing.SupportsInt] = None, null_value: typing.Optional[str] = None, render_mode: object = None) -> None
```
##### Description

Display a summary of the data

##### Parameters

- 
    **max_width**: intMaximum display width for the entire output in characters. 
- 
    **max_rows**: intMaximum number of rows to display. 
- 
    **max_col_width**: intMaximum number of characters to display per column. 
- 
    **null_value**: strString to display in place of NULL values. 
- 
    **render_mode**: objectRender mode for displaying the output. 

##### Example

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
##### Result

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
        
        `sql_query`
        
      

    
      ##### Signature

```
sql_query(self: _duckdb.DuckDBPyRelation) -> str
```
##### Description

Get the SQL query that is equivalent to the relation

##### Example

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
##### Result

```
SELECT 
    gen_random_uuid() AS id, 
    concat('value is ', CASE  WHEN ((mod("range", 2) = 0)) THEN ('even') ELSE 'uneven' END) AS description, 
    "range" AS "value", 
    (now() + CAST(concat("range", ' ', 'minutes') AS INTERVAL)) AS created_timestamp 
FROM "range"(1, 10)
```
#### 
        
        `type`
        
      

    
      ##### Description

Get the type of the relation.

##### Example

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
##### Result

```
QUERY_RELATION
```
#### 
        
        `types`
        
      

    
      ##### Description

Return a list containing the types of the columns of the relation.

**Aliases**: `dtypes`

##### Example

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
##### Result

```
[UUID, VARCHAR, BIGINT, TIMESTAMP WITH TIME ZONE]
```
## Transformation

This section contains the methods which can be used to chain queries. The methods are lazy evaluated.

| Name | Description | 
|---|---|
| `aggregate` | Compute the aggregate aggr_expr by the optional groups group_expr on the relation | 
| `apply` | Compute the function of a single column or a list of columns by the optional groups on the relation | 
| `cross` | Create cross/cartesian product of two relational objects | 
| `except_` | Create the set except of this relation object with another relation object in other_rel | 
| `filter` | Filter the relation object by the filter in filter_expr | 
| `insert` | Inserts the given values into the relation | 
| `insert_into` | Inserts the relation object into an existing table named table_name | 
| `intersect` | Create the set intersection of this relation object with another relation object in other_rel | 
| `join` | Join the relation object with another relation object in other_rel using the join condition expression in join_condition. Types supported are 'inner', 'left', 'right', 'outer', 'semi' and 'anti' | 
| `limit` | Only retrieve the first n rows from this relation object, starting at offset | 
| `map` | Calls the passed function on the relation | 
| `order` | Reorder the relation object by order_expr | 
| `project` | Project the relation object by the projection in project_expr | 
| `select` | Project the relation object by the projection in project_expr | 
| `sort` | Reorder the relation object by the provided expressions | 
| `union` | Create the set union of this relation object with another relation object in other_rel | 
| `update` | Update the given relation with the provided expressions | 

#### 
        
        `aggregate`
        
      

    
      ##### Signature

```
aggregate(self: _duckdb.DuckDBPyRelation, aggr_expr: object, group_expr: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Compute the aggregate aggr_expr by the optional groups group_expr on the relation

##### Parameters

- 
    **aggr_expr**: str, list[Expression]The list of columns and aggregation functions. 
- 
    **group_expr**: str, default: ''The list of columns to be included in `group_by`. If`None`,`group by all`is applied.

##### Example

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
##### Result

```
┌──────────────┐
│ max("value") │
│    int64     │
├──────────────┤
│            9 │
└──────────────┘
        
```
#### 
        
        `apply`
        
      

    
      ##### Signature

```
apply(self: _duckdb.DuckDBPyRelation, function_name: str, function_aggr: str, group_expr: str = '', function_parameter: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Compute the function of a single column or a list of columns by the optional groups on the relation

##### Parameters

- 
    **function_name**: strName of the function to apply over the relation. 
- 
    **function_aggr**: strThe list of columns to apply the function over. 
- 
    **group_expr**: str, default: ''Optional SQL expression for grouping. 
- 
    **function_parameter**: str, default: ''Optional parameters to pass into the function. 
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `cross`
        
      

    
      ##### Signature

```
cross(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### Description

Create cross/cartesian product of two relational objects

##### Parameters

- 
    **other_rel**: _duckdb.DuckDBPyRelationAnother relation to perform a cross product with. 

##### Example

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
##### Result

```
┌─────────────────────────────┬─────────────────┬───────┬───────────────────────────┬──────────────────────────────────────┬─────────────────┬───────┬───────────────────────────┐
│             id              │   description   │ value │     created_timestamp     │                  id                  │   description   │ value │     created_timestamp     │
│            uuid             │     varchar     │ int64 │ timestamp with time zone  │                 uuid                 │     varchar     │ int64 │ timestamp with time zone  │
├─────────────────────────────┼─────────────────┼───────┼───────────────────────────┼──────────────────────────────────────┼─────────────────┼───────┼───────────────────────────┤
│ cb2b453f-1a06-4f5e-abe1-b…  │ value is uneven │     1 │ 2025-04-10 09:53:29.78+02 │ cb2b453f-1a06-4f5e-abe1-bfd413581bcf │ value is uneven │     1 │ 2025-04-10 09:53:29.78+02 │
...
```
#### 
        
        `except_`
        
      

    
      ##### Signature

```
except_(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### Description

Create the set except of this relation object with another relation object in other_rel

##### Parameters

- 
    **other_rel**: _duckdb.DuckDBPyRelationThe relation to subtract from the current relation (set difference). 

##### Example

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
##### Result

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
        
        `filter`
        
      

    
      ##### Signature

```
filter(self: _duckdb.DuckDBPyRelation, filter_expr: object) -> _duckdb.DuckDBPyRelation
```
##### Description

Filter the relation object by the filter in filter_expr

##### Parameters

- 
    **filter_expr**: str, ExpressionThe filter expression to apply over the relation. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┬───────────────┬───────┬───────────────────────────┐
│                  id                  │  description  │ value │     created_timestamp     │
│                 uuid                 │    varchar    │ int64 │ timestamp with time zone  │
├──────────────────────────────────────┼───────────────┼───────┼───────────────────────────┤
│ b0684ab7-fcbf-41c5-8e4a-a51bdde86926 │ value is even │     2 │ 2025-04-10 09:54:29.78+02 │
└──────────────────────────────────────┴───────────────┴───────┴───────────────────────────┘
```
#### 
        
        `insert`
        
      

    
      ##### Signature

```
insert(self: _duckdb.DuckDBPyRelation, values: object) -> None
```
##### Description

Inserts the given values into the relation

##### Parameters

- 
    **values**: objectA tuple of values matching the relation column list, to be inserted. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┬───────────────┬───────┬───────────────────────────────┐
│                  id                  │  description  │ value │       created_timestamp       │
│                 uuid                 │    varchar    │ int64 │   timestamp with time zone    │
├──────────────────────────────────────┼───────────────┼───────┼───────────────────────────────┤
│ c6dfab87-fae6-4213-8f76-1b96a8d179f6 │ value is even │    10 │ 2025-04-10 10:02:24.652218+02 │
└──────────────────────────────────────┴───────────────┴───────┴───────────────────────────────┘
```
#### 
        
        `insert_into`
        
      

    
      ##### Signature

```
insert_into(self: _duckdb.DuckDBPyRelation, table_name: str) -> None
```
##### Description

Inserts the relation object into an existing table named table_name

##### Parameters

- 
    **table_name**: strThe table name to insert the data into. The relation must respect the column order of the table. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┬───────────────┬───────┬───────────────────────────────┐
│                  id                  │  description  │ value │       created_timestamp       │
│                 uuid                 │    varchar    │ int64 │   timestamp with time zone    │
├──────────────────────────────────────┼───────────────┼───────┼───────────────────────────────┤
│ 271c5ddd-c1d5-4638-b5a0-d8c7dc9e8220 │ value is even │    10 │ 2025-04-10 14:29:18.616379+02 │
└──────────────────────────────────────┴───────────────┴───────┴───────────────────────────────┘
```
#### 
        
        `intersect`
        
      

    
      ##### Signature

```
intersect(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### Description

Create the set intersection of this relation object with another relation object in other_rel

##### Parameters

- 
    **other_rel**: _duckdb.DuckDBPyRelationThe relation to intersect with the current relation (set intersection). 

##### Example

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
##### Result

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
        
        `join`
        
      

    
      ##### Signature

```
join(self: _duckdb.DuckDBPyRelation, other_rel: _duckdb.DuckDBPyRelation, condition: object, how: str = 'inner') -> _duckdb.DuckDBPyRelation
```
##### Description

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

`NATURAL`,`POSITIONAL`and`ASOF`joins are not provided by the relational API.`CROSS`joins are provided through the cross method.

##### Parameters

- 
    **other_rel**: _duckdb.DuckDBPyRelationThe relation to join with the current relation. 
- 
    **condition**: objectThe join condition, typically a SQL expression or the duplicated column name to join on. 
- 
    **how**: str, default: 'inner'The type of join to perform: 'inner', 'left', 'right', 'outer', 'semi' and 'anti'. 

##### Example

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
##### Result

```
┌──────────────┐
│ count_star() │
│    int64     │
├──────────────┤
│            9 │
└──────────────┘
```
#### 
        
        `limit`
        
      

    
      ##### Signature

```
limit(self: _duckdb.DuckDBPyRelation, n: typing.SupportsInt, offset: typing.SupportsInt = 0) -> _duckdb.DuckDBPyRelation
```
##### Description

Only retrieve the first n rows from this relation object, starting at offset

##### Parameters

- 
    **n**: intThe maximum number of rows to return. 
- 
    **offset**: int, default: 0The number of rows to skip before starting to return rows. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 4135597b-29e7-4cb9-a443-41f3d54f25df │ value is uneven │     1 │ 2025-04-10 10:52:03.678+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        `map`
        
      

    
      ##### Signature

```
map(self: _duckdb.DuckDBPyRelation, map_function: collections.abc.Callable, *, schema: typing.Optional[object] = None) -> _duckdb.DuckDBPyRelation
```
##### Description

Calls the passed function on the relation

##### Parameters

- 
    **map_function**: CallableA Python function that takes a DataFrame and returns a transformed DataFrame. 
- 
    **schema**: object, default: NoneOptional schema describing the structure of the output relation. 

##### Example

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
##### Result

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
        
        `order`
        
      

    
      ##### Signature

```
order(self: _duckdb.DuckDBPyRelation, order_expr: str) -> _duckdb.DuckDBPyRelation
```
##### Description

Reorder the relation object by order_expr

##### Parameters

- 
    **order_expr**: strSQL expression defining the ordering of the result rows. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 55899131-e3d3-463c-a215-f65cb8aef3bf │ value is uneven │     5 │ 2025-04-10 10:56:03.678+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        `project`
        
      

    
      ##### Signature

```
project(self: _duckdb.DuckDBPyRelation, *args, groups: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Project the relation object by the projection in project_expr

**Aliases**: `select`

##### Parameters

- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.

##### Example

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
##### Result

```
┌─────────────────┐
│   description   │
│     varchar     │
├─────────────────┤
│ value is uneven │
└─────────────────┘
```
#### 
        
        `select`
        
      

    
      ##### Signature

```
select(self: _duckdb.DuckDBPyRelation, *args, groups: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Project the relation object by the projection in project_expr

**Aliases**: `project`

##### Parameters

- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.

##### Example

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
##### Result

```
┌─────────────────┐
│   description   │
│     varchar     │
├─────────────────┤
│ value is uneven │
└─────────────────┘
```
#### 
        
        `sort`
        
      

    
      ##### Signature

```
sort(self: _duckdb.DuckDBPyRelation, *args) -> _duckdb.DuckDBPyRelation
```
##### Description

Reorder the relation object by the provided expressions

##### Example

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
##### Result

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
        
        `union`
        
      

    
      ##### Signature

```
union(self: _duckdb.DuckDBPyRelation, union_rel: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### Description

Create the set union of this relation object with another relation object in other_rel

The union is

`union all`. In order to retrieve distinct values, apply distinct.

##### Parameters

- 
    **union_rel**: _duckdb.DuckDBPyRelationThe relation to union with the current relation (set union). 

##### Example

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
##### Result

```
┌──────────────┐
│ count_star() │
│    int64     │
├──────────────┤
│           18 │
└──────────────┘
```
#### 
        
        `update`
        
      

    
      ##### Signature

```
update(self: _duckdb.DuckDBPyRelation, set: object, *, condition: object = None) -> None
```
##### Description

Update the given relation with the provided expressions

##### Parameters

- 
    **set**: objectMapping of columns to new values for the update operation. 
- 
    **condition**: object, default: NoneOptional condition to filter which rows to update. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 66dcaa14-f4a6-4a55-af3b-7f6aa23ab4ad │ NULL            │     1 │ 2025-04-10 16:54:49.317+02 │
│ c6a18a42-67fb-4c95-827b-c966f2f95b88 │ value is even   │     2 │ 2025-04-10 16:55:49.317+02 │
...
```
## Functions

This section contains the functions which can be applied to a relation, in order to get a (scalar) result. The functions are lazy evaluated.

| Name | Description | 
|---|---|
| `any_value` | Returns the first non-null value from a given expression | 
| `arg_max` | Finds the row with the maximum value for a value column and returns the value of that row for an argument column | 
| `arg_min` | Finds the row with the minimum value for a value column and returns the value of that row for an argument column | 
| `avg` | Computes the average of a given expression | 
| `bit_and` | Computes the bitwise AND of all bits present in a given expression | 
| `bit_or` | Computes the bitwise OR of all bits present in a given expression | 
| `bit_xor` | Computes the bitwise XOR of all bits present in a given expression | 
| `bitstring_agg` | Computes a bitstring with bits set for each distinct value in a given expression | 
| `bool_and` | Computes the logical AND of all values present in a given expression | 
| `bool_or` | Computes the logical OR of all values present in a given expression | 
| `count` | Computes the number of elements present in a given expression | 
| `cume_dist` | Computes the cumulative distribution within the partition | 
| `dense_rank` | Computes the dense rank within the partition | 
| `distinct` | Retrieve distinct rows from this relation object | 
| `favg` | Computes the average of all values present in a given expression using a more accurate floating point summation (Kahan Sum) | 
| `first` | Returns the first value of a given expression | 
| `first_value` | Computes the first value within the group or partition | 
| `fsum` | Computes the sum of all values present in a given expression using a more accurate floating point summation (Kahan Sum) | 
| `geomean` | Computes the geometric mean over all values present in a given expression | 
| `histogram` | Computes the histogram over all values present in a given expression | 
| `lag` | Computes the lag within the partition | 
| `last` | Returns the last value of a given expression | 
| `last_value` | Computes the last value within the group or partition | 
| `lead` | Computes the lead within the partition | 
| `list` | Returns a list containing all values present in a given expression | 
| `max` | Returns the maximum value present in a given expression | 
| `mean` | Computes the average of a given expression | 
| `median` | Computes the median over all values present in a given expression | 
| `min` | Returns the minimum value present in a given expression | 
| `mode` | Computes the mode over all values present in a given expression | 
| `n_tile` | Divides the partition as equally as possible into num_buckets | 
| `nth_value` | Computes the nth value within the partition | 
| `percent_rank` | Computes the relative rank within the partition | 
| `product` | Returns the product of all values present in a given expression | 
| `quantile` | Computes the exact quantile value for a given expression | 
| `quantile_cont` | Computes the interpolated quantile value for a given expression | 
| `quantile_disc` | Computes the exact quantile value for a given expression | 
| `rank` | Computes the rank within the partition | 
| `rank_dense` | Computes the dense rank within the partition | 
| `row_number` | Computes the row number within the partition | 
| `select_dtypes` | Select columns from the relation, by filtering based on type(s) | 
| `select_types` | Select columns from the relation, by filtering based on type(s) | 
| `std` | Computes the sample standard deviation for a given expression | 
| `stddev` | Computes the sample standard deviation for a given expression | 
| `stddev_pop` | Computes the population standard deviation for a given expression | 
| `stddev_samp` | Computes the sample standard deviation for a given expression | 
| `string_agg` | Concatenates the values present in a given expression with a separator | 
| `sum` | Computes the sum of all values present in a given expression | 
| `unique` | Returns the distinct values in a column. | 
| `value_counts` | Computes the number of elements present in a given expression, also projecting the original expression | 
| `var` | Computes the sample variance for a given expression | 
| `var_pop` | Computes the population variance for a given expression | 
| `var_samp` | Computes the sample variance for a given expression | 
| `variance` | Computes the sample variance for a given expression | 

#### 
        
        `any_value`
        
      

    
      ##### Signature

```
any_value(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Returns the first non-null value from a given expression

##### Parameters

- 
    **column**: strThe column name from which to retrieve any value. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`.
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┐
│            any_value(id)             │
│                 uuid                 │
├──────────────────────────────────────┤
│ 642ea3d7-793d-4867-a759-91c1226c25a0 │
└──────────────────────────────────────┘
```
#### 
        
        `arg_max`
        
      

    
      ##### Signature

```
arg_max(self: _duckdb.DuckDBPyRelation, arg_column: str, value_column: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Finds the row with the maximum value for a value column and returns the value of that row for an argument column

##### Parameters

- 
    **arg_column**: strThe column name for which to find the argument maximizing the value. 
- 
    **value_column**: strThe column name containing values used to determine the maximum. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`.
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `arg_min`
        
      

    
      ##### Signature

```
arg_min(self: _duckdb.DuckDBPyRelation, arg_column: str, value_column: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Finds the row with the minimum value for a value column and returns the value of that row for an argument column

##### Parameters

- 
    **arg_column**: strThe column name for which to find the argument minimizing the value. 
- 
    **value_column**: strThe column name containing values used to determine the minimum. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `avg`
        
      

    
      ##### Signature

```
avg(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the average of a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the average on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

```
┌──────────────┐
│ avg("value") │
│    double    │
├──────────────┤
│          5.0 │
└──────────────┘
 
```
#### 
        
        `bit_and`
        
      

    
      ##### Signature

```
bit_and(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the bitwise AND of all bits present in a given expression

##### Parameters

- 
    **column**: strThe column name to perform the bitwise AND aggregation on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `bit_or`
        
      

    
      ##### Signature

```
bit_or(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the bitwise OR of all bits present in a given expression

##### Parameters

- 
    **column**: strThe column name to perform the bitwise OR aggregation on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `bit_xor`
        
      

    
      ##### Signature

```
bit_xor(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the bitwise XOR of all bits present in a given expression

##### Parameters

- 
    **column**: strThe column name to perform the bitwise XOR aggregation on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `bitstring_agg`
        
      

    
      ##### Signature

```
bitstring_agg(self: _duckdb.DuckDBPyRelation, expression: str, min: typing.Optional[object] = None, max: typing.Optional[object] = None, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes a bitstring with bits set for each distinct value in a given expression

##### Parameters

- 
    **column**: strThe column name to aggregate as a bitstring. 
- 
    **min**: object, default: NoneOptional minimum bitstring value for aggregation. 
- 
    **max**: object, default: NoneOptional maximum bitstring value for aggregation. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `bool_and`
        
      

    
      ##### Signature

```
bool_and(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the logical AND of all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to perform the boolean AND aggregation on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `bool_or`
        
      

    
      ##### Signature

```
bool_or(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the logical OR of all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to perform the boolean OR aggregation on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `count`
        
      

    
      ##### Signature

```
count(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the number of elements present in a given expression

##### Parameters

- 
    **column**: strThe column name to perform count on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

```
┌───────────┐
│ count(id) │
│   int64   │
├───────────┤
│         9 │
└───────────┘
```
#### 
        
        `cume_dist`
        
      

    
      ##### Signature

```
cume_dist(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the cumulative distribution within the partition

##### Parameters

- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `dense_rank`
        
      

    
      ##### Signature

```
dense_rank(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the dense rank within the partition

**Aliases**: `rank_dense`

##### Parameters

- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `distinct`
        
      

    
      ##### Signature

```
distinct(self: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### Description

Retrieve distinct rows from this relation object

##### Example

```
import duckdb
duckdb_conn = duckdb.connect()
rel = duckdb_conn.sql("select range from range(1,4)")
rel = rel.union(union_rel=rel)
rel.distinct().order("range")
```
##### Result

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
        
        `favg`
        
      

    
      ##### Signature

```
favg(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the average of all values present in a given expression using a more accurate floating point summation (Kahan Sum)

##### Parameters

- 
    **column**: strThe column name to calculate the average on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `first`
        
      

    
      ##### Signature

```
first(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Returns the first value of a given expression

##### Parameters

- 
    **column**: strThe column name from which to retrieve the first value. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `first_value`
        
      

    
      ##### Signature

```
first_value(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the first value within the group or partition

##### Parameters

- 
    **column**: strThe column name from which to retrieve the first value. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `fsum`
        
      

    
      ##### Signature

```
fsum(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sum of all values present in a given expression using a more accurate floating point summation (Kahan Sum)

##### Parameters

- 
    **column**: strThe column name to calculate the sum on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `geomean`
        
      

    
      ##### Signature

```
geomean(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the geometric mean over all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the geometric mean on. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `histogram`
        
      

    
      ##### Signature

```
histogram(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the histogram over all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the histogram on. 
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `lag`
        
      

    
      ##### Signature

```
lag(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str, offset: typing.SupportsInt = 1, default_value: str = 'NULL', ignore_nulls: bool = False, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the lag within the partition

##### Parameters

- 
    **column**: strThe column name to apply the lag function on. 
- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **offset**: int, default: 1The number of rows to lag behind. 
- 
    **default_value**: str, default: 'NULL'The default value to return when the lag offset goes out of bounds. 
- 
    **ignore_nulls**: bool, default: FalseWhether to ignore NULL values when computing the lag. 
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `last`
        
      

    
      ##### Signature

```
last(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Returns the last value of a given expression

##### Parameters

- 
    **column**: strThe column name from which to retrieve the last value. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `last_value`
        
      

    
      ##### Signature

```
last_value(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the last value within the group or partition

##### Parameters

- 
    **column**: strThe column name from which to retrieve the last value within the window. 
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `lead`
        
      

    
      ##### Signature

```
lead(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str, offset: typing.SupportsInt = 1, default_value: str = 'NULL', ignore_nulls: bool = False, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the lead within the partition

##### Parameters

- 
    **column**: strThe column name to apply the lead function on. 
- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **offset**: int, default: 1The number of rows to lead ahead. 
- 
    **default_value**: str, default: 'NULL'The default value to return when the lead offset goes out of bounds. 
- 
    **ignore_nulls**: bool, default: FalseWhether to ignore NULL values when computing the lead. 
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `list`
        
      

    
      ##### Signature

```
list(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Returns a list containing all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to aggregate values into a list. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `max`
        
      

    
      ##### Signature

```
max(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Returns the maximum value present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the maximum value of. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `mean`
        
      

    
      ##### Signature

```
mean(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the average of a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the mean value of. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `median`
        
      

    
      ##### Signature

```
median(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the median over all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the median value of. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `min`
        
      

    
      ##### Signature

```
min(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Returns the minimum value present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the min value of. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `mode`
        
      

    
      ##### Signature

```
mode(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the mode over all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the mode (most frequent value) of. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `n_tile`
        
      

    
      ##### Signature

```
n_tile(self: _duckdb.DuckDBPyRelation, window_spec: str, num_buckets: typing.SupportsInt, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Divides the partition as equally as possible into num_buckets

##### Parameters

- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **num_buckets**: intThe number of buckets to divide the rows into. 
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `nth_value`
        
      

    
      ##### Signature

```
nth_value(self: _duckdb.DuckDBPyRelation, expression: str, window_spec: str, offset: typing.SupportsInt, ignore_nulls: bool = False, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the nth value within the partition

##### Parameters

- 
    **column**: strThe column name from which to retrieve the nth value within the window. 
- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **offset**: intThe position of the value to retrieve within the window (1-based index). 
- 
    **ignore_nulls**: bool, default: FalseWhether to ignore NULL values when computing the nth value. 
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `percent_rank`
        
      

    
      ##### Signature

```
percent_rank(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the relative rank within the partition

##### Parameters

- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `product`
        
      

    
      ##### Signature

```
product(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Returns the product of all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the product of. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `quantile`
        
      

    
      ##### Signature

```
quantile(self: _duckdb.DuckDBPyRelation, expression: str, q: object = 0.5, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the exact quantile value for a given expression

##### Parameters

- 
    **column**: strThe column name to compute the quantile for. 
- 
    **q**: object, default: 0.5The quantile value to compute (e.g., 0.5 for median). 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `quantile_cont`
        
      

    
      ##### Signature

```
quantile_cont(self: _duckdb.DuckDBPyRelation, expression: str, q: object = 0.5, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the interpolated quantile value for a given expression

##### Parameters

- 
    **column**: strThe column name to compute the continuous quantile for. 
- 
    **q**: object, default: 0.5The quantile value to compute (e.g., 0.5 for median). 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `quantile_disc`
        
      

    
      ##### Signature

```
quantile_disc(self: _duckdb.DuckDBPyRelation, expression: str, q: object = 0.5, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the exact quantile value for a given expression

##### Parameters

- 
    **column**: strThe column name to compute the discrete quantile for. 
- 
    **q**: object, default: 0.5The quantile value to compute (e.g., 0.5 for median). 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `rank`
        
      

    
      ##### Signature

```
rank(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the rank within the partition

##### Parameters

- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `rank_dense`
        
      

    
      ##### Signature

```
rank_dense(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the dense rank within the partition

**Aliases**: `dense_rank`

##### Parameters

- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `row_number`
        
      

    
      ##### Signature

```
row_number(self: _duckdb.DuckDBPyRelation, window_spec: str, projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the row number within the partition

##### Parameters

- 
    **window_spec**: strOptional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `select_dtypes`
        
      

    
      ##### Signature

```
select_dtypes(self: _duckdb.DuckDBPyRelation, types: object) -> _duckdb.DuckDBPyRelation
```
##### Description

Select columns from the relation, by filtering based on type(s)

**Aliases**: `select_types`

##### Parameters

- 
    **types**: objectData type(s) to select columns by. Can be a single type or a collection of types. 

##### Example

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
##### Result

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
        
        `select_types`
        
      

    
      ##### Signature

```
select_types(self: _duckdb.DuckDBPyRelation, types: object) -> _duckdb.DuckDBPyRelation
```
##### Description

Select columns from the relation, by filtering based on type(s)

**Aliases**: `select_dtypes`

##### Parameters

- 
    **types**: objectData type(s) to select columns by. Can be a single type or a collection of types. 

##### Example

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
##### Result

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
        
        `std`
        
      

    
      ##### Signature

```
std(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sample standard deviation for a given expression

**Aliases**: `stddev`, `stddev_samp`

##### Parameters

- 
    **column**: strThe column name to calculate the standard deviation for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `stddev`
        
      

    
      ##### Signature

```
stddev(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sample standard deviation for a given expression

**Aliases**: `std`, `stddev_samp`

##### Parameters

- 
    **column**: strThe column name to calculate the standard deviation for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `stddev_pop`
        
      

    
      ##### Signature

```
stddev_pop(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the population standard deviation for a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the standard deviation for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `stddev_samp`
        
      

    
      ##### Signature

```
stddev_samp(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sample standard deviation for a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the standard deviation for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `string_agg`
        
      

    
      ##### Signature

```
string_agg(self: _duckdb.DuckDBPyRelation, expression: str, sep: str = ',', groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Concatenates the values present in a given expression with a separator

##### Parameters

- 
    **column**: strThe column name to concatenate values from. 
- 
    **sep**: str, default: ','Separator string to use between concatenated values. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `sum`
        
      

    
      ##### Signature

```
sum(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sum of all values present in a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the sum for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `unique`
        
      

    
      ##### Signature

```
unique(self: _duckdb.DuckDBPyRelation, unique_aggr: str) -> _duckdb.DuckDBPyRelation
```
##### Description

Returns the distinct values in a column.

##### Parameters

- 
    **unique_aggr**: strThe column to get the distinct values for. 

##### Example

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
##### Result

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
        
        `value_counts`
        
      

    
      ##### Signature

```
value_counts(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the number of elements present in a given expression, also projecting the original expression

##### Parameters

- 
    **column**: strThe column name to count values from. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.

##### Example

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
##### Result

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
        
        `var`
        
      

    
      ##### Signature

```
var(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sample variance for a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the sample variance for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `var_pop`
        
      

    
      ##### Signature

```
var_pop(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the population variance for a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the population variance for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `var_samp`
        
      

    
      ##### Signature

```
var_samp(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sample variance for a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the sample variance for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

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
        
        `variance`
        
      

    
      ##### Signature

```
variance(self: _duckdb.DuckDBPyRelation, expression: str, groups: str = '', window_spec: str = '', projected_columns: str = '') -> _duckdb.DuckDBPyRelation
```
##### Description

Computes the sample variance for a given expression

##### Parameters

- 
    **column**: strThe column name to calculate the sample variance for. 
- 
    **groups**: str, default: ''Comma-separated list of columns to include in the `group by`.
- 
    **window_spec**: str, default: ''Optional window specification for window functions, provided as `over (partition by ... order by ...)`
- 
    **projected_columns**: str, default: ''Comma-separated list of columns to include in the result. 

##### Example

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
##### Result

```
┌─────────────────┬───────────────────┐
│   description   │ var_samp("value") │
│     varchar     │      double       │
├─────────────────┼───────────────────┤
│ value is even   │ 6.666666666666667 │
│ value is uneven │              10.0 │
└─────────────────┴───────────────────┘
```
## Output

This section contains the functions which will trigger an SQL execution and retrieve the data.

| Name | Description | 
|---|---|
| `arrow` | Alias of to_arrow_reader(). We recommend using to_arrow_reader() instead. | 
| `close` | Closes the result | 
| `create` | Creates a new table named table_name with the contents of the relation object | 
| `create_view` | Creates a view named view_name that refers to the relation object | 
| `df` | Execute and fetch all rows as a pandas DataFrame | 
| `execute` | Transform the relation into a result set | 
| `fetch_arrow_reader` | Execute and return an Arrow Record Batch Reader that yields all rows | 
| `fetch_arrow_table` | Execute and fetch all rows as an Arrow Table | 
| `fetch_df_chunk` | Execute and fetch a chunk of the rows | 
| `fetch_record_batch` | Execute and return an Arrow Record Batch Reader that yields all rows | 
| `fetchall` | Execute and fetch all rows as a list of tuples | 
| `fetchdf` | Execute and fetch all rows as a pandas DataFrame | 
| `fetchmany` | Execute and fetch the next set of rows as a list of tuples | 
| `fetchnumpy` | Execute and fetch all rows as a Python dict mapping each column to one numpy arrays | 
| `fetchone` | Execute and fetch a single row as a tuple | 
| `pl` | Execute and fetch all rows as a Polars DataFrame | 
| `tf` | Fetch a result as dict of TensorFlow Tensors | 
| `to_arrow_reader` | Execute and return an Arrow Record Batch Reader that yields all rows | 
| `to_arrow_table` | Execute and fetch all rows as an Arrow Table | 
| `to_csv` | Write the relation object to a CSV file in 'file_name' | 
| `to_df` | Execute and fetch all rows as a pandas DataFrame | 
| `to_parquet` | Write the relation object to a Parquet file in 'file_name' | 
| `to_table` | Creates a new table named table_name with the contents of the relation object | 
| `to_view` | Creates a view named view_name that refers to the relation object | 
| `torch` | Fetch a result as dict of PyTorch Tensors | 
| `write_csv` | Write the relation object to a CSV file in 'file_name' | 
| `write_parquet` | Write the relation object to a Parquet file in 'file_name' | 

#### 
        
        `arrow`
        
      

    
      ##### Signature

```
arrow(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000) -> pyarrow.lib.RecordBatchReader
```
##### Description

Alias of to_arrow_reader(). We recommend using to_arrow_reader() instead.

We recommend using

`to_arrow_reader()`instead.

**Aliases**: `to_arrow_reader`

##### Parameters

- 
    **batch_size**: int, default: 1000000The batch size for fetching the data. 

##### Example

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
##### Result

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
        
        `close`
        
      

    
      ##### Signature

```
close(self: _duckdb.DuckDBPyRelation) -> None
```
##### Description

Closes the result

#### 
        
        `create`
        
      

    
      ##### Signature

```
create(self: _duckdb.DuckDBPyRelation, table_name: str) -> None
```
##### Description

Creates a new table named table_name with the contents of the relation object

**Aliases**: `to_table`

##### Parameters

- 
    **table_name**: strThe name of the table to be created. There shouldn't be any other table with the same name. 

##### Example

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
##### Result

```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 3ac9e0ba-8390-4a02-ad72-33b1caea6354 │ value is uneven │     1 │ 2025-04-10 11:07:12.614+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        `create_view`
        
      

    
      ##### Signature

```
create_view(self: _duckdb.DuckDBPyRelation, view_name: str, replace: bool = True) -> _duckdb.DuckDBPyRelation
```
##### Description

Creates a view named view_name that refers to the relation object

**Aliases**: `to_view`

##### Parameters

- 
    **view_name**: strThe name of the view to be created. 
- 
    **replace**: bool, default: TrueIf the view should be created with `CREATE OR REPLACE`. When set to`False`, there shouldn't be another view with the same`view_name`.

##### Example

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
##### Result

```
┌──────────────────────────────────────┬─────────────────┬───────┬────────────────────────────┐
│                  id                  │   description   │ value │     created_timestamp      │
│                 uuid                 │     varchar     │ int64 │  timestamp with time zone  │
├──────────────────────────────────────┼─────────────────┼───────┼────────────────────────────┤
│ 3ac9e0ba-8390-4a02-ad72-33b1caea6354 │ value is uneven │     1 │ 2025-04-10 11:07:12.614+02 │
└──────────────────────────────────────┴─────────────────┴───────┴────────────────────────────┘
```
#### 
        
        `df`
        
      

    
      ##### Signature

```
df(self: _duckdb.DuckDBPyRelation, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### Description

Execute and fetch all rows as a pandas DataFrame

##### Parameters

- 
    **date_as_object**: bool, default: FalseIf the date columns should be interpreted as Python date objects. 

##### Example

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
##### Result

```
                                     id      description  value                created_timestamp
0  3ac9e0ba-8390-4a02-ad72-33b1caea6354  value is uneven      1 2025-04-10 11:07:12.614000+02:00
1  8b844392-1404-4bbc-b731-120f42c8ca27    value is even      2 2025-04-10 11:08:12.614000+02:00
2  ca5584ca-8e97-4fca-a295-ae3c16c32f5b  value is uneven      3 2025-04-10 11:09:12.614000+02:00
...
```
#### 
        
        `execute`
        
      

    
      ##### Signature

```
execute(self: _duckdb.DuckDBPyRelation) -> _duckdb.DuckDBPyRelation
```
##### Description

Transform the relation into a result set

##### Example

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
##### Result

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
        
        `fetch_arrow_reader`
        
      

    
      ##### Signature

```
fetch_arrow_reader(self: object, batch_size: typing.SupportsInt = 1000000) -> object
```
##### Description

Execute and return an Arrow Record Batch Reader that yields all rows

Deprecated

`fetch_arrow_reader()`is deprecated. Use`to_arrow_reader()`instead.

##### Parameters

- 
    **batch_size**: int, default: 1000000The batch size for fetching the data. 

##### Example

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
##### Result

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
        
        `fetch_arrow_table`
        
      

    
      ##### Signature

```
fetch_arrow_table(self: object, batch_size: typing.SupportsInt = 1000000) -> object
```
##### Description

Execute and fetch all rows as an Arrow Table

Deprecated

`fetch_arrow_table()`is deprecated. Use`to_arrow_table()`instead.

**Aliases**: `arrow`, `to_arrow_table`

##### Parameters

- 
    **batch_size**: int, default: 1000000The batch size for fetching the data. 

##### Example

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
##### Result

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
        
        `fetch_df_chunk`
        
      

    
      ##### Signature

```
fetch_df_chunk(self: _duckdb.DuckDBPyRelation, vectors_per_chunk: typing.SupportsInt = 1, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### Description

Execute and fetch a chunk of the rows

##### Parameters

- 
    **vectors_per_chunk**: int, default: 1Number of data chunks to be processed before converting to dataframe. 
- 
    **date_as_object**: bool, default: FalseIf the date columns should be interpreted as Python date objects. 

##### Example

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
##### Result

```
                                     id      description  value                created_timestamp
0  1587b4b0-3023-49fe-82cf-06303ca136ac  value is uneven      1 2025-04-10 11:24:51.259000+02:00
1  e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd    value is even      2 2025-04-10 11:25:51.259000+02:00
2  3f8ad67a-290f-4a22-b41b-0173b8e45afa  value is uneven      3 2025-04-10 11:26:51.259000+02:00
...
```
#### 
        
        `fetch_record_batch`
        
      

    
      ##### Signature

```
fetch_record_batch(self: object, rows_per_batch: typing.SupportsInt = 1000000) -> object
```
##### Description

Execute and return an Arrow Record Batch Reader that yields all rows

Deprecated

`fetch_record_batch()`is deprecated. Use`to_arrow_reader()`instead.

**Aliases**: `record_batch`

##### Parameters

- 
    **rows_per_batch**: int, default: 1000000The number of rows per batch. 

##### Example

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
##### Result

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
        
        `fetchall`
        
      

    
      ##### Signature

```
fetchall(self: _duckdb.DuckDBPyRelation) -> list
```
##### Description

Execute and fetch all rows as a list of tuples

##### Example

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
##### Result

```
[(UUID('1587b4b0-3023-49fe-82cf-06303ca136ac'),
  'value is uneven',
  1,
  datetime.datetime(2025, 4, 10, 11, 24, 51, 259000, tzinfo=<DstTzInfo 'Europe/Amsterdam' CEST+2:00:00 DST>))]
```
#### 
        
        `fetchdf`
        
      

    
      ##### Signature

```
fetchdf(self: _duckdb.DuckDBPyRelation, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### Description

Execute and fetch all rows as a pandas DataFrame

##### Parameters

- 
    **date_as_object**: bool, default: FalseIf the date columns should be interpreted as Python date objects. 

##### Example

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
##### Result

```
                                     id      description  value                created_timestamp
0  1587b4b0-3023-49fe-82cf-06303ca136ac  value is uneven      1 2025-04-10 11:24:51.259000+02:00
1  e4ab8cb4-4609-40cb-ad7e-4304ed5ed4bd    value is even      2 2025-04-10 11:25:51.259000+02:00
2  3f8ad67a-290f-4a22-b41b-0173b8e45afa  value is uneven      3 2025-04-10 11:26:51.259000+02:00
...
```
#### 
        
        `fetchmany`
        
      

    
      ##### Signature

```
fetchmany(self: _duckdb.DuckDBPyRelation, size: typing.SupportsInt = 1) -> list
```
##### Description

Execute and fetch the next set of rows as a list of tuples

Warning Executing any operation during the retrieval of the data from an aggregate relation, will close the result set.

`import duckdb duckdb_conn = duckdb.connect() rel = duckdb_conn.sql(""" select gen_random_uuid() as id, concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description, range as value, now() + concat(range,' ', 'minutes')::interval as created_timestamp from range(1, 10) """ ) agg_rel = rel.aggregate("value") while res := agg_rel.fetchmany(size=1): print(res) rel.show()`

##### Parameters

- 
    **size**: int, default: 1The number of records to be fetched. 

##### Example

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
##### Result

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
        
        `fetchnumpy`
        
      

    
      ##### Signature

```
fetchnumpy(self: _duckdb.DuckDBPyRelation) -> dict
```
##### Description

Execute and fetch all rows as a Python dict mapping each column to one numpy arrays

##### Example

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
##### Result

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
        
        `fetchone`
        
      

    
      ##### Signature

```
fetchone(self: _duckdb.DuckDBPyRelation) -> typing.Optional[tuple]
```
##### Description

Execute and fetch a single row as a tuple

Warning Executing any operation during the retrieval of the data from an aggregate relation, will close the result set.

`import duckdb duckdb_conn = duckdb.connect() rel = duckdb_conn.sql(""" select gen_random_uuid() as id, concat('value is ', case when mod(range,2)=0 then 'even' else 'uneven' end) as description, range as value, now() + concat(range,' ', 'minutes')::interval as created_timestamp from range(1, 10) """ ) agg_rel = rel.aggregate("value") while res := agg_rel.fetchone(): print(res) rel.show()`

##### Example

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
##### Result

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
        
        `pl`
        
      

    
      ##### Signature

```
pl(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000, *, lazy: bool = False) -> duckdb::PolarsDataFrame
```
##### Description

Execute and fetch all rows as a Polars DataFrame

##### Parameters

- 
    **batch_size**: int, default: 1000000The number of records to be fetched per batch. 

##### Example

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
##### Result

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
        
        `tf`
        
      

    
      ##### Signature

```
tf(self: _duckdb.DuckDBPyRelation) -> dict
```
##### Description

Fetch a result as dict of TensorFlow Tensors

##### Example

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
##### Result

```
{'description': <tf.Tensor: shape=(9,), dtype=string, numpy=
 array([b'value is uneven', b'value is even', b'value is uneven',
        b'value is even', b'value is uneven', b'value is even',
        b'value is uneven', b'value is even', b'value is uneven'],
       dtype=object)>,
 'value': <tf.Tensor: shape=(9,), dtype=int64, numpy=array([1, 2, 3, 4, 5, 6, 7, 8, 9])>}
```
#### 
        
        `to_arrow_reader`
        
      

    
      ##### Signature

```
to_arrow_reader(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000) -> pyarrow.lib.RecordBatchReader
```
##### Description

Execute and return an Arrow Record Batch Reader that yields all rows

**Aliases**: `arrow`

##### Parameters

- 
    **batch_size**: int, default: 1000000The batch size for fetching the data. 

##### Example

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
##### Result

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
        
        `to_arrow_table`
        
      

    
      ##### Signature

```
to_arrow_table(self: _duckdb.DuckDBPyRelation, batch_size: typing.SupportsInt = 1000000) -> pyarrow.lib.Table
```
##### Description

Execute and fetch all rows as an Arrow Table

**Aliases**: `fetch_arrow_table`

##### Parameters

- 
    **batch_size**: int, default: 1000000The batch size for fetching the data. 

##### Example

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
##### Result

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
        
        `to_csv`
        
      

    
      ##### Signature

```
to_csv(self: _duckdb.DuckDBPyRelation, file_name: str, *, sep: object = None, na_rep: object = None, header: object = None, quotechar: object = None, escapechar: object = None, date_format: object = None, timestamp_format: object = None, quoting: object = None, encoding: object = None, compression: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None) -> None
```
##### Description

Write the relation object to a CSV file in 'file_name'

**Aliases**: `write_csv`

##### Parameters

- 
    **file_name**: strThe name of the output CSV file. 
- 
    **sep**: str, default: ','Field delimiter for the output file. 
- 
    **na_rep**: str, default: ''Missing data representation. 
- 
    **header**: bool, default: TrueWhether to write column headers. 
- 
    **quotechar**: str, default: '"'Character used to quote fields containing special characters. 
- 
    **escapechar**: str, default: NoneCharacter used to escape the delimiter if quoting is set to QUOTE_NONE. 
- 
    **date_format**: str, default: NoneCustom format string for DATE values. 
- 
    **timestamp_format**: str, default: NoneCustom format string for TIMESTAMP values. 
- 
    **quoting**: int, default: csv.QUOTE_MINIMALControl field quoting behavior (e.g., QUOTE_MINIMAL, QUOTE_ALL). 
- 
    **encoding**: str, default: 'utf-8'Character encoding for the output file. 
- 
    **compression**: str, default: autoCompression type (e.g., 'gzip', 'bz2', 'zstd'). 
- 
    **overwrite**: bool, default: FalseWhen true, all existing files inside targeted directories will be removed (not supported on remote filesystems). Only has an effect when used with `partition_by`.
- 
    **per_thread_output**: bool, default: FalseWhen `true`, write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file**: bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes. 
- 
    **partition_by**: list[str], default: NoneList of column names to partition output by (creates folder structure). 
- 
    **write_partition_columns**: bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by`.

##### Example

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
##### Result

```
The data is exported to a CSV file, named code_example.csv
```
#### 
        
        `to_df`
        
      

    
      ##### Signature

```
to_df(self: _duckdb.DuckDBPyRelation, *, date_as_object: bool = False) -> pandas.DataFrame
```
##### Description

Execute and fetch all rows as a pandas DataFrame

##### Parameters

- 
    **date_as_object**: bool, default: FalseIf the date columns should be interpreted as Python date objects. 

##### Example

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
##### Result

```
                                     id      description  value                created_timestamp
0  e1f79925-60fd-4ee2-ae67-5eff6b0543d1  value is uneven      1 2025-04-10 11:56:04.452000+02:00
1  caa619d4-d79c-4c00-b82e-9319b086b6f8    value is even      2 2025-04-10 11:57:04.452000+02:00
2  64c68032-99b9-4e8f-b4a3-6c522d5419b3  value is uneven      3 2025-04-10 11:58:04.452000+02:00
...
```
#### 
        
        `to_parquet`
        
      

    
      ##### Signature

```
to_parquet(self: _duckdb.DuckDBPyRelation, file_name: str, *, compression: object = None, field_ids: object = None, row_group_size_bytes: object = None, row_group_size: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None, append: object = None, filename_pattern: object = None, file_size_bytes: object = None) -> None
```
##### Description

Write the relation object to a Parquet file in 'file_name'

**Aliases**: `write_parquet`

##### Parameters

- 
    **file_name**: strThe name of the output Parquet file. 
- 
    **compression**: str, default: 'snappy'The compression format to use ( `uncompressed`,`snappy`,`gzip`,`zstd`,`brotli`,`lz4`,`lz4_raw`).
- 
    **field_ids**: STRUCTThe field_id for each column. Pass auto to attempt to infer automatically. 
- 
    **row_group_size_bytes**: int, default: row_group_size * 1024The target size of each row group. You can pass either a human-readable string, e.g., 2MB, or an integer, i.e., the number of bytes. This option is only used when you have issued `SET preserve_insertion_order = false;`, otherwise, it is ignored.
- 
    **row_group_size**: int, default: 122880The target size, i.e., number of rows, of each row group. 
- 
    **overwrite**: bool, default: FalseIf True, overwrite the file if it exists. 
- 
    **per_thread_output**: bool, default: FalseWhen `True`, write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file**: bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes. 
- 
    **partition_by**: list[str], default: NoneList of column names to partition output by (creates folder structure). 
- 
    **write_partition_columns**: bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by`.
- 
    **append**: bool, default: FalseWhen `True`, in the event a filename pattern is generated that already exists, the path will be regenerated to ensure no existing files are overwritten. Only has an effect when used with`partition_by`.

##### Example

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
##### Result

```
The data is exported to a Parquet file, named code_example.parquet
```
#### 
        
        `to_table`
        
      

    
      ##### Signature

```
to_table(self: _duckdb.DuckDBPyRelation, table_name: str) -> None
```
##### Description

Creates a new table named table_name with the contents of the relation object

**Aliases**: `create`

##### Parameters

- 
    **table_name**: strThe name of the table to be created. There shouldn't be any other table with the same name. 

##### Example

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
##### Result

```
A table, named table_code_example, is created with the data of the relation
```
#### 
        
        `to_view`
        
      

    
      ##### Signature

```
to_view(self: _duckdb.DuckDBPyRelation, view_name: str, replace: bool = True) -> _duckdb.DuckDBPyRelation
```
##### Description

Creates a view named view_name that refers to the relation object

**Aliases**: `create_view`

##### Parameters

- 
    **view_name**: strThe name of the view to be created. 
- 
    **replace**: bool, default: TrueIf the view should be created with `CREATE OR REPLACE`. When set to`False`, there shouldn't be another view with the same`view_name`.

##### Example

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
##### Result

```
A view, named view_code_example, is created with the query definition of the relation
```
#### 
        
        `torch`
        
      

    
      ##### Signature

```
torch(self: _duckdb.DuckDBPyRelation) -> dict
```
##### Description

Fetch a result as dict of PyTorch Tensors

##### Example

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
##### Result

```
{'value': tensor([1, 2, 3, 4, 5, 6, 7, 8, 9])}
```
#### 
        
        `write_csv`
        
      

    
      ##### Signature

```
write_csv(self: _duckdb.DuckDBPyRelation, file_name: str, *, sep: object = None, na_rep: object = None, header: object = None, quotechar: object = None, escapechar: object = None, date_format: object = None, timestamp_format: object = None, quoting: object = None, encoding: object = None, compression: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None) -> None
```
##### Description

Write the relation object to a CSV file in 'file_name'

**Aliases**: `to_csv`

##### Parameters

- 
    **file_name**: strThe name of the output CSV file. 
- 
    **sep**: str, default: ','Field delimiter for the output file. 
- 
    **na_rep**: str, default: ''Missing data representation. 
- 
    **header**: bool, default: TrueWhether to write column headers. 
- 
    **quotechar**: str, default: '"'Character used to quote fields containing special characters. 
- 
    **escapechar**: str, default: NoneCharacter used to escape the delimiter if quoting is set to QUOTE_NONE. 
- 
    **date_format**: str, default: NoneCustom format string for DATE values. 
- 
    **timestamp_format**: str, default: NoneCustom format string for TIMESTAMP values. 
- 
    **quoting**: int, default: csv.QUOTE_MINIMALControl field quoting behavior (e.g., QUOTE_MINIMAL, QUOTE_ALL). 
- 
    **encoding**: str, default: 'utf-8'Character encoding for the output file. 
- 
    **compression**: str, default: autoCompression type (e.g., 'gzip', 'bz2', 'zstd'). 
- 
    **overwrite**: bool, default: FalseWhen true, all existing files inside targeted directories will be removed (not supported on remote filesystems). Only has an effect when used with `partition_by`.
- 
    **per_thread_output**: bool, default: FalseWhen `true`, write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file**: bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes. 
- 
    **partition_by**: list[str], default: NoneList of column names to partition output by (creates folder structure). 
- 
    **write_partition_columns**: bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by`.

##### Example

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
##### Result

```
The data is exported to a CSV file, named code_example.csv
```
#### 
        
        `write_parquet`
        
      

    
      ##### Signature

```
write_parquet(self: _duckdb.DuckDBPyRelation, file_name: str, *, compression: object = None, field_ids: object = None, row_group_size_bytes: object = None, row_group_size: object = None, overwrite: object = None, per_thread_output: object = None, use_tmp_file: object = None, partition_by: object = None, write_partition_columns: object = None, append: object = None, filename_pattern: object = None, file_size_bytes: object = None) -> None
```
##### Description

Write the relation object to a Parquet file in 'file_name'

**Aliases**: `to_parquet`

##### Parameters

- 
    **file_name**: strThe name of the output Parquet file. 
- 
    **compression**: str, default: 'snappy'The compression format to use ( `uncompressed`,`snappy`,`gzip`,`zstd`,`brotli`,`lz4`,`lz4_raw`).
- 
    **field_ids**: STRUCTThe field_id for each column. Pass auto to attempt to infer automatically. 
- 
    **row_group_size_bytes**: int, default: row_group_size * 1024The target size of each row group. You can pass either a human-readable string, e.g., 2MB, or an integer, i.e., the number of bytes. This option is only used when you have issued `SET preserve_insertion_order = false;`, otherwise, it is ignored.
- 
    **row_group_size**: int, default: 122880The target size, i.e., number of rows, of each row group. 
- 
    **overwrite**: bool, default: FalseIf True, overwrite the file if it exists. 
- 
    **per_thread_output**: bool, default: FalseWhen `True`, write one file per thread, rather than one file in total. This allows for faster parallel writing.
- 
    **use_tmp_file**: bool, default: FalseWrite to a temporary file before renaming to final name to avoid partial writes. 
- 
    **partition_by**: list[str], default: NoneList of column names to partition output by (creates folder structure). 
- 
    **write_partition_columns**: bool, default: FalseWhether or not to write partition columns into files. Only has an effect when used with `partition_by`.
- 
    **append**: bool, default: FalseWhen `True`, in the event a filename pattern is generated that already exists, the path will be regenerated to ensure no existing files are overwritten. Only has an effect when used with`partition_by`.

##### Example

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
##### Result

```
The data is exported to a Parquet file, named code_example.parquet
```

# Citations

1. Source page: https://duckdb.org/docs/current/clients/python/relational_api
