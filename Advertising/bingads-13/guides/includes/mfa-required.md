> [!IMPORTANT]
> Starting August 1st, 2021 we will require multi-factor authentication for all users who sign in through a third-party application that uses the Bing Ads API, Content API, and Hotel APIs.
> 
> You must update your application to use the new ```msads.manage``` scope (coming soon) via the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). All application developers must take action to use the new scope. 
> 
> - Prior to MFA enforcement the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) supports the ```ads.manage``` scope. Access tokens that you acquire for users via the ads.manage scope will no longer be authenticated.
> 
> - Prior to MFA enforcement the [Live Connect](authentication-oauth-live-connect.md) endpoint supports the ```bingads.manage``` scope. The Live Connect endpoint is already deprecated and will no longer be supported. Access tokens that you acquire for users via the bingads.manage scope will no longer be authenticated.
> 
> Upon enforcement of the MFA requirement, we will only authenticate access tokens on behalf of a user who passed through MFA via the new ```msads.manage``` scope on the Microsoft Identity endpoint.
> 
> The new ```msads.manage``` scope **requires renewed consent from all users of your application**. You must prompt users for consent using the new ```msads.manage``` scope after they have turned on multi-factor authentication. We recommend that you inform and guide users of your application to [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature) right away.
