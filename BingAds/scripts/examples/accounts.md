# Accounts

## Get details about the current account
```javascript
function getCurrentAccountDetails() {
  var currentAccount = BingAdsApp.currentAccount();
  Logger.log('Customer ID: ' + currentAccount.getCustomerId() +
      ', Currency Code: ' + currentAccount.getCurrencyCode() +
      ', Timezone: ' + currentAccount.getTimeZone());
  var stats = currentAccount.getStatsFor('LAST_MONTH');
  Logger.log(stats.getClicks() + ' clicks, ' +
    stats.getImpressions() + ' impressions last month');
}
```