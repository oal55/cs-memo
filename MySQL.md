# MySQL Notes
SQL uses three-valued-logic, true, false and NULL.


#### NULL


- Think of NULL as '*could be anything*'. Hence each of the following expressions evaluates to '*could be anything*':
  - `1 = NULL`
  - `1 != NULL` or `1 <> NULL`
  - `NULL = NULL`
- Use `is NULL` predicate to match NULL values.
- However, not every logical expression that includes a NULL term evaluates to NULL:
  - `(NULL = 1) or (1 = 1)` evaluates to true.
  - `(NULL = 1) and (1 = 0)` evaluates to false.
- Logical NULL indicates that a result *actually* depends on a NULL value.

