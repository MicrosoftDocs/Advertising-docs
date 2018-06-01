# AccountsApp
This is the top-level object for managing multiple accounts in Bing Ads.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[accounts](#accounts)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector of all accounts accessible to the current user under the current customer shell.
[select(BingAdsAccount account)](#select~bingadsaccount-account~)|void|Selects a [BingAdsAccount](./BingAdsAccount) as the the current account on which to perform operations.

## <a name="accounts"></a>accounts
Returns a selector of all accounts accessible to the current user under the current customer shell.

### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector of accounts managed by this account.

## <a name="select~bingadsaccount-account~"></a>select(BingAdsAccount account)
Selects a [BingAdsAccount](./BingAdsAccount) as the the current account on which to perform operations.

### Arguments:
|Name|Type|Description|
|-|-|-
account|[BingAdsAccount](./BingAdsAccount)|Account in whose context the script will continue executing.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

