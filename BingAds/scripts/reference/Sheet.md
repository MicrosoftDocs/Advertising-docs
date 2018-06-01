# Sheet
This class represents a worksheet within a spreadsheet.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[deleteColumns(long columnPosition, long numColumns)](#deletecolumns~long-columnposition_-long-numcolumns~)|void|Deletes the specified number of columns starting at the specified column position.
[deleteRows(long rowPosition, long numRows)](#deleterows~long-rowposition_-long-numrows~)|void|Deletes the specified number of rows in this sheet starting from the provided row index.
[getColumnWidth(long columnPosition)](#getcolumnwidth~long-columnposition~)|long|Returns the width of the specified column in pixels.
[getName](#getname)|String|Returns the name of the sheet.
[getRange(String a1Notation)](#getrange~string-a1notation~)|[Range](./Range)|Returns a range from this sheet specified in A1 or R1C1 notation.
[getRowHeight(long rowPosition)](#getrowheight~long-rowposition~)|int|Gets the height of the specified row in pixels.
[insertColumn(long columnIndex)](#insertcolumn~long-columnindex~)|[Sheet](./Sheet)|Insert a column at the specified column index.
[insertColumnsAfter(long columnIndex, long numColumns)](#insertcolumnsafter~long-columnindex_-long-numcolumns~)|[Sheet](./Sheet)|Inserts the specified number of new columns after the specified column index.
[insertRow(long rowIndex)](#insertrow~long-rowindex~)|long|Insert a row at the specified index.
[insertRowsAfter(long rowIndex, long numRows)](#insertrowsafter~long-rowindex_-long-numrows~)|[Sheet](./Sheet)|Inserts the specified number of new rows after the specified row index.
[setColumnWidth(long columnPosition, long width)](#setcolumnwidth~long-columnposition_-long-width~)|[Sheet](./Sheet)|Sets the width in pixels of the column at the specified position.
[setName(String name)](#setname~string-name~)|[Sheet](./Sheet)|Sets the name of this sheet.
[setRowHeight(long rowPosition, long height)](#setrowheight~long-rowposition_-long-height~)|[Sheet](./Sheet)|Sets the height in pixels of the row at the specified position.

## <a name="deletecolumns~long-columnposition_-long-numcolumns~"></a>deleteColumns(long columnPosition, long numColumns)
Deletes the specified number of columns starting at the specified column position. 

### Arguments:
|Name|Type|Description|
|-|-|-
columnPosition|long|Position of the first column to delete.
numColumns|long|Number of columns to delete.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="deleterows~long-rowposition_-long-numrows~"></a>deleteRows(long rowPosition, long numRows)
Deletes the specified number of rows in this sheet starting from the provided row index.

### Arguments:
|Name|Type|Description|
|-|-|-
rowPosition|long|Position of the first row to delete.
numRows|long|Number of rows to delete.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcolumnwidth~long-columnposition~"></a>getColumnWidth(long columnPosition)
Returns the width of the specified column in pixels.

### Arguments:
|Name|Type|Description|
|-|-|-
columnPosition|long|Position of the column to examine.
### Returns:
|Type|Description|
|-|-
long|Width of the specified column in pixels.

## <a name="getname"></a>getName
Returns the name of the sheet. 

### Returns:
|Type|Description|
|-|-
String|Name of the sheet.

## <a name="getrange~string-a1notation~"></a>getRange(String a1Notation)
Returns a range from this sheet specified in A1 or R1C1 notation. ```javascript
 // Get a range A1:D4 on sheet titled "Invoices"
 var ss = SpreadsheetApp.getActiveSpreadsheet();
 var range = ss.getRange("Invoices!A1:D4");

 // Get cell A1 on the first sheet
 var sheet = ss.getSheets()[0];
 var cell = sheet.getRange("A1");
```

### Arguments:
|Name|Type|Description|
|-|-|-
a1Notation|[Range](./Range)|Returns the range as specified in A1 notation.<br />
### Returns:
|Type|Description|
|-|-
[Range](./Range)|Specified range.

## <a name="getrowheight~long-rowposition~"></a>getRowHeight(long rowPosition)
Gets the height of the specified row in pixels. 

### Arguments:
|Name|Type|Description|
|-|-|-
rowPosition|int|Position of the row to examine.
### Returns:
|Type|Description|
|-|-
int|Row height in pixels.

## <a name="insertcolumn~long-columnindex~"></a>insertColumn(long columnIndex)
Insert a column at the specified column index. 

### Arguments:
|Name|Type|Description|
|-|-|-
columnIndex|long|Position where the new column should be added.
### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|Sheet, enables method chaining.

## <a name="insertcolumnsafter~long-columnindex_-long-numcolumns~"></a>insertColumnsAfter(long columnIndex, long numColumns)
Inserts the specified number of new columns after the specified column index.

### Arguments:
|Name|Type|Description|
|-|-|-
columnIndex|long|Position of the column after which the new columns should be added.
numColumns|long|Number of columns to add.
### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|Sheet, enables method chaining.

## <a name="insertrow~long-rowindex~"></a>insertRow(long rowIndex)
Insert a row at the specified index. 

### Arguments:
|Name|Type|Description|
|-|-|-
rowIndex|long|Position where the row should be inserted.
### Returns:
|Type|Description|
|-|-
long|Sheet, enables method chaining.

## <a name="insertrowsafter~long-rowindex_-long-numrows~"></a>insertRowsAfter(long rowIndex, long numRows)
Inserts the specified number of new rows after the specified row index.

### Arguments:
|Name|Type|Description|
|-|-|-
rowIndex|long|Index of the row after which the new rows should be added.
numRows|long|Number of rows to insert.
### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|Sheet, enables chaining.

## <a name="setcolumnwidth~long-columnposition_-long-width~"></a>setColumnWidth(long columnPosition, long width)
Sets the width in pixels of the column at the specified position.

### Arguments:
|Name|Type|Description|
|-|-|-
columnPosition|long|Position of the column to set the width of.
width|long|Width in pixels to set the column width to.
### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|Sheet, enables method chaining.

## <a name="setname~string-name~"></a>setName(String name)
Sets the name of this sheet.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|New name for the sheet.
### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|Sheet, enables method chaining.

## <a name="setrowheight~long-rowposition_-long-height~"></a>setRowHeight(long rowPosition, long height)
Sets the height in pixels of the row at the specified position.

### Arguments:
|Name|Type|Description|
|-|-|-
rowPosition|long|Row position to set the height of.
height|long|Height in pixels to set the row height to.
### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|Sheet, enables method chaining.

