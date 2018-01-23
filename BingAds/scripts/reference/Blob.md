# Blob
Provides methods to represent binary data and exchange.

|Method|Return Type|Description|
|-|-|-
[copyBlob]('#copyBlob')|[Blob](./Blob)|Returns a copy of this blob.<br />
[getAs(String contentType)]('#getAs-String-contentType)')|[Blob](./Blob)|Returns the contents of this blob converted to the specified MIME type. For blobs containing images, any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.<br />
[getBytes]('#getBytes')|Byte[]|Returns the contents of this blob as a byte array.<br />
[getContentType]('#getContentType')|String|Returns the content type of the data stored in this blob; null if the type is not known<br />
[getDataAsString]('#getDataAsString')|String|Returns the content of this blob as a String in UTF-8 encoding.<br />
[getDataAsString(String charset)]('#getDataAsString-String-charset)')|String|Returns the content of this blob as a String in the specified encoding.<br />
[getName]('#getName')|String|Returns the name of this blog.<br />
[setBytes(Byte[] data)]('#setBytes-Byte-data)')|[Blob](./Blob)|Sets the data to store in this blob.<br />
[setContentType(String contentType)]('#setContentType-String-contentType)')|[Blob](./Blob)|Sets the content type of the data stored in this blob.<br />
[setContentTypeFromExtension(String fileExtension)]('#setContentTypeFromExtension-String-fileExtension)')|[Blob](./Blob)|Sets the content type of the data stored in this blob based on the specified file extension. If the content type cannot be guessed from the specified extension, it will be set to null.<br />
[setDataFromString(String data)]('#setDataFromString-String-data)')|[Blob](./Blob)|Sets the data to store in this blob from the provided string in UTF-8 encoding.<br />
[setDataFromString(String data, String charset)]('#setDataFromString-String-data_ String charset)')|[Blob](./Blob)|Sets the data to store in this blob from the provided string in the given encoding.<br />
[setName(name)]('#setName-name)')|[Blob](./Blob)|Sets the name of the blob.<br />

<a name="#copyBlob"></a>
## copyBlob
Returns a copy of this blob.


<a name="#getAs-String-contentType)"></a>
## getAs(String contentType)
Returns the contents of this blob converted to the specified MIME type. For blobs containing images, any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.


<a name="#getBytes"></a>
## getBytes
Returns the contents of this blob as a byte array.


<a name="#getContentType"></a>
## getContentType
Returns the content type of the data stored in this blob; null if the type is not known


<a name="#getDataAsString"></a>
## getDataAsString
Returns the content of this blob as a String in UTF-8 encoding.


<a name="#getDataAsString-String-charset)"></a>
## getDataAsString(String charset)
Returns the content of this blob as a String in the specified encoding.


<a name="#getName"></a>
## getName
Returns the name of this blog.


<a name="#setBytes-Byte-data)"></a>
## setBytes(Byte[] data)
Sets the data to store in this blob.


<a name="#setContentType-String-contentType)"></a>
## setContentType(String contentType)
Sets the content type of the data stored in this blob.


<a name="#setContentTypeFromExtension-String-fileExtension)"></a>
## setContentTypeFromExtension(String fileExtension)
Sets the content type of the data stored in this blob based on the specified file extension. If the content type cannot be guessed from the specified extension, it will be set to null.


<a name="#setDataFromString-String-data)"></a>
## setDataFromString(String data)
Sets the data to store in this blob from the provided string in UTF-8 encoding.


<a name="#setDataFromString-String-data_ String charset)"></a>
## setDataFromString(String data, String charset)
Sets the data to store in this blob from the provided string in the given encoding.


<a name="#setName-name)"></a>
## setName(name)
Sets the name of the blob.


