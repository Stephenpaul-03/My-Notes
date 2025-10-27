## Type Conversion Functions

| Function | Description |
| --- | --- |
| `CAST(x AS type)` | Convert one type to another |
| `CONVERT()` | Same thing, different syntax (SQL Server) |
| `ISNULL(x, val)` | If x is null, return val (SQL Server) |
| `IFNULL(x, val)` | Same as above (MySQL) |
| `COALESCE(x1, x2, ...)` | First non-null value |
| `NULLIF(x, y)` | Returns NULL if x = y |
| `FORMAT()` | Formats number or date |
| `PARSE()` *(SQL Server)* | Parses a string to a specific type |