---
title: "Walkthrough: Bing Ads Web Application in PHP"
ms.service: "bing-ads"
ms.topic: "article"
---
# Walkthrough: Bing Ads Web Application in PHP
This example web application demonstrates OAuth authentication in production. The application will prompt a Microsoft account user for permission to manage their Bing Ads accounts. You must first [register an application](../guides/authentication-oauth.md#registerapplication) and take note of the client ID, client secret, and redirection URI. You'll also need your production [developer token](~/guides/get-started.md#get-developer-token). You can create the example step by step as described below, or start with the [provided examples](~/guides/code-examples.md).

## <a name="webapp"></a>Web Application Authentication Example Walk-Through

1.  Create a new file named *Index.php*, and add the code as shown in the following example.

    ```php
    <?php
    namespace Microsoft\BingAds\Samples;
        
    require_once "./vendor/autoload.php";
    
    include "WebAuthHelper.php";
    
    // Specify the Microsoft\BingAds\Samples classes that will be used.
    use Microsoft\BingAds\Samples\WebAuthHelper;
    
    ?>
    
    <!-- 
    Display a small form with a login button. In your application, you would implement code to allow
    the user to either log into your service or create a new account. 
    -->
    <h2>Bing Ads OAuth Demo</h2>
    
    <p>This application would like to manage your Bing Ads data. Click below to login and authorize this application.</p>
    
    <p>When you click OK below, you'll be redirected to the following URI:</p>
    <p><?php echo WebAuthHelper::RedirectUri ?></p>
    
    <!-- 
    When the user presses this button, they will be redirected to fully formed URL to request an authorization token. 
    From here, the user will be redirected to the redirectUriPath where the authorization token can be extracted. 
    -->
    <input type="button" onClick="return window.location='<?php echo WebAuthHelper::RedirectUri;?>';" value="OK" />
    ```

2.  Create a new file named *OAuth2Callback.php*, and add the code as shown in the following example.  

    ```php
    <?php
    namespace Microsoft\BingAds\Samples;
        
    require_once "./vendor/autoload.php";
    
    include "WebAuthHelper.php";
    
    // Specify the Microsoft\BingAds\Auth classes that will be used.
    use Microsoft\BingAds\Auth\AuthorizationData;
    use Microsoft\BingAds\Auth\OAuthTokenRequestException;
    use Microsoft\BingAds\Auth\OAuthWebAuthCodeGrant;
    
    // Specify the Microsoft\BingAds\Samples classes that will be used.
    use Microsoft\BingAds\Samples\WebAuthHelper;
    
    try 
    {
        session_start();
    
        if(!isset($_SESSION['AuthorizationData']) || !isset($_SESSION['AuthorizationData']->Authentication))
        {
            // Prepare the OAuth object for use with the authorization code grant flow. 
            // It is recommended that you specify a non guessable 'state' request parameter to help prevent
            // cross site request forgery (CSRF). 
            $authentication = (new OAuthWebAuthCodeGrant())
                ->withClientId(WebAuthHelper::ClientId)
                ->withClientSecret(WebAuthHelper::ClientSecret)
                ->withRedirectUri('https://' . $_SERVER['HTTP_HOST'] . WebAuthHelper::RedirectUri)
                ->withState(rand(0,999999999)); 
    
            // Assign this authentication instance to the global authorization_data. 
    
            $_SESSION['AuthorizationData'] = (new AuthorizationData())
                ->withAuthentication($authentication)
                ->withDeveloperToken(WebAuthHelper::DeveloperToken);
    
            $_SESSION['state'] = $_SESSION['AuthorizationData']->Authentication->State;
            
            // The user needs to provide consent for the application to access their Bing Ads accounts.
            header('Location: '. $_SESSION['AuthorizationData']->Authentication->GetAuthorizationEndpoint());
    
        }
        
        // If the current HTTP request is a callback from the Microsoft Account authorization server,
        // use the current request url containing authorization code to request new access and refresh tokens
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
    }
    catch(OAuthTokenRequestException $e)
    {
        // The user could not be authenticated or the grant is expired. 
        // The user must first sign in and if needed grant the client application access to the requested scope.
        print $e;
    }
    catch(Exception $e)
    {
        print $e;
    }
    
    ?>
    ```
3.  Create a new file named *CallBingAdsServices.php*, and add the code as shown in the following example.

    ```php
    <?php
    namespace Microsoft\BingAds\Samples;
        
    require_once "./vendor/autoload.php";
    
    include "WebAuthHelper.php";
    
    // Specify the Microsoft\BingAds\Auth classes that will be used.
    use Microsoft\BingAds\Auth\AuthorizationData;
    use Microsoft\BingAds\Auth\OAuthWebAuthCodeGrant;
    
    // Specify the Microsoft\BingAds\Samples classes that will be used.
    use Microsoft\BingAds\Samples\WebAuthHelper;
    
    session_start();
    
    // If there is no user authenticated, go back to the site index.
    
    if(!isset($_SESSION['AuthorizationData']) || 
       !isset($_SESSION['AuthorizationData']->Authentication) || 
       !isset($_SESSION['AuthorizationData']->Authentication->OAuthTokens)
    )
    {
        header('Location: '. 'https://' . $_SERVER['HTTP_HOST']);
    }
    
    printf("Access token: %s<br/><br/>", $_SESSION['AuthorizationData']->Authentication->OAuthTokens->AccessToken);
    printf("Refresh token: %s<br/><br/>", $_SESSION['AuthorizationData']->Authentication->OAuthTokens->RefreshToken);
    
    // If a refresh token is already present, use it to request new access and refresh tokens.
    // You should store refresh tokens securely i.e. not in session as shown in this demo.
    
    $refreshToken = $_SESSION['AuthorizationData']->Authentication->OAuthTokens->RefreshToken;
    if($refreshToken != null)
    {
        $_SESSION['AuthorizationData']->Authentication->RequestOAuthTokensByRefreshToken($refreshToken);
    }
    
    printf("Access token: %s<br/><br/>", $_SESSION['AuthorizationData']->Authentication->OAuthTokens->AccessToken);
    printf("Refresh token: %s<br/><br/>", $_SESSION['AuthorizationData']->Authentication->OAuthTokens->RefreshToken);
    
    session_unset();
    
    ?>
    ```

4.  Create a new file named *WebAuthHelper.php*, and add the code as shown in the following example. You must edit the sample below with the ClientId, ClientSecret, and RedirectionUri that were provisioned when you [registered your application](../guides/authentication-oauth.md#registerapplication). You'll also need to edit the example with your production [developer token](~/guides/get-started.md#get-developer-token). 

    ```php
    <?php

    namespace Microsoft\BingAds\Samples;
            
    /** 
     * Defines global settings that you can use for testing your application.
     * Your production implementation may vary, and you should always store sensitive information securely.
     */
    final class WebAuthHelper {
        const ClientId = 'ClientIdGoesHere';
        const ClientSecret = 'ClientSecretGoesHere'; 
        const RedirectUri = "/oauth2callback.php"; 
        const DeveloperToken = 'DeveloperTokenGoesHere';
    }
    
    ?>
    ```

5. The application is ready to be deployed to a server. For example you can publish a [Web App](http://azure.microsoft.com/services/app-service/web/) using the [Azure App Service](http://azure.microsoft.com/services/app-service/). 

## See Also
[Bing Ads Code Examples](../guides/code-examples.md)  
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

