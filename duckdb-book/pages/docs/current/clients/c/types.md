---
type: Web Page
title: Types – DuckDB
description: DuckDB is a strongly typed database system. As such, every column has
  a single type specified. This type is constant over the entire column. That is to
  say, a column that is labeled as an INTEGER column will only contain INTEGER values.
  DuckDB also supports columns of composite types. For example, it is possible to
  define an array of integers (INTEGER[]). It is also possible to define types as
  arbitrary structs (ROW(i INTEGER, j VARCHAR)). For that reason, native DuckDB type
  objects are not mere enums, but a class that can potentially be nested. Types in
  the C API are…
resource: https://duckdb.org/docs/current/clients/c/types
timestamp: '2026-07-09T12:17:10.843759+00:00'
---

DuckDB is a strongly typed database system. As such, every column has a single type specified. This type is constant
over the entire column. That is to say, a column that is labeled as an `INTEGER` column will only contain `INTEGER`
values.

DuckDB also supports columns of composite types. For example, it is possible to define an array of integers (`INTEGER[]`). It is also possible to define types as arbitrary structs (`ROW(i INTEGER, j VARCHAR)`). For that reason, native DuckDB type objects are not mere enums, but a class that can potentially be nested.

Types in the C API are modeled using an enum (`duckdb_type`) and a complex class (`duckdb_logical_type`). For most primitive types, e.g., integers or varchars, the enum is sufficient. For more complex types, such as lists, structs or decimals, the logical type must be used.

```
typedef enum DUCKDB_TYPE {
  DUCKDB_TYPE_INVALID = 0,
  DUCKDB_TYPE_BOOLEAN = 1,
  DUCKDB_TYPE_TINYINT = 2,
  DUCKDB_TYPE_SMALLINT = 3,
  DUCKDB_TYPE_INTEGER = 4,
  DUCKDB_TYPE_BIGINT = 5,
  DUCKDB_TYPE_UTINYINT = 6,
  DUCKDB_TYPE_USMALLINT = 7,
  DUCKDB_TYPE_UINTEGER = 8,
  DUCKDB_TYPE_UBIGINT = 9,
  DUCKDB_TYPE_FLOAT = 10,
  DUCKDB_TYPE_DOUBLE = 11,
  DUCKDB_TYPE_TIMESTAMP = 12,
  DUCKDB_TYPE_DATE = 13,
  DUCKDB_TYPE_TIME = 14,
  DUCKDB_TYPE_INTERVAL = 15,
  DUCKDB_TYPE_HUGEINT = 16,
  DUCKDB_TYPE_UHUGEINT = 32,
  DUCKDB_TYPE_VARCHAR = 17,
  DUCKDB_TYPE_BLOB = 18,
  DUCKDB_TYPE_DECIMAL = 19,
  DUCKDB_TYPE_TIMESTAMP_S = 20,
  DUCKDB_TYPE_TIMESTAMP_MS = 21,
  DUCKDB_TYPE_TIMESTAMP_NS = 22,
  DUCKDB_TYPE_ENUM = 23,
  DUCKDB_TYPE_LIST = 24,
  DUCKDB_TYPE_STRUCT = 25,
  DUCKDB_TYPE_MAP = 26,
  DUCKDB_TYPE_ARRAY = 33,
  DUCKDB_TYPE_UUID = 27,
  DUCKDB_TYPE_UNION = 28,
  DUCKDB_TYPE_BIT = 29,
  DUCKDB_TYPE_TIME_TZ = 30,
  DUCKDB_TYPE_TIMESTAMP_TZ = 31,
} duckdb_type;
```
## 
        
        [Functions](#functions)
        
      

    
The enum type of a column in the result can be obtained using the `duckdb_column_type` function. The logical type of a column can be obtained using the `duckdb_column_logical_type` function.

### 
        
        `duckdb_value`

    
`duckdb_value`The `duckdb_value` functions will auto-cast values as required. For example, it is no problem to use
`duckdb_value_double` on a column of type `duckdb_value_int32`. The value will be auto-cast and returned as a double.
Note that in certain cases the cast may fail. For example, this can happen if we request a `duckdb_value_int8` and the value does not fit within an `int8` value. In this case, a default value will be returned (usually `0` or `nullptr`). The same default value will also be returned if the corresponding value is `NULL`.

The `duckdb_value_is_null` function can be used to check if a specific value is `NULL` or not.

The exception to the auto-cast rule is the `duckdb_value_varchar_internal` function. This function does not auto-cast and only works for `VARCHAR` columns. The reason this function exists is that the result does not need to be freed.

`duckdb_value_varchar`and`duckdb_value_blob`require the result to be de-allocated using`duckdb_free`.

### 
        
        `duckdb_fetch_chunk`

    
`duckdb_fetch_chunk`The `duckdb_fetch_chunk` function can be used to read data chunks from a DuckDB result set, and is the most efficient way of reading data from a DuckDB result using the C API. It is also the only way of reading data of certain types from a DuckDB result. For example, the `duckdb_value` functions do not support structural reading of composite types (lists or structs) or more complex types like enums or decimals.

For more information about data chunks, see the [documentation on data chunks](/docs/current/clients/c/data_chunk.html).

## 
        
        [API Reference Overview](#api-reference-overview)
        
      

    
`duckdb_data_chunk `[duckdb_result_get_chunk](#duckdb_result_get_chunk)(duckdb_result result, idx_t chunk_index);
bool [duckdb_result_is_streaming](#duckdb_result_is_streaming)(duckdb_result result);
idx_t [duckdb_result_chunk_count](#duckdb_result_chunk_count)(duckdb_result result);
duckdb_result_type [duckdb_result_return_type](#duckdb_result_return_type)(duckdb_result result);
### 
        
        [Date Time Timestamp Helpers](#date-time-timestamp-helpers)
        
      

    
`duckdb_date_struct `[duckdb_from_date](#duckdb_from_date)(duckdb_date date);
duckdb_date [duckdb_to_date](#duckdb_to_date)(duckdb_date_struct date);
bool [duckdb_is_finite_date](#duckdb_is_finite_date)(duckdb_date date);
duckdb_time_struct [duckdb_from_time](#duckdb_from_time)(duckdb_time time);
duckdb_time_tz [duckdb_create_time_tz](#duckdb_create_time_tz)(int64_t micros, int32_t offset);
duckdb_time_tz_struct [duckdb_from_time_tz](#duckdb_from_time_tz)(duckdb_time_tz micros);
duckdb_time [duckdb_to_time](#duckdb_to_time)(duckdb_time_struct time);
duckdb_timestamp_struct [duckdb_from_timestamp](#duckdb_from_timestamp)(duckdb_timestamp ts);
duckdb_timestamp [duckdb_to_timestamp](#duckdb_to_timestamp)(duckdb_timestamp_struct ts);
bool [duckdb_is_finite_timestamp](#duckdb_is_finite_timestamp)(duckdb_timestamp ts);
bool [duckdb_is_finite_timestamp_s](#duckdb_is_finite_timestamp_s)(duckdb_timestamp_s ts);
bool [duckdb_is_finite_timestamp_ms](#duckdb_is_finite_timestamp_ms)(duckdb_timestamp_ms ts);
bool [duckdb_is_finite_timestamp_ns](#duckdb_is_finite_timestamp_ns)(duckdb_timestamp_ns ts);
### 
        
        [Hugeint Helpers](#hugeint-helpers)
        
      

    
`double `[duckdb_hugeint_to_double](#duckdb_hugeint_to_double)(duckdb_hugeint val);
duckdb_hugeint [duckdb_double_to_hugeint](#duckdb_double_to_hugeint)(double val);
### 
        
        [Decimal Helpers](#decimal-helpers)
        
      

    
`duckdb_decimal `[duckdb_double_to_decimal](#duckdb_double_to_decimal)(double val, uint8_t width, uint8_t scale);
double [duckdb_decimal_to_double](#duckdb_decimal_to_double)(duckdb_decimal val);
### 
        
        [Logical Type Interface](#logical-type-interface)
        
      

    
`duckdb_logical_type `[duckdb_create_logical_type](#duckdb_create_logical_type)(duckdb_type type);
char *[duckdb_logical_type_get_alias](#duckdb_logical_type_get_alias)(duckdb_logical_type type);
void [duckdb_logical_type_set_alias](#duckdb_logical_type_set_alias)(duckdb_logical_type type, const char *alias);
duckdb_logical_type [duckdb_create_list_type](#duckdb_create_list_type)(duckdb_logical_type type);
duckdb_logical_type [duckdb_create_array_type](#duckdb_create_array_type)(duckdb_logical_type type, idx_t array_size);
duckdb_logical_type [duckdb_create_map_type](#duckdb_create_map_type)(duckdb_logical_type key_type, duckdb_logical_type value_type);
duckdb_logical_type [duckdb_create_union_type](#duckdb_create_union_type)(duckdb_logical_type *member_types, const char **member_names, idx_t member_count);
duckdb_logical_type [duckdb_create_struct_type](#duckdb_create_struct_type)(duckdb_logical_type *member_types, const char **member_names, idx_t member_count);
duckdb_logical_type [duckdb_create_enum_type](#duckdb_create_enum_type)(const char **member_names, idx_t member_count);
duckdb_logical_type [duckdb_create_decimal_type](#duckdb_create_decimal_type)(uint8_t width, uint8_t scale);
duckdb_type [duckdb_get_type_id](#duckdb_get_type_id)(duckdb_logical_type type);
uint8_t [duckdb_decimal_width](#duckdb_decimal_width)(duckdb_logical_type type);
uint8_t [duckdb_decimal_scale](#duckdb_decimal_scale)(duckdb_logical_type type);
duckdb_type [duckdb_decimal_internal_type](#duckdb_decimal_internal_type)(duckdb_logical_type type);
duckdb_type [duckdb_enum_internal_type](#duckdb_enum_internal_type)(duckdb_logical_type type);
uint32_t [duckdb_enum_dictionary_size](#duckdb_enum_dictionary_size)(duckdb_logical_type type);
char *[duckdb_enum_dictionary_value](#duckdb_enum_dictionary_value)(duckdb_logical_type type, idx_t index);
duckdb_logical_type [duckdb_list_type_child_type](#duckdb_list_type_child_type)(duckdb_logical_type type);
duckdb_logical_type [duckdb_array_type_child_type](#duckdb_array_type_child_type)(duckdb_logical_type type);
idx_t [duckdb_array_type_array_size](#duckdb_array_type_array_size)(duckdb_logical_type type);
duckdb_logical_type [duckdb_map_type_key_type](#duckdb_map_type_key_type)(duckdb_logical_type type);
duckdb_logical_type [duckdb_map_type_value_type](#duckdb_map_type_value_type)(duckdb_logical_type type);
idx_t [duckdb_struct_type_child_count](#duckdb_struct_type_child_count)(duckdb_logical_type type);
char *[duckdb_struct_type_child_name](#duckdb_struct_type_child_name)(duckdb_logical_type type, idx_t index);
duckdb_logical_type [duckdb_struct_type_child_type](#duckdb_struct_type_child_type)(duckdb_logical_type type, idx_t index);
idx_t [duckdb_union_type_member_count](#duckdb_union_type_member_count)(duckdb_logical_type type);
char *[duckdb_union_type_member_name](#duckdb_union_type_member_name)(duckdb_logical_type type, idx_t index);
duckdb_logical_type [duckdb_union_type_member_type](#duckdb_union_type_member_type)(duckdb_logical_type type, idx_t index);
void [duckdb_destroy_logical_type](#duckdb_destroy_logical_type)(duckdb_logical_type *type);
duckdb_state [duckdb_register_logical_type](#duckdb_register_logical_type)(duckdb_connection con, duckdb_logical_type type, duckdb_create_type_info info);
#### 
        
        `duckdb_result_get_chunk`

    
`duckdb_result_get_chunk`Warning Deprecation notice. This method is scheduled for removal in a future release.

Fetches a data chunk from the duckdb_result. This function should be called repeatedly until the result is exhausted.

The result must be destroyed with `duckdb_destroy_data_chunk`.

This function supersedes all `duckdb_value` functions, as well as the `duckdb_column_data` and `duckdb_nullmask_data`
functions. It results in significantly better performance, and should be preferred in newer code-bases.

If this function is used, none of the other result functions can be used and vice versa (i.e., this function cannot be mixed with the legacy result functions).

Use `duckdb_result_chunk_count` to figure out how many chunks there are in the result.

##### 
        
        [Syntax](#syntax)
        
      

    
```
duckdb_data_chunk duckdb_result_get_chunk(
  duckdb_result result,
  idx_t chunk_index
);
```
##### 
        
        [Parameters](#parameters)
        
      

    
- `result`: The result object to fetch the data chunk from.
- `chunk_index`: The chunk index to fetch from.

##### 
        
        [Return Value](#return-value)
        
      

    
The resulting data chunk. Returns `NULL` if the chunk index is out of bounds.

#### 
        
        `duckdb_result_is_streaming`

    
`duckdb_result_is_streaming`Warning Deprecation notice. This method is scheduled for removal in a future release.

Checks if the type of the internal result is StreamQueryResult.

##### 
        
        [Syntax](#syntax-1)
        
      

    
```
bool duckdb_result_is_streaming(
  duckdb_result result
);
```
##### 
        
        [Parameters](#parameters-1)
        
      

    
- `result`: The result object to check.

##### 
        
        [Return Value](#return-value-1)
        
      

    
Whether or not the result object is of the type StreamQueryResult

#### 
        
        `duckdb_result_chunk_count`

    
`duckdb_result_chunk_count`Warning Deprecation notice. This method is scheduled for removal in a future release.

Returns the number of data chunks present in the result.

##### 
        
        [Syntax](#syntax-2)
        
      

    
```
idx_t duckdb_result_chunk_count(
  duckdb_result result
);
```
##### 
        
        [Parameters](#parameters-2)
        
      

    
- `result`: The result object

##### 
        
        [Return Value](#return-value-2)
        
      

    
Number of data chunks present in the result.

#### 
        
        `duckdb_result_return_type`

    
`duckdb_result_return_type`Returns the return_type of the given result, or DUCKDB_RETURN_TYPE_INVALID on error

##### 
        
        [Syntax](#syntax-3)
        
      

    
```
duckdb_result_type duckdb_result_return_type(
  duckdb_result result
);
```
##### 
        
        [Parameters](#parameters-3)
        
      

    
- `result`: The result object

##### 
        
        [Return Value](#return-value-3)
        
      

    
The return_type

#### 
        
        `duckdb_from_date`

    
`duckdb_from_date`Decompose a `duckdb_date` object into year, month and date (stored as `duckdb_date_struct`).

##### 
        
        [Syntax](#syntax-4)
        
      

    
```
duckdb_date_struct duckdb_from_date(
  duckdb_date date
);
```
##### 
        
        [Parameters](#parameters-4)
        
      

    
- `date`: The date object, as obtained from a- `DUCKDB_TYPE_DATE`column.

##### 
        
        [Return Value](#return-value-4)
        
      

    
The `duckdb_date_struct` with the decomposed elements.

#### 
        
        `duckdb_to_date`

    
`duckdb_to_date`Re-compose a `duckdb_date` from year, month and date (`duckdb_date_struct`).

##### 
        
        [Syntax](#syntax-5)
        
      

    
```
duckdb_date duckdb_to_date(
  duckdb_date_struct date
);
```
##### 
        
        [Parameters](#parameters-5)
        
      

    
- `date`: The year, month and date stored in a- `duckdb_date_struct`.

##### 
        
        [Return Value](#return-value-5)
        
      

    
The `duckdb_date` element.

#### 
        
        `duckdb_is_finite_date`

    
`duckdb_is_finite_date`Test a `duckdb_date` to see if it is a finite value.

##### 
        
        [Syntax](#syntax-6)
        
      

    
```
bool duckdb_is_finite_date(
  duckdb_date date
);
```
##### 
        
        [Parameters](#parameters-6)
        
      

    
- `date`: The date object, as obtained from a- `DUCKDB_TYPE_DATE`column.

##### 
        
        [Return Value](#return-value-6)
        
      

    
True if the date is finite, false if it is ±infinity.

#### 
        
        `duckdb_from_time`

    
`duckdb_from_time`Decompose a `duckdb_time` object into hour, minute, second and microsecond (stored as `duckdb_time_struct`).

##### 
        
        [Syntax](#syntax-7)
        
      

    
```
duckdb_time_struct duckdb_from_time(
  duckdb_time time
);
```
##### 
        
        [Parameters](#parameters-7)
        
      

    
- `time`: The time object, as obtained from a- `DUCKDB_TYPE_TIME`column.

##### 
        
        [Return Value](#return-value-7)
        
      

    
The `duckdb_time_struct` with the decomposed elements.

#### 
        
        `duckdb_create_time_tz`

    
`duckdb_create_time_tz`Create a `duckdb_time_tz` object from micros and a timezone offset.

##### 
        
        [Syntax](#syntax-8)
        
      

    
```
duckdb_time_tz duckdb_create_time_tz(
  int64_t micros,
  int32_t offset
);
```
##### 
        
        [Parameters](#parameters-8)
        
      

    
- `micros`: The microsecond component of the time.
- `offset`: The timezone offset component of the time.

##### 
        
        [Return Value](#return-value-8)
        
      

    
The `duckdb_time_tz` element.

#### 
        
        `duckdb_from_time_tz`

    
`duckdb_from_time_tz`Decompose a TIME_TZ objects into micros and a timezone offset.

Use `duckdb_from_time` to further decompose the micros into hour, minute, second and microsecond.

##### 
        
        [Syntax](#syntax-9)
        
      

    
```
duckdb_time_tz_struct duckdb_from_time_tz(
  duckdb_time_tz micros
);
```
##### 
        
        [Parameters](#parameters-9)
        
      

    
- `micros`: The time object, as obtained from a- `DUCKDB_TYPE_TIME_TZ`column.

#### 
        
        `duckdb_to_time`

    
`duckdb_to_time`Re-compose a `duckdb_time` from hour, minute, second and microsecond (`duckdb_time_struct`).

##### 
        
        [Syntax](#syntax-10)
        
      

    
```
duckdb_time duckdb_to_time(
  duckdb_time_struct time
);
```
##### 
        
        [Parameters](#parameters-10)
        
      

    
- `time`: The hour, minute, second and microsecond in a- `duckdb_time_struct`.

##### 
        
        [Return Value](#return-value-9)
        
      

    
The `duckdb_time` element.

#### 
        
        `duckdb_from_timestamp`

    
`duckdb_from_timestamp`Decompose a `duckdb_timestamp` object into a `duckdb_timestamp_struct`.

##### 
        
        [Syntax](#syntax-11)
        
      

    
```
duckdb_timestamp_struct duckdb_from_timestamp(
  duckdb_timestamp ts
);
```
##### 
        
        [Parameters](#parameters-11)
        
      

    
- `ts`: The ts object, as obtained from a- `DUCKDB_TYPE_TIMESTAMP`column.

##### 
        
        [Return Value](#return-value-10)
        
      

    
The `duckdb_timestamp_struct` with the decomposed elements.

#### 
        
        `duckdb_to_timestamp`

    
`duckdb_to_timestamp`Re-compose a `duckdb_timestamp` from a duckdb_timestamp_struct.

##### 
        
        [Syntax](#syntax-12)
        
      

    
```
duckdb_timestamp duckdb_to_timestamp(
  duckdb_timestamp_struct ts
);
```
##### 
        
        [Parameters](#parameters-12)
        
      

    
- `ts`: The de-composed elements in a- `duckdb_timestamp_struct`.

##### 
        
        [Return Value](#return-value-11)
        
      

    
The `duckdb_timestamp` element.

#### 
        
        `duckdb_is_finite_timestamp`

    
`duckdb_is_finite_timestamp`Test a `duckdb_timestamp` to see if it is a finite value.

##### 
        
        [Syntax](#syntax-13)
        
      

    
```
bool duckdb_is_finite_timestamp(
  duckdb_timestamp ts
);
```
##### 
        
        [Parameters](#parameters-13)
        
      

    
- `ts`: The duckdb_timestamp object, as obtained from a- `DUCKDB_TYPE_TIMESTAMP`column.

##### 
        
        [Return Value](#return-value-12)
        
      

    
True if the timestamp is finite, false if it is ±infinity.

#### 
        
        `duckdb_is_finite_timestamp_s`

    
`duckdb_is_finite_timestamp_s`Test a `duckdb_timestamp_s` to see if it is a finite value.

##### 
        
        [Syntax](#syntax-14)
        
      

    
```
bool duckdb_is_finite_timestamp_s(
  duckdb_timestamp_s ts
);
```
##### 
        
        [Parameters](#parameters-14)
        
      

    
- `ts`: The duckdb_timestamp_s object, as obtained from a- `DUCKDB_TYPE_TIMESTAMP_S`column.

##### 
        
        [Return Value](#return-value-13)
        
      

    
True if the timestamp is finite, false if it is ±infinity.

#### 
        
        `duckdb_is_finite_timestamp_ms`

    
`duckdb_is_finite_timestamp_ms`Test a `duckdb_timestamp_ms` to see if it is a finite value.

##### 
        
        [Syntax](#syntax-15)
        
      

    
```
bool duckdb_is_finite_timestamp_ms(
  duckdb_timestamp_ms ts
);
```
##### 
        
        [Parameters](#parameters-15)
        
      

    
- `ts`: The duckdb_timestamp_ms object, as obtained from a- `DUCKDB_TYPE_TIMESTAMP_MS`column.

##### 
        
        [Return Value](#return-value-14)
        
      

    
True if the timestamp is finite, false if it is ±infinity.

#### 
        
        `duckdb_is_finite_timestamp_ns`

    
`duckdb_is_finite_timestamp_ns`Test a `duckdb_timestamp_ns` to see if it is a finite value.

##### 
        
        [Syntax](#syntax-16)
        
      

    
```
bool duckdb_is_finite_timestamp_ns(
  duckdb_timestamp_ns ts
);
```
##### 
        
        [Parameters](#parameters-16)
        
      

    
- `ts`: The duckdb_timestamp_ns object, as obtained from a- `DUCKDB_TYPE_TIMESTAMP_NS`column.

##### 
        
        [Return Value](#return-value-15)
        
      

    
True if the timestamp is finite, false if it is ±infinity.

#### 
        
        `duckdb_hugeint_to_double`

    
`duckdb_hugeint_to_double`Converts a duckdb_hugeint object (as obtained from a `DUCKDB_TYPE_HUGEINT` column) into a double.

##### 
        
        [Syntax](#syntax-17)
        
      

    
```
double duckdb_hugeint_to_double(
  duckdb_hugeint val
);
```
##### 
        
        [Parameters](#parameters-17)
        
      

    
- `val`: The hugeint value.

##### 
        
        [Return Value](#return-value-16)
        
      

    
The converted `double` element.

#### 
        
        `duckdb_double_to_hugeint`

    
`duckdb_double_to_hugeint`Converts a double value to a duckdb_hugeint object.

If the conversion fails because the double value is too big the result will be 0.

##### 
        
        [Syntax](#syntax-18)
        
      

    
```
duckdb_hugeint duckdb_double_to_hugeint(
  double val
);
```
##### 
        
        [Parameters](#parameters-18)
        
      

    
- `val`: The double value.

##### 
        
        [Return Value](#return-value-17)
        
      

    
The converted `duckdb_hugeint` element.

#### 
        
        `duckdb_double_to_decimal`

    
`duckdb_double_to_decimal`Converts a double value to a duckdb_decimal object.

If the conversion fails because the double value is too big, or the width/scale are invalid the result will be 0.

##### 
        
        [Syntax](#syntax-19)
        
      

    
```
duckdb_decimal duckdb_double_to_decimal(
  double val,
  uint8_t width,
  uint8_t scale
);
```
##### 
        
        [Parameters](#parameters-19)
        
      

    
- `val`: The double value.

##### 
        
        [Return Value](#return-value-18)
        
      

    
The converted `duckdb_decimal` element.

#### 
        
        `duckdb_decimal_to_double`

    
`duckdb_decimal_to_double`Converts a duckdb_decimal object (as obtained from a `DUCKDB_TYPE_DECIMAL` column) into a double.

##### 
        
        [Syntax](#syntax-20)
        
      

    
```
double duckdb_decimal_to_double(
  duckdb_decimal val
);
```
##### 
        
        [Parameters](#parameters-20)
        
      

    
- `val`: The decimal value.

##### 
        
        [Return Value](#return-value-19)
        
      

    
The converted `double` element.

#### 
        
        `duckdb_create_logical_type`

    
`duckdb_create_logical_type`Creates a `duckdb_logical_type` from a primitive type.
The resulting logical type must be destroyed with `duckdb_destroy_logical_type`.

Returns an invalid logical type, if type is: `DUCKDB_TYPE_INVALID`, `DUCKDB_TYPE_DECIMAL`, `DUCKDB_TYPE_ENUM`,
`DUCKDB_TYPE_LIST`, `DUCKDB_TYPE_STRUCT`, `DUCKDB_TYPE_MAP`, `DUCKDB_TYPE_ARRAY`, or `DUCKDB_TYPE_UNION`.

##### 
        
        [Syntax](#syntax-21)
        
      

    
```
duckdb_logical_type duckdb_create_logical_type(
  duckdb_type type
);
```
##### 
        
        [Parameters](#parameters-21)
        
      

    
- `type`: The primitive type to create.

##### 
        
        [Return Value](#return-value-20)
        
      

    
The logical type.

#### 
        
        `duckdb_logical_type_get_alias`

    
`duckdb_logical_type_get_alias`Returns the alias of a duckdb_logical_type, if set, else `nullptr`.
The result must be destroyed with `duckdb_free`.

##### 
        
        [Syntax](#syntax-22)
        
      

    
```
char *duckdb_logical_type_get_alias(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-22)
        
      

    
- `type`: The logical type

##### 
        
        [Return Value](#return-value-21)
        
      

    
The alias or `nullptr`

#### 
        
        `duckdb_logical_type_set_alias`

    
`duckdb_logical_type_set_alias`Sets the alias of a duckdb_logical_type.

##### 
        
        [Syntax](#syntax-23)
        
      

    
```
void duckdb_logical_type_set_alias(
  duckdb_logical_type type,
  const char *alias
);
```
##### 
        
        [Parameters](#parameters-23)
        
      

    
- `type`: The logical type
- `alias`: The alias to set

#### 
        
        `duckdb_create_list_type`

    
`duckdb_create_list_type`Creates a LIST type from its child type.
The return type must be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-24)
        
      

    
```
duckdb_logical_type duckdb_create_list_type(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-24)
        
      

    
- `type`: The child type of the list

##### 
        
        [Return Value](#return-value-22)
        
      

    
The logical type.

#### 
        
        `duckdb_create_array_type`

    
`duckdb_create_array_type`Creates an ARRAY type from its child type.
The return type must be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-25)
        
      

    
```
duckdb_logical_type duckdb_create_array_type(
  duckdb_logical_type type,
  idx_t array_size
);
```
##### 
        
        [Parameters](#parameters-25)
        
      

    
- `type`: The child type of the array.
- `array_size`: The number of elements in the array.

##### 
        
        [Return Value](#return-value-23)
        
      

    
The logical type.

#### 
        
        `duckdb_create_map_type`

    
`duckdb_create_map_type`Creates a MAP type from its key type and value type.
The return type must be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-26)
        
      

    
```
duckdb_logical_type duckdb_create_map_type(
  duckdb_logical_type key_type,
  duckdb_logical_type value_type
);
```
##### 
        
        [Parameters](#parameters-26)
        
      

    
- `key_type`: The map's key type.
- `value_type`: The map's value type.

##### 
        
        [Return Value](#return-value-24)
        
      

    
The logical type.

#### 
        
        `duckdb_create_union_type`

    
`duckdb_create_union_type`Creates a UNION type from the passed arrays.
The return type must be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-27)
        
      

    
```
duckdb_logical_type duckdb_create_union_type(
  duckdb_logical_type *member_types,
  const char **member_names,
  idx_t member_count
);
```
##### 
        
        [Parameters](#parameters-27)
        
      

    
- `member_types`: The array of union member types.
- `member_names`: The union member names.
- `member_count`: The number of union members.

##### 
        
        [Return Value](#return-value-25)
        
      

    
The logical type.

#### 
        
        `duckdb_create_struct_type`

    
`duckdb_create_struct_type`Creates a STRUCT type based on the member types and names.
The resulting type must be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-28)
        
      

    
```
duckdb_logical_type duckdb_create_struct_type(
  duckdb_logical_type *member_types,
  const char **member_names,
  idx_t member_count
);
```
##### 
        
        [Parameters](#parameters-28)
        
      

    
- `member_types`: The array of types of the struct members.
- `member_names`: The array of names of the struct members.
- `member_count`: The number of members of the struct.

##### 
        
        [Return Value](#return-value-26)
        
      

    
The logical type.

#### 
        
        `duckdb_create_enum_type`

    
`duckdb_create_enum_type`Creates an ENUM type from the passed member name array.
The resulting type should be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-29)
        
      

    
```
duckdb_logical_type duckdb_create_enum_type(
  const char **member_names,
  idx_t member_count
);
```
##### 
        
        [Parameters](#parameters-29)
        
      

    
- `member_names`: The array of names that the enum should consist of.
- `member_count`: The number of elements that were specified in the array.

##### 
        
        [Return Value](#return-value-27)
        
      

    
The logical type.

#### 
        
        `duckdb_create_decimal_type`

    
`duckdb_create_decimal_type`Creates a DECIMAL type with the specified width and scale.
The resulting type should be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-30)
        
      

    
```
duckdb_logical_type duckdb_create_decimal_type(
  uint8_t width,
  uint8_t scale
);
```
##### 
        
        [Parameters](#parameters-30)
        
      

    
- `width`: The width of the decimal type
- `scale`: The scale of the decimal type

##### 
        
        [Return Value](#return-value-28)
        
      

    
The logical type.

#### 
        
        `duckdb_get_type_id`

    
`duckdb_get_type_id`Retrieves the enum `duckdb_type` of a `duckdb_logical_type`.

##### 
        
        [Syntax](#syntax-31)
        
      

    
```
duckdb_type duckdb_get_type_id(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-31)
        
      

    
- `type`: The logical type.

##### 
        
        [Return Value](#return-value-29)
        
      

    
The `duckdb_type` id.

#### 
        
        `duckdb_decimal_width`

    
`duckdb_decimal_width`Retrieves the width of a decimal type.

##### 
        
        [Syntax](#syntax-32)
        
      

    
```
uint8_t duckdb_decimal_width(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-32)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-30)
        
      

    
The width of the decimal type

#### 
        
        `duckdb_decimal_scale`

    
`duckdb_decimal_scale`Retrieves the scale of a decimal type.

##### 
        
        [Syntax](#syntax-33)
        
      

    
```
uint8_t duckdb_decimal_scale(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-33)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-31)
        
      

    
The scale of the decimal type

#### 
        
        `duckdb_decimal_internal_type`

    
`duckdb_decimal_internal_type`Retrieves the internal storage type of a decimal type.

##### 
        
        [Syntax](#syntax-34)
        
      

    
```
duckdb_type duckdb_decimal_internal_type(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-34)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-32)
        
      

    
The internal type of the decimal type

#### 
        
        `duckdb_enum_internal_type`

    
`duckdb_enum_internal_type`Retrieves the internal storage type of an enum type.

##### 
        
        [Syntax](#syntax-35)
        
      

    
```
duckdb_type duckdb_enum_internal_type(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-35)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-33)
        
      

    
The internal type of the enum type

#### 
        
        `duckdb_enum_dictionary_size`

    
`duckdb_enum_dictionary_size`Retrieves the dictionary size of the enum type.

##### 
        
        [Syntax](#syntax-36)
        
      

    
```
uint32_t duckdb_enum_dictionary_size(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-36)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-34)
        
      

    
The dictionary size of the enum type

#### 
        
        `duckdb_enum_dictionary_value`

    
`duckdb_enum_dictionary_value`Retrieves the dictionary value at the specified position from the enum.

The result must be freed with `duckdb_free`.

##### 
        
        [Syntax](#syntax-37)
        
      

    
```
char *duckdb_enum_dictionary_value(
  duckdb_logical_type type,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-37)
        
      

    
- `type`: The logical type object
- `index`: The index in the dictionary

##### 
        
        [Return Value](#return-value-35)
        
      

    
The string value of the enum type. Must be freed with `duckdb_free`.

#### 
        
        `duckdb_list_type_child_type`

    
`duckdb_list_type_child_type`Retrieves the child type of the given LIST type. Also accepts MAP types.
The result must be freed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-38)
        
      

    
```
duckdb_logical_type duckdb_list_type_child_type(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-38)
        
      

    
- `type`: The logical type, either LIST or MAP.

##### 
        
        [Return Value](#return-value-36)
        
      

    
The child type of the LIST or MAP type.

#### 
        
        `duckdb_array_type_child_type`

    
`duckdb_array_type_child_type`Retrieves the child type of the given ARRAY type.

The result must be freed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-39)
        
      

    
```
duckdb_logical_type duckdb_array_type_child_type(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-39)
        
      

    
- `type`: The logical type. Must be ARRAY.

##### 
        
        [Return Value](#return-value-37)
        
      

    
The child type of the ARRAY type.

#### 
        
        `duckdb_array_type_array_size`

    
`duckdb_array_type_array_size`Retrieves the array size of the given array type.

##### 
        
        [Syntax](#syntax-40)
        
      

    
```
idx_t duckdb_array_type_array_size(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-40)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-38)
        
      

    
The fixed number of elements the values of this array type can store.

#### 
        
        `duckdb_map_type_key_type`

    
`duckdb_map_type_key_type`Retrieves the key type of the given map type.

The result must be freed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-41)
        
      

    
```
duckdb_logical_type duckdb_map_type_key_type(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-41)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-39)
        
      

    
The key type of the map type. Must be destroyed with `duckdb_destroy_logical_type`.

#### 
        
        `duckdb_map_type_value_type`

    
`duckdb_map_type_value_type`Retrieves the value type of the given map type.

The result must be freed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-42)
        
      

    
```
duckdb_logical_type duckdb_map_type_value_type(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-42)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-40)
        
      

    
The value type of the map type. Must be destroyed with `duckdb_destroy_logical_type`.

#### 
        
        `duckdb_struct_type_child_count`

    
`duckdb_struct_type_child_count`Returns the number of children of a struct type.

##### 
        
        [Syntax](#syntax-43)
        
      

    
```
idx_t duckdb_struct_type_child_count(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-43)
        
      

    
- `type`: The logical type object

##### 
        
        [Return Value](#return-value-41)
        
      

    
The number of children of a struct type.

#### 
        
        `duckdb_struct_type_child_name`

    
`duckdb_struct_type_child_name`Retrieves the name of the struct child.

The result must be freed with `duckdb_free`.

##### 
        
        [Syntax](#syntax-44)
        
      

    
```
char *duckdb_struct_type_child_name(
  duckdb_logical_type type,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-44)
        
      

    
- `type`: The logical type object
- `index`: The child index

##### 
        
        [Return Value](#return-value-42)
        
      

    
The name of the struct type. Must be freed with `duckdb_free`.

#### 
        
        `duckdb_struct_type_child_type`

    
`duckdb_struct_type_child_type`Retrieves the child type of the given struct type at the specified index.

The result must be freed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-45)
        
      

    
```
duckdb_logical_type duckdb_struct_type_child_type(
  duckdb_logical_type type,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-45)
        
      

    
- `type`: The logical type object
- `index`: The child index

##### 
        
        [Return Value](#return-value-43)
        
      

    
The child type of the struct type. Must be destroyed with `duckdb_destroy_logical_type`.

#### 
        
        `duckdb_union_type_member_count`

    
`duckdb_union_type_member_count`Returns the number of members that the union type has.

##### 
        
        [Syntax](#syntax-46)
        
      

    
```
idx_t duckdb_union_type_member_count(
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-46)
        
      

    
- `type`: The logical type (union) object

##### 
        
        [Return Value](#return-value-44)
        
      

    
The number of members of a union type.

#### 
        
        `duckdb_union_type_member_name`

    
`duckdb_union_type_member_name`Retrieves the name of the union member.

The result must be freed with `duckdb_free`.

##### 
        
        [Syntax](#syntax-47)
        
      

    
```
char *duckdb_union_type_member_name(
  duckdb_logical_type type,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-47)
        
      

    
- `type`: The logical type object
- `index`: The child index

##### 
        
        [Return Value](#return-value-45)
        
      

    
The name of the union member. Must be freed with `duckdb_free`.

#### 
        
        `duckdb_union_type_member_type`

    
`duckdb_union_type_member_type`Retrieves the child type of the given union member at the specified index.

The result must be freed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-48)
        
      

    
```
duckdb_logical_type duckdb_union_type_member_type(
  duckdb_logical_type type,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-48)
        
      

    
- `type`: The logical type object
- `index`: The child index

##### 
        
        [Return Value](#return-value-46)
        
      

    
The child type of the union member. Must be destroyed with `duckdb_destroy_logical_type`.

#### 
        
        `duckdb_destroy_logical_type`

    
`duckdb_destroy_logical_type`Destroys the logical type and de-allocates all memory allocated for that type.

##### 
        
        [Syntax](#syntax-49)
        
      

    
```
void duckdb_destroy_logical_type(
  duckdb_logical_type *type
);
```
##### 
        
        [Parameters](#parameters-49)
        
      

    
- `type`: The logical type to destroy.

#### 
        
        `duckdb_register_logical_type`

    
`duckdb_register_logical_type`Registers a custom type within the given connection. The type must have an alias

##### 
        
        [Syntax](#syntax-50)
        
      

    
```
duckdb_state duckdb_register_logical_type(
  duckdb_connection con,
  duckdb_logical_type type,
  duckdb_create_type_info info
);
```
##### 
        
        [Parameters](#parameters-50)
        
      

    
- `con`: The connection to use
- `type`: The custom type to register

##### 
        
        [Return Value](#return-value-47)
        
      

    
Whether or not the registration was successful.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/types
