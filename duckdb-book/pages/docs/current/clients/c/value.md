---
type: Web Page
title: Values – DuckDB
description: The value class represents a single value of any type. API Reference
  Overview void duckdb_destroy_value(duckdb_value *value); duckdb_value duckdb_create_varchar(const
  char *text); duckdb_value duckdb_create_varchar_length(const char *text, idx_t length);
  duckdb_value duckdb_create_bool(bool input); duckdb_value duckdb_create_int8(int8_t
  input); duckdb_value duckdb_create_uint8(uint8_t input); duckdb_value duckdb_create_int16(int16_t
  input); duckdb_value duckdb_create_uint16(uint16_t input); duckdb_value duckdb_create_int32(int32_t
  input); duckdb_value duckdb_create_uint32(uint32_t input); duckdb_value duckdb_create_uint64(uint64_t
  input); duckdb_value duckdb_create_int64(int64_t val); duckdb_value duckdb_create_hugeint(duckdb_hugeint
  input); duckdb_value duckdb_create_uhugeint(duckdb_uhugeint input); duckdb_value
  duckdb_create_bignum(duckdb_bignum input); duckdb_value duckdb_create_decimal(duckdb_decimal
  input); duckdb_value duckdb_create_float(float input); duckdb_value duckdb_create_double(double
  input); duckdb_value duckdb_create_date(duckdb_date input); duckdb_value duckdb_create_time(duckdb_time
  input); duckdb_value duckdb_create_time_ns(duckdb_time_ns input); duckdb_value duckdb_create_time_tz_value(duckdb_time_tz
  value); duckdb_value duckdb_create_timestamp(duckdb_timestamp input); duckdb_value
  duckdb_create_timestamp_tz(duckdb_timestamp input); duckdb_value duckdb_create_timestamp_s(duckdb_timestamp_s
  input); duckdb_value duckdb_create_timestamp_ms(duckdb_timestamp_ms input); duckdb_value
  duckdb_create_timestamp_ns(duckdb_timestamp_ns input); duckdb_value duckdb_create_interval(duckdb_interval…
resource: https://duckdb.org/docs/current/clients/c/value
timestamp: '2026-07-09T12:17:10.843759+00:00'
---

The value class represents a single value of any type.

## 
        
        [API Reference Overview](#api-reference-overview)
        
      

    
`void `[duckdb_destroy_value](#duckdb_destroy_value)(duckdb_value *value);
duckdb_value [duckdb_create_varchar](#duckdb_create_varchar)(const char *text);
duckdb_value [duckdb_create_varchar_length](#duckdb_create_varchar_length)(const char *text, idx_t length);
duckdb_value [duckdb_create_bool](#duckdb_create_bool)(bool input);
duckdb_value [duckdb_create_int8](#duckdb_create_int8)(int8_t input);
duckdb_value [duckdb_create_uint8](#duckdb_create_uint8)(uint8_t input);
duckdb_value [duckdb_create_int16](#duckdb_create_int16)(int16_t input);
duckdb_value [duckdb_create_uint16](#duckdb_create_uint16)(uint16_t input);
duckdb_value [duckdb_create_int32](#duckdb_create_int32)(int32_t input);
duckdb_value [duckdb_create_uint32](#duckdb_create_uint32)(uint32_t input);
duckdb_value [duckdb_create_uint64](#duckdb_create_uint64)(uint64_t input);
duckdb_value [duckdb_create_int64](#duckdb_create_int64)(int64_t val);
duckdb_value [duckdb_create_hugeint](#duckdb_create_hugeint)(duckdb_hugeint input);
duckdb_value [duckdb_create_uhugeint](#duckdb_create_uhugeint)(duckdb_uhugeint input);
duckdb_value [duckdb_create_bignum](#duckdb_create_bignum)(duckdb_bignum input);
duckdb_value [duckdb_create_decimal](#duckdb_create_decimal)(duckdb_decimal input);
duckdb_value [duckdb_create_float](#duckdb_create_float)(float input);
duckdb_value [duckdb_create_double](#duckdb_create_double)(double input);
duckdb_value [duckdb_create_date](#duckdb_create_date)(duckdb_date input);
duckdb_value [duckdb_create_time](#duckdb_create_time)(duckdb_time input);
duckdb_value [duckdb_create_time_ns](#duckdb_create_time_ns)(duckdb_time_ns input);
duckdb_value [duckdb_create_time_tz_value](#duckdb_create_time_tz_value)(duckdb_time_tz value);
duckdb_value [duckdb_create_timestamp](#duckdb_create_timestamp)(duckdb_timestamp input);
duckdb_value [duckdb_create_timestamp_tz](#duckdb_create_timestamp_tz)(duckdb_timestamp input);
duckdb_value [duckdb_create_timestamp_s](#duckdb_create_timestamp_s)(duckdb_timestamp_s input);
duckdb_value [duckdb_create_timestamp_ms](#duckdb_create_timestamp_ms)(duckdb_timestamp_ms input);
duckdb_value [duckdb_create_timestamp_ns](#duckdb_create_timestamp_ns)(duckdb_timestamp_ns input);
duckdb_value [duckdb_create_interval](#duckdb_create_interval)(duckdb_interval input);
duckdb_value [duckdb_create_blob](#duckdb_create_blob)(const uint8_t *data, idx_t length);
duckdb_value [duckdb_create_bit](#duckdb_create_bit)(duckdb_bit input);
duckdb_value [duckdb_create_uuid](#duckdb_create_uuid)(duckdb_uhugeint input);
bool [duckdb_get_bool](#duckdb_get_bool)(duckdb_value val);
int8_t [duckdb_get_int8](#duckdb_get_int8)(duckdb_value val);
uint8_t [duckdb_get_uint8](#duckdb_get_uint8)(duckdb_value val);
int16_t [duckdb_get_int16](#duckdb_get_int16)(duckdb_value val);
uint16_t [duckdb_get_uint16](#duckdb_get_uint16)(duckdb_value val);
int32_t [duckdb_get_int32](#duckdb_get_int32)(duckdb_value val);
uint32_t [duckdb_get_uint32](#duckdb_get_uint32)(duckdb_value val);
int64_t [duckdb_get_int64](#duckdb_get_int64)(duckdb_value val);
uint64_t [duckdb_get_uint64](#duckdb_get_uint64)(duckdb_value val);
duckdb_hugeint [duckdb_get_hugeint](#duckdb_get_hugeint)(duckdb_value val);
duckdb_uhugeint [duckdb_get_uhugeint](#duckdb_get_uhugeint)(duckdb_value val);
duckdb_bignum [duckdb_get_bignum](#duckdb_get_bignum)(duckdb_value val);
duckdb_decimal [duckdb_get_decimal](#duckdb_get_decimal)(duckdb_value val);
float [duckdb_get_float](#duckdb_get_float)(duckdb_value val);
double [duckdb_get_double](#duckdb_get_double)(duckdb_value val);
duckdb_date [duckdb_get_date](#duckdb_get_date)(duckdb_value val);
duckdb_time [duckdb_get_time](#duckdb_get_time)(duckdb_value val);
duckdb_time_ns [duckdb_get_time_ns](#duckdb_get_time_ns)(duckdb_value val);
duckdb_time_tz [duckdb_get_time_tz](#duckdb_get_time_tz)(duckdb_value val);
duckdb_timestamp [duckdb_get_timestamp](#duckdb_get_timestamp)(duckdb_value val);
duckdb_timestamp [duckdb_get_timestamp_tz](#duckdb_get_timestamp_tz)(duckdb_value val);
duckdb_timestamp_s [duckdb_get_timestamp_s](#duckdb_get_timestamp_s)(duckdb_value val);
duckdb_timestamp_ms [duckdb_get_timestamp_ms](#duckdb_get_timestamp_ms)(duckdb_value val);
duckdb_timestamp_ns [duckdb_get_timestamp_ns](#duckdb_get_timestamp_ns)(duckdb_value val);
duckdb_interval [duckdb_get_interval](#duckdb_get_interval)(duckdb_value val);
duckdb_logical_type [duckdb_get_value_type](#duckdb_get_value_type)(duckdb_value val);
duckdb_blob [duckdb_get_blob](#duckdb_get_blob)(duckdb_value val);
duckdb_bit [duckdb_get_bit](#duckdb_get_bit)(duckdb_value val);
duckdb_uhugeint [duckdb_get_uuid](#duckdb_get_uuid)(duckdb_value val);
char *[duckdb_get_varchar](#duckdb_get_varchar)(duckdb_value value);
duckdb_value [duckdb_create_struct_value](#duckdb_create_struct_value)(duckdb_logical_type type, duckdb_value *values);
duckdb_value [duckdb_create_list_value](#duckdb_create_list_value)(duckdb_logical_type type, duckdb_value *values, idx_t value_count);
duckdb_value [duckdb_create_array_value](#duckdb_create_array_value)(duckdb_logical_type type, duckdb_value *values, idx_t value_count);
duckdb_value [duckdb_create_map_value](#duckdb_create_map_value)(duckdb_logical_type map_type, duckdb_value *keys, duckdb_value *values, idx_t entry_count);
duckdb_value [duckdb_create_union_value](#duckdb_create_union_value)(duckdb_logical_type union_type, idx_t tag_index, duckdb_value value);
idx_t [duckdb_get_map_size](#duckdb_get_map_size)(duckdb_value value);
duckdb_value [duckdb_get_map_key](#duckdb_get_map_key)(duckdb_value value, idx_t index);
duckdb_value [duckdb_get_map_value](#duckdb_get_map_value)(duckdb_value value, idx_t index);
bool [duckdb_is_null_value](#duckdb_is_null_value)(duckdb_value value);
duckdb_value [duckdb_create_null_value](#duckdb_create_null_value)();
idx_t [duckdb_get_list_size](#duckdb_get_list_size)(duckdb_value value);
duckdb_value [duckdb_get_list_child](#duckdb_get_list_child)(duckdb_value value, idx_t index);
duckdb_value [duckdb_create_enum_value](#duckdb_create_enum_value)(duckdb_logical_type type, uint64_t value);
uint64_t [duckdb_get_enum_value](#duckdb_get_enum_value)(duckdb_value value);
duckdb_value [duckdb_get_struct_child](#duckdb_get_struct_child)(duckdb_value value, idx_t index);
char *[duckdb_value_to_string](#duckdb_value_to_string)(duckdb_value value);
#### 
        
        `duckdb_destroy_value`

    
`duckdb_destroy_value`Destroys the value and de-allocates all memory allocated for that type.

##### 
        
        [Syntax](#syntax)
        
      

    
```
void duckdb_destroy_value(
  duckdb_value *value
);
```
##### 
        
        [Parameters](#parameters)
        
      

    
- `value`: The value to destroy.

#### 
        
        `duckdb_create_varchar`

    
`duckdb_create_varchar`Creates a value from a null-terminated string

##### 
        
        [Syntax](#syntax-1)
        
      

    
```
duckdb_value duckdb_create_varchar(
  const char *text
);
```
##### 
        
        [Parameters](#parameters-1)
        
      

    
- `text`: The null-terminated string

##### 
        
        [Return Value](#return-value)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_varchar_length`

    
`duckdb_create_varchar_length`Creates a value from a string

##### 
        
        [Syntax](#syntax-2)
        
      

    
```
duckdb_value duckdb_create_varchar_length(
  const char *text,
  idx_t length
);
```
##### 
        
        [Parameters](#parameters-2)
        
      

    
- `text`: The text
- `length`: The length of the text

##### 
        
        [Return Value](#return-value-1)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_bool`

    
`duckdb_create_bool`Creates a value from a boolean

##### 
        
        [Syntax](#syntax-3)
        
      

    
```
duckdb_value duckdb_create_bool(
  bool input
);
```
##### 
        
        [Parameters](#parameters-3)
        
      

    
- `input`: The boolean value

##### 
        
        [Return Value](#return-value-2)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_int8`

    
`duckdb_create_int8`Creates a value from an int8_t (a tinyint)

##### 
        
        [Syntax](#syntax-4)
        
      

    
```
duckdb_value duckdb_create_int8(
  int8_t input
);
```
##### 
        
        [Parameters](#parameters-4)
        
      

    
- `input`: The tinyint value

##### 
        
        [Return Value](#return-value-3)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_uint8`

    
`duckdb_create_uint8`Creates a value from a uint8_t (a utinyint)

##### 
        
        [Syntax](#syntax-5)
        
      

    
```
duckdb_value duckdb_create_uint8(
  uint8_t input
);
```
##### 
        
        [Parameters](#parameters-5)
        
      

    
- `input`: The utinyint value

##### 
        
        [Return Value](#return-value-4)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_int16`

    
`duckdb_create_int16`Creates a value from an int16_t (a smallint)

##### 
        
        [Syntax](#syntax-6)
        
      

    
```
duckdb_value duckdb_create_int16(
  int16_t input
);
```
##### 
        
        [Parameters](#parameters-6)
        
      

    
- `input`: The smallint value

##### 
        
        [Return Value](#return-value-5)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_uint16`

    
`duckdb_create_uint16`Creates a value from a uint16_t (a usmallint)

##### 
        
        [Syntax](#syntax-7)
        
      

    
```
duckdb_value duckdb_create_uint16(
  uint16_t input
);
```
##### 
        
        [Parameters](#parameters-7)
        
      

    
- `input`: The usmallint value

##### 
        
        [Return Value](#return-value-6)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_int32`

    
`duckdb_create_int32`Creates a value from an int32_t (an integer)

##### 
        
        [Syntax](#syntax-8)
        
      

    
```
duckdb_value duckdb_create_int32(
  int32_t input
);
```
##### 
        
        [Parameters](#parameters-8)
        
      

    
- `input`: The integer value

##### 
        
        [Return Value](#return-value-7)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_uint32`

    
`duckdb_create_uint32`Creates a value from a uint32_t (a uinteger)

##### 
        
        [Syntax](#syntax-9)
        
      

    
```
duckdb_value duckdb_create_uint32(
  uint32_t input
);
```
##### 
        
        [Parameters](#parameters-9)
        
      

    
- `input`: The uinteger value

##### 
        
        [Return Value](#return-value-8)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_uint64`

    
`duckdb_create_uint64`Creates a value from a uint64_t (a ubigint)

##### 
        
        [Syntax](#syntax-10)
        
      

    
```
duckdb_value duckdb_create_uint64(
  uint64_t input
);
```
##### 
        
        [Parameters](#parameters-10)
        
      

    
- `input`: The ubigint value

##### 
        
        [Return Value](#return-value-9)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_int64`

    
`duckdb_create_int64`Creates a value from an int64

##### 
        
        [Return Value](#return-value-10)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-11)
        
      

    
```
duckdb_value duckdb_create_int64(
  int64_t val
);
```
#### 
        
        `duckdb_create_hugeint`

    
`duckdb_create_hugeint`Creates a value from a hugeint

##### 
        
        [Syntax](#syntax-12)
        
      

    
```
duckdb_value duckdb_create_hugeint(
  duckdb_hugeint input
);
```
##### 
        
        [Parameters](#parameters-11)
        
      

    
- `input`: The hugeint value

##### 
        
        [Return Value](#return-value-11)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_uhugeint`

    
`duckdb_create_uhugeint`Creates a value from a uhugeint

##### 
        
        [Syntax](#syntax-13)
        
      

    
```
duckdb_value duckdb_create_uhugeint(
  duckdb_uhugeint input
);
```
##### 
        
        [Parameters](#parameters-12)
        
      

    
- `input`: The uhugeint value

##### 
        
        [Return Value](#return-value-12)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_bignum`

    
`duckdb_create_bignum`Creates a BIGNUM value from a duckdb_bignum

##### 
        
        [Syntax](#syntax-14)
        
      

    
```
duckdb_value duckdb_create_bignum(
  duckdb_bignum input
);
```
##### 
        
        [Parameters](#parameters-13)
        
      

    
- `input`: The duckdb_bignum value

##### 
        
        [Return Value](#return-value-13)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_decimal`

    
`duckdb_create_decimal`Creates a DECIMAL value from a duckdb_decimal

##### 
        
        [Syntax](#syntax-15)
        
      

    
```
duckdb_value duckdb_create_decimal(
  duckdb_decimal input
);
```
##### 
        
        [Parameters](#parameters-14)
        
      

    
- `input`: The duckdb_decimal value

##### 
        
        [Return Value](#return-value-14)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_float`

    
`duckdb_create_float`Creates a value from a float

##### 
        
        [Syntax](#syntax-16)
        
      

    
```
duckdb_value duckdb_create_float(
  float input
);
```
##### 
        
        [Parameters](#parameters-15)
        
      

    
- `input`: The float value

##### 
        
        [Return Value](#return-value-15)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_double`

    
`duckdb_create_double`Creates a value from a double

##### 
        
        [Syntax](#syntax-17)
        
      

    
```
duckdb_value duckdb_create_double(
  double input
);
```
##### 
        
        [Parameters](#parameters-16)
        
      

    
- `input`: The double value

##### 
        
        [Return Value](#return-value-16)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_date`

    
`duckdb_create_date`Creates a value from a date

##### 
        
        [Syntax](#syntax-18)
        
      

    
```
duckdb_value duckdb_create_date(
  duckdb_date input
);
```
##### 
        
        [Parameters](#parameters-17)
        
      

    
- `input`: The date value

##### 
        
        [Return Value](#return-value-17)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_time`

    
`duckdb_create_time`Creates a value from a time

##### 
        
        [Syntax](#syntax-19)
        
      

    
```
duckdb_value duckdb_create_time(
  duckdb_time input
);
```
##### 
        
        [Parameters](#parameters-18)
        
      

    
- `input`: The time value

##### 
        
        [Return Value](#return-value-18)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_time_ns`

    
`duckdb_create_time_ns`Creates a value from a time_ns

##### 
        
        [Syntax](#syntax-20)
        
      

    
```
duckdb_value duckdb_create_time_ns(
  duckdb_time_ns input
);
```
##### 
        
        [Parameters](#parameters-19)
        
      

    
- `input`: The time value

##### 
        
        [Return Value](#return-value-19)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_time_tz_value`

    
`duckdb_create_time_tz_value`Creates a value from a time_tz.
Not to be confused with `duckdb_create_time_tz`, which creates a duckdb_time_tz_t.

##### 
        
        [Syntax](#syntax-21)
        
      

    
```
duckdb_value duckdb_create_time_tz_value(
  duckdb_time_tz value
);
```
##### 
        
        [Parameters](#parameters-20)
        
      

    
- `value`: The time_tz value

##### 
        
        [Return Value](#return-value-20)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_timestamp`

    
`duckdb_create_timestamp`Creates a TIMESTAMP value from a duckdb_timestamp

##### 
        
        [Syntax](#syntax-22)
        
      

    
```
duckdb_value duckdb_create_timestamp(
  duckdb_timestamp input
);
```
##### 
        
        [Parameters](#parameters-21)
        
      

    
- `input`: The duckdb_timestamp value

##### 
        
        [Return Value](#return-value-21)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_timestamp_tz`

    
`duckdb_create_timestamp_tz`Creates a TIMESTAMP_TZ value from a duckdb_timestamp

##### 
        
        [Syntax](#syntax-23)
        
      

    
```
duckdb_value duckdb_create_timestamp_tz(
  duckdb_timestamp input
);
```
##### 
        
        [Parameters](#parameters-22)
        
      

    
- `input`: The duckdb_timestamp value

##### 
        
        [Return Value](#return-value-22)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_timestamp_s`

    
`duckdb_create_timestamp_s`Creates a TIMESTAMP_S value from a duckdb_timestamp_s

##### 
        
        [Syntax](#syntax-24)
        
      

    
```
duckdb_value duckdb_create_timestamp_s(
  duckdb_timestamp_s input
);
```
##### 
        
        [Parameters](#parameters-23)
        
      

    
- `input`: The duckdb_timestamp_s value

##### 
        
        [Return Value](#return-value-23)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_timestamp_ms`

    
`duckdb_create_timestamp_ms`Creates a TIMESTAMP_MS value from a duckdb_timestamp_ms

##### 
        
        [Syntax](#syntax-25)
        
      

    
```
duckdb_value duckdb_create_timestamp_ms(
  duckdb_timestamp_ms input
);
```
##### 
        
        [Parameters](#parameters-24)
        
      

    
- `input`: The duckdb_timestamp_ms value

##### 
        
        [Return Value](#return-value-24)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_timestamp_ns`

    
`duckdb_create_timestamp_ns`Creates a TIMESTAMP_NS value from a duckdb_timestamp_ns

##### 
        
        [Syntax](#syntax-26)
        
      

    
```
duckdb_value duckdb_create_timestamp_ns(
  duckdb_timestamp_ns input
);
```
##### 
        
        [Parameters](#parameters-25)
        
      

    
- `input`: The duckdb_timestamp_ns value

##### 
        
        [Return Value](#return-value-25)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_interval`

    
`duckdb_create_interval`Creates a value from an interval

##### 
        
        [Syntax](#syntax-27)
        
      

    
```
duckdb_value duckdb_create_interval(
  duckdb_interval input
);
```
##### 
        
        [Parameters](#parameters-26)
        
      

    
- `input`: The interval value

##### 
        
        [Return Value](#return-value-26)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_blob`

    
`duckdb_create_blob`Creates a value from a blob

##### 
        
        [Syntax](#syntax-28)
        
      

    
```
duckdb_value duckdb_create_blob(
  const uint8_t *data,
  idx_t length
);
```
##### 
        
        [Parameters](#parameters-27)
        
      

    
- `data`: The blob data
- `length`: The length of the blob data

##### 
        
        [Return Value](#return-value-27)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_bit`

    
`duckdb_create_bit`Creates a BIT value from a duckdb_bit

##### 
        
        [Syntax](#syntax-29)
        
      

    
```
duckdb_value duckdb_create_bit(
  duckdb_bit input
);
```
##### 
        
        [Parameters](#parameters-28)
        
      

    
- `input`: The duckdb_bit value

##### 
        
        [Return Value](#return-value-28)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_create_uuid`

    
`duckdb_create_uuid`Creates a UUID value from a uhugeint

##### 
        
        [Syntax](#syntax-30)
        
      

    
```
duckdb_value duckdb_create_uuid(
  duckdb_uhugeint input
);
```
##### 
        
        [Parameters](#parameters-29)
        
      

    
- `input`: The duckdb_uhugeint containing the UUID

##### 
        
        [Return Value](#return-value-29)
        
      

    
The value. This must be destroyed with `duckdb_destroy_value`.

#### 
        
        `duckdb_get_bool`

    
`duckdb_get_bool`Returns the boolean value of the given value.

##### 
        
        [Syntax](#syntax-31)
        
      

    
```
bool duckdb_get_bool(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-30)
        
      

    
- `val`: A duckdb_value containing a boolean

##### 
        
        [Return Value](#return-value-30)
        
      

    
A boolean, or false if the value cannot be converted

#### 
        
        `duckdb_get_int8`

    
`duckdb_get_int8`Returns the int8_t value of the given value.

##### 
        
        [Syntax](#syntax-32)
        
      

    
```
int8_t duckdb_get_int8(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-31)
        
      

    
- `val`: A duckdb_value containing a tinyint

##### 
        
        [Return Value](#return-value-31)
        
      

    
A int8_t, or MinValue

#### 
        
        `duckdb_get_uint8`

    
`duckdb_get_uint8`Returns the uint8_t value of the given value.

##### 
        
        [Syntax](#syntax-33)
        
      

    
```
uint8_t duckdb_get_uint8(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-32)
        
      

    
- `val`: A duckdb_value containing a utinyint

##### 
        
        [Return Value](#return-value-32)
        
      

    
A uint8_t, or MinValue

#### 
        
        `duckdb_get_int16`

    
`duckdb_get_int16`Returns the int16_t value of the given value.

##### 
        
        [Syntax](#syntax-34)
        
      

    
```
int16_t duckdb_get_int16(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-33)
        
      

    
- `val`: A duckdb_value containing a smallint

##### 
        
        [Return Value](#return-value-33)
        
      

    
A int16_t, or MinValue

#### 
        
        `duckdb_get_uint16`

    
`duckdb_get_uint16`Returns the uint16_t value of the given value.

##### 
        
        [Syntax](#syntax-35)
        
      

    
```
uint16_t duckdb_get_uint16(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-34)
        
      

    
- `val`: A duckdb_value containing a usmallint

##### 
        
        [Return Value](#return-value-34)
        
      

    
A uint16_t, or MinValue

#### 
        
        `duckdb_get_int32`

    
`duckdb_get_int32`Returns the int32_t value of the given value.

##### 
        
        [Syntax](#syntax-36)
        
      

    
```
int32_t duckdb_get_int32(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-35)
        
      

    
- `val`: A duckdb_value containing an integer

##### 
        
        [Return Value](#return-value-35)
        
      

    
A int32_t, or MinValue

#### 
        
        `duckdb_get_uint32`

    
`duckdb_get_uint32`Returns the uint32_t value of the given value.

##### 
        
        [Syntax](#syntax-37)
        
      

    
```
uint32_t duckdb_get_uint32(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-36)
        
      

    
- `val`: A duckdb_value containing a uinteger

##### 
        
        [Return Value](#return-value-36)
        
      

    
A uint32_t, or MinValue

#### 
        
        `duckdb_get_int64`

    
`duckdb_get_int64`Returns the int64_t value of the given value.

##### 
        
        [Syntax](#syntax-38)
        
      

    
```
int64_t duckdb_get_int64(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-37)
        
      

    
- `val`: A duckdb_value containing a bigint

##### 
        
        [Return Value](#return-value-37)
        
      

    
A int64_t, or MinValue

#### 
        
        `duckdb_get_uint64`

    
`duckdb_get_uint64`Returns the uint64_t value of the given value.

##### 
        
        [Syntax](#syntax-39)
        
      

    
```
uint64_t duckdb_get_uint64(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-38)
        
      

    
- `val`: A duckdb_value containing a ubigint

##### 
        
        [Return Value](#return-value-38)
        
      

    
A uint64_t, or MinValue

#### 
        
        `duckdb_get_hugeint`

    
`duckdb_get_hugeint`Returns the hugeint value of the given value.

##### 
        
        [Syntax](#syntax-40)
        
      

    
```
duckdb_hugeint duckdb_get_hugeint(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-39)
        
      

    
- `val`: A duckdb_value containing a hugeint

##### 
        
        [Return Value](#return-value-39)
        
      

    
A duckdb_hugeint, or MinValue

#### 
        
        `duckdb_get_uhugeint`

    
`duckdb_get_uhugeint`Returns the uhugeint value of the given value.

##### 
        
        [Syntax](#syntax-41)
        
      

    
```
duckdb_uhugeint duckdb_get_uhugeint(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-40)
        
      

    
- `val`: A duckdb_value containing a uhugeint

##### 
        
        [Return Value](#return-value-40)
        
      

    
A duckdb_uhugeint, or MinValue

#### 
        
        `duckdb_get_bignum`

    
`duckdb_get_bignum`Returns the duckdb_bignum value of the given value.
The `data` field must be destroyed with `duckdb_free`.

##### 
        
        [Syntax](#syntax-42)
        
      

    
```
duckdb_bignum duckdb_get_bignum(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-41)
        
      

    
- `val`: A duckdb_value containing a BIGNUM

##### 
        
        [Return Value](#return-value-41)
        
      

    
A duckdb_bignum. The `data` field must be destroyed with `duckdb_free`.

#### 
        
        `duckdb_get_decimal`

    
`duckdb_get_decimal`Returns the duckdb_decimal value of the given value.

##### 
        
        [Syntax](#syntax-43)
        
      

    
```
duckdb_decimal duckdb_get_decimal(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-42)
        
      

    
- `val`: A duckdb_value containing a DECIMAL

##### 
        
        [Return Value](#return-value-42)
        
      

    
A duckdb_decimal, or MinValue

#### 
        
        `duckdb_get_float`

    
`duckdb_get_float`Returns the float value of the given value.

##### 
        
        [Syntax](#syntax-44)
        
      

    
```
float duckdb_get_float(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-43)
        
      

    
- `val`: A duckdb_value containing a float

##### 
        
        [Return Value](#return-value-43)
        
      

    
A float, or NAN if the value cannot be converted

#### 
        
        `duckdb_get_double`

    
`duckdb_get_double`Returns the double value of the given value.

##### 
        
        [Syntax](#syntax-45)
        
      

    
```
double duckdb_get_double(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-44)
        
      

    
- `val`: A duckdb_value containing a double

##### 
        
        [Return Value](#return-value-44)
        
      

    
A double, or NAN if the value cannot be converted

#### 
        
        `duckdb_get_date`

    
`duckdb_get_date`Returns the date value of the given value.

##### 
        
        [Syntax](#syntax-46)
        
      

    
```
duckdb_date duckdb_get_date(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-45)
        
      

    
- `val`: A duckdb_value containing a date

##### 
        
        [Return Value](#return-value-45)
        
      

    
A duckdb_date, or MinValue

#### 
        
        `duckdb_get_time`

    
`duckdb_get_time`Returns the time value of the given value.

##### 
        
        [Syntax](#syntax-47)
        
      

    
```
duckdb_time duckdb_get_time(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-46)
        
      

    
- `val`: A duckdb_value containing a time

##### 
        
        [Return Value](#return-value-46)
        
      

    
A duckdb_time, or MinValue

#### 
        
        `duckdb_get_time_ns`

    
`duckdb_get_time_ns`Returns the time_ns value of the given value.

##### 
        
        [Syntax](#syntax-48)
        
      

    
```
duckdb_time_ns duckdb_get_time_ns(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-47)
        
      

    
- `val`: A duckdb_value containing a time_ns

##### 
        
        [Return Value](#return-value-47)
        
      

    
A duckdb_time_ns, or MinValue

#### 
        
        `duckdb_get_time_tz`

    
`duckdb_get_time_tz`Returns the time_tz value of the given value.

##### 
        
        [Syntax](#syntax-49)
        
      

    
```
duckdb_time_tz duckdb_get_time_tz(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-48)
        
      

    
- `val`: A duckdb_value containing a time_tz

##### 
        
        [Return Value](#return-value-48)
        
      

    
A duckdb_time_tz, or MinValue

#### 
        
        `duckdb_get_timestamp`

    
`duckdb_get_timestamp`Returns the TIMESTAMP value of the given value.

##### 
        
        [Syntax](#syntax-50)
        
      

    
```
duckdb_timestamp duckdb_get_timestamp(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-49)
        
      

    
- `val`: A duckdb_value containing a TIMESTAMP

##### 
        
        [Return Value](#return-value-49)
        
      

    
A duckdb_timestamp, or MinValue

#### 
        
        `duckdb_get_timestamp_tz`

    
`duckdb_get_timestamp_tz`Returns the TIMESTAMP_TZ value of the given value.

##### 
        
        [Syntax](#syntax-51)
        
      

    
```
duckdb_timestamp duckdb_get_timestamp_tz(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-50)
        
      

    
- `val`: A duckdb_value containing a TIMESTAMP_TZ

##### 
        
        [Return Value](#return-value-50)
        
      

    
A duckdb_timestamp, or MinValue

#### 
        
        `duckdb_get_timestamp_s`

    
`duckdb_get_timestamp_s`Returns the duckdb_timestamp_s value of the given value.

##### 
        
        [Syntax](#syntax-52)
        
      

    
```
duckdb_timestamp_s duckdb_get_timestamp_s(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-51)
        
      

    
- `val`: A duckdb_value containing a TIMESTAMP_S

##### 
        
        [Return Value](#return-value-51)
        
      

    
A duckdb_timestamp_s, or MinValue

#### 
        
        `duckdb_get_timestamp_ms`

    
`duckdb_get_timestamp_ms`Returns the duckdb_timestamp_ms value of the given value.

##### 
        
        [Syntax](#syntax-53)
        
      

    
```
duckdb_timestamp_ms duckdb_get_timestamp_ms(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-52)
        
      

    
- `val`: A duckdb_value containing a TIMESTAMP_MS

##### 
        
        [Return Value](#return-value-52)
        
      

    
A duckdb_timestamp_ms, or MinValue

#### 
        
        `duckdb_get_timestamp_ns`

    
`duckdb_get_timestamp_ns`Returns the duckdb_timestamp_ns value of the given value.

##### 
        
        [Syntax](#syntax-54)
        
      

    
```
duckdb_timestamp_ns duckdb_get_timestamp_ns(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-53)
        
      

    
- `val`: A duckdb_value containing a TIMESTAMP_NS

##### 
        
        [Return Value](#return-value-53)
        
      

    
A duckdb_timestamp_ns, or MinValue

#### 
        
        `duckdb_get_interval`

    
`duckdb_get_interval`Returns the interval value of the given value.

##### 
        
        [Syntax](#syntax-55)
        
      

    
```
duckdb_interval duckdb_get_interval(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-54)
        
      

    
- `val`: A duckdb_value containing a interval

##### 
        
        [Return Value](#return-value-54)
        
      

    
A duckdb_interval, or MinValue

#### 
        
        `duckdb_get_value_type`

    
`duckdb_get_value_type`Returns the type of the given value. The type is valid as long as the value is not destroyed. The type itself must not be destroyed.

##### 
        
        [Syntax](#syntax-56)
        
      

    
```
duckdb_logical_type duckdb_get_value_type(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-55)
        
      

    
- `val`: A duckdb_value

##### 
        
        [Return Value](#return-value-55)
        
      

    
A duckdb_logical_type.

#### 
        
        `duckdb_get_blob`

    
`duckdb_get_blob`Returns the blob value of the given value.

##### 
        
        [Syntax](#syntax-57)
        
      

    
```
duckdb_blob duckdb_get_blob(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-56)
        
      

    
- `val`: A duckdb_value containing a blob

##### 
        
        [Return Value](#return-value-56)
        
      

    
A duckdb_blob

#### 
        
        `duckdb_get_bit`

    
`duckdb_get_bit`Returns the duckdb_bit value of the given value.
The `data` field must be destroyed with `duckdb_free`.

##### 
        
        [Syntax](#syntax-58)
        
      

    
```
duckdb_bit duckdb_get_bit(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-57)
        
      

    
- `val`: A duckdb_value containing a BIT

##### 
        
        [Return Value](#return-value-57)
        
      

    
A duckdb_bit

#### 
        
        `duckdb_get_uuid`

    
`duckdb_get_uuid`Returns a duckdb_uhugeint representing the UUID value of the given value.

##### 
        
        [Syntax](#syntax-59)
        
      

    
```
duckdb_uhugeint duckdb_get_uuid(
  duckdb_value val
);
```
##### 
        
        [Parameters](#parameters-58)
        
      

    
- `val`: A duckdb_value containing a UUID

##### 
        
        [Return Value](#return-value-58)
        
      

    
A duckdb_uhugeint representing the UUID value

#### 
        
        `duckdb_get_varchar`

    
`duckdb_get_varchar`Obtains a string representation of the given value.
The result must be destroyed with `duckdb_free`.

##### 
        
        [Syntax](#syntax-60)
        
      

    
```
char *duckdb_get_varchar(
  duckdb_value value
);
```
##### 
        
        [Parameters](#parameters-59)
        
      

    
- `value`: The value

##### 
        
        [Return Value](#return-value-59)
        
      

    
The string value. This must be destroyed with `duckdb_free`.

#### 
        
        `duckdb_create_struct_value`

    
`duckdb_create_struct_value`Creates a struct value from a type and an array of values. Must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-61)
        
      

    
```
duckdb_value duckdb_create_struct_value(
  duckdb_logical_type type,
  duckdb_value *values
);
```
##### 
        
        [Parameters](#parameters-60)
        
      

    
- `type`: The type of the struct
- `values`: The values for the struct fields

##### 
        
        [Return Value](#return-value-60)
        
      

    
The struct value, or nullptr, if any child type is `DUCKDB_TYPE_ANY` or `DUCKDB_TYPE_INVALID`.

#### 
        
        `duckdb_create_list_value`

    
`duckdb_create_list_value`Creates a list value from a child (element) type and an array of values of length `value_count`.
Must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-62)
        
      

    
```
duckdb_value duckdb_create_list_value(
  duckdb_logical_type type,
  duckdb_value *values,
  idx_t value_count
);
```
##### 
        
        [Parameters](#parameters-61)
        
      

    
- `type`: The type of the list
- `values`: The values for the list
- `value_count`: The number of values in the list

##### 
        
        [Return Value](#return-value-61)
        
      

    
The list value, or nullptr, if the child type is `DUCKDB_TYPE_ANY` or `DUCKDB_TYPE_INVALID`.

#### 
        
        `duckdb_create_array_value`

    
`duckdb_create_array_value`Creates an array value from a child (element) type and an array of values of length `value_count`.
Must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-63)
        
      

    
```
duckdb_value duckdb_create_array_value(
  duckdb_logical_type type,
  duckdb_value *values,
  idx_t value_count
);
```
##### 
        
        [Parameters](#parameters-62)
        
      

    
- `type`: The type of the array
- `values`: The values for the array
- `value_count`: The number of values in the array

##### 
        
        [Return Value](#return-value-62)
        
      

    
The array value, or nullptr, if the child type is `DUCKDB_TYPE_ANY` or `DUCKDB_TYPE_INVALID`.

#### 
        
        `duckdb_create_map_value`

    
`duckdb_create_map_value`Creates a map value from a map type and two arrays, one for the keys and one for the values, each of length
`entry_count`. Must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-64)
        
      

    
```
duckdb_value duckdb_create_map_value(
  duckdb_logical_type map_type,
  duckdb_value *keys,
  duckdb_value *values,
  idx_t entry_count
);
```
##### 
        
        [Parameters](#parameters-63)
        
      

    
- `map_type`: The map type
- `keys`: The keys of the map
- `values`: The values of the map
- `entry_count`: The number of entries (key-value pairs) in the map

##### 
        
        [Return Value](#return-value-63)
        
      

    
The map value, or nullptr, if the parameters are invalid.

#### 
        
        `duckdb_create_union_value`

    
`duckdb_create_union_value`Creates a union value from a union type, a tag index and a value.
Must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-65)
        
      

    
```
duckdb_value duckdb_create_union_value(
  duckdb_logical_type union_type,
  idx_t tag_index,
  duckdb_value value
);
```
##### 
        
        [Parameters](#parameters-64)
        
      

    
- `union_type`: The union type
- `tag_index`: The index of the tag of the union
- `value`: The value of the union for that tag

##### 
        
        [Return Value](#return-value-64)
        
      

    
The union value, or nullptr, if the parameters are invalid.

#### 
        
        `duckdb_get_map_size`

    
`duckdb_get_map_size`Returns the number of elements in a MAP value.

##### 
        
        [Syntax](#syntax-66)
        
      

    
```
idx_t duckdb_get_map_size(
  duckdb_value value
);
```
##### 
        
        [Parameters](#parameters-65)
        
      

    
- `value`: The MAP value.

##### 
        
        [Return Value](#return-value-65)
        
      

    
The number of elements in the map.

#### 
        
        `duckdb_get_map_key`

    
`duckdb_get_map_key`Returns the MAP key at index as a duckdb_value.

##### 
        
        [Syntax](#syntax-67)
        
      

    
```
duckdb_value duckdb_get_map_key(
  duckdb_value value,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-66)
        
      

    
- `value`: The MAP value.
- `index`: The index of the key.

##### 
        
        [Return Value](#return-value-66)
        
      

    
The key as a duckdb_value.

#### 
        
        `duckdb_get_map_value`

    
`duckdb_get_map_value`Returns the MAP value at index as a duckdb_value.

##### 
        
        [Syntax](#syntax-68)
        
      

    
```
duckdb_value duckdb_get_map_value(
  duckdb_value value,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-67)
        
      

    
- `value`: The MAP value.
- `index`: The index of the value.

##### 
        
        [Return Value](#return-value-67)
        
      

    
The value as a duckdb_value.

#### 
        
        `duckdb_is_null_value`

    
`duckdb_is_null_value`Returns whether the value's type is SQLNULL or not.

##### 
        
        [Syntax](#syntax-69)
        
      

    
```
bool duckdb_is_null_value(
  duckdb_value value
);
```
##### 
        
        [Parameters](#parameters-68)
        
      

    
- `value`: The value to check.

##### 
        
        [Return Value](#return-value-68)
        
      

    
True, if the value's type is SQLNULL, otherwise false.

#### 
        
        `duckdb_create_null_value`

    
`duckdb_create_null_value`Creates a value of type SQLNULL.

##### 
        
        [Return Value](#return-value-69)
        
      

    
The duckdb_value representing SQLNULL. This must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-70)
        
      

    
```
duckdb_value duckdb_create_null_value(
  
);
```
#### 
        
        `duckdb_get_list_size`

    
`duckdb_get_list_size`Returns the number of elements in a LIST value.

##### 
        
        [Syntax](#syntax-71)
        
      

    
```
idx_t duckdb_get_list_size(
  duckdb_value value
);
```
##### 
        
        [Parameters](#parameters-69)
        
      

    
- `value`: The LIST value.

##### 
        
        [Return Value](#return-value-70)
        
      

    
The number of elements in the list.

#### 
        
        `duckdb_get_list_child`

    
`duckdb_get_list_child`Returns the LIST child at index as a duckdb_value.

##### 
        
        [Syntax](#syntax-72)
        
      

    
```
duckdb_value duckdb_get_list_child(
  duckdb_value value,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-70)
        
      

    
- `value`: The LIST value.
- `index`: The index of the child.

##### 
        
        [Return Value](#return-value-71)
        
      

    
The child as a duckdb_value.

#### 
        
        `duckdb_create_enum_value`

    
`duckdb_create_enum_value`Creates an enum value from a type and a value. Must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-73)
        
      

    
```
duckdb_value duckdb_create_enum_value(
  duckdb_logical_type type,
  uint64_t value
);
```
##### 
        
        [Parameters](#parameters-71)
        
      

    
- `type`: The type of the enum
- `value`: The value for the enum

##### 
        
        [Return Value](#return-value-72)
        
      

    
The enum value, or nullptr.

#### 
        
        `duckdb_get_enum_value`

    
`duckdb_get_enum_value`Returns the enum value of the given value.

##### 
        
        [Syntax](#syntax-74)
        
      

    
```
uint64_t duckdb_get_enum_value(
  duckdb_value value
);
```
##### 
        
        [Parameters](#parameters-72)
        
      

    
- `value`: A duckdb_value containing an enum

##### 
        
        [Return Value](#return-value-73)
        
      

    
A uint64_t, or MinValue

#### 
        
        `duckdb_get_struct_child`

    
`duckdb_get_struct_child`Returns the STRUCT child at index as a duckdb_value.

##### 
        
        [Syntax](#syntax-75)
        
      

    
```
duckdb_value duckdb_get_struct_child(
  duckdb_value value,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-73)
        
      

    
- `value`: The STRUCT value.
- `index`: The index of the child.

##### 
        
        [Return Value](#return-value-74)
        
      

    
The child as a duckdb_value.

#### 
        
        `duckdb_value_to_string`

    
`duckdb_value_to_string`Returns the SQL string representation of the given value.

##### 
        
        [Syntax](#syntax-76)
        
      

    
```
char *duckdb_value_to_string(
  duckdb_value value
);
```
##### 
        
        [Parameters](#parameters-74)
        
      

    
- `value`: A duckdb_value.

##### 
        
        [Return Value](#return-value-75)
        
      

    
The SQL string representation as a null-terminated string. The result must be freed with `duckdb_free`.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/value
