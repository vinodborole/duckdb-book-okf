---
type: Web Page
title: Output Formats – DuckDB
description: The .mode dot command may be used to change the appearance of the tables
  returned in the terminal output. In addition to customizing the appearance, these
  modes have additional benefits. This can be useful for presenting DuckDB output
  elsewhere by redirecting the terminal output to a file. Using the insert mode will
  build a series of SQL statements that can be used to insert the data at a later
  point. The markdown mode is particularly useful for building documentation and the
  latex mode is useful for writing academic papers. Warning Unicode handling in Windows
  Terminal When long results are displayed…
resource: https://duckdb.org/docs/current/clients/cli/output_formats
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

The `.mode` [dot command](/docs/current/clients/cli/dot_commands.html) may be used to change the appearance of the tables returned in the terminal output. In addition to customizing the appearance, these modes have additional benefits. This can be useful for presenting DuckDB output elsewhere by redirecting the terminal [output to a file](/docs/current/clients/cli/dot_commands.html#output-writing-results-to-a-file). Using the `insert` mode will build a series of SQL statements that can be used to insert the data at a later point.
The `markdown` mode is particularly useful for building documentation and the `latex` mode is useful for writing academic papers.

  Warning Unicode handling in Windows Terminal

When long results are displayed in Windows Terminal the [more system utility](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/more)
is used by default to provide the scrolling through the results. This utility has incomplete support of Unicode,
depending on the output data, in some cases it can display Unicode characters in garbled form.

We suggest using the [third-party less utility](<https://en.wikipedia.org/wiki/Less_(Unix)>) instead,
that is installed by default along with the [Git for Windows](https://git-scm.com/install/windows) installation.
It can be enabled the following way:

```
.pager '"C:\Program Files\Git\usr\bin\less.exe" -R'
```

## 
        
        [List of Output Formats](#list-of-output-formats)
        
      

    
| Mode | Description | 
|---|---|
| `ascii` | Columns/rows delimited by 0x1F and 0x1E | 
| `box` | Tables using unicode box-drawing characters | 
| `csv` | Comma-separated values | 
| `column` | Output in columns (See `.width` ) | 
| `duckbox` | Tables with extensive features (default) | 
| `html` | HTML `<table>` code | 
| `insert TABLE` | SQL insert statements for `TABLE` | 
| `json` | Results in a JSON array | 
| `jsonlines` | Results in a NDJSON | 
| `latex` | LaTeX tabular environment code | 
| `line` | One value per line | 
| `list` | Values delimited by `\|` | 
| `markdown` | Markdown table format | 
| `quote` | Escape answers as for SQL | 
| `table` | ASCII-art table | 
| `tabs` | Tab-separated values | 
| `tcl` | TCL list elements | 
| `trash` | No output | 

## 
        
        [Changing the Output Format](#changing-the-output-format)
        
      

    
Use the vanilla `.mode` dot command to query the appearance currently in use.

```
.mode
```
```
current output mode: duckbox
```
Use the `.mode` dot command with an argument to set the output format.

```
.mode markdown
SELECT 'quacking intensifies' AS incoming_ducks;
```
```
|    incoming_ducks    |
|----------------------|
| quacking intensifies |
```
The output appearance can also be adjusted with the `.separator` command. If using an export mode that relies on a separator (`csv` or `tabs` for example), the separator will be reset when the mode is changed. For example, `.mode csv` will set the separator to a comma (`,`). Using `.separator "|"` will then convert the output to be pipe-separated.

```
.mode csv
SELECT 1 AS col_1, 2 AS col_2
UNION ALL
SELECT 10 AS col1, 20 AS col_2;
```
```
col_1,col_2
1,2
10,20
```
```
.separator "|"
SELECT 1 AS col_1, 2 AS col_2
UNION ALL
SELECT 10 AS col1, 20 AS col_2;
```
```
col_1|col_2
1|2
10|20
```
## 
        
        [Paging](#paging)
        
      

    
The CLI supports paging for large result sets using the `.pager` command. When enabled, results that exceed the terminal size are displayed in a pager (such as `less`) for easier navigation.

The pager has three modes:

- `automatic` (default) – The pager is triggered when the result exceeds the row or column threshold.
- `on` – The pager is always used for output.
- `off` – The pager is disabled.

```
.pager on
```
```
.pager off
```
```
.pager automatic
```
In automatic mode, the thresholds for triggering the pager can be configured:

```
.pager set_row_threshold 50
.pager set_column_threshold 5
```
A custom pager command can be set by passing it as an argument:

```
.pager less -RS
```
The default pager command can also be configured via the `DUCKDB_PAGER` or `PAGER` environment variables.

## 
        
        [`duckbox` Mode](#duckbox-mode)
        
      

    
`duckbox` Mode
By default, DuckDB renders query results in `duckbox` mode, which is a feature-rich ASCII-art style output format.

The duckbox mode supports the `large_number_rendering` option, which allows human-readable rendering of large numbers. It has three levels:

- `off` – All numbers are printed using regular formatting.
- `footer` (default) – Large numbers are augmented with the human-readable format. Only applies to single-row results.
- `all` - All large numbers are replaced with the human-readable format.

See the following examples:

```
.large_number_rendering off
SELECT pi() * 1_000_000_000 AS x;
```
```
┌───────────────────┐
│         x         │
│      double       │
├───────────────────┤
│ 3141592653.589793 │
└───────────────────┘
```
```
.large_number_rendering footer
SELECT pi() * 1_000_000_000 AS x;
```
```
┌───────────────────┐
│         x         │
│      double       │
├───────────────────┤
│ 3141592653.589793 │
│  (3.14 billion)   │
└───────────────────┘
```
```
.large_number_rendering all
SELECT pi() * 1_000_000_000 AS x;
```
```
┌──────────────┐
│      x       │
│    double    │
├──────────────┤
│ 3.14 billion │
└──────────────┘
```

# Citations

1. Source page: https://duckdb.org/docs/current/clients/cli/output_formats
