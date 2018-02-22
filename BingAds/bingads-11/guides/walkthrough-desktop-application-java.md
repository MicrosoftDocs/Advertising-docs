---
title: "Walkthrough: Bing Ads Desktop Application in Java"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Create a desktop application using the Bing Ads Java SDK.
dev_langs:
  - java
---
# Walkthrough: Bing Ads Desktop Application in Java
The example desktop application sends authentication requests to the Microsoft account and Bing Ads services for the user credentials that you provide, and then gets the accounts that the authenticated user can access. You must first [register an application](../guides/authentication-oauth.md#registerapplication) and take note of the client ID. You'll also need your production [developer token](~/guides/get-started.md#get-developer-token). You can create the example step by step as described below, or start with the [provided examples](~/guides/code-examples.md).

> [!NOTE]
> This example demonstrates OAuth authentication in production. For information on configuring sandbox, please see [Configuring Sandbox](#sandbox) below.

## <a name="code"></a>Code Walkthrough

1.  Open the Eclipse development environment.

2.  Create a new project through **File** -&gt; **New** -&gt; **Project** -&gt; **Maven** -&gt; **Maven Project**, and click **Next**.

3.  In the **New Maven Project** dialog, check the option to **Create a simple project (skip archetype selection)** and click **Next**.

4.  In the **New Maven Project** dialog, specify your project's artifact parameters and then click **Finish**. For example, you can set the **Group Id** to com.microsoft.bingads.examples and **Artifact Id** to BingAdsDesktopApp.

5.  In **Project Explorer**, right-click the pom.xml file and select **Open With** -&gt; **Text Editor**. Add the *com.microsoft.bingads* dependency as shown in the following example and save pom.xml.

    > [!NOTE]
    > For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).

    ```xml
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <groupId>com.microsoft.bingads.examples</groupId>
      <artifactId>BingAdsDesktopApp</artifactId>
      <version>0.0.1-SNAPSHOT</version>
      <dependencies>
        <dependency>
          <groupId>com.microsoft.bingads</groupId>
          <artifactId>microsoft.bingads</artifactId>
          <version>11.5.1</version>
        </dependency>
      </dependencies>
    </project>
    ```

6.  In **Project Explorer**, right-click the BingAdsDesktopApp project (or the name of your project if you chose a different artifact identifier in the previous step) and select **New** -&gt; **Class**. Choose a package name, for example *com.microsoft.bingads.examples*. Name the class *OAuthDesktopApplication* and then click **Finish**.

7.  Open the OAuthDesktopApplication.java file and replace its contents with the following code block. You must edit the sample below with the ClientId that was provisioned when you [registered your application](../guides/authentication-oauth.md#registerapplication). You'll also need to edit the example with your production [developer token](~/guides/get-started.md#get-developer-token).

    > [!NOTE]
    > If you observe any errors related to *javafx* import statements, try removing the *JRE System Library* and adding it back again. In **Project Explorer**, right-click the BingAdsDesktopApp and select **Build Path** -&gt; **Configure Build Path**. In the **Libraries** tab, select JRE System Library and click **Remove**. Remain in the **Libraries** tab and click **Add Library**, select JRE System Library, click **Next**, and then click **Finish**.

    ```java
    package com.microsoft.bingads.examples;

    import java.net.URL;
    import java.rmi.RemoteException;

    import javafx.application.Application;
    import javafx.event.EventHandler;
    import javafx.scene.Scene;
    import javafx.scene.web.WebEngine;
    import javafx.scene.web.WebEvent;
    import javafx.scene.web.WebView;
    import javafx.stage.Stage;

    import com.microsoft.bingads.*;
    import com.microsoft.bingads.v11.customermanagement.*;

    public class OAuthDesktopApplication extends Application {

        private boolean alreadyHaveRedirect = false;

        static AuthorizationData authorizationData;
        static ServiceClient<ICustomerManagementService> CustomerService; 

        //private static java.lang.String DeveloperToken = "<DeveloperTokenGoesHere>";
        //private static java.lang.String ClientId = "<ClientIdGoesHere>";

        @Override
        public void start(Stage primaryStage) {

        	// Create an instance of OAuthDesktopMobileAuthCodeGrant that will be used to manage Microsoft Account user authorization. 
        	// Replace ClientId with the value configured when you registered your application. 

            final OAuthDesktopMobileAuthCodeGrant oAuthDesktopMobileAuthCodeGrant = new OAuthDesktopMobileAuthCodeGrant(ClientId);

            oAuthDesktopMobileAuthCodeGrant.setNewTokensListener(new NewOAuthTokensReceivedListener() {
                @Override
                public void onNewOAuthTokensReceived(OAuthTokens newTokens) {
                       java.lang.String newAccessToken = newTokens.getAccessToken();
                       java.lang.String newRefreshToken = newTokens.getRefreshToken();
                       java.lang.String refreshTime = new java.text.SimpleDateFormat(
                    		   "MM/dd/yyyy HH:mm:ss").format(new java.util.Date());

                       System.out.printf("Token refresh time: %s\n", refreshTime);
                       System.out.printf("New access token: %s\n", newAccessToken);
                       System.out.printf("You should securely store this new refresh token: %s\n", newRefreshToken);

                }
            });

            // WebView is a Node that manages a WebEngine and displays its content. 
            // For more information, see javafx.scene.web at https://docs.oracle.com/javafx/2/api/javafx/scene/web/WebView.html

            WebView webView = new WebView();       

            webView.getEngine().setOnStatusChanged(new EventHandler<WebEvent<String>>() {

                // You may need to override the handle method depending on your project and JRE settings
                // @Override 
                public void handle(WebEvent<String> event) {
                    if (event.getSource() instanceof WebEngine) {
                        try {
                            WebEngine webEngine = (WebEngine) event.getSource();
                            String webEngineLocation = webEngine.getLocation();
                            URL url = new URL(webEngineLocation); 

                            System.out.println(url);

                            if (url.getPath().equals("/oauth20_desktop.srf")) {
                                if (alreadyHaveRedirect) {
                                    return;
                                }

                                alreadyHaveRedirect = true;

                                // To get the initial access and refresh tokens you must call requestAccessAndRefreshTokens with the authorization redirection URL. 

                                OAuthTokens tokens = oAuthDesktopMobileAuthCodeGrant.requestAccessAndRefreshTokens(url);

                                System.out.println("Access token: " + tokens.getAccessToken());
                                System.out.println("Refresh token: " + tokens.getRefreshToken());

                                authorizationData = new AuthorizationData();
                                authorizationData.setDeveloperToken(DeveloperToken);
                                authorizationData.setAuthentication(oAuthDesktopMobileAuthCodeGrant);

                                CustomerService = new ServiceClient<ICustomerManagementService>(
                                        authorizationData, 
                                        ICustomerManagementService.class);

                                User user = getUser(null);

                                // Search for the accounts that the user can access.

                                ArrayOfAccount accounts = searchAccountsByUserId(user.getId());

                                System.out.println("The user can access the following Bing Ads accounts: \n");
                                printAccounts(accounts);

                            }

                        // Customer Management service operations can throw AdApiFaultDetail.
                        } catch (AdApiFaultDetail_Exception ex) {
                            System.out.println("The operation failed with the following faults:\n");

                            for (AdApiError error : ex.getFaultInfo().getErrors().getAdApiErrors())
                            {
                	            System.out.printf("AdApiError\n");
                	            System.out.printf("Code: %d\nError Code: %s\nMessage: %s\n\n", error.getCode(), error.getErrorCode(), error.getMessage());
                            }

                        // Customer Management service operations can throw ApiFault.
                        } catch (ApiFault_Exception ex) {
                            System.out.println("The operation failed with the following faults:\n");

                            for (OperationError error : ex.getFaultInfo().getOperationErrors().getOperationErrors())
                            {
                	            System.out.printf("OperationError\n");
                	            System.out.printf("Code: %d\nMessage: %s\n\n", error.getCode(), error.getMessage());
                            }
                        } catch (RemoteException ex) {
                            System.out.println("Service communication error encountered: ");
                            System.out.println(ex.getMessage());
                            ex.printStackTrace();
                        } catch (Exception ex) {
                            // Ignore fault exceptions that we already caught.

                            if ( ex.getCause() instanceof AdApiFaultDetail_Exception ||
                                 ex.getCause() instanceof ApiFault_Exception )
                            {
                                ;
                            }
                            else
                            {
                                System.out.println("Error encountered: ");
                                System.out.println(ex.getMessage());
                                ex.printStackTrace();
                            }
                        }
                    }
                }
            });

            // Request user consent by connecting to the Microsoft Account authorization endpoint through a web browser. 

            URL authorizationEndpoint = oAuthDesktopMobileAuthCodeGrant.getAuthorizationEndpoint();

            webView.getEngine().load(authorizationEndpoint.toString());

            // The user will be prompted through the Microsoft Account authorization web browser control to grant permissions for your application
            // to manage their Bing Ads accounts. The authorization service calls back to your application with the redirection URI, which 
            // includes an authorization code if the user authorized your application to manage their Bing Ads accounts. 
            // For example the callback URI includes an access token as follows if the user granted permissions for your application to manage 
            // their Bing Ads accounts: https://login.live.com/oauth20_desktop.srf?code=Access-Code-Provided-Here&lc=1033. 

            Scene scene = new Scene(webView, 800, 600);

            primaryStage.setTitle("Bing Ads Desktop Application Example");
            primaryStage.setScene(scene);
            primaryStage.show();
        }

        // Gets a User object by the specified Bing Ads user identifier.

        static User getUser(java.lang.Long userId) throws RemoteException, Exception
        {
            GetUserRequest request = new GetUserRequest();

            request.setUserId(userId);

            return CustomerService.getService().getUser(request).getUser();
        }

        // Searches by UserId for accounts that the user can manage.

        static ArrayOfAccount searchAccountsByUserId(java.lang.Long userId) throws AdApiFaultDetail_Exception, ApiFault_Exception{       

            ArrayOfPredicate predicates = new ArrayOfPredicate();
            Predicate predicate = new Predicate();
            predicate.setField("UserId");
            predicate.setOperator(PredicateOperator.EQUALS);
            predicate.setValue("" + userId);
            predicates.getPredicates().add(predicate);

            Paging paging = new Paging();
            paging.setIndex(0);
            paging.setSize(10);

            final SearchAccountsRequest searchAccountsRequest = new SearchAccountsRequest();
            searchAccountsRequest.setPredicates(predicates);
            searchAccountsRequest.setPageInfo(paging);

            return CustomerService.getService().searchAccounts(searchAccountsRequest).getAccounts();
        }

        // Outputs the account and parent customer identifiers for the specified accounts.

        static void printAccounts(ArrayOfAccount accounts) throws RemoteException, Exception
        {
            for (Account account : accounts.getAccounts())
            {
            	System.out.printf("AccountId: %d\n", account.getId());
            	System.out.printf("CustomerId: %d\n\n", account.getParentCustomerId());
            }
        }

        // Launch the application

        public static void main(String[] args) {
            launch(args);
        }
    }
    ```

8.  Edit the *ClientId* and *DeveloperToken* values to your own credentials. If you are using sandbox, first follow the steps below in [Configuring Sandbox](#sandbox).

9. Right-click OAuthDesktopApplication.java, and click **Run As** -&gt; **Java Application**.

## <a name="sandbox"></a>Configuring Sandbox
To use the [Sandbox](../guides/sandbox.md) environment, create a new text file named *bingads.properties* within your project source root directory e.g. **ProjectName\src\bingads.properties** and add the following text. The following are the complete contents of the *bingads.properties* file. If the sandbox environment setting is malformed or missing, the default environment is production.

```no-highlight
environment=Sandbox
```

Sandbox does not support OAuth, so you must use *PasswordAuthentication*. You can remove all code above that refers to oAuthDesktopMobileAuthCodeGrant, and simply add these lines before you create the new ServiceClient for ICustomerManagementService.

```java
authorizationData = new AuthorizationData();
authorizationData.setDeveloperToken("DeveloperTokenGoesHere");
PasswordAuthentication passwordAuthentication = 
    new PasswordAuthentication("UserNameGoesHere", "PasswordGoesHere");
authorizationData.setAuthentication(passwordAuthentication);

// This snippet is already provided in the sample above.
CustomerService = new ServiceClient<ICustomerManagementService>(
    authorizationData, 
    ICustomerManagementService.class);
```

## See Also
[Sandbox](../guides/sandbox.md)  
[Bing Ads Code Examples](../guides/code-examples.md)  
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

