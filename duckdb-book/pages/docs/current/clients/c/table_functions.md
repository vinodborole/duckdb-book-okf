---
type: Web Page
title: Table Functions – DuckDB
description: The table function API can be used to define a table function that can
  then be called from within DuckDB in the FROM clause of a query. API Reference Overview
  duckdb_table_function duckdb_create_table_function(); void duckdb_destroy_table_function(duckdb_table_function
  *table_function); void duckdb_table_function_set_name(duckdb_table_function table_function,
  const char *name); void duckdb_table_function_add_parameter(duckdb_table_function
  table_function, duckdb_logical_type type); void duckdb_table_function_add_named_parameter(duckdb_table_function
  table_function, const char *name, duckdb_logical_type type); void duckdb_table_function_set_extra_info(duckdb_table_function
  table_function, void *extra_info, duckdb_delete_callback_t destroy); void duckdb_table_function_set_bind(duckdb_table_function
  table_function, duckdb_table_function_bind_t bind); void duckdb_table_function_set_init(duckdb_table_function
  table_function, duckdb_table_function_init_t init); void duckdb_table_function_set_local_init(duckdb_table_function
  table_function, duckdb_table_function_init_t init); void duckdb_table_function_set_function(duckdb_table_function
  table_function, duckdb_table_function_t function); void duckdb_table_function_supports_projection_pushdown(duckdb_table_function
  table_function, bool pushdown); duckdb_state duckdb_register_table_function(duckdb_connection
  con, duckdb_table_function function); Table Function Bind void *duckdb_bind_get_extra_info(duckdb_bind_info
  info); void duckdb_table_function_get_client_context(duckdb_bind_info info,…
resource: https://duckdb.org/docs/current/clients/c/table_functions
timestamp: '2026-08-03T09:53:51.508916+00:00'
---

The table function API can be used to define a table function that can then be called from within DuckDB in the `FROM` clause of a query.

## 
        
        [API Reference Overview](#api-reference-overview)
        
      

    
`duckdb_table_function` [duckdb_create_table_function](#duckdb_create_table_function)();
void [duckdb_destroy_table_function](#duckdb_destroy_table_function)(duckdb_table_function *table_function);
void [duckdb_table_function_set_name](#duckdb_table_function_set_name)(duckdb_table_function table_function, const char *name);
void [duckdb_table_function_add_parameter](#duckdb_table_function_add_parameter)(duckdb_table_function table_function, duckdb_logical_type type);
void [duckdb_table_function_add_named_parameter](#duckdb_table_function_add_named_parameter)(duckdb_table_function table_function, const char *name, duckdb_logical_type type);
void [duckdb_table_function_set_extra_info](#duckdb_table_function_set_extra_info)(duckdb_table_function table_function, void *extra_info, duckdb_delete_callback_t destroy);
void [duckdb_table_function_set_bind](#duckdb_table_function_set_bind)(duckdb_table_function table_function, duckdb_table_function_bind_t bind);
void [duckdb_table_function_set_init](#duckdb_table_function_set_init)(duckdb_table_function table_function, duckdb_table_function_init_t init);
void [duckdb_table_function_set_local_init](#duckdb_table_function_set_local_init)(duckdb_table_function table_function, duckdb_table_function_init_t init);
void [duckdb_table_function_set_function](#duckdb_table_function_set_function)(duckdb_table_function table_function, duckdb_table_function_t function);
void [duckdb_table_function_supports_projection_pushdown](#duckdb_table_function_supports_projection_pushdown)(duckdb_table_function table_function, bool pushdown);
duckdb_state [duckdb_register_table_function](#duckdb_register_table_function)(duckdb_connection con, duckdb_table_function function);
### 
        
        [Table Function Bind](#table-function-bind)
        
      

    
`void *`[duckdb_bind_get_extra_info](#duckdb_bind_get_extra_info)(duckdb_bind_info info);
void [duckdb_table_function_get_client_context](#duckdb_table_function_get_client_context)(duckdb_bind_info info, duckdb_client_context *out_context);
void [duckdb_bind_add_result_column](#duckdb_bind_add_result_column)(duckdb_bind_info info, const char *name, duckdb_logical_type type);
idx_t [duckdb_bind_get_parameter_count](#duckdb_bind_get_parameter_count)(duckdb_bind_info info);
duckdb_value [duckdb_bind_get_parameter](#duckdb_bind_get_parameter)(duckdb_bind_info info, idx_t index);
duckdb_value [duckdb_bind_get_named_parameter](#duckdb_bind_get_named_parameter)(duckdb_bind_info info, const char *name);
void [duckdb_bind_set_bind_data](#duckdb_bind_set_bind_data)(duckdb_bind_info info, void *bind_data, duckdb_delete_callback_t destroy);
void [duckdb_bind_set_cardinality](#duckdb_bind_set_cardinality)(duckdb_bind_info info, idx_t cardinality, bool is_exact);
void [duckdb_bind_set_error](#duckdb_bind_set_error)(duckdb_bind_info info, const char *error);
### 
        
        [Table Function Init](#table-function-init)
        
      

    
`void *`[duckdb_init_get_extra_info](#duckdb_init_get_extra_info)(duckdb_init_info info);
void *[duckdb_init_get_bind_data](#duckdb_init_get_bind_data)(duckdb_init_info info);
void [duckdb_init_set_init_data](#duckdb_init_set_init_data)(duckdb_init_info info, void *init_data, duckdb_delete_callback_t destroy);
idx_t [duckdb_init_get_column_count](#duckdb_init_get_column_count)(duckdb_init_info info);
idx_t [duckdb_init_get_column_index](#duckdb_init_get_column_index)(duckdb_init_info info, idx_t column_index);
void [duckdb_init_set_max_threads](#duckdb_init_set_max_threads)(duckdb_init_info info, idx_t max_threads);
void [duckdb_init_set_error](#duckdb_init_set_error)(duckdb_init_info info, const char *error);
### 
        
        [Table Function](#table-function)
        
      

    
`void *`[duckdb_function_get_extra_info](#duckdb_function_get_extra_info)(duckdb_function_info info);
void *[duckdb_function_get_bind_data](#duckdb_function_get_bind_data)(duckdb_function_info info);
void *[duckdb_function_get_init_data](#duckdb_function_get_init_data)(duckdb_function_info info);
void *[duckdb_function_get_local_init_data](#duckdb_function_get_local_init_data)(duckdb_function_info info);
void [duckdb_function_set_error](#duckdb_function_set_error)(duckdb_function_info info, const char *error);
#### 
        
        [`duckdb_create_table_function`](#duckdb_create_table_function)
        
      

    
`duckdb_create_table_function`
Creates a new empty table function.

The return value should be destroyed with `duckdb_destroy_table_function`.

##### 
        
        [Return Value](#return-value)
        
      

    
The table function object.

##### 
        
        [Syntax](#syntax)
        
      

    
```
duckdb_table_function duckdb_create_table_function(
  
);
```
#### 
        
        [`duckdb_destroy_table_function`](#duckdb_destroy_table_function)
        
      

    
`duckdb_destroy_table_function`
Destroys the given table function object.

##### 
        
        [Syntax](#syntax-1)
        
      

    
```
void duckdb_destroy_table_function(
  duckdb_table_function *table_function
);
```
##### 
        
        [Parameters](#parameters)
        
      

    
- `table_function` : The table function to destroy

#### 
        
        [`duckdb_table_function_set_name`](#duckdb_table_function_set_name)
        
      

    
`duckdb_table_function_set_name`
Sets the name of the given table function.

##### 
        
        [Syntax](#syntax-2)
        
      

    
```
void duckdb_table_function_set_name(
  duckdb_table_function table_function,
  const char *name
);
```
##### 
        
        [Parameters](#parameters-1)
        
      

    
- `table_function` : The table function
- `name` : The name of the table function

#### 
        
        [`duckdb_table_function_add_parameter`](#duckdb_table_function_add_parameter)
        
      

    
`duckdb_table_function_add_parameter`
Adds a parameter to the table function.

##### 
        
        [Syntax](#syntax-3)
        
      

    
```
void duckdb_table_function_add_parameter(
  duckdb_table_function table_function,
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-2)
        
      

    
- `table_function` : The table function.
- `type` : The parameter type. Cannot contain INVALID.

#### 
        
        [`duckdb_table_function_add_named_parameter`](#duckdb_table_function_add_named_parameter)
        
      

    
`duckdb_table_function_add_named_parameter`
Adds a named parameter to the table function.

##### 
        
        [Syntax](#syntax-4)
        
      

    
```
void duckdb_table_function_add_named_parameter(
  duckdb_table_function table_function,
  const char *name,
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-3)
        
      

    
- `table_function` : The table function.
- `name` : The parameter name.
- `type` : The parameter type. Cannot contain INVALID.

#### 
        
        [`duckdb_table_function_set_extra_info`](#duckdb_table_function_set_extra_info)
        
      

    
`duckdb_table_function_set_extra_info`
Assigns extra information to the table function that can be fetched during binding, etc.

##### 
        
        [Syntax](#syntax-5)
        
      

    
```
void duckdb_table_function_set_extra_info(
  duckdb_table_function table_function,
  void *extra_info,
  duckdb_delete_callback_t destroy
);
```
##### 
        
        [Parameters](#parameters-4)
        
      

    
- `table_function` : The table function
- `extra_info` : The extra information
- `destroy` : The callback that will be called to destroy the extra information (if any)

#### 
        
        [`duckdb_table_function_set_bind`](#duckdb_table_function_set_bind)
        
      

    
`duckdb_table_function_set_bind`
Sets the bind function of the table function.

##### 
        
        [Syntax](#syntax-6)
        
      

    
```
void duckdb_table_function_set_bind(
  duckdb_table_function table_function,
  duckdb_table_function_bind_t bind
);
```
##### 
        
        [Parameters](#parameters-5)
        
      

    
- `table_function` : The table function
- `bind` : The bind function

#### 
        
        [`duckdb_table_function_set_init`](#duckdb_table_function_set_init)
        
      

    
`duckdb_table_function_set_init`
Sets the init function of the table function.

##### 
        
        [Syntax](#syntax-7)
        
      

    
```
void duckdb_table_function_set_init(
  duckdb_table_function table_function,
  duckdb_table_function_init_t init
);
```
##### 
        
        [Parameters](#parameters-6)
        
      

    
- `table_function` : The table function
- `init` : The init function

#### 
        
        [`duckdb_table_function_set_local_init`](#duckdb_table_function_set_local_init)
        
      

    
`duckdb_table_function_set_local_init`
Sets the thread-local init function of the table function.

##### 
        
        [Syntax](#syntax-8)
        
      

    
```
void duckdb_table_function_set_local_init(
  duckdb_table_function table_function,
  duckdb_table_function_init_t init
);
```
##### 
        
        [Parameters](#parameters-7)
        
      

    
- `table_function` : The table function
- `init` : The init function

#### 
        
        [`duckdb_table_function_set_function`](#duckdb_table_function_set_function)
        
      

    
`duckdb_table_function_set_function`
Sets the main function of the table function.

##### 
        
        [Syntax](#syntax-9)
        
      

    
```
void duckdb_table_function_set_function(
  duckdb_table_function table_function,
  duckdb_table_function_t function
);
```
##### 
        
        [Parameters](#parameters-8)
        
      

    
- `table_function` : The table function
- `function` : The function

#### 
        
        [`duckdb_table_function_supports_projection_pushdown`](#duckdb_table_function_supports_projection_pushdown)
        
      

    
`duckdb_table_function_supports_projection_pushdown`
Sets whether or not the given table function supports projection pushdown.

If this is set to true, the system will provide a list of all required columns in the `init` stage through
the `duckdb_init_get_column_count` and `duckdb_init_get_column_index` functions.
If this is set to false (the default), the system will expect all columns to be projected.

##### 
        
        [Syntax](#syntax-10)
        
      

    
```
void duckdb_table_function_supports_projection_pushdown(
  duckdb_table_function table_function,
  bool pushdown
);
```
##### 
        
        [Parameters](#parameters-9)
        
      

    
- `table_function` : The table function
- `pushdown` : True if the table function supports projection pushdown, false otherwise.

#### 
        
        [`duckdb_register_table_function`](#duckdb_register_table_function)
        
      

    
`duckdb_register_table_function`
Register the table function object within the given connection.

The function requires at least a name, a bind function, an init function and a main function.

If the function is incomplete or a function with this name already exists DuckDBError is returned.

##### 
        
        [Syntax](#syntax-11)
        
      

    
```
duckdb_state duckdb_register_table_function(
  duckdb_connection con,
  duckdb_table_function function
);
```
##### 
        
        [Parameters](#parameters-10)
        
      

    
- `con` : The connection to register it in.
- `function` : The function pointer

##### 
        
        [Return Value](#return-value-1)
        
      

    
Whether or not the registration was successful.

#### 
        
        [`duckdb_bind_get_extra_info`](#duckdb_bind_get_extra_info)
        
      

    
`duckdb_bind_get_extra_info`
Retrieves the extra info of the function as set in `duckdb_table_function_set_extra_info`.

##### 
        
        [Syntax](#syntax-12)
        
      

    
```
void *duckdb_bind_get_extra_info(
  duckdb_bind_info info
);
```
##### 
        
        [Parameters](#parameters-11)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-2)
        
      

    
The extra info

#### 
        
        [`duckdb_table_function_get_client_context`](#duckdb_table_function_get_client_context)
        
      

    
`duckdb_table_function_get_client_context`
Retrieves the client context of the bind info of a table function.

##### 
        
        [Syntax](#syntax-13)
        
      

    
```
void duckdb_table_function_get_client_context(
  duckdb_bind_info info,
  duckdb_client_context *out_context
);
```
##### 
        
        [Parameters](#parameters-12)
        
      

    
- `info` : The bind info object of the table function.
- `out_context` : The client context of the bind info. Must be destroyed with`duckdb_destroy_client_context` .

#### 
        
        [`duckdb_bind_add_result_column`](#duckdb_bind_add_result_column)
        
      

    
`duckdb_bind_add_result_column`
Adds a result column to the output of the table function.

##### 
        
        [Syntax](#syntax-14)
        
      

    
```
void duckdb_bind_add_result_column(
  duckdb_bind_info info,
  const char *name,
  duckdb_logical_type type
);
```
##### 
        
        [Parameters](#parameters-13)
        
      

    
- `info` : The table function's bind info.
- `name` : The column name.
- `type` : The logical column type.

#### 
        
        [`duckdb_bind_get_parameter_count`](#duckdb_bind_get_parameter_count)
        
      

    
`duckdb_bind_get_parameter_count`
Retrieves the number of regular (non-named) parameters to the function.

##### 
        
        [Syntax](#syntax-15)
        
      

    
```
idx_t duckdb_bind_get_parameter_count(
  duckdb_bind_info info
);
```
##### 
        
        [Parameters](#parameters-14)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-3)
        
      

    
The number of parameters

#### 
        
        [`duckdb_bind_get_parameter`](#duckdb_bind_get_parameter)
        
      

    
`duckdb_bind_get_parameter`
Retrieves the parameter at the given index.

The result must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-16)
        
      

    
```
duckdb_value duckdb_bind_get_parameter(
  duckdb_bind_info info,
  idx_t index
);
```
##### 
        
        [Parameters](#parameters-15)
        
      

    
- `info` : The info object
- `index` : The index of the parameter to get

##### 
        
        [Return Value](#return-value-4)
        
      

    
The value of the parameter. Must be destroyed with `duckdb_destroy_value`.

#### 
        
        [`duckdb_bind_get_named_parameter`](#duckdb_bind_get_named_parameter)
        
      

    
`duckdb_bind_get_named_parameter`
Retrieves a named parameter with the given name.

The result must be destroyed with `duckdb_destroy_value`.

##### 
        
        [Syntax](#syntax-17)
        
      

    
```
duckdb_value duckdb_bind_get_named_parameter(
  duckdb_bind_info info,
  const char *name
);
```
##### 
        
        [Parameters](#parameters-16)
        
      

    
- `info` : The info object
- `name` : The name of the parameter

##### 
        
        [Return Value](#return-value-5)
        
      

    
The value of the parameter. Must be destroyed with `duckdb_destroy_value`.

#### 
        
        [`duckdb_bind_set_bind_data`](#duckdb_bind_set_bind_data)
        
      

    
`duckdb_bind_set_bind_data`
Sets the user-provided bind data in the bind object of the table function. This object can be retrieved again during execution.

##### 
        
        [Syntax](#syntax-18)
        
      

    
```
void duckdb_bind_set_bind_data(
  duckdb_bind_info info,
  void *bind_data,
  duckdb_delete_callback_t destroy
);
```
##### 
        
        [Parameters](#parameters-17)
        
      

    
- `info` : The bind info of the table function.
- `bind_data` : The bind data object.
- `destroy` : The callback to destroy the bind data (if any).

#### 
        
        [`duckdb_bind_set_cardinality`](#duckdb_bind_set_cardinality)
        
      

    
`duckdb_bind_set_cardinality`
Sets the cardinality estimate for the table function, used for optimization.

##### 
        
        [Syntax](#syntax-19)
        
      

    
```
void duckdb_bind_set_cardinality(
  duckdb_bind_info info,
  idx_t cardinality,
  bool is_exact
);
```
##### 
        
        [Parameters](#parameters-18)
        
      

    
- `info` : The bind data object.
- `is_exact` : Whether or not the cardinality estimate is exact, or an approximation

#### 
        
        [`duckdb_bind_set_error`](#duckdb_bind_set_error)
        
      

    
`duckdb_bind_set_error`
Report that an error has occurred while calling bind on a table function.

##### 
        
        [Syntax](#syntax-20)
        
      

    
```
void duckdb_bind_set_error(
  duckdb_bind_info info,
  const char *error
);
```
##### 
        
        [Parameters](#parameters-19)
        
      

    
- `info` : The info object
- `error` : The error message

#### 
        
        [`duckdb_init_get_extra_info`](#duckdb_init_get_extra_info)
        
      

    
`duckdb_init_get_extra_info`
Retrieves the extra info of the function as set in `duckdb_table_function_set_extra_info`.

##### 
        
        [Syntax](#syntax-21)
        
      

    
```
void *duckdb_init_get_extra_info(
  duckdb_init_info info
);
```
##### 
        
        [Parameters](#parameters-20)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-6)
        
      

    
The extra info

#### 
        
        [`duckdb_init_get_bind_data`](#duckdb_init_get_bind_data)
        
      

    
`duckdb_init_get_bind_data`
Gets the bind data set by `duckdb_bind_set_bind_data` during the bind.

Note that the bind data should be considered as read-only. For tracking state, use the init data instead.

##### 
        
        [Syntax](#syntax-22)
        
      

    
```
void *duckdb_init_get_bind_data(
  duckdb_init_info info
);
```
##### 
        
        [Parameters](#parameters-21)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-7)
        
      

    
The bind data object

#### 
        
        [`duckdb_init_set_init_data`](#duckdb_init_set_init_data)
        
      

    
`duckdb_init_set_init_data`
Sets the user-provided init data in the init object. This object can be retrieved again during execution.

##### 
        
        [Syntax](#syntax-23)
        
      

    
```
void duckdb_init_set_init_data(
  duckdb_init_info info,
  void *init_data,
  duckdb_delete_callback_t destroy
);
```
##### 
        
        [Parameters](#parameters-22)
        
      

    
- `info` : The info object
- `init_data` : The init data object.
- `destroy` : The callback that will be called to destroy the init data (if any)

#### 
        
        [`duckdb_init_get_column_count`](#duckdb_init_get_column_count)
        
      

    
`duckdb_init_get_column_count`
Returns the number of projected columns.

This function must be used if projection pushdown is enabled to figure out which columns to emit.

##### 
        
        [Syntax](#syntax-24)
        
      

    
```
idx_t duckdb_init_get_column_count(
  duckdb_init_info info
);
```
##### 
        
        [Parameters](#parameters-23)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-8)
        
      

    
The number of projected columns.

#### 
        
        [`duckdb_init_get_column_index`](#duckdb_init_get_column_index)
        
      

    
`duckdb_init_get_column_index`
Returns the column index of the projected column at the specified position.

This function must be used if projection pushdown is enabled to figure out which columns to emit.

##### 
        
        [Syntax](#syntax-25)
        
      

    
```
idx_t duckdb_init_get_column_index(
  duckdb_init_info info,
  idx_t column_index
);
```
##### 
        
        [Parameters](#parameters-24)
        
      

    
- `info` : The info object
- `column_index` : The index at which to get the projected column index, from 0..duckdb_init_get_column_count(info)

##### 
        
        [Return Value](#return-value-9)
        
      

    
The column index of the projected column.

#### 
        
        [`duckdb_init_set_max_threads`](#duckdb_init_set_max_threads)
        
      

    
`duckdb_init_set_max_threads`
Sets how many threads can process this table function in parallel (default: 1)

##### 
        
        [Syntax](#syntax-26)
        
      

    
```
void duckdb_init_set_max_threads(
  duckdb_init_info info,
  idx_t max_threads
);
```
##### 
        
        [Parameters](#parameters-25)
        
      

    
- `info` : The info object
- `max_threads` : The maximum amount of threads that can process this table function

#### 
        
        [`duckdb_init_set_error`](#duckdb_init_set_error)
        
      

    
`duckdb_init_set_error`
Report that an error has occurred while calling init.

##### 
        
        [Syntax](#syntax-27)
        
      

    
```
void duckdb_init_set_error(
  duckdb_init_info info,
  const char *error
);
```
##### 
        
        [Parameters](#parameters-26)
        
      

    
- `info` : The info object
- `error` : The error message

#### 
        
        [`duckdb_function_get_extra_info`](#duckdb_function_get_extra_info)
        
      

    
`duckdb_function_get_extra_info`
Retrieves the extra info of the function as set in `duckdb_table_function_set_extra_info`.

##### 
        
        [Syntax](#syntax-28)
        
      

    
```
void *duckdb_function_get_extra_info(
  duckdb_function_info info
);
```
##### 
        
        [Parameters](#parameters-27)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-10)
        
      

    
The extra info

#### 
        
        [`duckdb_function_get_bind_data`](#duckdb_function_get_bind_data)
        
      

    
`duckdb_function_get_bind_data`
Gets the table function's bind data set by `duckdb_bind_set_bind_data`.

Note that the bind data is read-only. For tracking state, use the init data instead.

##### 
        
        [Syntax](#syntax-29)
        
      

    
```
void *duckdb_function_get_bind_data(
  duckdb_function_info info
);
```
##### 
        
        [Parameters](#parameters-28)
        
      

    
- `info` : The function info object.

##### 
        
        [Return Value](#return-value-11)
        
      

    
The bind data object.

#### 
        
        [`duckdb_function_get_init_data`](#duckdb_function_get_init_data)
        
      

    
`duckdb_function_get_init_data`
Gets the init data set by `duckdb_init_set_init_data` during the init.

##### 
        
        [Syntax](#syntax-30)
        
      

    
```
void *duckdb_function_get_init_data(
  duckdb_function_info info
);
```
##### 
        
        [Parameters](#parameters-29)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-12)
        
      

    
The init data object

#### 
        
        [`duckdb_function_get_local_init_data`](#duckdb_function_get_local_init_data)
        
      

    
`duckdb_function_get_local_init_data`
Gets the thread-local init data set by `duckdb_init_set_init_data` during the local_init.

##### 
        
        [Syntax](#syntax-31)
        
      

    
```
void *duckdb_function_get_local_init_data(
  duckdb_function_info info
);
```
##### 
        
        [Parameters](#parameters-30)
        
      

    
- `info` : The info object

##### 
        
        [Return Value](#return-value-13)
        
      

    
The init data object

#### 
        
        [`duckdb_function_set_error`](#duckdb_function_set_error)
        
      

    
`duckdb_function_set_error`
Report that an error has occurred while executing the function.

##### 
        
        [Syntax](#syntax-32)
        
      

    
```
void duckdb_function_set_error(
  duckdb_function_info info,
  const char *error
);
```
##### 
        
        [Parameters](#parameters-31)
        
      

    
- `info` : The info object
- `error` : The error message

# Citations

1. Source page: https://duckdb.org/docs/current/clients/c/table_functions
