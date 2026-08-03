---
type: Web Page
title: Prepared Statements – DuckDB
description: 'A prepared statement is a parameterized query. The query is prepared
  with question marks (?) or dollar symbols ($1) indicating the parameters of the
  query. Values can then be bound to these parameters, after which the prepared statement
  can be executed using those parameters. A single query can be prepared once and
  executed many times. Prepared statements are useful to: Easily supply parameters
  to functions while avoiding string concatenation/SQL injection attacks. Speeding
  up queries that will be executed many times with different parameters. DuckDB supports
  prepared statements in the C API with the duckdb_prepare method. The duckdb_bind
  family of functions…'
resource: https://duckdb.org/docs/current/clients/c/prepared
timestamp: '2026-08-03T09:53:51.508916+00:00'
---

A prepared statement is a parameterized query. The query is prepared with question marks (`?`) or dollar symbols (`$1`) indicating the parameters of the query. Values can then be bound to these parameters, after which the prepared statement can be executed using those parameters. A single query can be prepared once and executed many times.

Prepared statements are useful to:

- Easily supply parameters to functions while avoiding string concatenation/SQL injection attacks.
- Speeding up queries that will be executed many times with different parameters.

DuckDB supports prepared statements in the C API with the `duckdb_prepare` method. The `duckdb_bind` family of functions is used to supply values for subsequent execution of the prepared statement using `duckdb_execute_prepared`. After we are done with the prepared statement it can be cleaned up using the `duckdb_destroy_prepare` method.

## 
        
        [Example](#example)
        
      

    
```
duckdb_prepared_statement stmt;
duckdb_result result;
if (duckdb_prepare(con, "INSERT INTO integers VALUES ($1, $2)", &stmt) == DuckDBError) {
    // handle error
}
duckdb_bind_int32(stmt, 1, 42); // the parameter index starts counting at 1!
duckdb_bind_int32(stmt, 2, 43);
// NULL as second parameter means no result set is requested
duckdb_execute_prepared(stmt, NULL);
duckdb_destroy_prepare(&stmt);
// we can also query result sets using prepared statements
if (duckdb_prepare(con, "SELECT * FROM integers WHERE i = ?", &stmt) == DuckDBError) {
    // handle error
}
duckdb_bind_int32(stmt, 1, 42);
duckdb_execute_prepared(stmt, &result);
// do something with result
// clean up
duckdb_destroy_result(&result);
duckdb_destroy_prepare(&stmt);
```
After calling `duckdb_prepare`, the prepared statement parameters can be inspected using `duckdb_nparams` and `duckdb_param_type`. In case the prepare fails, the error can be obtained through `duckdb_prepare_error`.

It is not required that the `duckdb_bind` family of functions matches the prepared statement parameter type exactly. The values will be auto-cast to the required value as required. For example, calling `duckdb_bind_int8` on a parameter type of `DUCKDB_TYPE_INTEGER` will work as expected.

  Warning Do **not** use prepared statements to insert large amounts of data into DuckDB. Instead it is recommended to use the [Appender](/docs/current/clients/c/appender.html).

## 
        
        [API Reference Overview](#api-reference-overview)
        
      

    
`duckdb_state` [duckdb_prepare](#duckdb_prepare)(duckdb_connection connection, const char *query, duckdb_prepared_statement *out_prepared_statement);
void [duckdb_destroy_prepare](#duckdb_destroy_prepare)(duckdb_prepared_statement *prepared_statement);
const char *[duckdb_prepare_error](#duckdb_prepare_error)(duckdb_prepared_statement prepared_statement);
idx_t [duckdb_nparams](#duckdb_nparams)(duckdb_prepared_statement prepared_statement);
const char *[duckdb_parameter_name](#duckdb_parameter_name)(duckdb_prepared_statement prepared_statement, idx_t index);
duckdb_type [duckdb_param_type](#duckdb_param_type)(duckdb_prepared_statement prepared_statement, idx_t param_idx);
duckdb_logical_type [duckdb_param_logical_type](#duckdb_param_logical_type)(duckdb_prepared_statement prepared_statement, idx_t param_idx);
duckdb_state [duckdb_clear_bindings](#duckdb_clear_bindings)(duckdb_prepared_statement prepared_statement);
duckdb_statement_type [duckdb_prepared_statement_type](#duckdb_prepared_statement_type)(duckdb_prepared_statement statement);
idx_t [duckdb_prepared_statement_column_count](#duckdb_prepared_statement_column_count)(duckdb_prepared_statement prepared_statement);
const char *[duckdb_prepared_statement_column_name](#duckdb_prepared_statement_column_name)(duckdb_prepared_statement prepared_statement, idx_t col_idx);
duckdb_logical_type [duckdb_prepared_statement_column_logical_type](#duckdb_prepared_statement_column_logical_type)(duckdb_prepared_statement prepared_statement, idx_t col_idx);
duckdb_type [duckdb_prepared_statement_column_type](#duckdb_prepared_statement_column_type)(duckdb_prepared_statement prepared_statement, idx_t col_idx);
#### 
        
        [`duckdb_prepare`](#duckdb_prepare)
        
      

    
`duckdb_prepare`
Create a prepared statement object from a query.

Note that after calling `duckdb_prepare`, the prepared statement should always be destroyed using
`duckdb_destroy_prepare`, even if the prepare fails.

If the prepare fails, `duckdb_prepare_error` can be called to obtain the reason why the prepare failed.

##### 
        
        [Syntax](#syntax)
        
      

    
```
duckdb_state duckdb_prepare(
  duckdb_connection connection,
  const char *query,
  duckdb_prepared_statement *out_prepared_statement
);
```
##### 
        
        [Parameters](#parameters)
        
      

    
- `connection` : The connection object
- `query` : The SQL query to prepare
- `out_prepared_statement` : The resulting prepared statement object

##### 
        
        [Return Value](#return-value)
        
      

    
`DuckDBSuccess` on success or `DuckDBError` on failure.

#### 
        
        [`duckdb_destroy_prepare`](#duckdb_destroy_prepare)
        
      

    
`duckdb_destroy_prepare`
Closes the prepared statement and de-allocates all memory allocated for the statement.

##### 
        
        [Syntax](#syntax-1)
        
      

    
```
void duckdb_destroy_prepare(
  duckdb_prepared_statement *prepared_statement
);
```
##### 
        
        [Parameters](#parameters-1)
        
      

    
- `prepared_statement` : The prepared statement to destroy.

#### 
        
        [`duckdb_prepare_error`](#duckdb_prepare_error)
        
      

    
`duckdb_prepare_error`
Returns the error message associated with the given prepared statement.
If the prepared statement has no error message, this returns `nullptr` instead.

The error message should not be freed. It will be de-allocated when `duckdb_destroy_prepare` is called.

##### 
        
        [Syntax](#syntax-2)
        
      

    
```
const char *duckdb_prepare_error(
  duckdb_prepared_statement prepared_statement
);
```
##### 
        
        [Parameters](#parameters-2)
        
      

    
- `prepared_statement` : The prepared statement to obtain the error from.

##### 
        
        [Return Value](#return-value-1)
        
      

    
The error message, or `nullptr` if there is none.

#### 
        
        [`duckdb_nparams`](#duckdb_nparams)
        
      

    
`duckdb_nparams`
Returns the number of parameters that can be provided to the given prepared statement.

Returns 0 if the query was not successfully prepared.

##### 
        
        [Syntax](#syntax-3)
        
      

    
```
idx_t duckdb_nparams(
  duckdb_prepared_statement prepared_statement
);
```
##### 
        
        [Parameters](#parameters-3)
        
      

    
- `prepared_statement` : The prepared statement to obtain the number of parameters for.

#### 
        
        [`duckdb_parameter_name`](#duckdb_parameter_name)
        
      

    
`duckdb_parameter_name`
Returns the name used to identify the parameter
The returned string should be freed using `duckdb_free`.

Returns NULL if the index is out of range for the provided prepared statement.

##### 
        
        [Syntax](#syntax-4)
        
      

    
```
const char *duckdb_parameter_name(
  duckdb_prepared_statement prepared_statement,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-4)
        
      

    
- `prepared_statement` : The prepared statement for which to get the parameter name from.

#### 
        
        [`duckdb_param_type`](#duckdb_param_type)
        
      

    
`duckdb_param_type`
Returns the parameter type for the parameter at the given index.

Returns `DUCKDB_TYPE_INVALID` if the parameter index is out of range or the statement was not successfully prepared.

##### 
        
        [Syntax](#syntax-5)
        
      

    
```
duckdb_type duckdb_param_type(
  duckdb_prepared_statement prepared_statement,
  idx_t param_idx
);
```
##### 
        
        [Parameters](#parameters-5)
        
      

    
- `prepared_statement` : The prepared statement.
- `param_idx` : The parameter index.

##### 
        
        [Return Value](#return-value-2)
        
      

    
The parameter type

#### 
        
        [`duckdb_param_logical_type`](#duckdb_param_logical_type)
        
      

    
`duckdb_param_logical_type`
Returns the logical type for the parameter at the given index.

Returns `nullptr` if the parameter index is out of range or the statement was not successfully prepared.

The return type of this call should be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-6)
        
      

    
```
duckdb_logical_type duckdb_param_logical_type(
  duckdb_prepared_statement prepared_statement,
  idx_t param_idx
);
```
##### 
        
        [Parameters](#parameters-6)
        
      

    
- `prepared_statement` : The prepared statement.
- `param_idx` : The parameter index.

##### 
        
        [Return Value](#return-value-3)
        
      

    
The logical type of the parameter

#### 
        
        [`duckdb_clear_bindings`](#duckdb_clear_bindings)
        
      

    
`duckdb_clear_bindings`
Clear the params bind to the prepared statement.

##### 
        
        [Syntax](#syntax-7)
        
      

    
```
duckdb_state duckdb_clear_bindings(
  duckdb_prepared_statement prepared_statement
);
```
#### 
        
        [`duckdb_prepared_statement_type`](#duckdb_prepared_statement_type)
        
      

    
`duckdb_prepared_statement_type`
Returns the statement type of the statement to be executed

##### 
        
        [Syntax](#syntax-8)
        
      

    
```
duckdb_statement_type duckdb_prepared_statement_type(
  duckdb_prepared_statement statement
);
```
##### 
        
        [Parameters](#parameters-7)
        
      

    
- `statement` : The prepared statement.

##### 
        
        [Return Value](#return-value-4)
        
      

    
duckdb_statement_type value or DUCKDB_STATEMENT_TYPE_INVALID

#### 
        
        [`duckdb_prepared_statement_column_count`](#duckdb_prepared_statement_column_count)
        
      

    
`duckdb_prepared_statement_column_count`
Returns the number of columns present in the result of the prepared statement. If any of the column types are invalid, the result will be 1.

##### 
        
        [Syntax](#syntax-9)
        
      

    
```
idx_t duckdb_prepared_statement_column_count(
  duckdb_prepared_statement prepared_statement
);
```
##### 
        
        [Parameters](#parameters-8)
        
      

    
- `prepared_statement` : The prepared statement.

##### 
        
        [Return Value](#return-value-5)
        
      

    
The number of columns present in the result of the prepared statement.

#### 
        
        [`duckdb_prepared_statement_column_name`](#duckdb_prepared_statement_column_name)
        
      

    
`duckdb_prepared_statement_column_name`
Returns the name of the specified column of the result of the prepared_statement.
The returned string should be freed using `duckdb_free`.

Returns `nullptr` if the column is out of range.

##### 
        
        [Syntax](#syntax-10)
        
      

    
```
const char *duckdb_prepared_statement_column_name(
  duckdb_prepared_statement prepared_statement,
  idx_t col_idx
);
```
##### 
        
        [Parameters](#parameters-9)
        
      

    
- `prepared_statement` : The prepared statement.
- `col_idx` : The column index.

##### 
        
        [Return Value](#return-value-6)
        
      

    
The column name of the specified column.

#### 
        
        [`duckdb_prepared_statement_column_logical_type`](#duckdb_prepared_statement_column_logical_type)
        
      

    
`duckdb_prepared_statement_column_logical_type`
Returns the column type of the specified column of the result of the prepared_statement.

Returns `DUCKDB_TYPE_INVALID` if the column is out of range.
The return type of this call should be destroyed with `duckdb_destroy_logical_type`.

##### 
        
        [Syntax](#syntax-11)
        
      

    
```
duckdb_logical_type duckdb_prepared_statement_column_logical_type(
  duckdb_prepared_statement prepared_statement,
  idx_t col_idx
);
```
##### 
        
        [Parameters](#parameters-10)
        
      

    
- `prepared_statement` : The prepared statement to fetch the column type from.
- `col_idx` : The column index.

##### 
        
        [Return Value](#return-value-7)
        
      

    
The logical type of the specified column.

#### 
        
        [`duckdb_prepared_statement_column_type`](#duckdb_prepared_statement_column_type)
        
      

    
`duckdb_prepared_statement_column_type`
Returns the column type of the specified column of the result of the prepared_statement.

Returns `DUCKDB_TYPE_INVALID` if the column is out of range.

##### 
        
        [Syntax](#syntax-12)
        
      

    
```
duckdb_type duckdb_prepared_statement_column_type(
  duckdb_prepared_statement prepared_statement,
  idx_t col_idx
);
```
##### 
        
        [Parameters](#parameters-11)
        
      

    
- `prepared_statement` : The prepared statement to fetch the column type from.
- `col_idx` : The column index.

##### 
        
        [Return Value](#return-value-8)
        
      

    
The type of the specified column.

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/prepared
