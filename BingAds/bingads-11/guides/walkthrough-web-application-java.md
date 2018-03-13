---
title: "Walkthrough: Bing Ads Web Application in Java"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Create a web application using the Bing Ads Java SDK.
dev_langs:
  - java
---
# Walkthrough: Bing Ads Web Application in Java
The example web application sends authentication requests to the Microsoft account and Bing Ads services for the user credentials that you provide, and then adds a campaign using the Bulk service. You must first [register an application](authentication-oauth.md#registerapplication) and take note of the client ID, client secret, and redirection URI. You'll also need your production [developer token](get-started.md#get-developer-token).  You can create the example step by step as described below, or start with the [provided examples](code-examples.md).

> [!NOTE]
> This example demonstrates OAuth authentication in production. For information on configuring sandbox, please see [Configuring Sandbox](#sandbox) below.

## <a name="webapp"></a>Web Application Authentication Example Walk-Through

1.  Open the Eclipse development environment.

2.  Create a new project through **File** -&gt; **New** -&gt; **Project** -&gt; **Maven** -&gt; **Maven Project**, and click **Next**.

3.  In the **New Maven Project** dialog, make sure the option to **Create a simple project (skip archetype selection)** is not selected and click **Next**. You will select a Maven archetype in the next step.

4.  In the **New Maven Project** dialog, select the Maven web app archetype and click **Next**. The **Group Id** is org.apache.maven.archetypes and the **Artifact Id** is maven-archetype-webapp.

5.  In the **New Maven Project** dialog, specify your project's artifact parameters and then click **Finish**. For example, you can set the **Group Id** to com.microsoft.bingads.examples and **Artifact Id** to BingAdsWebApp.

6.  Add the required javax servlet JARs to your project library if they are not already in your Java build path. In **Project Explorer**, right-click the BingAdsWebApp project and click **Properties**. In the **Properties** dialog go to the **Java Build Path** -&gt; **Libraries** tab, click **Add External JARs**, and then navigate to *{EclipseInstallationPath}/plugins/* and select for example both *javax.servlet.jsp_2.2.0.v201112011158* and *javax.servlet_3.0.0.v201112011016*.

7.  Include the servlet JARs to the project's order and exported entries. In the **Java Build Path** -&gt; **Order and Export** tab, click **Select All** (at least select the servlet JARs), and then click **Finish**.

8.  Include the servlet JARs in the project's *Web Deployment Assembly*. In **Project Explorer**, right-click the BingAdsWebApp project and select **Properties**. In the **Properties** dialog go to **Deployment Assembly** -&gt; **Add**, select *Java Build Path Entries*, and click **Next**. Select all of the JARs that you added in the previous steps, click **Finish** in the **New Assembly Directive** dialog, and then click **Apply** in the **Properties** dialog.

9. In **Project Explorer**, right-click the pom.xml file and select **Open With** -&gt; **Text Editor**. Add the *com.microsoft.bingads* dependency as shown in the following example and save pom.xml.

    > [!NOTE]
    > For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).

    ```xml
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <groupId>com.microsoft.bingads.examples</groupId>
      <artifactId>BingAdsWebApp</artifactId>
      <packaging>war</packaging>
      <version>0.0.1-SNAPSHOT</version>
      <name>BingAdsWebApp Maven Webapp</name>
      <url>http://maven.apache.org</url>
      <dependencies>
        <dependency>
          <groupId>junit</groupId>
          <artifactId>junit</artifactId>
          <version>3.8.1</version>
          <scope>test</scope>
        </dependency>
        <dependency>
          <groupId>com.microsoft.bingads</groupId>
          <artifactId>microsoft.bingads</artifactId>
          <version>11.5.9</version>
        </dependency>
      </dependencies>
      <build>
        <finalName>BingAdsWebApp</finalName>
      </build>
    </project>
    ```

10. In **Project Explorer**, right-click the Web Content folder of your BingAdsWebApp project and select **New** -&gt; **JSP File**. Name the file *index.jsp* and then click **Finish**.

11. Open the Index.jsp file and replace its contents with the following code block. You must edit the sample below with the ClientId, ClientSecret, and RedirectionUri that were provisioned when you [registered your application](authentication-oauth.md#registerapplication). You'll also need to edit the example with your production [developer token](get-started.md#get-developer-token). If you are using sandbox, you need to follow the steps below in [Configuring Sandbox](#sandbox).

    ```java
    <%@ page language="java" contentType="text/html; charset=utf-8" pageEncoding="utf-8"%>
    <%@ page import="java.net.URL" %>
    <%@ page import="com.microsoft.bingads.*" %>
    <%@ page import="com.microsoft.bingads.v11.customermanagement.*" %>

    <%! 
    	static AuthorizationData authorizationData;
    	static ServiceClient<ICustomerManagementService> CustomerService; 

    	private static java.lang.String DeveloperToken = "<DeveloperTokenGoesHere>";
    	private static java.lang.String ClientId = "<ClientIdGoesHere>";
    	private static java.lang.String ClientSecret = "<ClientSecretGoesHere>";
    private static java.lang.String RedirectUri = "<RedirectUriGoesHere>";

    	static long accountsCount = 0;
     %>

     <%! 
    	//Gets a User object by the specified Bing Ads user identifier.

    	 static User getUser(java.lang.Long userId) throws Exception
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

    	 static void printAccounts(ArrayOfAccount accounts) throws Exception
    	 {
    	     for (Account account : accounts.getAccounts())
    	     {
    	     	System.out.printf("AccountId: %d\n", account.getId());
    	     	System.out.printf("CustomerId: %d\n", account.getParentCustomerId());
    	     }
    	 }
     %>

    <%
    	// Main execution  

      try {

          	OAuthWebAuthCodeGrant oAuthWebAuthCodeGrant = new OAuthWebAuthCodeGrant(
    			ClientId, 
    			ClientSecret, 
    			new URL(RedirectUri));

          	oAuthWebAuthCodeGrant.setNewTokensListener(new NewOAuthTokensReceivedListener() {
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

          	if (authorizationData == null) {
              	if (request.getParameter("code") == null) {				
    				URL authorizationUrl = oAuthWebAuthCodeGrant.getAuthorizationEndpoint();
    				response.sendRedirect(authorizationUrl.toString());
    				return;
    			} else {		
    				OAuthTokens tokens = oAuthWebAuthCodeGrant.requestAccessAndRefreshTokens(
    					new URL(request.getRequestURL() + "?" + request.getQueryString()));

    				authorizationData = new AuthorizationData();
    				authorizationData.setDeveloperToken(DeveloperToken);
    				authorizationData.setAuthentication(oAuthWebAuthCodeGrant);
    			}
    		}

    		CustomerService = new ServiceClient<ICustomerManagementService>(
    			authorizationData, 
    			ICustomerManagementService.class);

    		User user = getUser(null);

          // Search for the accounts that the user can access.

          ArrayOfAccount accounts = searchAccountsByUserId(user.getId());
          accountsCount = accounts.getAccounts().size();

          System.out.println("The user can access the following Bing Ads accounts: \n");
          printAccounts(accounts);

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
    %>

    <!DOCTYPE html>
    <html>
    <head>
        <meta http-equiv="Content-type" content="text/html; charset=utf-8">
        <title>Bing Ads Web Application Example</title>
        <link rel="stylesheet" href="styles/styles.css" type="text/css" media="screen">
    </head>
    <body>
        <div id="content" class="container">
        	<div>
        		<br/>    		    		
        		<b>You have <%= accountsCount %> accounts</b>    		

        	</div> 
        </div>
    </body>
    </html>
    ```

12. The application is ready to be deployed to a server. For example you can publish a [Web App](http://azure.microsoft.com/services/app-service/web/) using the [Azure App Service](http://azure.microsoft.com/services/app-service/). For more information, see [Deploying a Web Application](#deploy). When you start the application you will be prompted by default for Microsoft account credentials to authenticate in production.

## <a name="sandbox"></a>Configuring Sandbox
To use the [Sandbox](sandbox.md) environment, create a new text file named *bingads.properties* within your project source root directory e.g. **ProjectName\src\bingads.properties** and add the following text. The following are the complete contents of the *bingads.properties* file. If the sandbox environment setting is malformed or missing, the default environment is production.

```no-highlight
environment=Sandbox
```
You can also set the environment for each ServiceClient individually as follows.

```java
CustomerService = new ServiceClient<ICustomerManagementService>(
    authorizationData,
    ApiEnvironment.SANDBOX,
    ICustomerManagementService.class);
```

Whether you set the ServiceClient environment globally or individually, separately you'll also need to set the OAuth environment to sandbox.

```java
OAuthWebAuthCodeGrant oAuthWebAuthCodeGrant = new OAuthWebAuthCodeGrant(
        ClientId, 
        ClientSecret, 
        new URL(RedirectUri),
        ApiEnvironment.SANDBOX);
```

## <a name="deploy"></a>Deploying a Web Application
If you are using Microsoft Azure to deploy your web application, the following are required.

-   A distribution of a Java-based web server or application server, such as Apache Tomcat, GlassFish, JBoss Application Server, Jetty, or IBM® WebSphere® Application Server Liberty Core.

-   An Azure subscription, which can be acquired from [http://azure.microsoft.com/pricing/purchase-options/](http://azure.microsoft.com/pricing/purchase-options/).

-   Optionally you can install the Azure Toolkit for Eclipse (by Microsoft Open Technologies) and deploy your web application using Azure cloud services. For more information, see [Installing the Azure Toolkit for Eclipse (by Microsoft Open Technologies)](https://docs.microsoft.com/en-us/azure/azure-toolkit-for-eclipse-installation).

## See Also
[Sandbox](sandbox.md)  
[Bing Ads Code Examples](code-examples.md)  
[Bing Ads Web Service Addresses](web-service-addresses.md)  

