# Blob
Provides methods to represent binary data and exchange.

|Method|Return Type|Description|
|-|-|-
copyBlob|[Blob](./Blob)|Returns a copy of this blob.<br />
getAs(String contentType)|[Blob](./Blob)|Returns the contents of this blob converted to the specified MIME type. For blobs containing images, any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.<br />
getBytes|Byte[]|Returns the contents of this blob as a byte array.<br />
getContentType|String|Returns the content type of the data stored in this blob; null if the type is not known<br />
getDataAsString|String|Returns the content of this blob as a String in UTF-8 encoding.<br />
getDataAsString(String charset)|String|Returns the content of this blob as a String in the specified encoding.<br />
getName|String|Returns the name of this blog.<br />
setBytes(Byte[] data)|[Blob](./Blob)|Sets the data to store in this blob.<br />
setContentType(String contentType)|[Blob](./Blob)|Sets the content type of the data stored in this blob.<br />
setContentTypeFromExtension(String fileExtension)|[Blob](./Blob)|Sets the content type of the data stored in this blob based on the specified file extension. If the content type cannot be guessed from the specified extension, it will be set to null.<br />
setDataFromString(String data)|[Blob](./Blob)|Sets the data to store in this blob from the provided string in UTF-8 encoding.<br />
setDataFromString(String data, String charset)|[Blob](./Blob)|Sets the data to store in this blob from the provided string in the given encoding.<br />
setName(name)|[Blob](./Blob)|Sets the name of the blob.<br />
