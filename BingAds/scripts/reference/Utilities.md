# Utilities
Provides utility methods for encoding/decoding data, formatting dates, manipulating JSON data and other miscellaneous logic.

|Method|Return Type|Description|
|-|-|-
base64Decode(String encoded)|Byte[]|Returns the raw data represented by the argument as a byte array. The argument needs to be encoded as base-64.<br />
base64Encode(String encoded, Charset charset)|Byte[]|Returns the raw data represented by the argument as a byte array and in the specified character set. The argument needs to be encoded as base-64.<br />
computeHmacSignature(MacAlgorithm algorithm, String value, String key)|Byte[]|Returns a message authentication code computed by the specified algorithm on the specified key and value.<br />
formatDate(Date date, String timeZone, String format)|String|Returns a date formatted according to the <br />
formatString(String template, Object... args)|String|Returns a string with <br />
newBlob(Byte[] data)|[Blob](./Blob)|Creates a new blob object from the provided byte array.<br />
newBlob(Byte[] data, String contentType)|[Blob](./Blob)|Creates a new blob object from the provided byte array and content type (can be null). <br />
newBlob(Byte[] data, String contentType, String name)|[Blob](./Blob)|Creates a new blob object from the provided byte array, content type (can be null), and name.<br />
newBlob(String data)|[Blob](./Blob)|Creates a new blob object from the provided string.<br />
newBlob(String data, String contentType)|[Blob](./Blob)|Creates a new blob object from the provided string and content type (can be null). <br />
newBlob(String data, String contentType, String name)|[Blob](./Blob)|Creates a new blob object from the provided string, content type (can be null), and name.<br />
parseCsv(String csv)|String[][]|Returns a 2D string array parsed from the specified CSV string.<br />
parseCsv(String csv, Char delimiter)|String[][]|Returns a 2D string array parsed from the specified CSV string and the custom delimiter character.<br />
Sleep(int milliseconds)|void|Pauses the execution of the script for the specified number of milliseconds. The maximum allowed value for the argument is 300000 (or 5 minutes).<br />
unzip(Blob blob)|[Blob[]](./Blob)|Decompresses and returns the component files contained within the blob representing a zip file. <br />
zip(Blob[] blobs)|[Blob](./Blob)|Compresses the files in the blob array and returns a blob representing a zip file.<br />
zip(Blob[] blobs, String name)|[Blob](./Blob)|Compresses the files in the blob array and returns a blob representing a zip file with the name specified in the second argument.<br />
