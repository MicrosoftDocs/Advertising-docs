---
title: "Authentication With the SDKs"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Learn about authentication and basic service calls with the Bing Ads SDKs.
dev_langs:
  - csharp
  - java
  - php
  - python
---
# Authentication With the SDKs
This article covers authentication and basic service calls with the Bing Ads SDKs. 

## <a name="sandbox"></a>Configuring Sandbox
The SDK uses the production environment by default. With the .NET and Java SDKs you can change it to sandbox with a global configuration. Whereas the global configuration is not available with PHP and Python SDKs you could create a global configuration or other custom solution.

```csharp
// Set the BingAdsEnvironment key to Sandbox within the <appSettings> node of your project root's Web.config file (for web apps) or App.config file (for native apps).
<add key="BingAdsEnvironment" value ="Sandbox"/>
```
```java
// Create a new text file named bingads.properties within your project source root directory e.g. **ProjectName\src\bingads.properties** and add only the following text. 
// If the sandbox environment setting is malformed or missing, the default environment is production.
environment=Sandbox
```

You can also set the API environment parameter of individual [Bulk Service Manager](sdk-bulk-service-manager.md), [Service Client](#serviceclient), and [Reporting Service Manager](sdk-reporting-service-manager.md) instances. Setting the *apiEnvironment* overrides the global setting only for the specified service client instance or instances. Unless otherwise intended, you should be careful not to inadvertently configure a mixed set of environments.    

```csharp
BulkServiceManager BulkService = new BulkServiceManager(authorizationData, ApiEnvironment.Sandbox);

ServiceClient<ICustomerManagementService> Service = new ServiceClient<ICustomerManagementService>(authorizationData, ApiEnvironment.Sandbox);
    
ReportingServiceManager ReportingService = new ReportingServiceManager(authorizationData, ApiEnvironment.Sandbox);
```

```java
BulkServiceManager BulkService = new BulkServiceManager(authorizationData, ApiEnvironment.SANDBOX);

ServiceClient<ICustomerManagementService> CustomerService = 
    new ServiceClient<ICustomerManagementService>(
        authorizationData,
        ApiEnvironment.SANDBOX,
        ICustomerManagementService.class
    );
    
ReportingServiceManager ReportingService = new ReportingServiceManager(authorizationData, ApiEnvironment.SANDBOX);
```
```php
$customerProxy = new ServiceClient(ServiceClientType::CustomerManagementVersion12, $authorizationData, ApiEnvironment::Sandbox);
```
```python
# Set the environment property of each ServiceClient instance to 'sandbox' (not case sensitive). 
# If the sandbox environment setting is malformed or missing, the default environment is production.
# Once the environment is initialized you may not reset it for the service client instance. 
# To switch between sandbox and production, you must create a new service client instance.

bulk_service_manager = BulkServiceManager(
    authorization_data=authorization_data, 
    version = 12,
    poll_interval_in_milliseconds = 5000, 
    environment = 'sandbox',
)

customer_service = ServiceClient(
    'CustomerManagementService', 
    version = 12,
    authorization_data=authorization_data, 
    environment = 'sandbox',
)

reporting_service_manager = ReportingServiceManager(
    authorization_data=authorization_data, 
    version = 12,
    poll_interval_in_milliseconds = 5000, 
    environment = 'sandbox',
)
```

## <a name="oauth"></a>Using OAuth
Bing Ads SDKs support the standard OAuth 2.0 flow as defined in detail in the [The OAuth 2.0 Authorization Framework](http://tools.ietf.org/html/rfc6749).The OAuth classes in the SDK abstract the low level user authorization details such as formatting the authorization and redirect URIs, setting the request headers, and parsing the redirect traffic and response stream. To use OAuth with the Bing Ads .NET SDK, the *Authentication* property of your [AuthorizationData](#authorization-data) object must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant* or *OAuthDesktopMobileImplicitGrant*. 

For repeat or long term authentication, you should follow the authorization code grant flow for obtaining an access token. The steps below follow the authorization code grant flow. For more information both about authorization code and implicit grant flows, see the [Authentication with OAuth](authentication-oauth.md) guide.

1.  Create an instance of *OAuthWebAuthCodeGrant*, that will be used to manage Microsoft Account user authorization. Replace client ID, client secret, and redirection URI with the values configured in [Registering Your Application](authentication-oauth.md#registerapplication).

    ```csharp
    var oAuthWebAuthCodeGrant = new OAuthWebAuthCodeGrant(ClientId, ClientSecret, new Uri(RedirectionUri), ApiEnvironment);
    
    // It is recommended that you specify a non guessable 'state' request parameter to help prevent
    // cross site request forgery (CSRF). 
    oAuthWebAuthCodeGrant.State = "ClientStateGoesHere";
    ```
    ```java
    OAuthWebAuthCodeGrant oAuthWebAuthCodeGrant = new OAuthWebAuthCodeGrant(ClientId, ClientSecret, new URL(RedirectionUri), ApiEnvironment);
    
    // It is recommended that you specify a non guessable 'state' request parameter to help prevent
    // cross site request forgery (CSRF). 
    oAuthWebAuthCodeGrant.setState("ClientStateGoesHere");
    ```
    ```php
    // Prepare the OAuth object for use with the authorization code grant flow. 
    // It is recommended that you specify a non guessable 'state' request parameter to help prevent
    // cross site request forgery (CSRF). 
    $authentication = (new OAuthWebAuthCodeGrant())
        ->withClientId(ClientId)
        ->withClientSecret(ClientSecret)
        ->withEnvironment(ApiEnvironment)
        ->withRedirectUri('https://' . $_SERVER['HTTP_HOST'] . RedirectUri)
        ->withState(rand(0,999999999)); 
    
    // Assign this authentication instance to the global authorization_data. 

    $_SESSION['AuthorizationData'] = (new AuthorizationData())
        ->withAuthentication($authentication)
        ->withDeveloperToken(AuthHelper::DeveloperToken);
    
    $_SESSION['state'] = $_SESSION['AuthorizationData']->Authentication->State;
    ```
    ```python
    oauth_web_auth_code_grant = OAuthWebAuthCodeGrant(
        client_id=CLIENT_ID,
        client_secret=CLIENT_SECRET,
        env=ENVIRONMENT,
        redirection_uri=REDIRECTION_URI
    )
    
    # It is recommended that you specify a non guessable 'state' request parameter to help prevent
    # cross site request forgery (CSRF). 
    oauth_web_auth_code_grant.state="ClientStateGoesHere"
    ```

2.  Request user consent by connecting to the Microsoft Account authorization endpoint through a web browser control. Call the *GetAuthorizationEndpoint* method of the *OAuthWebAuthCodeGrant* instance that you created in the earlier step.

    ```csharp
    return Redirect(oAuthWebAuthCodeGrant.GetAuthorizationEndpoint().ToString());
    ```
    ```java
    URL authorizationEndpoint = oAuthWebAuthCodeGrant.getAuthorizationEndpoint();
    response.sendRedirect(authorizationEndpoint.toString());
    ```
    ```php
    // The user needs to provide consent for the application to access their Bing Ads accounts.
    header('Location: '. $_SESSION['AuthorizationData']->Authentication->GetAuthorizationEndpoint());
    ```
    ```python
    oauth_web_auth_code_grant.get_authorization_endpoint()
    ```
    
    The user will be prompted through the Microsoft Account authorization web browser control to grant permissions for your application to manage their Bing Ads accounts.
    
    The authorization service calls back to your application with the redirection URI, which includes an authorization code if the user authorized your application to manage their Bing Ads accounts. For example the callback Url includes an authorization code as follows if the user granted permissions for your application to manage their Bing Ads accounts: *https://contoso.com/redirect/?code=CODE&state=ClientStateGoesHere*. If the user granted your application permissions to manage their Bing Ads accounts, you should use the code right away in the next step. The short duration of the authorization code, approximately 5 minutes, is subject to change.
    
    If the user denied your application permissions to manage their Bing Ads accounts, the callback URI includes an error and error description field as follows: *REDIRECTURI?error=access_denied&error_description=ERROR_DESCRIPTION&state=ClientStateGoesHere*.

3.  Use the authorization code to request the access token and refresh token. Pass the full callback URI when using the *OAuthWebAuthCodeGrant* instance to request the access token and refresh token.

    ```csharp
    if (Request["code"] != null)
    {
        // If you set the client state in step #1 above, verify that the authorization
        // server returns the same value before proceeding.
        if (oAuthWebAuthCodeGrant.State != "ClientStateGoesHere")
            throw new HttpRequestException("The OAuth response state does not match the client request state.");
       
        await oAuthWebAuthCodeGrant.RequestAccessAndRefreshTokensAsync(Request.Url);
    }
    ```
    ```java
    if (request.getParameter("code") != null)
    {
        // If you set the client state in step #1 above, verify that the authorization
        // server returns the same value before proceeding.
        if (oAuthWebAuthCodeGrant.getState() != ClientState)
            throw new Exception("The OAuth response state does not match the client request state.");
                           
        oAuthWebAuthCodeGrant.requestAccessAndRefreshTokens(new URL(request.getRequestURL() + "?" + request.getQueryString()));
    }
    ```
    ```php
    if($_GET['code'] != null)
    {   
        // Verify whether the 'state' value is the same random value we created
        // when the authorization request was initiated.
        if ($_GET['state'] != $_SESSION['state'])
        {
            throw new Exception(sprintf(
                "The OAuth response state (%s) does not match the client request state (%s)", 
                $_GET['state'], 
                $_SESSION['state']));
        }   
        
        $_SESSION['AuthorizationData']->Authentication->RequestOAuthTokensByResponseUri($_SERVER['HTTP_HOST'] . $_SERVER['REQUEST_URI']);
                
        header('Location: '. '/CallBingAdsServices.php');
    }
    ```
    ```python
    if oauth_web_auth_code_grant.state != "ClientStateGoesHere":
       raise Exception("The OAuth response state does not match the client request state.")

    oauth_web_auth_code_grant.request_oauth_tokens_by_response_uri(RESPONSE_URI)
    oauth_tokens = oauth_web_auth_code_grant.oauth_tokens
    access_token = oauth_tokens.access_token
    ```

    If this step succeeded, your application has permissions to manage the user's Bing Ads accounts. To call Bing Ads services, you should initialize either [Service Client](#serviceclient), [Bulk Service Manager](sdk-bulk-service-manager.md), or [Reporting Service Manager](sdk-reporting-service-manager.md) with [AuthorizationData](#authorization-data) that contains your *OAuthWebAuthCodeGrant* instance.
    
    For more information, see [Using AuthorizationData](#authorization-data), [Using Service Client](#serviceclient), [Using BulkServiceManager](sdk-bulk-service-manager.md), and [Using ReportingServiceManager](sdk-reporting-service-manager.md).

4.  When calling Bing Ads services with [Service Client](#serviceclient), [Bulk Service Manager](sdk-bulk-service-manager.md), or [Reporting Service Manager](sdk-reporting-service-manager.md), it is important to save the most recent refresh token whenever new OAuth tokens are received.  

    ```csharp
    // If you already have a refresh token, use it to request new access and refresh tokens.

    if (GetRefreshToken(out refreshToken))
    {
        oAuthWebAuthCodeGrant.RequestAccessAndRefreshTokensAsync(refreshToken);
    }

    // When calling Bing Ads services with Service Client, Bulk Service Manager, or Reporting Service Manager, each instance will refresh your access token automatically if they detect the AuthenticationTokenExpired (109) error code. It is important to save the most recent refresh token whenever new OAuth tokens are received. You will want to subscribe to the NewOAuthTokensReceived event handler.

    oAuthWebAuthCodeGrant.NewOAuthTokensReceived += 
        (sender, args) => SaveRefreshToken(args.NewRefreshToken);
    ```
    ```java
    // If you already have a refresh token, use it to request new access and refresh tokens.

    if (refreshToken != null)
    {
        oAuthWebAuthCodeGrant.requestAccessAndRefreshTokens(refreshToken);
    }

    // When calling Bing Ads services with Service Client, Bulk Service Manager, or Reporting Service Manager, each instance will refresh your access token automatically if they detect the AuthenticationTokenExpired (109) error code. It is important to save the most recent refresh token whenever new OAuth tokens are received. You will want to implement event handling using the NewOAuthTokensReceivedListener.

    oAuthWebAuthCodeGrant.setNewTokensListener(new NewOAuthTokensReceivedListener() {
        @Override
        public void onNewOAuthTokensReceived(OAuthTokens newTokens) {
               saveRefreshToken(newTokens.getRefreshToken());
        }
    });
    ```
    ```php
    // If you already have a refresh token, use it to request new access and refresh tokens.
    $_SESSION['AuthorizationData']->Authentication->RequestOAuthTokensByRefreshToken($refreshToken);
    ```
    ```python
    oauth_web_auth_code_grant.token_refreshed_callback=save_refresh_token
    ```
        
    You can also get the *AccessToken*, *RefreshToken*, and *ExpiresIn* values from the *OAuthTokens* property of your *OAuthWebAuthCodeGrant* instance by calling *request_oauth_tokens_by_refresh_token*.
    
    ```python
    # When calling Bing Ads services with Service Client, Bulk Service Manager, or Reporting Service Manager, each instance will refresh your access token automatically if they detect the AuthenticationTokenExpired (109) error code. It is important to save the most recent refresh token whenever new OAuth tokens are received. You will want to register a callback function to automatically save the refresh token anytime it is refreshed. For example if you defined have a save_refresh_token() method that securely stores your refresh token, set the authentication token_refreshed_callback property of each OAuthWebAuthCodeGrant instance.

    oauth_web_auth_code_grant.token_refreshed_callback=save_refresh_token

    # If you already have a refresh token, use it to request new access and refresh tokens.

    if refresh_token is not None:
        oauth_web_auth_code_grant.request_oauth_tokens_by_refresh_token(refresh_token)
    ```
    
    > [!IMPORTANT]
    > A refresh token can last up to 90 days. Regardless, you should expect to start again from Step 1 and request user consent if, for example the Microsoft Account user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf.


## <a name="authorization-data"></a>Using AuthorizationData
The [AuthorizationData](#authorization-data) class contains properties that Bing Ads uses to authorize a user. The [Service Client](#serviceclient), [Bulk Service Manager](sdk-bulk-service-manager.md) and [Reporting Service Manager](sdk-reporting-service-manager.md) classes handle common request header fields for you, allowing you to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the [AuthorizationData](#authorization-data) object once for each service. 

The following code block shows how to create an instance of [AuthorizationData](#authorization-data) and set its *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties.

```csharp
var authorizationData = new AuthorizationData
{
    Authentication = <AuthenticationGoesHere>, 
    CustomerId = <CustomerIdGoesHere>,
    AccountId = <AccountIdGoesHere>,
    DeveloperToken = "<DeveloperTokenGoesHere>"
};
```
```java
static AuthorizationData authorizationData = new AuthorizationData();
authorizationData.setAuthentication(<AuthenticationGoesHere>);
authorizationData.setCustomerId("<CustomerIdGoesHere>");
authorizationData.setAccountId("<AccountIdGoesHere>");
authorizationData.setDeveloperToken("<DeveloperTokenGoesHere>");
```
```php
$authorizationData = (new AuthorizationData())
    ->withAuthentication($AuthenticationGoesHere)
    ->withCustomerId($CustomerIdGoesHere)
    ->withAccountId($AccountIdGoesHere)
    ->withDeveloperToken($DeveloperTokenGoesHere);
```
```python
authorization_data = AuthorizationData(
    authentication = <AuthenticationGoesHere>,
    customer_id = <CustomerIdGoesHere>,
    account_id = <AccountIdGoesHere>,
    developer_token = '<DeveloperTokenGoesHere>'
)
```

The *Authentication* property must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant*, or *OAuthDesktopMobileImplicitGrant*. 

Some services such as Customer Management do not accept *CustomerId* and *CustomerAccountId* headers, so they will be ignored if you specified them in the [AuthorizationData](#authorization-data) object.

## <a name="serviceclient"></a>Using Service Client
You can use an instance of the *ServiceClient* class to call any methods of one of the Bing Ads [web services](web-service-addresses.md). The *ServiceClient* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the [AuthorizationData](#authorization-data) object once for each service. 

> [!TIP]
> If you are using the Bulk or Reporting services, use the [Bulk Service Manager](sdk-bulk-service-manager.md) or [Reporting Service Manager](sdk-reporting-service-manager.md) instead of *ServiceClient*. For example the [Bulk Service Manager](sdk-bulk-service-manager.md) will submit your download request to the bulk service, poll the service until completed, and download the file to the local directory that you specified in the request. You'll save even more time because you don't have to write or parse the upload or results files. 

```csharp
// The primary method of the ServiceClient class is CallAsync. The method parameter is the delegate for the service operation that you want to call. The request parameter of this method must be a request message corresponding to the name of the service operation specified by the first request parameter. The request message must match the service operation that is specified as the delegate in the first request.

public async Task<TResponse> CallAsync<TRequest, TResponse>(
    Func<TService, TRequest, Task<TResponse>> method, TRequest request)

// In the following sample, the method delegate is (s, r) => s.GetUserAsync(r) which takes a GetUserRequest message as the request parameter (TRequest) and returns a GetUserResponse message (TResponse).

private async Task<User> GetUserAsync(long? userId)
{
    var request = new GetUserRequest
    {
        UserId = userId
    };

    return (await _customerService.CallAsync((s, r) => s.GetUserAsync(r), request)).User;
}
```
```java
// You can use the Customer Management service to get the current authenticated user.

ServiceClient<ICustomerManagementService> CustomerService = new ServiceClient<ICustomerManagementService>(
		authorizationData, 
		ICustomerManagementService.class);

java.lang.Long userId = null;
final GetUserRequest getUserRequest = new GetUserRequest();
getUserRequest.setUserId(userId);

User user = CustomerService.getService().getUser(getUserRequest).getUser();
```
```php
// You can use a single instance of the ServiceClient class to call any methods in the service, for example you can set the CustomerManagementVersion12 service client type as follows.

$customerProxy = new ServiceClient(ServiceClientType::CustomerManagementVersion12, $authorizationData, ApiEnvironment::Production);
)
```
```python
# You can use the Customer Management service to get the current authenticated user.

customer_service = ServiceClient(
    'CustomerManagementService', 
    version = 12,
    authorization_data=authorization_data, 
    environment = ENVIRONMENT,
)

user = customer_service.GetUser(UserId = None).User
```

> [!IMPORTANT]
> If you set the *AuthenticationToken*, *CustomerId*, *AccountId*, or *DeveloperToken* header elements in the request parameter e.g., *GetUserRequest*, they will be ignored. [Service Client](#serviceclient) always uses the [AuthorizationData](#authorization-data) provided with its initialization.


## See Also
[Sandbox](sandbox.md)  
[Bing Ads Code Examples](code-examples.md)    
[Bing Ads Web Service Addresses](web-service-addresses.md)  
