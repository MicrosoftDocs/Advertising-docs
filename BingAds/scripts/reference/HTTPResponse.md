# HTTPResponse
Provides access to information about HTTP responses.

|Method|Return Type|Description|
|-|-|-
[getAllHeaders]('#getAllHeaders}')|Object|Returns a JavaScript key/value map of HTTP headers.<br />
[getAs(String contentType)]('#getAs-String-contentType)}')|[Blob](./Blob)|Returns the contents of this object as a blob converted to the specified MIME type. For blobs containing images,  any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.<br />
[getBlob]('#getBlob}')|[Blob](./Blob)|Returns the data inside this object as a blob.<br />
[getContent]('#getContent}')|Byte[]|Returns the raw binary content of this HTTP response as a byte array.<br />
[getContentText]('#getContentText}')|String|Returns the content of this HTTP response encoded as a string.<br />
[getContentText(String charset)]('#getContentText-String-charset)}')|String|Returns the content of this HTTP response encoded as a string using the specified character set.<br />
[getHeaders]('#getHeaders}')|Object|Returns the attribute/value map of headers for this HTTP response.<br />
[getResponseCode]('#getResponseCode}')|int|Returns the HTTP status code (for e.g., 200 for OK) of this HTTP response.<br />

<a name="#getAllHeaders"></a>
## getAllHeaders
Returns a JavaScript key/value map of HTTP headers.


<a name="#getAs-String-contentType)"></a>
## getAs(String contentType)
Returns the contents of this object as a blob converted to the specified MIME type. For blobs containing images,  any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.


<a name="#getBlob"></a>
## getBlob
Returns the data inside this object as a blob.


<a name="#getContent"></a>
## getContent
Returns the raw binary content of this HTTP response as a byte array.


<a name="#getContentText"></a>
## getContentText
Returns the content of this HTTP response encoded as a string.


<a name="#getContentText-String-charset)"></a>
## getContentText(String charset)
Returns the content of this HTTP response encoded as a string using the specified character set.


<a name="#getHeaders"></a>
## getHeaders
Returns the attribute/value map of headers for this HTTP response.


<a name="#getResponseCode"></a>
## getResponseCode
Returns the HTTP status code (for e.g., 200 for OK) of this HTTP response.


