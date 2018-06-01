# Range
This class represents a range of cells in a worksheet.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[copyTo(Range destination)](#copyto~range-destination~)|void|Copies content and formatting information from this range to the target range.
[getAddress](#getaddress)|String|Get the address of this range.
[getColumn](#getcolumn)|long|Returns the starting column position for this range.
[getFormula](#getformula)|String|Returns the formula (in A1 notation), if defined, for the top-left cell of this range.
[getLastRow](#getlastrow)|long|Returns the position of the last row of this range.
[getNumColumns](#getnumcolumns)|long|Returns the number of columns in this range.
[getNumRows](#getnumrows)|long|Returns the number of rows in this range.
[getRow](#getrow)|long|Returns the position of the row for this range.
[getValue](#getvalue)|Object|Returns the value contained by the top-left cell in this range.
[getValues](#getvalues)|Object[][]|Returns a two-dimensional array of values contained by this range, beginning with the top-left cell.
[isBlank](#isblank)|Boolean|Returns a Boolean value that indicates if this range is blank.
[setFontSize(long size)](#setfontsize~long-size~)|[Range](./Range)|Sets the specified point size to use for fonts on all the cells in this range.
[setFontWeight(String fontWeight)](#setfontweight~string-fontweight~)|[Range](./Range)|Sets the specified font weight to use for all the cells in this range. Valid values include 'normal' and 'bold'.
[setHorizontalAlignment(String alignment)](#sethorizontalalignment~string-alignment~)|[Range](./Range)|Sets the horizontal alignment of content in the cells in this range. Valid values include 'left', 'center' or 'normal'.
[setValue(Object value)](#setvalue~object-value~)|[Range](./Range)|Sets the value to all cells in this range.
[setValues(Object[][] values)](#setvalues~object[]-values~)|[Range](./Range)|Sets the specified values to the cells in this range, assigning each value to the cell based on matching row and column positions. The dimensions of the input value array must match the dimensions of this range.
[setVerticalAlignment(String alignment)](#setverticalalignment~string-alignment~)|[Range](./Range)|Sets the vertical alignment of content in the cells in this range. Valid values include 'top', 'middle' or 'bottom'.

## <a name="copyto~range-destination~"></a>copyTo(Range destination)
Copies content and formatting information from this range to the target range.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getaddress"></a>getAddress
Get the address of this range. 

### Returns:
|Type|Description|
|-|-
String|Address of the range.

## <a name="getcolumn"></a>getColumn
Returns the starting column position for this range.

### Returns:
|Type|Description|
|-|-
long|

## <a name="getformula"></a>getFormula
Returns the formula (in A1 notation), if defined, for the top-left cell of this range.

### Returns:
|Type|Description|
|-|-
String|

## <a name="getlastrow"></a>getLastRow
Returns the position of the last row of this range.

### Returns:
|Type|Description|
|-|-
long|

## <a name="getnumcolumns"></a>getNumColumns
Returns the number of columns in this range.

### Returns:
|Type|Description|
|-|-
long|

## <a name="getnumrows"></a>getNumRows
Returns the number of rows in this range.

### Returns:
|Type|Description|
|-|-
long|

## <a name="getrow"></a>getRow
Returns the position of the row for this range.

### Returns:
|Type|Description|
|-|-
long|

## <a name="getvalue"></a>getValue
Returns the value contained by the top-left cell in this range.

### Returns:
|Type|Description|
|-|-
Object|

## <a name="getvalues"></a>getValues
Returns a two-dimensional array of values contained by this range, beginning with the top-left cell.

### Returns:
|Type|Description|
|-|-
Object[][]|

## <a name="isblank"></a>isBlank
Returns a Boolean value that indicates if this range is blank.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this range is blank.

## <a name="setfontsize~long-size~"></a>setFontSize(long size)
Sets the specified point size to use for fonts on all the cells in this range.

### Returns:
|Type|Description|
|-|-
[Range](./Range)|

## <a name="setfontweight~string-fontweight~"></a>setFontWeight(String fontWeight)
Sets the specified font weight to use for all the cells in this range. Valid values include 'normal' and 'bold'.

### Arguments:
|Name|Type|Description|
|-|-|-
fontWeight|String|Font weight, either 'bold' or 'normal'.
### Returns:
|Type|Description|
|-|-
[Range](./Range)|

## <a name="sethorizontalalignment~string-alignment~"></a>setHorizontalAlignment(String alignment)
Sets the horizontal alignment of content in the cells in this range. Valid values include 'left', 'center' or 'normal'.

### Arguments:
|Name|Type|Description|
|-|-|-
alignment|String|Alignment to use.
### Returns:
|Type|Description|
|-|-
[Range](./Range)|

## <a name="setvalue~object-value~"></a>setValue(Object value)
Sets the value to all cells in this range.

### Arguments:
|Name|Type|Description|
|-|-|-
value|Object|the value for the range
### Returns:
|Type|Description|
|-|-
[Range](./Range)|

## <a name="setvalues~object[]-values~"></a>setValues(Object[][] values)
Sets the specified values to the cells in this range, assigning each value to the cell based on matching row and column positions. The dimensions of the input value array must match the dimensions of this range.

### Arguments:
|Name|Type|Description|
|-|-|-
values|Object[][]|a two-dimensional array of values
### Returns:
|Type|Description|
|-|-
[Range](./Range)|

## <a name="setverticalalignment~string-alignment~"></a>setVerticalAlignment(String alignment)
Sets the vertical alignment of content in the cells in this range. Valid values include 'top', 'middle' or 'bottom'.

### Arguments:
|Name|Type|Description|
|-|-|-
alignment|String|Alignment to use.
### Returns:
|Type|Description|
|-|-
[Range](./Range)|

