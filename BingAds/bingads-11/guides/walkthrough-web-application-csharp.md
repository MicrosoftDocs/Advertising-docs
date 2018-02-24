---
title: "Walkthrough: Bing Ads Web Application in C#"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Create a web application using the Bing Ads .NET SDK.
dev_langs:
  - csharp
---
# Walkthrough: Bing Ads Web Application in C# #
The example web application sends authentication requests to the Microsoft account and Bing Ads services for the user credentials that you provide, and then adds a campaign using the Bulk service. You must first [register an application](../guides/authentication-oauth.md#registerapplication) and take note of the client ID, client secret, and redirection URI. You'll also need your production [developer token](~/guides/get-started.md#get-developer-token). 

> [!NOTE]
> This example demonstrates OAuth authentication in production. For information on configuring sandbox, please see [Configuring Sandbox](#sandbox) below.

## <a name="code"></a>Code Walkthrough
1.  Open the [Visual Studio Community](https://www.visualstudio.com/vs/community/) development environment.

2.  Create a new project through **File** -&gt; **New** -&gt; **Project** -&gt; **Templates** -&gt; **Visual C#** -&gt; **Web** -&gt; **ASP.NET Web Application**. Name the project *BingAdsWebApp* and click **OK**.

3.  Select the **MVC** project template and click **OK**.

4.  Within the BingAdsWebApp project, install the SDK through NuGet. For more information, see [Installing the SDK](../guides/get-started-csharp.md#installation).

5.  Within the **Views** -&gt; **Home** folder of the BingAdsWebApp project, open the Index.cshtml file and replace its contents with the following code block. This defines the web page view that displays results of the service calls that will be written further below.

    ```no-highlight
    @{
    ViewBag.Title = "Index";
    }
    
    <h2>Index</h2>
    
    @if (ViewBag.CampaignId != null)
    {
        <h4>Added new Campaign</h4>
        <p>Customer Id: @ViewBag.CustomerId</p>
        <p>Account Id: @ViewBag.AccountId</p>
        <p>Campaign Id: @ViewBag.CampaignId</p>
    
        <p><a href="https://bingads.microsoft.com/campaign/campaigns?cid=@ViewBag.CustomerId&aid=@ViewBag.AccountId">View all of your campaigns in Bing Ads</a></p>
    }
    
    <p><b style="color: red">@ViewBag.Errors</b></p>
    
    <p><b style="color: red">@ViewBag.CampaignErrors</b></p>
    ```

6. Within the **Controllers** folder of the BingAdsWebApp project, open the HomeController.cs file and replace its contents with the following code block. This defines the service calls that will determine which results are displayed in the view that was defined above. You must edit the sample below with the ClientId, ClientSecret, and RedirectionUri that were provisioned when you [registered your application](../guides/authentication-oauth.md#registerapplication). You'll also need to edit the example with your production [developer token](~/guides/get-started.md#get-developer-token). 

    ```csharp
    using System;
    using System.Globalization;
    using System.IO;
    using System.Linq;
    using System.ServiceModel;
    using System.Threading.Tasks;
    using System.Web.Mvc;
    using Microsoft.BingAds;
    using Microsoft.BingAds.V11.Bulk;
    using Microsoft.BingAds.V11.Bulk.Entities;
    using Microsoft.BingAds.V11.CampaignManagement;
    using Microsoft.BingAds.V11.CustomerManagement;

    namespace BingAdsWebApp.Controllers
    {
        public class HomeController : Controller
        {
            private const string ClientId = "<ClientIdGoesHere>";
            private const string ClientSecret = "<ClientSecretGoesHere>";
            private const string RedirectionUri = "<RedirectionUriGoesHere>";
            private const string DeveloperToken = "<DeveloperTokenGoesHere>";
            private static string ClientState = "OptionalClientStateGoesHere";

            private static AuthorizationData _authorizationData;
            private readonly string _refreshTokenFilePath = Path.Combine(Path.GetTempPath(), "refreshToken.txt");

            private static long?[,] _accountCustomerIds;
            private static ServiceClient<ICustomerManagementService> _customerService;
            private static BulkServiceManager _bulkService;

            /// <summary>
            /// Controls the contents displayed at Index.cshtml.
            /// </summary>
            public async Task<ActionResult> Index()
            {
                try
                {
                    // If there is already an authenticated Microsoft account during this HTTP session, 
                    // go ahead and call Bing Ads service operations.
    
                    if (Session["auth"] != null)
                    {
                        return await CallBingAdsServices((OAuthWebAuthCodeGrant)Session["auth"]);
                    }
    
                    // Prepare the OAuth object for use with the authorization code grant flow. 
    
                    var oAuthWebAuthCodeGrant = new OAuthWebAuthCodeGrant(ClientId, ClientSecret, new Uri(RedirectionUri));
    
                    // It is recommended that you specify a non guessable 'state' request parameter to help prevent
                    // cross site request forgery (CSRF). 
                    oAuthWebAuthCodeGrant.State = ClientState;
    
                    // When calling Bing Ads services with ServiceClient or BulkServiceManager, each will refresh your access token 
                    // automatically if they detect the AuthenticationTokenExpired (109) error code. 
                    // As a best practice you should always use the most recent provided refresh token.
                    // Save the refresh token whenever new OAuth tokens are received by subscribing to the NewOAuthTokensReceived event handler. 
    
                    oAuthWebAuthCodeGrant.NewOAuthTokensReceived +=
                        (sender, args) => SaveRefreshToken(args.NewRefreshToken);
    
                    // If a refresh token is already present, use it to request new access and refresh tokens.
    
                    if (RefreshTokenExists())
                    {
                        // To force the authorization prompt, you can clear a previous refresh token.
                        DeleteRefreshToken();
    
                        await oAuthWebAuthCodeGrant.RequestAccessAndRefreshTokensAsync(GetRefreshToken());
    
                        // Save the authentication object in a session for future requests.
                        Session["auth"] = oAuthWebAuthCodeGrant;
    
                        return await CallBingAdsServices((OAuthWebAuthCodeGrant)Session["auth"]);
                    }
    
                    // If the current HTTP request is a callback from the Microsoft Account authorization server,
                    // use the current request url containing authorization code to request new access and refresh tokens
                    if (Request["code"] != null)
                    {
                        if (oAuthWebAuthCodeGrant.State != ClientState)
                            throw new HttpRequestException("The OAuth response state does not match the client request state.");
    
                        await oAuthWebAuthCodeGrant.RequestAccessAndRefreshTokensAsync(Request.Url);
    
                        // Save the authentication object in a session for future requests. 
                        Session["auth"] = oAuthWebAuthCodeGrant;
    
                        return await CallBingAdsServices((OAuthWebAuthCodeGrant)Session["auth"]);
                    }
    
                    // If there is no refresh token saved and no callback from the authorization server, 
                    // then connect to the authorization server and request user consent. 
                    return Redirect(oAuthWebAuthCodeGrant.GetAuthorizationEndpoint().ToString());
                }
                // OAuth classes can throw OAuthTokenRequestException
                catch (OAuthTokenRequestException ex)
                {
                    ViewBag.Errors = string.Format("Couldn't get OAuth tokens. \nError: {0}. Description: {1}",
                        ex.Details.Error, ex.Details.Description);
    
                    return View();
                }
                // Bulk service operations can throw AdApiFaultDetail.
                catch (FaultException<Microsoft.BingAds.Bulk.AdApiFaultDetail> ex)
                {
                    ViewBag.Errors = string.Format("Error when calling the Bulk service: ");
                    ViewBag.Errors += string.Join("; ",
                        ex.Detail.Errors.Select(e => string.Format("{0}: {1}", e.Code, ex.Message)));

                    return View();
                }
                // Customer Management service operations can throw AdApiFaultDetail.
                catch (FaultException<Microsoft.BingAds.CustomerManagement.AdApiFaultDetail> ex)
                {
                    ViewBag.Errors = string.Format("Error when calling the Customer Management service: ");
                    ViewBag.Errors += string.Join("; ",
                        ex.Detail.Errors.Select(e => string.Format("{0}: {1}", e.Code, ex.Message)));

                    return View();
                }
                catch (Exception ex)
                {
                    ViewBag.Errors = ex.Message;

                    return View();
                }
            }

            /// <summary>
            /// Adds a campaign to an account of the current authenticated user. 
            /// </summary>
            private async Task<ActionResult> CallBingAdsServices(Authentication authentication)
            {
                // Uses the first account in a list of accounts that the current authenticated user may access. 
                // If you want to use a specific account identifier, you can set _authorizationData to the value directly
                // instead of calling GetUserDataAsync. 

                _authorizationData = await GetUserDataAsync(authentication);
                var campaignId = await AddCampaignInBulkAsync(_authorizationData);

                ViewBag.CustomerId = _authorizationData.CustomerId;
                ViewBag.AccountId = _authorizationData.AccountId;
                ViewBag.CampaignId = campaignId;

                return View();
            }

            /// <summary>
            /// Uses the BulkService class to add a campaign. 
            /// </summary>
            private async Task<long?> AddCampaignInBulkAsync(AuthorizationData authorizationData)
            {
                _bulkService = new BulkServiceManager(authorizationData);
                _bulkService.StatusPollIntervalInMilliseconds = 1000;

                var uploadResults = await _bulkService.UploadEntitiesAsync(new EntityUploadParameters
                {
                    Entities = new BulkEntity[]
                    {
                        new BulkCampaign
                        {
                            AccountId = authorizationData.AccountId,
                            Campaign = new Campaign
                            {
                                Name = "Campaign " + DateTime.UtcNow.ToString(CultureInfo.InvariantCulture),
                                BudgetType = BudgetLimitType.DailyBudgetAccelerated,
                                DailyBudget = 10,
                                TimeZone = "PacificTimeUSCanadaTijuana"
                            }
                        }
                    },
                    ResponseMode = ResponseMode.ErrorsAndResults
                });

                var campaign = uploadResults.OfType<BulkCampaign>().Single();

                if (campaign.HasErrors)
                {
                    ViewBag.Errors = string.Format("Bulk Upload Error(s): ");
                    ViewBag.Errors += string.Join("; ",
                        campaign.Errors.Select(e => string.Format("{0}: {1}", e.Number, e.Error)));
                }

                return campaign.Campaign.Id;
            }

            /// <summary>
            /// Get customer and account identifiers for the current authenticated user. 
            /// </summary>
            private async Task<AuthorizationData> GetUserDataAsync(Authentication authentication)
            {
                // Some service operations only need Authentication and DeveloperToken elements. 
                // Use these credentials at minimum to get customer and account identifiers before managing campaigns. 
                _authorizationData = new AuthorizationData
                {
                    Authentication = authentication,
                    DeveloperToken = DeveloperToken
                };

                _customerService = new ServiceClient<ICustomerManagementService>(_authorizationData);

                // Get the Bing Ads user identifier for the current authenticated user.
                var user = await GetUserAsync(null);

                var accounts = await SearchAccountsByUserIdAsync(user.Id);

                if (accounts.Length > 0 && accounts[0].Id != null)
                {
                    _authorizationData.AccountId = (long)(accounts[0].Id);
                    _authorizationData.CustomerId = accounts[0].ParentCustomerId;
                }

                // Store the parent customer identifier in the second array dimension

                _accountCustomerIds = new long?[accounts.Length, 2];

                for (var i = 0; i < accounts.Length; i++)
                {
                    _accountCustomerIds[i, 0] = accounts[i].Id;
                    _accountCustomerIds[i, 1] = accounts[i].ParentCustomerId;
                }

                SetUserDataByAccountIndex(0);

                return _authorizationData;
            }

            /// <summary>
            /// Gets a User object by the specified Bing Ads user identifier.
            /// </summary>
            /// <param name="userId">The identifier of the user to get. If null, this operation returns the User object 
            /// corresponding to the current authenticated user of the global customer management ServiceClient.</param>
            /// <returns>The User object corresponding to the specified Bing Ads user identifier.</returns>
            private async Task<User> GetUserAsync(long? userId)
            {
                var request = new GetUserRequest
                {
                    UserId = userId
                };

                return (await _customerService.CallAsync((s, r) => s.GetUserAsync(r), request)).User;
            }

            /// <summary>
            /// Search for account details by UserId.
            /// </summary>
            /// <param name="userId">The Bing Ads user identifier.</param>
            /// <returns>List of accounts that the user can manage.</returns>
            private async Task<Account[]> SearchAccountsByUserIdAsync(long? userId)
            {
                var predicate = new Predicate
                {
                    Field = "UserId",
                    Operator = PredicateOperator.Equals,
                    Value = userId.ToString()
                };

                var paging = new Paging
                {
                    Index = 0,
                    Size = 10
                };

                var request = new SearchAccountsRequest
                {
                    Ordering = null,
                    PageInfo = paging,
                    Predicates = new[] { predicate }
                };

                return (await _customerService.CallAsync((s, r) => s.SearchAccountsAsync(r), request)).Accounts.ToArray();
            }

            /// <summary>
            /// Utility method for setting the customer and account identifiers within the global 
            /// <see cref="_authorizationData"/> instance. 
            /// </summary>
            /// <param name="accountIndex">The index of the account within the <see cref="_accountCustomerIds"/>
            /// multi-dimensional array.</param>
            private void SetUserDataByAccountIndex(int accountIndex)
            {
                if (accountIndex < 0 || accountIndex > _accountCustomerIds.Length) return;

                var accountId = _accountCustomerIds[accountIndex, 0];
                var customerId = _accountCustomerIds[accountIndex, 1];

                if (accountId == null || customerId == null) return;

                _authorizationData.AccountId = (long)accountId;
                _authorizationData.CustomerId = (int)customerId;
            }

            /// <summary>
            /// Saves the refresh token to the global refresh token file path
            /// </summary>
            /// <param name="refreshToken">The refresh token to save.</param>
            private void SaveRefreshToken(string refreshToken)
            {
                System.IO.File.WriteAllText(_refreshTokenFilePath, refreshToken);
            }

            /// <summary>
            /// Deletes the contents in the refresh token file
            /// </summary>
            private void DeleteRefreshToken()
            {
                System.IO.File.Delete(_refreshTokenFilePath);
            }
            
            /// <summary>
            /// Determines whether the global refresh token exists.
            /// </summary>
            /// <returns>Returns true if the global refresh token file exists.</returns>
            private bool RefreshTokenExists()
            {
                return System.IO.File.Exists(_refreshTokenFilePath);
            }

            /// <summary>
            /// Gets the global refresh token within the global refresh token file.
            /// </summary>
            /// <returns>The global refresh token.</returns>
            private string GetRefreshToken()
            {
                return System.IO.File.ReadAllText(_refreshTokenFilePath);
            }
        }
    }
    ```

7. Click **Build** -&gt; **Build BingAdsWebApp**, and then publish the application. For example you can publish a [Web App](http://azure.microsoft.com/en-us/services/app-service/web/) using the [Azure App Service](http://azure.microsoft.com/services/app-service/). When you start the application you will be prompted by default for Microsoft account credentials to authenticate in production.

## <a name="sandbox"></a>Configuring Sandbox
To use sandbox, follow these additional steps.

Replace the try block within HomeController.cs with the following snippet. Authentication with Microsoft account credentials is not supported in sandbox.

```csharp
try
{
    // Prepare legacy Bing Ads UserName and Password authentication object
    var authorization = new PasswordAuthentication("<UserNameGoesHere>", "<PasswordGoesHere>");

    var userData = await GetUserData(authorization);

    return await AddCampaignInBulk(userData);
}
```

Set the *BingAdsEnvironment* key to Sandbox within the *&lt;appSettings&gt;* node of your project root's *Web.config* file.

```xml
<add key="BingAdsEnvironment" value ="Sandbox"/>
```

Optionally you should remove any unused local variables that had been used for OAuth in production.

## See Also
[Sandbox](../guides/sandbox.md)  
[Bing Ads Code Examples](../guides/code-examples.md)  
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

