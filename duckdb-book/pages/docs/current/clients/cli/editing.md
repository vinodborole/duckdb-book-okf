---
type: Web Page
title: Editing – DuckDB
description: The linenoise-based CLI editor is available for macOS, Linux and Windows.
  DuckDB's CLI uses a line-editing library based on linenoise, which has shortcuts
  that are based on Emacs mode of readline. Below is a list of available commands.
  You can also view these shortcuts from within the CLI using .help shortcuts. Moving
  Key Action Left Move back a character Right Move forward a character Up Move up
  a line. When on the first line, move to previous history entry Down Move down a
  line. When on last line, move to next history entry Home Move to beginning of buffer
  End…
resource: https://duckdb.org/docs/current/clients/cli/editing
timestamp: '2026-08-24T07:05:55.104476+00:00'
---

Search Shortcut cmd + k | ctrl + k
		

	
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

Editing

					
  The linenoise-based CLI editor is available for macOS, Linux and Windows.

DuckDB's CLI uses a line-editing library based on [linenoise](https://github.com/antirez/linenoise), which has shortcuts that are based on [Emacs mode of readline](https://readline.kablamo.org/emacs.html). Below is a list of available commands. You can also view these shortcuts from within the CLI using `.help shortcuts`.

## 
        
        [Moving](#moving)
        
      

    
| Key | Action | 
|---|---|
| `Left` | Move back a character | 
| `Right` | Move forward a character | 
| `Up` | Move up a line. When on the first line, move to previous history entry | 
| `Down` | Move down a line. When on last line, move to next history entry | 
| `Home` | Move to beginning of buffer | 
| `End` | Move to end of buffer | 
| `Ctrl` +`Left` | Move back a word | 
| `Ctrl` +`Right` | Move forward a word | 
| `Ctrl` +`A` | Move to beginning of buffer | 
| `Ctrl` +`B` | Move back a character | 
| `Ctrl` +`E` | Move to end of buffer | 
| `Ctrl` +`F` | Move forward a character | 
| `Alt` +`Left` | Move back a word | 
| `Alt` +`Right` | Move forward a word | 

## 
        
        [History](#history)
        
      

    
| Key | Action | 
|---|---|
| `Ctrl` +`P` | Move to previous history entry | 
| `Ctrl` +`N` | Move to next history entry | 
| `Ctrl` +`R` | Search the history | 
| `Ctrl` +`S` | Search the history | 
| `Alt` +`<` | Move to first history entry | 
| `Alt` +`>` | Move to last history entry | 
| `Alt` +`N` | Search the history | 
| `Alt` +`P` | Search the history | 

## 
        
        [Changing Text](#changing-text)
        
      

    
| Key | Action | 
|---|---|
| `Backspace` | Delete previous character | 
| `Delete` | Delete next character | 
| `Ctrl` +`D` | Delete next character. When buffer is empty, end editing | 
| `Ctrl` +`H` | Delete previous character | 
| `Ctrl` +`K` | Delete everything after the cursor | 
| `Ctrl` +`T` | Swap current and next character | 
| `Ctrl` +`U` | Delete all text | 
| `Ctrl` +`W` | Delete previous word | 
| `Alt` +`C` | Convert next word to titlecase | 
| `Alt` +`D` | Delete next word | 
| `Alt` +`L` | Convert next word to lowercase | 
| `Alt` +`R` | Delete all text | 
| `Alt` +`T` | Swap current and next word | 
| `Alt` +`U` | Convert next word to uppercase | 
| `Alt` +`Backspace` | Delete previous word | 
| `Alt` +`\` | Delete spaces around cursor | 

## 
        
        [Completing](#completing)
        
      

    
| Key | Action | 
|---|---|
| `Tab` | Autocomplete. When autocompleting, cycle to next entry | 
| `Shift` +`Tab` | When autocompleting, cycle to previous entry | 
| `Esc` +`Esc` | When autocompleting, revert autocompletion | 

## 
        
        [Miscellaneous](#miscellaneous)
        
      

    
| Key | Action | 
|---|---|
| `Enter` | Execute query. If query is not complete, insert a newline at the end of the buffer | 
| `Ctrl` +`J` | Execute query. If query is not complete, insert a newline at the end of the buffer | 
| `Ctrl` +`C` | Cancel editing of current query | 
| `Ctrl` +`G` | Cancel editing of current query | 
| `Ctrl` +`L` | Clear screen | 
| `Ctrl` +`O` | Cancel editing of current query | 
| `Ctrl` +`X` | Insert a newline after the cursor | 
| `Ctrl` +`Q` , then click | Move cursor to mouse click position | 
| `Ctrl` +`Z` | Suspend CLI and return to shell, use `fg` to re-open | 

## 
        
        [External Editor Mode](#external-editor-mode)
        
      

    
Use `.edit` or `\e` to open a query in an external text editor.

- When entered alone, it opens the previous command for editing.
- When used inside a multi-line command, it opens the current command in the editor.

The editor is taken from the first set environment variable among `DUCKDB_EDITOR`, `EDITOR` or `VISUAL` (in that order). If none are set, `vi` is used.

## 
        
        [Using Read-Line](#using-read-line)
        
      

    
If you prefer, you can use [`rlwrap`](https://github.com/hanslub42/rlwrap) to use read-line directly with the shell. Then, use `Shift`+`Enter` to insert a newline and `Enter` to execute the query:

```
rlwrap --substitute-prompt="D " duckdb -batch
```
© 2026 DuckDB Foundation, Amsterdam NL

# Citations

1. Source page: https://duckdb.org/docs/current/clients/cli/editing
