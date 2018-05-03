|Element|Description|Data Type|
|-----------|---------------|-------------|
|AuthenticationToken|The OAuth access token that represents a Microsoft Account user who has permissions to Bing Ads accounts.|**string**|
|CustomerAccountId|The identifier of the account that owns the entities in the request. This header element must have the same value as the AccountId body element when both are required.|**string**|
|CustomerId|The identifier of the customer that contains and owns the account. If you manage an account of another customer, you should use that customer ID instead of your own customer ID.|**string**|
|DeveloperToken|The developer token used to access the Bing Ads API.|**string**|
|Password|The Bing Ads managed user's sign-in password.|**string**|
|UserName|The Bing Ads managed user's sign-in name. You must not set this element to a Microsoft account or email address.|**string**|

> [!IMPORTANT]
> The UserName and Password header elements are deprecated in favor of the AuthenticationToken header i.e., [Authentication with OAuth](../../guides/authentication-oauth.md). As of August 1st, 2018, all Bing Ads API Version 11 service calls with managed UserName and Password credentials will return an error. Bing Ads API Version 12 already does not accept the managed user credentials. In a future version of the API, the UserName and Password header elements will be removed from the service definitions.   

> [!NOTE]
> The CustomerAccountId and CustomerId are required for most service operations, and as a best practice you should always specify them in the request.  
