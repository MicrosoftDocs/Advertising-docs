|Element|Description|Data Type|
|-----------|---------------|-------------|
|AuthenticationToken|The OAuth access token that represents a Microsoft Account user who has permissions to Bing Ads accounts.|**string**|
|CustomerAccountId|The identifier of the account that owns the entities in the request. This header element must have the same value as the AccountId body element when both are required.|**string**|
|CustomerId|The identifier of the customer that contains and owns the account. If you manage an account of another customer, you should use that customer ID instead of your own customer ID.|**string**|
|DeveloperToken|The developer token used to access the Bing Ads API.|**string**|
|Password|The Bing Ads managed user's sign-in password.|**string**|
|UserName|The Bing Ads managed user's sign-in name. You must not set this element to a Microsoft account or email address.|**string**|

> [!IMPORTANT]
> The UserName and Password header elements are deprecated. In future versions of the API, Bing Ads will transition exclusively to Microsoft Account (email address) authentication. For more information, see [Authentication with OAuth](~/guides/authentication-oauth.md). UserName and Password are still required for Bing Ads managed credentials, but they are not applicable for Microsoft account authentication. To authenticate a Microsoft account, use the AuthenticationToken] header instead of UserName and Password.  

> [!NOTE]
> The CustomerAccountId and CustomerId are required for most service operations, and as a best practice you should always specify them in the request.  
