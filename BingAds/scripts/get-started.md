# Get Started With Bing Ads Scripts

1. Sign in to your Bing Ads account.
2. Expand the <strong>Bulk Operations</strong> section of the navigation panel on the left.
3. Click <strong>Scripts</strong>.
4. Copy and paste the code below into the code editor.
```javascript
function main() {
    var keywords = BingAdsApp.keywords()
        .orderBy("Impressions DESC")
        .forDateRange("YESTERDAY")
        .withLimit(10)
        .get();

    Logger.log("10 keywords with most impressions yesterday");
    while (keywords.hasNext()) {
        var keyword = keywords.next();
        Logger.log(keyword.getText() + ": " +
            keyword.getStatsFor("YESTERDAY").getImpressions());
    }
}
```
5. To execute the script in preview mode, click <strong>Preview</strong>.