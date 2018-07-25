### Operators
The operator that you use depends on the column's type. Operators are case-sensitive. For example, you must use STARTS_WITH instead of starts\_with. 

Operators for columns that contain integers and long values: 

```
<
<=
>
>=
=
!=
```

Operators for columns that contain double values: 

```
<
>
```

Operators for columns that contain string values: 

```
=
!=
STARTS_WITH
STARTS_WITH_IGNORE_CASE
CONTAINS
CONTAINS_IGNORE_CASE
DOES_NOT_CONTAIN
DOES_NOT_CONTAIN_IGNORE_CASE
```

Operators for columns that contain enumeration values: 

```
=
!=
IN []
NOT_IN []
```

