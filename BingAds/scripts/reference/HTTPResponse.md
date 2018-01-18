# HTTPResponse
Provides access to information about HTTP responses.

|Method|Return Type|Description|
|-|-|-
getAllHeaders|Object|Returns a JavaScript key/value map of HTTP headers.<br />
getAs(String contentType)|[Blob](./Blob)|Returns the contents of this object as a blob converted to the specified MIME type. For blobs containing images,  any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.<br />
getBlob|[Blob](./Blob)|Returns the data inside this object as a blob.<br />
getContent|Byte[]|Returns the raw binary content of this HTTP response as a byte array.<br />
getContentText|String|Returns the content of this HTTP response encoded as a string.<br />
getContentText(String charset)|String|Returns the content of this HTTP response encoded as a string using the specified character set.<br />
getHeaders|Object|Returns the attribute/value map of headers for this HTTP response.<br />
getResponseCode|int|Returns the HTTP status code (for e.g., 200 for OK) of this HTTP response.<br />
