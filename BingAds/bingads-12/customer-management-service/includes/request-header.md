|Element|Description|Data Type|
|-----------|---------------|-------------|
|AuthenticationToken|The OAuth access token that represents a Microsoft Account user who has permissions to Bing Ads accounts.|**string**|
|DeveloperToken|The developer token used to access the Bing Ads API.|**string**|
|Password|The Bing Ads managed user's sign-in password.|**string**|
|UserName|The Bing Ads managed user's sign-in name. You must not set this element to a Microsoft account or email address.|**string**|

> [!IMPORTANT]
> The UserName and Password header elements are deprecated. In future versions of the API, Bing Ads will transition exclusively to Microsoft Account (email address) authentication. For more information, see [Authentication with OAuth](~/guides/authentication-oauth.md). UserName and Password are still required for Bing Ads managed credentials, but they are not applicable for Microsoft account authentication. To authenticate a Microsoft account, use the AuthenticationToken] header instead of UserName and Password.  
