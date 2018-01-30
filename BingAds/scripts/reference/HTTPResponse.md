# HTTPResponse
Provides access to information about HTTP responses.

## Methods
|Method Name|Return Type|Description|
|-|-|-
[getAllHeaders](#getallheaders)|Object|Returns a JavaScript key/value map of HTTP headers.<br />
[getAs(String contentType)](#getas~string-contenttype~)|[Blob](./Blob)|Returns the contents of this object as a blob converted to the specified MIME type. For blobs containing images,  any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.<br />
[getBlob](#getblob)|[Blob](./Blob)|Returns the data inside this object as a blob.<br />
[getContent](#getcontent)|Byte[]|Returns the raw binary content of this HTTP response as a byte array.<br />
[getContentText](#getcontenttext)|String|Returns the content of this HTTP response encoded as a string.<br />
[getContentText(String charset)](#getcontenttext~string-charset~)|String|Returns the content of this HTTP response encoded as a string using the specified character set.<br />
[getHeaders](#getheaders)|Object|Returns the attribute/value map of headers for this HTTP response.<br />
[getResponseCode](#getresponsecode)|int|Returns the HTTP status code (for e.g., 200 for OK) of this HTTP response.<br />

## <a name="getallheaders"></a>getAllHeaders
Returns a JavaScript key/value map of HTTP headers.


## <a name="getas~string-contenttype~"></a>getAs(String contentType)
Returns the contents of this object as a blob converted to the specified MIME type. For blobs containing images,  any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.


## <a name="getblob"></a>getBlob
Returns the data inside this object as a blob.


## <a name="getcontent"></a>getContent
Returns the raw binary content of this HTTP response as a byte array.


## <a name="getcontenttext"></a>getContentText
Returns the content of this HTTP response encoded as a string.


## <a name="getcontenttext~string-charset~"></a>getContentText(String charset)
Returns the content of this HTTP response encoded as a string using the specified character set.


## <a name="getheaders"></a>getHeaders
Returns the attribute/value map of headers for this HTTP response.


## <a name="getresponsecode"></a>getResponseCode
Returns the HTTP status code (for e.g., 200 for OK) of this HTTP response.


