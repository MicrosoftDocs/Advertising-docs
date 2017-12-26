# Utilities
Provides utility methods for encoding/decoding data, formatting dates, manipulating JSON data and other miscellaneous logic.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[base64Decode(String encoded)](#base64decode~string-encoded~)|Byte[]|Returns the raw data represented by the argument as a byte array. The argument needs to be encoded as base-64.<br />
[base64Encode(String encoded, Charset charset)](#base64encode~string-encoded_-charset-charset~)|Byte[]|Returns the raw data represented by the argument as a byte array and in the specified character set. The argument needs to be encoded as base-64.<br />
[computeHmacSignature(MacAlgorithm algorithm, String value, String key)](#computehmacsignature~macalgorithm-algorithm_-string-value_-string-key~)|Byte[]|Returns a message authentication code computed by the specified algorithm on the specified key and value.<br />
[formatDate(Date date, String timeZone, String format)](#formatdate~date-date_-string-timezone_-string-format~)|String|Returns a date formatted according to the <br />
[formatString(String template, Object... args)](#formatstring~string-template_-object...-args~)|String|Returns a string with <br />
[newBlob(Byte[] data)](#newblob~byte-data~)|[Blob](./Blob)|Creates a new blob object from the provided byte array.<br />
[newBlob(Byte[] data, String contentType)](#newblob~byte-data_-string-contenttype~)|[Blob](./Blob)|Creates a new blob object from the provided byte array and content type (can be null). <br />
[newBlob(Byte[] data, String contentType, String name)](#newblob~byte-data_-string-contenttype_-string-name~)|[Blob](./Blob)|Creates a new blob object from the provided byte array, content type (can be null), and name.<br />
[newBlob(String data)](#newblob~string-data~)|[Blob](./Blob)|Creates a new blob object from the provided string.<br />
[newBlob(String data, String contentType)](#newblob~string-data_-string-contenttype~)|[Blob](./Blob)|Creates a new blob object from the provided string and content type (can be null). <br />
[newBlob(String data, String contentType, String name)](#newblob~string-data_-string-contenttype_-string-name~)|[Blob](./Blob)|Creates a new blob object from the provided string, content type (can be null), and name.<br />
[parseCsv(String csv)](#parsecsv~string-csv~)|String[][]|Returns a 2D string array parsed from the specified CSV string.<br />
[parseCsv(String csv, Char delimiter)](#parsecsv~string-csv_-char-delimiter~)|String[][]|Returns a 2D string array parsed from the specified CSV string and the custom delimiter character.<br />
[Sleep(int milliseconds)](#sleep~int-milliseconds~)|void|Pauses the execution of the script for the specified number of milliseconds. The maximum allowed value for the argument is 300000 (or 5 minutes).<br />
[unzip(Blob blob)](#unzip~blob-blob~)|[Blob[]](./Blob)|Decompresses and returns the component files contained within the blob representing a zip file. <br />
[zip(Blob[] blobs)](#zip~blob-blobs~)|[Blob](./Blob)|Compresses the files in the blob array and returns a blob representing a zip file.<br />
[zip(Blob[] blobs, String name)](#zip~blob-blobs_-string-name~)|[Blob](./Blob)|Compresses the files in the blob array and returns a blob representing a zip file with the name specified in the second argument.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="base64decode~string-encoded~"></a>base64Decode(String encoded)
Returns the raw data represented by the argument as a byte array. The argument needs to be encoded as base-64.

### Returns:
|Type|Description|
|-|-
Byte[]|
&nbsp;|&nbsp;
## <a name="base64encode~string-encoded_-charset-charset~"></a>base64Encode(String encoded, Charset charset)
Returns the raw data represented by the argument as a byte array and in the specified character set. The argument needs to be encoded as base-64.

### Returns:
|Type|Description|
|-|-
Byte[]|
&nbsp;|&nbsp;
## <a name="computehmacsignature~macalgorithm-algorithm_-string-value_-string-key~"></a>computeHmacSignature(MacAlgorithm algorithm, String value, String key)
Returns a message authentication code computed by the specified algorithm on the specified key and value.

### Returns:
|Type|Description|
|-|-
Byte[]|
&nbsp;|&nbsp;
## <a name="formatdate~date-date_-string-timezone_-string-format~"></a>formatDate(Date date, String timeZone, String format)
Returns a date formatted according to the 

### Returns:
|Type|Description|
|-|-
String|
&nbsp;|&nbsp;
## <a name="formatstring~string-template_-object...-args~"></a>formatString(String template, Object... args)
Returns a string with 

### Returns:
|Type|Description|
|-|-
String|
&nbsp;|&nbsp;
## <a name="newblob~byte-data~"></a>newBlob(Byte[] data)
Creates a new blob object from the provided byte array.

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
## <a name="newblob~byte-data_-string-contenttype~"></a>newBlob(Byte[] data, String contentType)
Creates a new blob object from the provided byte array and content type (can be null). 

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
## <a name="newblob~byte-data_-string-contenttype_-string-name~"></a>newBlob(Byte[] data, String contentType, String name)
Creates a new blob object from the provided byte array, content type (can be null), and name.

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
## <a name="newblob~string-data~"></a>newBlob(String data)
Creates a new blob object from the provided string.

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
## <a name="newblob~string-data_-string-contenttype~"></a>newBlob(String data, String contentType)
Creates a new blob object from the provided string and content type (can be null). 

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
## <a name="newblob~string-data_-string-contenttype_-string-name~"></a>newBlob(String data, String contentType, String name)
Creates a new blob object from the provided string, content type (can be null), and name.

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
## <a name="parsecsv~string-csv~"></a>parseCsv(String csv)
Returns a 2D string array parsed from the specified CSV string.

### Returns:
|Type|Description|
|-|-
String[][]|
&nbsp;|&nbsp;
## <a name="parsecsv~string-csv_-char-delimiter~"></a>parseCsv(String csv, Char delimiter)
Returns a 2D string array parsed from the specified CSV string and the custom delimiter character.

### Returns:
|Type|Description|
|-|-
String[][]|
&nbsp;|&nbsp;
## <a name="sleep~int-milliseconds~"></a>Sleep(int milliseconds)
Pauses the execution of the script for the specified number of milliseconds. The maximum allowed value for the argument is 300000 (or 5 minutes).

### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="unzip~blob-blob~"></a>unzip(Blob blob)
Decompresses and returns the component files contained within the blob representing a zip file. 

### Returns:
|Type|Description|
|-|-
[Blob[]](./Blob)|
&nbsp;|&nbsp;
## <a name="zip~blob-blobs~"></a>zip(Blob[] blobs)
Compresses the files in the blob array and returns a blob representing a zip file.

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
## <a name="zip~blob-blobs_-string-name~"></a>zip(Blob[] blobs, String name)
Compresses the files in the blob array and returns a blob representing a zip file with the name specified in the second argument.

### Returns:
|Type|Description|
|-|-
[Blob](./Blob)|
&nbsp;|&nbsp;
