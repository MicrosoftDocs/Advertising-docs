|Element|Description|Data Type|
|-----------|---------------|-------------|
|AuthenticationToken|The OAuth access token that represents the credentials of user who has permissions to Microsoft Advertising accounts.|**string**|
|CustomerAccountId|The identifier of the ad account that owns the entities in the request. This header element must have the same value as the AccountId body element when both are required. This element is required for most service operations, and as a best practice you should always set it.|**string**|
|CustomerId|The identifier of the manager account (customer) the user is accessing or operating from. A user can have access to multiple manager accounts. This element is required for most service operations, and as a best practice you should always set it.|**string**|
|DeveloperToken|The developer token used to access the Bing Ads API.|**string**|
|Password|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials.|**string**|
|UserName|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials.|**string**|
