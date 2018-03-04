---
title: "Walkthrough: Bing Ads Desktop Application in C#"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Create a desktop application using the Bing Ads .NET SDK.
dev_langs:
  - csharp
---
# Walkthrough: Bing Ads Desktop Application in C# #
The example desktop application sends authentication requests to the Microsoft account and Bing Ads services for the user credentials that you provide, and then adds a campaign using the Bulk service. You must first [register an application](authentication-oauth.md#registerapplication) and take note of the client ID. You'll also need your production [developer token](get-started.md#get-developer-token). You can create the example project step by step as described below, or download examples within a Visual Studio solution [GitHub](https://github.com/BingAds/BingAds-dotNet-SDK/tree/master/examples/BingAdsExamples).

> [!NOTE]
> This example demonstrates OAuth authentication in production. For information on configuring sandbox, please see [Configuring Sandbox](#sandbox) below.

## <a name="code"></a>Code Walkthrough

1.  Open the [Visual Studio Community](https://www.visualstudio.com/vs/community/) development environment.

2.  Create a new project through **File** -&gt; **New** -&gt; **Project** -&gt; **Templates** -&gt; **Visual Studio C#** -&gt; **WPF Application**. Name the project *BingAdsDesktopApp* and click **OK**.

3.  Within the BingAdsDesktopApp project, install the SDK through NuGet. For more information, see [Installing the SDK](get-started-csharp.md#installation).

4.  Open the MainWindow.xaml file and replace its contents with the following code block. This defines the presentation view that displays results of the service calls that will be written further below.

    ```xaml
    <Window x:Class="BingAdsDesktopApp.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            Title="MainWindow" SizeToContent="Height" Width="525">
        <Grid>
            <StackPanel>
                <Button Name="CallServicesButton" Click="CallServicesButton_OnClick" Width="150" Height="25">Call Bing Ads Services</Button>
                <WebBrowser Name="WebBrowser" Height="525"></WebBrowser>
            </StackPanel>
        </Grid>
    </Window>
    ```

5.  Open the MainWindow.xaml.cs file and replace its contents with the following code block. This defines the service calls that will determine which results are displayed in the view that was defined above. You must edit the sample below with the ClientId that was provisioned when you [registered your application](authentication-oauth.md#registerapplication). You'll also need to edit the example with your production [developer token](get-started.md#get-developer-token). 

    ```csharp
    using System;
    using System.Globalization;
    using System.IO;
    using System.Linq;
    using System.ServiceModel;
    using System.Threading.Tasks;
    using System.Windows;
    using Microsoft.BingAds;
    using Microsoft.BingAds.V11.Bulk;
    using Microsoft.BingAds.V11.Bulk.Entities;
    using Microsoft.BingAds.V11.CampaignManagement;
    using Microsoft.BingAds.V11.CustomerManagement;

    namespace BingAdsDesktopApp
    {
        /// <summary>
        /// Interaction logic for MainWindow.xaml
        /// </summary>
        public partial class MainWindow
        {
            private const string ClientId = "ClientIdGoesHere";
            private const string DeveloperToken = "DeveloperTokenGoesHere";
            private static string ClientState = "ClientStateGoesHere";

            private Authentication _auth;
            private static AuthorizationData _authorizationData;
            private readonly string _refreshTokenFilePath = Path.Combine(Path.GetTempPath(), "refreshToken.txt");

            private static long?[,] _accountCustomerIds;
            private static ServiceClient<ICustomerManagementService> _customerService;
            private static BulkServiceManager _bulkService;

            public MainWindow()
            {
                InitializeComponent();
            }

            private async void CallServicesButton_OnClick(object sender, RoutedEventArgs e)
            {
                try
                {
                    // If there is already an authenticated Microsoft account during the current application runtime, 
                    // go ahead and call Bing Ads service operations. 
                    if (_auth != null)
                    {
                        await CallBingAdsServices(_auth);
                        return;
                    }
    
                    // Prepare the OAuth object for use with the authorization code grant flow. 
                    var oAuthDesktopMobileAuthCodeGrant = new OAuthDesktopMobileAuthCodeGrant(ClientId);
    
                    // It is recommended that you specify a non guessable 'state' request parameter to help prevent
                    // cross site request forgery (CSRF). 
                    oAuthDesktopMobileAuthCodeGrant.State = ClientState;
    
                    // Save the refresh token to a file whenever new OAuth tokens are received. 
                    oAuthDesktopMobileAuthCodeGrant.NewOAuthTokensReceived +=
                            (s, args) => File.WriteAllText(_refreshTokenFilePath, args.NewRefreshToken);
    
                    // If a refresh token is alreaedy present, use it to request new access and refresh tokens.
                    if (File.Exists(_refreshTokenFilePath)) // If there is an existing refresh token
                    {
                        await oAuthDesktopMobileAuthCodeGrant.RequestAccessAndRefreshTokensAsync(File.ReadAllText(_refreshTokenFilePath));
    
                        // Save the authorization objects in a session for future requests.
                        _auth = oAuthDesktopMobileAuthCodeGrant;
    
                        await CallBingAdsServices(_auth);
                        return;
                    }
    
                    // Navigate the web browser to the Microsoft Account authorization page.
                    WebBrowser.Navigated += async (s, args) =>
                    {
                        // If the current request is a callback from the Microsoft Account authorization server,
                        // use the current request url containing authorization code to request new access and refresh tokens
                        if (args.Uri.AbsolutePath == oAuthDesktopMobileAuthCodeGrant.RedirectionUri.AbsolutePath)
                        {
                            try
                            {
                                if (oAuthDesktopMobileAuthCodeGrant.State != ClientState)
                                    throw new HttpRequestException("The OAuth response state does not match the client request state.");
    
                                await oAuthDesktopMobileAuthCodeGrant.RequestAccessAndRefreshTokensAsync(args.Uri);
    
                                // Save the authorization object in a session for future requests. 
                                _auth = oAuthDesktopMobileAuthCodeGrant;
    
                                await CallBingAdsServices(_auth);
                            }
                            catch (OAuthTokenRequestException ex)
                            {
                                MessageBox.Show(
                                    string.Format("Couldn't get OAuth tokens. Error: {0}. Description: {1}", ex.Details.Error, ex.Details.Description),
                                    "Error when requesting OAuth tokens", MessageBoxButton.OK, MessageBoxImage.Error
                                );
                            }
                            catch (FaultException<Microsoft.BingAds.CustomerManagement.AdApiFaultDetail> ex)
                            {
                                MessageBox.Show(
                                    string.Join("; ", ex.Detail.Errors.Select(error => string.Format("{0}: {1}", error.Code, error.Message))),
                                    "Error when calling the Customer Management service", MessageBoxButton.OK, MessageBoxImage.Error
                                );
                            }
                            catch (FaultException<Microsoft.BingAds.Bulk.AdApiFaultDetail> ex)
                            {
                                MessageBox.Show(
                                    string.Join("; ", ex.Detail.Errors.Select(error => string.Format("{0}: {1}", error.Code, error.Message))),
                                    "Error when calling the Bulk service", MessageBoxButton.OK, MessageBoxImage.Error
                                );
                            }
                            catch (Exception ex)
                            {
                                MessageBox.Show(
                                    ex.Message,
                                    "Error", MessageBoxButton.OK, MessageBoxImage.Error
                                );
                            }
                        }
                    };
    
                    // If there is no refresh token saved and no callback from the authorization server, 
                    // then connect to the authorization server and request user consent. 
                    WebBrowser.Navigate(oAuthDesktopMobileAuthCodeGrant.GetAuthorizationEndpoint());
                }
                catch (OAuthTokenRequestException ex)
                {
                    MessageBox.Show(
                        string.Format("Couldn't get OAuth tokens. Error: {0}. Description: {1}", ex.Details.Error, ex.Details.Description),
                        "Error when requesting OAuth tokens", MessageBoxButton.OK, MessageBoxImage.Error
                    );
                }
                catch (FaultException<Microsoft.BingAds.CustomerManagement.AdApiFaultDetail> ex)
                {
                    MessageBox.Show(
                        string.Join("; ", ex.Detail.Errors.Select(error => string.Format("{0}: {1}", error.Code, error.Message))),
                        "Error when calling the Customer Management service", MessageBoxButton.OK, MessageBoxImage.Error
                    );
                }
                catch (FaultException<Microsoft.BingAds.Bulk.AdApiFaultDetail> ex)
                {
                    MessageBox.Show(
                        string.Join("; ", ex.Detail.Errors.Select(error => string.Format("{0}: {1}", error.Code, error.Message))),
                        "Error when calling the Bulk service", MessageBoxButton.OK, MessageBoxImage.Error
                    );
                }
                catch (Exception ex)
                {
                    MessageBox.Show(
                        ex.Message,
                        "Error", MessageBoxButton.OK, MessageBoxImage.Error
                    );
                }
            }

            /// <summary>
            /// Adds a campaign to an account of the current authenticated user. 
            /// </summary>
            private async Task CallBingAdsServices(Authentication authentication)
            {
                // Uses the first account in a list of accounts that the current authenticated user may access. 
                // If you want to use a specific account identifier, you can set _authorizationData to the value directly
                // instead of calling GetUserDataAsync. 

                _authorizationData = await GetUserDataAsync(authentication);
                var campaignId = await AddCampaignInBulkAsync(_authorizationData);

                MessageBox.Show(string.Format("Added new campaign:\n\nCustomerId: {0}\nAccountId: {1}\nCampaignId: {2}",
                    _authorizationData.CustomerId, _authorizationData.AccountId, campaignId));
            }

            /// <summary>
            /// Uses the BulkServiceManager class to add a campaign. 
            /// </summary>
            private async Task<long?> AddCampaignInBulkAsync(AuthorizationData authorizationData)
            {
                _bulkService = new BulkServiceManager(authorizationData);
                _bulkService.StatusPollIntervalInMilliseconds = 1000;

                // Note that UploadEntities writes a temporary file for upload.
                // You can get and set the BulkServiceManager.WorkingDirectory property.
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
                    MessageBox.Show(
                        string.Join("; ", campaign.Errors.Select(error => string.Format("{0}: {1}", error.Number, error.Error))),
                        "Upload had errors", MessageBoxButton.OK, MessageBoxImage.Error
                    );
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
            /// Gets a User object by the specified UserId.
            /// </summary>
            /// <param name="userId">The Bing Ads user identifier.</param>
            /// <returns>The Bing Ads user.</returns>
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
        }
    }
    ```

6.  Click **Build** -&gt; **Build BingAdsDesktopApp**, and then run the application. When you start the application you will be prompted by default for Microsoft account credentials to authenticate in production.

## <a name="sandbox"></a>Configuring Sandbox
To use sandbox, follow these additional steps.

Replace the try block within MainWindow.xaml.cs with the following snippet. 

```csharp
try
{
    // Prepare legacy Bing Ads UserName and Password authentication object
    var authorization = new PasswordAuthentication("<UserNameGoesHere>", "<PasswordGoesHere>");

    var userData = await GetUserData(authorization);

    return await AddCampaignInBulk(userData);
}
```

Set the *BingAdsEnvironment* key to Sandbox within the *&lt;appSettings&gt;* node of your project root's *App.config* file.

```xml
<add key="BingAdsEnvironment" value ="Sandbox"/>
```

Optionally you should remove any unused local variables that had been used for OAuth in production.

## See Also
[Sandbox](sandbox.md)  
[Bing Ads Code Examples](code-examples.md)  
[Bing Ads Web Service Addresses](web-service-addresses.md)  

