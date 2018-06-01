# SpreadsheetApp
This class allows users to open and create spreadsheets on OneDrive.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[create(String name)](#create~string-name~)|[Spreadsheet](./Spreadsheet)|Creates a new spreadsheet with the specified name.
[openById(String id)](#openbyid~string-id~)|[Spreadsheet](./Spreadsheet)|Opens the spreadsheet with the specified ID.
[openByName(String name)](#openbyname~string-name~)|[Spreadsheet](./Spreadsheet)|Opens the spreadsheet identified by the specified name.

## <a name="create~string-name~"></a>create(String name)
Creates a new spreadsheet with the specified name.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Name for the new spreadsheet.
### Returns:
|Type|Description|
|-|-
[Spreadsheet](./Spreadsheet)|New spreadsheet.

## <a name="openbyid~string-id~"></a>openById(String id)
Opens the spreadsheet with the specified ID.

### Returns:
|Type|Description|
|-|-
[Spreadsheet](./Spreadsheet)|Spreadsheet with the specified ID.

## <a name="openbyname~string-name~"></a>openByName(String name)
Opens the spreadsheet identified by the specified name.

### Arguments:
|Name|Type|Description|
|-|-|-
arg1|String|Name of the spreadsheet to open.
### Returns:
|Type|Description|
|-|-
[Spreadsheet](./Spreadsheet)|Spreadsheet identified by the specified name.

