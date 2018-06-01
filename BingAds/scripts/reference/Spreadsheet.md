# Spreadsheet
This class represents a spreadsheet.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getId](#getid)|String|Returns the unique ID for this spreadsheet.
[getName](#getname)|String|Returns the name of this spreadsheet.
[getSheetByName(String name)](#getsheetbyname~string-name~)|[Sheet](./Sheet)|Returns the sheet with the specified name.
[getSheets](#getsheets)|[Sheet[]](./Sheet)|Returns all the sheets in this spreadsheet.
[insertSheet](#insertsheet)|[Sheet](./Sheet)|Inserts a new sheet in this spreadsheet using the default name and makes it the active sheet.

## <a name="getid"></a>getId
Returns the unique ID for this spreadsheet.

### Returns:
|Type|Description|
|-|-
String|Unique ID for this spreadsheet.

## <a name="getname"></a>getName
Returns the name of this spreadsheet.

### Returns:
|Type|Description|
|-|-
String|Name of this spreadsheet.

## <a name="getsheetbyname~string-name~"></a>getSheetByName(String name)
Returns the sheet with the specified name.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Name of the sheet to get.
### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|Sheet with the specified name.

## <a name="getsheets"></a>getSheets
Returns all the sheets in this spreadsheet.

### Returns:
|Type|Description|
|-|-
[Sheet[]](./Sheet)|Array of all the sheets in this spreadsheet.

## <a name="insertsheet"></a>insertSheet
Inserts a new sheet in this spreadsheet using the default name and makes it the active sheet.

### Returns:
|Type|Description|
|-|-
[Sheet](./Sheet)|New sheet.

