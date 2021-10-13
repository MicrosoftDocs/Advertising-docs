---
title: What tracking or URL parameters can I use?
description: Review the URL parameters you can add to your tracking template or destination URLs to find out how visitors got to your website.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What tracking or URL parameters can I use?

You add URL parameters to your destination URL or tracking template to find out how visitors got to your website. URL parameters allow you to track information about the source of an ad click.

Although the variable names and the parameters can change, the structure is always the same:

- A **parameter**, enclosed by **{ }** that tells Microsoft Advertising what data you want returned when an ad is clicked.  The specific parameters to choose from are listed in the table below.
- A **variable** that you define to store that data. The name of the variable is up to you, but it should be the name used in your website's script to store the value that the parameter is returning. Work with your website programmers who can help you define appropriate names to use.

Putting it all together, it looks like this:

*www.yourLandingPageURL.com*?*variable*={*parameter*}

If you are adding more than one *variable*={*parameter*}, you separate the variable/parameter pair with an ampersand (&amp;).
## Available parameters for:

## Destination URL, final URLs, tracking templates and custom parameters
<table>
  <tr>
    <th scope="col">
              *{CampaignId}*
            </th>
  </tr>
  <tr>
    <td> <strong>What it returns:</strong>
              <para>The ID of the campaign that triggered the ad.
              For example, suppose your destination URL is www.northwindtraders.com/{CampaignId}. Assuming that your campaign ID is 2410012280, the destination URL will be www.northwindtraders.com/2410012280.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{Campaign}*
            </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
              <para> The name of the campaign that triggered the ad.
              For example, suppose your destination URL is www.northwindtraders.com/{Campaign}. Assuming that your campaign name is Sale, the destination URL will be www.northwindtraders.com/Sale.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{AdGroupId}*
            </th>
  </tr>
  <tr>
    <td><strong>What it returns</strong>
            <para>The ID of the ad group that triggered the ad.
              For example, suppose your destination URL is www.northwindtraders.com/{AdGroupId}. Assuming that your ad group ID is 2410012280, the destination URL will be www.northwindtraders.com/2410012280.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{AdGroup}*
            </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
              <para>The name of the ad group that triggered the ad.
              For example, suppose your destination URL is www.northwindtraders.com/{AdGroup}. Assuming that your ad group ID is Clearance, the destination URL will be www.northwindtraders.com/Clearance.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{TargetId}*
            </th>
  </tr>
  <tr>
    <td><strong>What it returns</strong>
              <para> The ID of the keyword ("kwd"), remarketing or audience list ("aud"), dynamic ad target ("dat"), product partition ("pla"), or targeted location ID ("loc") that triggered the ad.</para><para>If there are more than one ID, they will appear in the following order: aud, dat, kwd, pla. For example, if you associate remarketing list "1234" with keyword "5678", the {TargetId} would be replaced by "aud-1234:kwd-5678".</para><para>Note: In-market audiences and LinkedIn profile targeting cannot be tracked through this parameter as this would expose individual user behavior on Bing and other Microsoft properties.  </para></td>
  </tr>
  <tr>
    <th scope="col">
              *{MatchType}*
            </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
              <para> The match type used to deliver an ad. This can be different from the {BidMatchType}. For example, if you bid on a broad match and the search term was an exact match. 
               This can help you determine what match types are getting the most clicks.</para><ul><li>
                  *e*=exact
                </li><li>
                  *p*=phrase
                </li><li>
                  *b*=broad
                </li><li>
                  *b*=expanded (Expanded match is treated as a broad match.)
                </li></ul></td>
  </tr>
  <tr>
    <th scope="col">
                    *{BidMatchType}*
                  </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
                    <para>The keyword bid match type. This can be different than {MatchType}. For example, if you bid on a broad match and the search term was an exact match.
                    When used with {MatchType} this can help you refine your bidding, keyword and landing page strategies.</para><ul><li>
                        *be*=bidded exact
                      </li><li>
                        *bp*=bidded phrase
                      </li><li>
                        *bb*=bidded broad
                      </li></ul></td>
  </tr>
  <tr>
    <th scope="col">
              *{Network}*
            </th>
  </tr>
  <tr>
    <td>
                <strong>What it returns</strong>
              <para> The ad network type on which the ad was served.</para><ul><li>
                  o = owned and operated (Bing, AOL, and Yahoo search results)
                </li><li>
                  s = syndicated (search partner site results)
                </li><li>
                  a = audience (Microsoft Audience Network placements)
                </li></ul>
              For example, suppose your destination URL is www.northwindtraders.com/network={Network}. Assuming that your network (ad distribution) is <strong>Bing, AOL and Yahoo search (owned and operated) only</strong>, the destination URL will be www.northwindtraders.com/network=o.</td>
  </tr>
  <tr>
    <th scope="col">
              *{Device}*
            </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
              <para>One of the following codes depending on where the click came from. This list can help you determine what type of devices are generating the most clicks. You can then customize your ads and bids accordingly.</para><ul><li>
                  *m*=mobile device
                </li><li>
                  *t*=tablet device
                </li><li>
                  *c*=desktop or laptop computer
                </li></ul></td>
  </tr>
  <tr>
    <th scope="col">
                    *{IfMobile:string}*
                  </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
                    <para>The <strong>string</strong> text (that you define) to the right of the colon if the ad is displayed on a mobile device.  For example, if your parameter was {IfMobile:adDisplayedOnMobile} and your ad was displayed on a mobile device, your server log would receive <strong>adDisplayedOnMobile</strong>.</para></td>
  </tr>
  <tr>
    <th scope="col">
                    *{IfNotMobile:string}*
                  </th>
  </tr>
  <tr>
    <td><strong>What it returns</strong>
                    <para>The <strong>string</strong> text (that you define) to the right of the colon if the ad is displayed on a desktop, laptop, or tablet device.  For example, if your parameter looked like this: {IfNotMobile:adNotOnMobile} and your ad was displayed on a mobile device, your server log would receive: adNotOnMobile.</para></td>
  </tr>
  <tr>
    <th scope="col">
                    *{IfSearch:string}*
                  </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
                    <para> The <strong>string</strong> text (that you define) to the right of the colon if the ad is displayed on the search network.  For example, if your parameter looked like this: {IfSearch:adDisplayedOnSearch} and your ad was displayed on the search network, your server log would receive: adDisplayedOnSearch. </para></td>
  </tr>
  <tr>
    <th scope="col">
              *{IfNative:string}*
            </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
              <para>The <strong>string</strong> text (that you define) to the right of the colon will be substituted into the URL if the ad is displayed as a Microsoft Audience Ad.  For example, if your parameter looked like this: {IfNative:nativeAd} and your ad was displayed as an audience ad, your server log would receive: nativeAd.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{IfPLA:string}*
            </th>
  </tr>
  <tr>
    <td><strong>What it returns</strong>
              <para>The <strong>string</strong> text (that you define) to the right of the colon will be substituted into the URL if the ad is displayed as a product ad.  For example, if your parameter looked like this: {IfPLA:productAd} and your ad was displayed as a product ad, your server log would receive: productAd.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{AdId}*
            </th>
    <td></td>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
              <para>The numeric ID of the displayed ad.</para><para> You can get your ad ID on the Ads table on the Campaigns page. If the <strong>Ad ID</strong> column is not displayed in the table, click <strong>Columns</strong> and select<strong> Ad ID</strong>. Then click <strong>OK</strong>.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{keyword:default}*
            </th>
    <td></td>
  </tr>
  <tr>
    <td><strong>What it returns</strong>
              <para>Substitutes the keyword that matched the user's search term. Spaces in the keyword will each be substituted with "%20" to ensure the URL is valid.</para><para>
                Note: You should provide a default string that the system will use if including the substitution value will cause the expanded string to exceed the string limit of the URL.
              </para><para> Substitution of your default text is not supported, so you should not include characters such as a space which would cause the URL to be invalid.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{msclkid}*
            </th>
    <td></td>
  </tr>
  <tr>
    <td>
              <strong>What it returns</strong>
              <para>A unique ClickID for the clicks on the ad. To learn more, see [Description of methodology](https://go.microsoft.com/fwlink?LinkId=398319)
            </para></td>
  </tr>
  <tr>
    <th scope="col">
              *{OrderItemId}*
            </th>
  </tr>
  <tr>
    <td>  <strong>What it returns</strong>
              <para>The numeric ID for the keyword that triggered the display of your ad.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{param1:default}*
            </th>
  </tr>
  <tr>
    <td><strong>What it returns</strong>
              <para> Substitutes {Param1} in the URL with the Param1 setting of the keyword that matched the user's search term.</para><para>
                Note: You should provide a default string that the system will use if including the substitution value will cause the expanded string to exceed the string limit of the URL.
              </para></td>
  </tr>
  <tr>
    <th scope="col">
              *{param2:default}*
            </th>
  </tr>
  <tr></tr>
  <tr>
    <td><strong>What it returns</strong>
              <para> Substitutes {Param2} in the URL with the Param2 setting of the keyword that matched the user's search term.</para><para>
                Note: You should provide a default string that the system will use if including the substitution value will cause the expanded string to exceed the string limit of the URL.
              </para></td>
  </tr>
  <tr>
    <th scope="col">
              *{param3:default}*
            </th>
  </tr>
  <tr>
    <td><strong>What it returns</strong>
              <para>Substitutes {Param3} in the URL with the Param3 setting of the keyword that matched the user's search term.</para><para>
                Note: You should provide a default string that the system will use if including the substitution value will cause the expanded string to exceed the string limit of the URL.
              </para></td>
  </tr>
  <tr>
    <th scope="col">
                    *{QueryString}*
                  </th>
  </tr>
  <tr>
    <td> <strong>What it returns</strong>
                    <para>The search query text that the user entered.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{copy:queryparameter}*
            </th>
  </tr>
  <tr>
    <td>
      <para>{copy} parameter doesn't work with final URLs but it does work with destination URLs.</para>
      <para>
              When an ad with an App Extension, Image ad extension or Sitelink Extension is served, the {copy} string in the ad extension's destination URL is replaced with the specified query parameter from the ad’s resolved destination URL. The resolved destination URL is the URL used by the ad at the time the ad is served; after all dynamic text strings in the ad’s destination URL are substituted with actual values. For example, if a Sitelink Extensions's destination URL contains {copy:myId} and the ad’s resolved destination URL includes ?myId=123, the {copy:myId} string will be replaced with myId=123. If the ad’s resolved destination URL does not include the query parameter, the {copy} string will be replaced with the name portion of the query parameter. For example, myId=.
</para>
      <more_info type="ICON_NOTE">
        <more_info_item>If you have upgraded your keyword destination URLs to final URL but haven't upgraded your Sitelink Extension URLs yet, the {copy} parameter will still work for the Sitelink Extension. For example:
                <para>
                  <strong>Keyword Final URL (upgraded):</strong> 
                </para><para style="font-family:courier">
                    http://www.example.com?a=1&amp;b=desk
                  </para><para>
                    <strong>Keyword Mobile URL (upgraded):</strong> 
                  </para><para style="font-family:courier">
                    http://www.example.com?a=1&amp;b=mob
                  </para><para>
                    <strong>Sitelink Extension URL (not upgraded):</strong> 
                  </para><para style="font-family:courier">
                    http://www.example.com?a=1&amp;{copy:b}
                  </para></more_info_item>
      </more_info>
    </td>
  </tr>
  <tr>
    <th scope="col">
              *{feeditemid}*
            </th>
  </tr>
  <tr>
    <td>  <strong>What it returns</strong>
              <para>The ID of the ad extension that was clicked.</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{loc_physical_ms}*
            </th>
  </tr>
  <tr>
    <td>  <strong>What it returns</strong>
              <para>The geographical location code of the physical location of the click. For more information on geographical location codes, take a look at [this Bing Ads API doc](https://go.microsoft.com/fwlink?LinkId=536556).</para></td>
  </tr>
  <tr>
    <th scope="col">
              *{loc_interest_ms}*
            </th>
  </tr>
  <tr>
    <td>  <strong>What it returns</strong>
              <para>The geographical location code of the location of interest that triggered the ad. For more information on geographical location codes, take a look at [this Bing Ads API doc](https://go.microsoft.com/fwlink?LinkId=536556)</para></td>
  </tr>
</table>

> [!IMPORTANT]
> Custom parameters will return the variable if added to a tracking template but will return an empty value if added to a destination URL.

## Tracking templates only
Tracking templates should include a parameter that inserts your landing page URL using either the {lpurl} or other advanced parameters. Once your ad is clicked, these parameters will insert your final URL. If you don’t include a URL insertion parameter in your tracking template, your landing page URL will break.

|*{lpurl} Basic setup*|
|---|
|**When to use:**You track your tags on the actual landing page.**Tracking template structure:**{lpurl}, a question mark, and then any parameters**Example:**|Final URL:|http://example.com||---|---||Tracking template:|{lpurl}?matchtype={matchtype}||Landing page URL:|http://example.com?matchtype={matchtype}||
|*{lpurl} 1 redirect and parameters*|
|**When to use:**You have 1 redirect to a tracking website and want to send parameters to it.**Tracking template structure:**Redirect URL, a question mark, url={lpurl}, an ampersand, and then any parameters**Example:**|Final URL:|http://example.com||---|---||Tracking template:|http://tracker.com?url={lpurl}&amp;matchtype={matchtype}||Landing page URL:|http://tracker.com?url=http%3A%2F%2Fexample.com&amp;matchtype={matchtype}||
|*{lpurl} 1 redirect and landing page parameters (tracking template)*|
|**When to use:**You have 1 redirect to a tracking website and want to send parameters to your landing page using a tracking template.**Tracking template structure:**Redirect URL, a question mark, url={lpurl}, %3F, %26, and then any parametersSince {lpurl} is not at the beginning of the tracking template, you need to add %3F after {lpurl} instead of a question mark. You also need to replace the ampersand (&amp;) with %26.**Example:**|Final URL:|http://example.com||---|---||Tracking template:|http://tracker.com?url={lpurl}%3F%26matchtype={matchtype}||Landing page URL:|http://tracker.com?url=http%3A%2F%2Fexample.com%3F%26matchtype={matchtype}||
|*{lpurl} 1 redirect and landing page parameters (no tracking template)*|
|**When to use:**You have 1 redirect to a tracking website and want to send parameters to your landing page without using a tracking template.**Tracking template structure:**Redirect URL, a question mark, url={lpurl}Best to store landing page parameters in the final URL when using a redirect URL so that Bing does all the encoding inside {lpurl} when evaluating the tracking template.**Example:**|Final URL:|http://example.com?matchtype={matchtype}||---|---||Tracking template:|http://tracker.com?url={lpurl}||Landing page URL:|http://tracker.com?url=http%3A%2F%2Fexample.com%3F%26matchtype={matchtype}||

> [!NOTE]
> We recommend that you put the {lpurl} at the beginning of the tracking template. If you don't, the final URL will be escaped. All characters that are not letters, numbers, or the following punctuation characters will be escaped: -, _, ., !, \*, (, and ).

## Advanced parameters

There are also advanced parameters that you can use if you have more than 1 redirect or want to use escaped or unescaped URLs. Here is a quick summary:
|Parameter|What it returns|
|---|---|
|{lpurl+2}|The Final URL escaped twice. Also known as double encoding. You use this when you have 2 redirects before reaching the landing page.|Final URL:|http://example.com||---|---||Tracking template:|http://a-tracker.com?urlb=http%3A%2F%2Fb-tracker.com%3Furl%3D{lpurl+2}||Landing page URL:|http://a-tracker.com?urlb=http%3A%2F%2Fb-tracker.com%3Furl%3Dhttp%253A%252F%252Fexample.com||
|{lpurl+3}|The Final URL, escaped three times. Also known as triple encoding. You use this when you have 3 redirects before reaching the landing page.|Final URL:|http://example.com||---|---||Tracking template:|http://a-tracker.com?urlb=http%3A%2F%2Fb-tracker.com%3Furlc%3Dhttp%253A%252F%252Fc-tracker.com%253Furl%253D{lpurl+3}||Landing page URL:|http://a-tracker.com?urlb=http%3A%2F%2Fb-tracker.com%3Furlc%3Dhttp%253A%252F%252Fc-tracker.com%253Furl%253Dhttp%25253A%25252F%25252Fexample.com||
|{unescapedlpurl}|The Final URL, unescaped.|
|{escapedlpurl}|The Final URL, escaped. Escapes all characters that are not letters, numbers, or the following punctuation characters: -, _, ., !, \*, (, and ).|
|{escapedlpurl+2}|The Final URL, escaped twice. Useful when you have a chain of redirects.|
|{escapedlpurl+3}|The Final URL, escaped three times. Useful when you have a chain of redirects.|

## What characters to add after the URL insertion parameter?
As seen in the examples above, what you add after the URL insertion parameter is dependent on where in the tracking template you place it. You will want to adhere to the following rules or your website/third-party system may not properly save the information from your URL parameters.

|Parameter|Tracking template location|Followed by|Example|
|---|---|---|---|
|{lpurl}|Beginning|?|{lpurl}?|
|{lpurl}|Not at the beginning|%3F|{lpurl}%3F|
|{lpurl+2}|Not at the beginning|%253F|{lpurl+2}%253F|
|{lpurl+3}|Not at the beginning|%25253F|{lpurl+3}%25253F|
|{unescapedlpurl}|Anywhere|?|{unescapedlpurl}?|
|{escapedlpurl}|Anywhere|%3F|{escapedlpurl}%3F|
|{escapedlpurl+2}|Anywhere|%253F|{escapedlpurl+2}%253F|
|{escapedlpurl+3}|Anywhere|%25253F|{escapedlpurl+2}%253F|

Microsoft Advertising will replace the question mark in your tracking template with an ampersand or a correctly escaped version of an ampersand if your final URL already contains a question mark.

## Final URL only
|Parameter|What it returns|
|---|---|
|*{ignore}*|Ignores the tracking elements of your Final URL to help to reduce the crawl load on your website. It can only be used in your Final or Final mobile URL.                  For example, if your Final URL is http://www.example.com/product?p1=a&amp;/p2=b&amp;p3=c&amp;p4=d, and the tracking info following the question mark in the URL doesn’t change the landing page, you can insert {ignore} before your tracking info to indicate that everything after it is merely tracking info. Here’s an example of how to do this: http://www.example.com/product?{ignore}p1=a&amp;p2=b&amp;p3=c&amp;p4=d|

Here are some things to bear in mind when using {ignore}

- {ignore} can’t be embedded inside other parameters.
- You must use {ignore} in your Final URL if anything in your Final URL can be modified by a third party when someone clicks your ad.

## Microsoft Shopping Campaigns only
If you advertise with product ads in your Microsoft Shopping Campaigns, the DestinationUrl of a BiddableAdGroupCriterion can include the following dynamic text strings. The strings are case-insensitive and must include the opening and closing braces.

|Parameter|What it returns|
|---|---|
|*{CriterionId}*|The identifier of the Microsoft Shopping product group used with product ads.|
|*{product_channel}*|The type of shopping channel (online or local)  that the product in the clicked ad is sold.|
|*{product_country}*|The country of sale for the product in the clicked ad. For example, US, UK, etc.|
|*{ProductId}*|The numeric ID of the product that triggered your ad. This comes from your Microsoft Merchant Center  catalog and is used with product ads.|
|*{product_language}*|The language of your product information, as indicated in your Merchant Center data feed. For example, EN, FR.|
|*{seller_name}*|The value associated with the seller for that product, which can be the seller name from the feed or the store name based on if the advertiser is an aggregator or not.|

 

