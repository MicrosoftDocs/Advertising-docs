### Operators
The operator that you use in a condition call depends on the column's type. Operators are case-sensitive. For example, "starts\_with" won't work (you must use STARTS_WITH). 

For Integer and Long columns: 

```
<  <=  >  >=  =  !=
```

For Double columns: 

```
<  >
```

For String columns: 

```
=  !=  STARTS_WITH  STARTS_WITH_IGNORE_CASE  CONTAINS
 CONTAINS_IGNORE_CASE  DOES_NOT_CONTAIN  DOES_NOT_CONTAIN_IGNORE_CASE
```

For Enumeration columns: 

```
=  !=  IN []  NOT_IN []
```

