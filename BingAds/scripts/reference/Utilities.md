# Utilities
Provides utility methods for encoding/decoding data, formatting dates, manipulating JSON data and other miscellaneous logic.

|Method|Return Type|Description|
|-|-|-
[base64Decode(String encoded)]('#base64Decode-String-encoded)')|Byte[]|Returns the raw data represented by the argument as a byte array. The argument needs to be encoded as base-64.<br />
[base64Encode(String encoded, Charset charset)]('#base64Encode-String-encoded_ Charset charset)')|Byte[]|Returns the raw data represented by the argument as a byte array and in the specified character set. The argument needs to be encoded as base-64.<br />
[computeHmacSignature(MacAlgorithm algorithm, String value, String key)]('#computeHmacSignature-MacAlgorithm-algorithm_ String value, String key)')|Byte[]|Returns a message authentication code computed by the specified algorithm on the specified key and value.<br />
[formatDate(Date date, String timeZone, String format)]('#formatDate-Date-date_ String timeZone, String format)')|String|Returns a date formatted according to the <br />
[formatString(String template, Object... args)]('#formatString-String-template_ Object... args)')|String|Returns a string with <br />
[newBlob(Byte[] data)]('#newBlob-Byte-data)')|[Blob](./Blob)|Creates a new blob object from the provided byte array.<br />
[newBlob(Byte[] data, String contentType)]('#newBlob-Byte-data_ String contentType)')|[Blob](./Blob)|Creates a new blob object from the provided byte array and content type (can be null). <br />
[newBlob(Byte[] data, String contentType, String name)]('#newBlob-Byte-data_ String contentType, String name)')|[Blob](./Blob)|Creates a new blob object from the provided byte array, content type (can be null), and name.<br />
[newBlob(String data)]('#newBlob-String-data)')|[Blob](./Blob)|Creates a new blob object from the provided string.<br />
[newBlob(String data, String contentType)]('#newBlob-String-data_ String contentType)')|[Blob](./Blob)|Creates a new blob object from the provided string and content type (can be null). <br />
[newBlob(String data, String contentType, String name)]('#newBlob-String-data_ String contentType, String name)')|[Blob](./Blob)|Creates a new blob object from the provided string, content type (can be null), and name.<br />
[parseCsv(String csv)]('#parseCsv-String-csv)')|String[][]|Returns a 2D string array parsed from the specified CSV string.<br />
[parseCsv(String csv, Char delimiter)]('#parseCsv-String-csv_ Char delimiter)')|String[][]|Returns a 2D string array parsed from the specified CSV string and the custom delimiter character.<br />
[Sleep(int milliseconds)]('#Sleep-int-milliseconds)')|void|Pauses the execution of the script for the specified number of milliseconds. The maximum allowed value for the argument is 300000 (or 5 minutes).<br />
[unzip(Blob blob)]('#unzip-Blob-blob)')|[Blob[]](./Blob)|Decompresses and returns the component files contained within the blob representing a zip file. <br />
[zip(Blob[] blobs)]('#zip-Blob-blobs)')|[Blob](./Blob)|Compresses the files in the blob array and returns a blob representing a zip file.<br />
[zip(Blob[] blobs, String name)]('#zip-Blob-blobs_ String name)')|[Blob](./Blob)|Compresses the files in the blob array and returns a blob representing a zip file with the name specified in the second argument.<br />

<a name="base64Decode-String-encoded)"></a>
## base64Decode(String encoded)
Returns the raw data represented by the argument as a byte array. The argument needs to be encoded as base-64.


<a name="base64Encode-String-encoded_ Charset charset)"></a>
## base64Encode(String encoded, Charset charset)
Returns the raw data represented by the argument as a byte array and in the specified character set. The argument needs to be encoded as base-64.


<a name="computeHmacSignature-MacAlgorithm-algorithm_ String value, String key)"></a>
## computeHmacSignature(MacAlgorithm algorithm, String value, String key)
Returns a message authentication code computed by the specified algorithm on the specified key and value.


<a name="formatDate-Date-date_ String timeZone, String format)"></a>
## formatDate(Date date, String timeZone, String format)
Returns a date formatted according to the 


<a name="formatString-String-template_ Object... args)"></a>
## formatString(String template, Object... args)
Returns a string with 


<a name="newBlob-Byte-data)"></a>
## newBlob(Byte[] data)
Creates a new blob object from the provided byte array.


<a name="newBlob-Byte-data_ String contentType)"></a>
## newBlob(Byte[] data, String contentType)
Creates a new blob object from the provided byte array and content type (can be null). 


<a name="newBlob-Byte-data_ String contentType, String name)"></a>
## newBlob(Byte[] data, String contentType, String name)
Creates a new blob object from the provided byte array, content type (can be null), and name.


<a name="newBlob-String-data)"></a>
## newBlob(String data)
Creates a new blob object from the provided string.


<a name="newBlob-String-data_ String contentType)"></a>
## newBlob(String data, String contentType)
Creates a new blob object from the provided string and content type (can be null). 


<a name="newBlob-String-data_ String contentType, String name)"></a>
## newBlob(String data, String contentType, String name)
Creates a new blob object from the provided string, content type (can be null), and name.


<a name="parseCsv-String-csv)"></a>
## parseCsv(String csv)
Returns a 2D string array parsed from the specified CSV string.


<a name="parseCsv-String-csv_ Char delimiter)"></a>
## parseCsv(String csv, Char delimiter)
Returns a 2D string array parsed from the specified CSV string and the custom delimiter character.


<a name="Sleep-int-milliseconds)"></a>
## Sleep(int milliseconds)
Pauses the execution of the script for the specified number of milliseconds. The maximum allowed value for the argument is 300000 (or 5 minutes).


<a name="unzip-Blob-blob)"></a>
## unzip(Blob blob)
Decompresses and returns the component files contained within the blob representing a zip file. 


<a name="zip-Blob-blobs)"></a>
## zip(Blob[] blobs)
Compresses the files in the blob array and returns a blob representing a zip file.


<a name="zip-Blob-blobs_ String name)"></a>
## zip(Blob[] blobs, String name)
Compresses the files in the blob array and returns a blob representing a zip file with the name specified in the second argument.


