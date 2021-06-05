> [!IMPORTANT]
> Starting August 1st, 2021 we will require multi-factor authentication for all users who sign in through a third-party application that uses the Bing Ads API, Content API, and Hotel APIs.
> 
> You must update your application to use the new ```msads.manage``` scope via the [Microsoft identity platform endpoint](../authentication-oauth-identity-platform.md). All application developers must take action to use the new scope. 
> 
> - Prior to MFA enforcement the [Microsoft identity platform endpoint](../authentication-oauth-identity-platform.md) supports the ```ads.manage``` scope. Access tokens that you acquire for users via the ads.manage scope will no longer be authenticated.
> 
> - Prior to MFA enforcement the [Live Connect](../authentication-oauth-live-connect.md) endpoint supports the ```bingads.manage``` scope. The Live Connect endpoint is already deprecated and will no longer be supported. Access tokens that you acquire for users via the bingads.manage scope will no longer be authenticated.
> 
> Upon enforcement of MFA, we will only authenticate access tokens on behalf of a user who granted consent to your application via the ```msads.manage``` scope on the Microsoft Identity endpoint.
> 
> The new ```msads.manage``` scope **requires renewed consent from all users of your application**. You must prompt users for consent using the new ```msads.manage``` scope whether or not they have turned on multi-factor authentication. This ensures that they provide a second form of identification or proof when granting consent to your application.  
> 
> We also recommend that you inform and guide users of your application to [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature) so that a second proof will be required when they grant permissions for any application.
