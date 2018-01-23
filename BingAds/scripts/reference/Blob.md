# Blob
Provides methods to represent binary data and exchange.

|Method|Return Type|Description|
|-|-|-
[copyBlob]("#copyblob")|[Blob](./Blob)|Returns a copy of this blob.<br />
[getAs(String contentType)]("#getas~string-contenttype~")|[Blob](./Blob)|Returns the contents of this blob converted to the specified MIME type. For blobs containing images, any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.<br />
[getBytes]("#getbytes")|Byte[]|Returns the contents of this blob as a byte array.<br />
[getContentType]("#getcontenttype")|String|Returns the content type of the data stored in this blob; null if the type is not known<br />
[getDataAsString]("#getdataasstring")|String|Returns the content of this blob as a String in UTF-8 encoding.<br />
[getDataAsString(String charset)]("#getdataasstring~string-charset~")|String|Returns the content of this blob as a String in the specified encoding.<br />
[getName]("#getname")|String|Returns the name of this blog.<br />
[setBytes(Byte[] data)]("#setbytes~byte-data~")|[Blob](./Blob)|Sets the data to store in this blob.<br />
[setContentType(String contentType)]("#setcontenttype~string-contenttype~")|[Blob](./Blob)|Sets the content type of the data stored in this blob.<br />
[setContentTypeFromExtension(String fileExtension)]("#setcontenttypefromextension~string-fileextension~")|[Blob](./Blob)|Sets the content type of the data stored in this blob based on the specified file extension. If the content type cannot be guessed from the specified extension, it will be set to null.<br />
[setDataFromString(String data)]("#setdatafromstring~string-data~")|[Blob](./Blob)|Sets the data to store in this blob from the provided string in UTF-8 encoding.<br />
[setDataFromString(String data, String charset)]("#setdatafromstring~string-data_-string-charset~")|[Blob](./Blob)|Sets the data to store in this blob from the provided string in the given encoding.<br />
[setName(name)]("#setname~name~")|[Blob](./Blob)|Sets the name of the blob.<br />

## <a name="copyblob"></a>copyBlob
Returns a copy of this blob.


## <a name="getas~string-contenttype~"></a>getAs(String contentType)
Returns the contents of this blob converted to the specified MIME type. For blobs containing images, any image format such as 'image/bmp', 'image/gif', 'image/jpeg', or 'image/png' can be specified for the input parameter.


## <a name="getbytes"></a>getBytes
Returns the contents of this blob as a byte array.


## <a name="getcontenttype"></a>getContentType
Returns the content type of the data stored in this blob; null if the type is not known


## <a name="getdataasstring"></a>getDataAsString
Returns the content of this blob as a String in UTF-8 encoding.


## <a name="getdataasstring~string-charset~"></a>getDataAsString(String charset)
Returns the content of this blob as a String in the specified encoding.


## <a name="getname"></a>getName
Returns the name of this blog.


## <a name="setbytes~byte-data~"></a>setBytes(Byte[] data)
Sets the data to store in this blob.


## <a name="setcontenttype~string-contenttype~"></a>setContentType(String contentType)
Sets the content type of the data stored in this blob.


## <a name="setcontenttypefromextension~string-fileextension~"></a>setContentTypeFromExtension(String fileExtension)
Sets the content type of the data stored in this blob based on the specified file extension. If the content type cannot be guessed from the specified extension, it will be set to null.


## <a name="setdatafromstring~string-data~"></a>setDataFromString(String data)
Sets the data to store in this blob from the provided string in UTF-8 encoding.


## <a name="setdatafromstring~string-data_-string-charset~"></a>setDataFromString(String data, String charset)
Sets the data to store in this blob from the provided string in the given encoding.


## <a name="setname~name~"></a>setName(name)
Sets the name of the blob.


