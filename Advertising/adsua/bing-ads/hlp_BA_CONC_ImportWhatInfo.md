---
title: What gets imported from Google Ads
description: Most of the information in your campaigns is included when you import it from Google Ads. Here's a list of what gets imported, as well as some exceptions.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What gets imported from Google Ads

Now that you’ve imported your campaigns from Google Ads, you can check the status of your import, review error logs, and edit, pause, or delete your import schedule. Keep in mind that not all information will be imported, but that doesn’t mean it’s not supported within Microsoft Advertising. So, after you import, be sure to review your campaigns to make sure everything is good to go and add the missing information back to your campaigns.

## Items you should check during import

Some specific situations require special attention during import. If you are importing any of the items below, make sure to review the following information.

## Ad distribution (Network)
Ad distribution is where you want your ads to show. When a Google Ads ad group is imported, it is mapped in the following ways:

- If the network is the **Search and Display Network**, we set it to **Search**.
- If the network is the **Google Search Network**, we set it to **Search**.

To learn more, see [About ad distribution](./hlp_BA_CONC_AboutAdDistribution.md).
> [!NOTE]
> If the network is the **Google Search Network**, and **Include search partners** is selected, then Bing will target all search networks. (Bing, AOL, and Yahoo search and syndicated search partners)
> Syndicated search is only available in certain countries. To learn more, see [What is the search network?](./hlp_BA_CONC_SearchNetContentNet.md).
> Microsoft Advertising stopped serving ads on the content network.

## Age and gender targeting
By importing your age and gender targeting, you can reach customers who’re likely to be within the demographic range you choose. Microsoft Advertising matches most of your Google Ads age and gender targets, however, there are a few differences that you can review in the tables below.

|Google Ads age groups|Microsoft Advertising age groups|
|---|---|
|18-24|18-24|
|25-34|25-34|
|35-44|35-49|
|55-64|50-64|
|65+|65+|
|Unknown|Not imported|

|Google Ads gender groups|Microsoft Advertising gender groups|
|---|---|
|Male|Male|
|Female|Female|
|Unknown|Not imported|

> [!IMPORTANT]
> The Google Ads age group of 45-54 will not be imported into Microsoft Advertising.

## Audience targeting
Audiences are groups of potential customers that you can target. By importing your audiences from Google Ads, you can boost your campaign performance by reaching people browsing your website through Bing.

## Audience targeting: FAQ

## Which audience types can I import from Google Ads?
> [!NOTE]
> Please note that any audience list that has the following attributes, will not be imported from Google Ads:
> - Audience lists created at the MCC level. List types must belong to the account you’re importing from.
> - Automatically created lists
> - Lists set to match every rule group
> - Remarketing list created in Google Analytics

Below are lists without those attributes.

<table>
  <tr>
    <th style="width:180px" scope="col">
                    Google Ads audience type
                  </th>
    <th style="width:220px" scope="col">
                    What gets imported
                  </th>
    <th style="width:220px" scope="col">
                    What doesn't get imported
                  </th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    Affinity
                  </th>
    <td style="text-align:left">
                    N/A
                  </td>
    <td style="text-align:left">
                    All lists
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    App users
                  </th>
    <td style="text-align:left">
                    N/A
                  </td>
    <td style="text-align:left">
                    All lists
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    Combined lists:
                  </th>
    <td style="text-align:left">
                    Lists that use AND, OR, and NOT conditions
                  </td>
    <td style="text-align:left">
                    Lists that only use the NOT condition
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    Customer lists
                  </th>
    <td style="text-align:left">
                    N/A
                  </td>
    <td style="text-align:left">
                    All lists
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    Detailed Demographics
                  </th>
    <td style="text-align:left">
                    N/A
                  </td>
    <td style="text-align:left">
                    All lists
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    In-market
                  </th>
    <td style="text-align:left">
                    All lists
                  </td>
    <td style="text-align:left">
                    N/A
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    Similar audiences
                  </th>
    <td style="text-align:left">
                    N/A
                  </td>
    <td style="text-align:left">
                    All lists
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    Website visitors (also called rule-based remarketing list)
                  </th>
    <td style="text-align:left">
                    Lists of the following type:
                    <ul><li>
                        Vistors of a page
                      </li><li>
                        Vistors of a page who also visited another page
                      </li><li>
                        Vistors of a page who did not visit another page
                      </li></ul></td>
    <td style="text-align:left">
                    Lists of the following type:
                    <ul><li>
                        Visitors of a page during specific dates
                      </li><li>
                        Visitors of a page with specific tags
                      </li><li>
                        Created using parameters that are not supported in Microsoft Advertising (for example, type and category ID)
                      </li><li>
                        Specific date-based
                      </li></ul><para>
                      Any membership duration that is greater than 180 days will be lowered to 180 days during import.
                    </para></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    YouTube vistors
                  </th>
    <td style="text-align:left">
                    N/A
                  </td>
    <td style="text-align:left">
                    All lists
                  </td>
  </tr>
</table>

## What happens when I import an individual in-market audience that doesn’t exist in Microsoft Advertising?
When you import a specific in-market audience that doesn’t exist in Microsoft Advertising, all its associations are mapped to its parent audience. For example, let’s say you want to import an ad group or campaign with one audience, “Apparel &amp; Accessories/Bow ties.” Since “Bow ties” is not supported by Microsoft Advertising, all associations with “Bowties” would be mapped to its parent audience, “Apparel &amp; Accessories,” instead.
## What happens when I import multiple in-market audiences?
When you import multiple associations that are mapped to the same in-market audience, only associations with the **direct** audience are imported. For example, let’s say you want to import an ad group or campaign with two audience associations:

- The first association is with “Apparel &amp; Accessories.”
- The second association is with “Apparel &amp; Accessories/Bow ties.”

Only the ad group or campaign's first association will be imported because it can be mapped directly to the audience, “Apparel &amp; Accessories.” The ad group or campaign's other association will not be imported.

## Importing multiple in-market audiences with no direct associations

When you import multiple associations that are mapped to the same in-market audience, and there are **no** direct associations available, then only the association that is active **and** has the highest bid boost will be imported and mapped to its parent audience. For example, let’s say you want to import an ad group or campaign with three audience associations, all of which are not available in Microsoft Advertising:

- The first association is with “Apparel &amp; Accessories/Bow ties,” is active, and has a 20% bid boost.
- The second association is with “Apparel &amp; Accessories/Belts,” is active, and has a 10% bid boost.
- The third association is with “Apparel &amp; Accessories/Bracelets,” is paused, and has a 30% bid boost.

Only the ad group or campaign's first association will be imported because out of all the active associations, it has the highest bid boost. The ad group or campaign's other two associations will not be imported.

## What happens when I import multiple in-market audiences with no direct associations?
When you import multiple associations that are mapped to the same in-market audience, and there are **no** direct associations available, then only the association that is active **and** has the highest bid boost will be imported and mapped to its parent audience. For example, let’s say you want to import an ad group or campaign with three audience associations, all of which are not available in Microsoft Advertising:

- The first association is with “Apparel &amp; Accessories/Bow ties,” is active, and has a 20% bid boost.
- The second association is with “Apparel &amp; Accessories/Belts,” is active, and has a 10% bid boost.
- The third association is with “Apparel &amp; Accessories/Bracelets,” is paused, and has a 30% bid boost.

Only the ad group or campaign's first association will be imported because out of all the active associations, it has the highest bid boost. The ad group or campaign's other two associations will not be imported.

## How do I know which in-market audience associations were mapped to their parent audiences?
After your import completes, you can see in-market audience associations and their parent audiences under **Import Summary** on the **Import Campaigns** page. Please note that if there were any issues with the import, the **Logs** table will include an error file to review, as well as the settings that were in effect at the time of the import.
## What happens to existing in-market associations if an audience becomes available in Microsoft Advertising?
When a Google Ads audience becomes available in Microsoft Advertising, we will update its associations automatically when you re-import. For example, let’s say you have an ad group in Google Ads associated with the audience “Apparel &amp; Accessories/Bow ties.” Since “Bow ties” is an audience not yet supported by Bing, its associations will be mapped to its parent audience, “Apparel &amp; Accessories.” However, when “Bow ties” becomes available, Microsoft Advertising will delete the existing association, “Apparel &amp; Accessories” and create a new association, “Apparel &amp; Accessories/ Bow ties.”
## How do I associate a UET tag?
A Universal Event Tracking (UET) tag records what customers do on your website and sends that information to Microsoft Advertising. If you’re importing remarketing lists or other audiences, you’ll need to associate a specific UET tag with each. If you don’t have a UET tag in Microsoft Advertising yet, we will create one for you if you select this option.

1. When customizing import options, under UET tag, select **Associate the following UET tag with any remarketing list, audience, or conversion goal that has not previously imported into Microsoft Advertising**.
1. Select an existing UET tag or create a new tag.
1. If you are creating a tag, enter the **Tag name** and **Tag description**.

> [!NOTE]
> Campaign-level associations will only be imported for search network campaigns.
> If any ad group-level associations already exists for a particular campaign in Microsoft Advertising, its campaign-level associations will not be imported from Google Ads.

## Bids and budgets
> [!IMPORTANT]
> Please note that the import option **Update bids and bid strategies** is now split into **Update bids** and **Update bid strategies**. Even with this change, your original bid settings will remain the same. You can review the **Bids and budgets** section of your import options to customize your settings at anytime.

Both Microsoft Advertising and Google Ads offer you the ability to limit your campaign spend on a daily basis.

Microsoft Advertising has different minimum bid and budget requirements than Google Ads. To help you import all of your data quickly, any bids or budgets that are too low will be raised to meet our minimums. These minimums can be found in the table below. Keep in the mind that while you can opt out of these increases during the import setup, the campaigns that don’t meet these minimums won’t get imported.

## Minimum bids and budgets

|Currency|Search campaignminimum bid|Shopping campaignminimum bid|Search and shopping campaignsminimum daily budget|
|---|---|---|---|
|Argentine Peso (ARS)|0.05|0.05|0.05|
|Australian Dollar (AUD)|0.01|0.01|0.05|
|Thai Baht (THB)|0.14|0.14|2.00|
|Brazilian real (BRL)|0.01|0.01|0.10|
|Canadian dollar (CAD)|0.05|0.01|0.05|
|Chilean peso (CLP)|5.10|5.10|5.10|
|Colombian peso (COP)|18.05|18.05|18.05|
|Danish krone (DKK)|0.06|0.06|0.06|
|Euro (EUR)|0.05|0.01 (France, Germany, Spain, Switzerland, Austria, Belgium, Netherlands, Italy, and Sweden only)|0.05|
|Hong Kong dollar (HKD)|1.00|1.00|1.00|
|Indian rupee (INR)|0.50|0.01|0.82|
|Indonesian rupiah (IDR)|35.00|35.00|480.00|
|Malaysian ringgit (MYR)|0.01|0.01|0.15|
|Mexican peso (MXN)|0.14|0.14|0.14|
|New Taiwan dollar (TWD)|0.01|0.01|100.00|
|New Zealand dollar (NZD)|0.01|0.01|0.05|
|Norwegian krone (NOK)|0.06|0.06|0.06|
|Peruvian nuevo sol (PEN)|0.03|0.03|0.03|
|Philippine peso (PHP)|0.20|0.20|2.00|
|Polish Zloty (PLN)|0.01|0.01|0.10|
|Pound sterling (GBP)|0.05|0.01|0.05|
|Singapore dollar (SGD)|0.01|0.01|0.11|
|Swedish krona (SEK)|0.07|0.07|0.07|
|Swiss franc (CHF)|0.05|0.05|0.05|
|South African Rand (ZAR)|0.01|0.01|0.10|
|Turkish Lira (TRY)|1|1|10|
|U.S. dollar (USD)|0.05|0.01|0.05|

## Currency mismatch

If the currencies you set for your Google Ads and Microsoft Advertising account do not match, you can either convert your currency data to match Microsoft Advertising, or opt out. If you choose to opt out, you can manually adjust your bids and budgets using the import options or after your import is complete. If you set up an account and need to [change the currency](./hlp_BA_CONC_Currency.md), you will need to set up a new account. If you have campaigns, ad groups, ads, and settings in the old account, then you will want to export them from the old account and import them into the new one.

## Bid strategies
> [!IMPORTANT]
> Please note that the import option **Update bids and bid strategies** is now split into **Update bids** and **Update bid strategies**. All new and scheduled imports have the **Update bid strategies** option enabled by default. To opt out, uncheck **Update bid strategies** under **Bids and budgets** in your import options.

Some bid strategies are not supported in Microsoft Advertising. For unsupported bid strategies, your campaign bid strategy will be set to Enhanced CPC and bids will be set to an amount we recommend. Please note that you can update these bids after you import them to Microsoft Advertising.

## Device targeting
> [!NOTE]
> Please note that the import option **Do not import negative bid modifier for desktop (except -100%)** is only available to customers using the new simplified import worflow.

Without the simplified import workflow we will import all of your negative bid modifiers from Google Ads. With the simplified import worflow if you don't choose customizations we will not import negative bid modifiers for desktop targets (except modifiers set to -100%). Using -100% effectively opts you out of displaying your ads on desktops. You can choose customizations to change the default option and import negative bid modifiers.

## Dynamic search ads
> [!NOTE]
> This feature is currently available in Australia, Austria, Belgium, Canada, Denmark, Finland, France, Germany, Ireland, Italy, Netherlands, New Zealand, Norway, Spain, Sweden, Switzerland, United Kingdom, and United States.

[Dynamic search ads](./hlp_BA_CONC_DynamicSearchAds.md) provide a streamlined, low-touch way to make sure customers searching on the Microsoft Search Network find your products or services.

Mixed mode campaigns from Google Ads are campaigns that contain both dynamic search ads and other types (e.g., Expanded Text Ads). If you’re in a market where dynamic search ads are not yet supported by Microsoft Advertising we will only import other ad types into **Standard** ad groups. Once dynamic search ads are available in your market, we will import dynamic search ads into **Dynamic** ad groups and other ad types into **Standard** ad groups. Both ad group types will be created in search campaigns.

If you import dynamic search ads containing display URL paths that exceed 15 characters, the paths will be dropped. The rest of the ad, including the URL without the excessive paths, will stay the same.

## Language targeting
## Campaign and ad group languages

Targeting multiple languages allows you to have different ad groups in the same campaign show ads on websites in different languages. During an import, campaign languages are set to the Google Ads’ target languages that we support and ad group languages are automatically set to **Use the campaign settings**.

Microsoft Advertising supports the following ad languages:

[!INCLUDE [AvailableAdLanguages](./includes/AvailableAdLanguages.md)]
If you’d like to opt out of target language updates during a re-import, simply uncheck **Campaign and ad group languages** in your import options.  Please note that if you import target languages from Google Ads but your Microsoft Advertising campaigns don’t have any, all supported targeted languages will still be imported regardless of whether or not you opted out of target language updates. If we don't support any of the targeted languages you imported from Google Ads, your campaign will not import and be flagged with the error message: “Unsupported target languages.”

## Location targeting
When you import your Google Ads campaigns, we take the imported location targets and automatically match them to the same location targets in Microsoft Advertising. However, there may be location targets (such as smaller cities) in Google Ads that we don't support. When this happens, we automatically expand the target so that it can be mapped to a nearby locale (such as a state, region, or a province) per Google Ads geographic data. If both the focused and expanded location targets are unsupported by Microsoft Advertising, neither will be imported.

For example, let’s say you have a campaign in Google Ads whose location target is set to an unsupported city A in the state/region/province B. In this scenario, we will automatically map it to the supported parent location, state/region/province B. If both city A and state/region/province B are unsupported by Microsoft Advertising, neither location targets will be imported.

## Opt out of expanding your location targets

1. Click **Import Campaigns** at the top of the page.
1. Select **Import from Google Ads**.
1. Click **Sign into Google**.
1. Select the Google Ads campaign you want to import, then click **Continue**.
1. Under **Choose Import Options**, select **Do not expand unsupported location targets**.

Please note that by selecting this option, unsupported location targets will not be imported, however, your campaigns will continue to serve worldwide without location targeting.

## Pause campaigns containing only unsupported location targets immediately after importing

1. Click **Import Campaigns** at the top of the page.
1. Select **Import from Google Ads**.
1. Click **Sign into Google**.
1. Select the Google Ads campaign you want to import, then click **Continue**.
1. Under **Choose Import Options**, select **Pause campaigns when all imported location targets are unsupported**.

Please note that if you select this option, and a campaign contains both supported **and** unsupported location targets, the campaign will not be paused, and supported location targets will continue to serve.

## Review your imported location targets

You can review all your imported location targets in the Import Summary, including which unsupported location targets were mapped to a supported parent location. If you have any items with issues from importing, you can download your import errors to a spreadsheet. Each unsupported location target that gets mapped to a parent location target will be indicated with a warning in the downloaded spreadsheet. You can then decide to keep the supported location target, update the location target, or delete it all together.
## Negative keyword lists
You can use negative keywords or keyword phrases to help prevent your ad from being displayed when a search query or other input contains your keywords but is irrelevant to your landing page content. With a shared negative keyword list, you can apply entire lists of negative keywords to multiple campaigns and make changes across campaigns by editing a single list. When the checkbox next to **Negative keyword list** under **Choose Import Options** is selected, the following will occur:
- All negative keyword lists from Google Ads will be imported. Negative keyword lists with identical names in Microsoft Advertising will be updated.
- Negative keywords from both Microsoft Advertising and Google Ads will be merged.
- Microsoft Advertising associations will be overwritten by any current Google Ads associations.

## Shopping campaigns
Before you import your Google shopping campaigns into Microsoft Advertising Shopping Campaigns, make sure to create a Microsoft Merchant Center store. Then, when you import, you must link your store to the incoming shopping campaign.

If you will be using an existing Google catalog, make sure the catalog has valid data in the **Country of sale** field. Microsoft Advertising supports the following countries for this field:
- Australia
- Austria
- Belgium
- Canada
- Denmark
- Finland
- France
- Germany
- India
- Ireland
- Italy
- Netherlands
- Norway
- Spain
- Switzerland
- Sweden
- United Kingdom
- United States

## URL Tracking
URL tracking allows you to find out how people got to your website by adding tracking parameters in Microsoft Advertising and then using a third-party tracking tool or service to analyze the data. You should check tracking templates, custom parameters, final URL suffix, utm_source, and other settings to ensure accurate reporting.

If your Google Ads campaign uses the utm_source parameter, the value for that parameter is likely "Google," "GoogleAds," or a close variant such as "googleshopping" or "GoogleAdsIndia." These values will be replaced by "bing." For example, **http://www.example.com/?utm_source=google** will be imported as **http://www.example.com/?utm_source=bing**.

## Items that can’t be imported but can be re-created using Microsoft Advertising

- Account-level App Extensions
- Ad group-level App Extensions
- Automated rules
- IP exclusions

> [!NOTE]
> You can now import from Google Ads:
> - 20 thousand campaigns
> - 10 million ad groups
> - 20 million keywords
> - 20 million ads
> - 5.5 million ad group-level and campaign-level negative keywords combined
> - 10 million ad group product partitions
> - 200,000 all other entities combined
> - 3 million targets

## Detailed list of imported and updated items

Whether this is your first time or you’re re-importing an existing campaign, it’s important to keep track of all the items that are either transferred or updated, and which ones are simply left untouched. To make it easier for you,  please refer to the list below to see which items get brought over during your initial import as well as which items Microsoft Advertising updates when you repeat the process.

> [!NOTE]
> Please note that the list below is not a comprehensive list of imported items. Microsoft Advertising imports all the data needed to manage your campaigns and aims to provide the best experience for you.

## Main entities imported and updated for search campaigns

## Campaigns
|Items|Imported from Google Ads|Updated during re-import|
|---|---|---|
|Campaign name: Campaign names in Microsoft Advertising are not case-sensitive. If you import or re-import campaigns named “Coffee Sales” and “coffee sales” from Google Ads, you will see an error for a duplicate campaign name. However, if you import a campaign named “Coffee Sales” under an account that already contains a campaign named “coffee sales”, we recognize them as the same, and will update accordingly.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Campaign labels|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Budget amount|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Budget type|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Bid strategy:              Some bid strategies are not supported in Microsoft Advertising. For unsupported bid strategies, your campaign bid strategy will be set to Enhanced CPC and bids will be set to an amount we recommend. Please note that you can update these bids after you import them to Microsoft Advertising.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Start/End date: Please note that Google Ads supports start and end dates at the campaign-level, while Microsoft Advertising supports them only at the ad group-level.  That means that the imported campaign level date range will override the existing ad group date range in Microsoft Advertising. Also note that if the end date has passed for a campaign that you import, the end date for ad groups in the campaign will be set to January 1, 2050.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Status|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Tracking template|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Custom parameters|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Time zone:              When you import a campaign for the first time, the time zone at account-level is used. After that, the time zone doesn’t change.|![green check mark](../images/Global_Icon_CheckMark.png)||
|Campaign type|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Sales country|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|

> [!NOTE]
> Ad group and campaign updates are fetched from previous imports to match those currently in Google Ads. If these items were created by a Microsoft Advertising online import after March 21, 2016, their updates will be fetched. Ad groups and campaigns imported previous to that date will not be updated. Instead, new or duplicative items may be created.
> If ad groups and campaigns were created during an import using Microsoft Advertising Editor Version 11.25 and beyond, their updates will be fetched. Please note that items downloaded locally or imported using a previous version of Microsoft Advertising Editor will not be updated. Instead, new or duplicative items may be created.
> If a Google Ads campaign name matches an existing Microsoft Advertising campaign name, the two will be merged during an import.

## Ad groups
<table>
  <tr>
    <th style="width:220px" scope="col">
              Items
            </th>
    <th style="width:220px" scope="col">
              Imported from Google Ads
            </th>
    <th style="width:220px" scope="col">
              Updated during re-import
            </th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Ad group name: Ad group names in Microsoft Advertising are not case-sensitive. If you import or re-import ad groups named “Coffee Sales” and “coffee sales” from Google Ads, you will see an error for a duplicate ad group name. However, if you import a campaign named “Coffee Sales” under a campaign that already contains an ad group named “coffee sales”, we recognize them as the same, and will update accordingly.
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Ad group labels
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Status
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Start/End date: Please note that Google Ads supports start and end dates at the campaign-level, while Microsoft Advertising supports them only at the ad group-level.  That means that the imported campaign level date range will override the existing ad group date range in Microsoft Advertising. Also note that if the end date has passed for a campaign that you import, the end date for ad groups in the campaign will be set to January 1, 2050.
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Medium (ad distribution): Ad distribution is where you want your ads to show. When a Google Ads ad group is imported, it is mapped in the following ways:

              <ul><li>
                  If the network is the <strong>Search and Display Network</strong>, we set it to <strong>Search</strong>.
                </li><li>
                  If the network is the <strong>Display Network</strong>, we do not import it.
                </li><li>
                  If the network is the <strong>Google Search Network</strong>, we set it to <strong>Search</strong>.
                </li></ul></th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Bid strategy: Ad groups will use the campaign’s bid strategy. If the ad group is explicitly set to Manual CPC, then it will be imported with Manual CPC.
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Pricing model
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Ad rotation: Flattened from Google Ads campaign.
              <ul><li>Optimize For Clicks and Optimize for Conversions is mapped to Optimized For Clicks.</li><li>Rotate evenly and Rotate indefinitely is mapped to Rotate Evenly.</li><li>Start and End date are not imported.</li></ul></th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <td>
              Bid
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Language: Flattened from Google Ads campaign. If there are multiple languages, we select the one with the maximum market share.
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Native bid adjustment
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Tracking template
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Custom parameters
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
</table>

> [!NOTE]
> Ad group and campaign updates are fetched from previous imports to match those currently in Google Ads. If these items were created by a Microsoft Advertising online import after March 21, 2016, their updates will be fetched. Ad groups and campaigns imported previous to that date will not be updated. Instead, new or duplicative items may be created.
> If ad groups and campaigns were created during an import using Microsoft Advertising Editor Version 11.25 and beyond, their updates will be fetched. Please note that items downloaded locally or imported using a previous version of Microsoft Advertising Editor will not be updated. Ad groups and campaigns imported using a previous version will not be updated. Instead, new or duplicative items may be created.
> If a Google Ads campaign name matches an existing Microsoft Advertising campaign name, the two will be merged during an import.

## Keywords
|Items|Imported from Google Ads|Updated during re-import|
|---|---|---|
|Keyword text|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Match type: When you import a campaign for the first time, the match type is imported. After that, the match type is not updated.|![green check mark](../images/Global_Icon_CheckMark.png)||
|Bid|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Bid strategy: Keywords will use the ad group’s bid strategy. If the keyword is explicitly set to Manual CPC, then it will be imported with Manual CPC.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Status|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Param1|![green check mark](../images/Global_Icon_CheckMark.png)||
|Param2|![green check mark](../images/Global_Icon_CheckMark.png)||
|Param3|![green check mark](../images/Global_Icon_CheckMark.png)||
|Final URL|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Final mobile URL|![green check mark](../images/Global_Icon_CheckMark.png)||
|Tracking template|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Custom parameters|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|

## Standard text ads
> [!NOTE]
> Microsoft Advertising no longer supports importing standard text ads from Google Ads. However, if you imported standard text ads before August 3rd, 2017 and choose to re-import them, we will import status changes (Pause/Unpause) from Google Ads.

## Expanded Text Ads
|Items|Imported from Google Ads|Updated during re-import|
|---|---|---|
|Title part 1: Microsoft Advertising and Google Ads allow 30 characters. Google Ads calls this headline 1.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Title part 2: Microsoft Advertising and Google Ads allow 30 characters. Google Ads calls this headline 2.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Title part 3: Microsoft Advertising and Google Ads allow 30 characters. Google Ads calls this headline 3.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Description: Microsoft Advertising and Google Ads allow 90 characters.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Description 2: Microsoft Advertising and Google Ads allow 90 characters.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Path 1: Microsoft Advertising and Google Ads allow 15 characters.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Path 2: Microsoft Advertising and Google Ads allow 15 characters.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|URL custom parameters|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Tracking template|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Final URL: Microsoft Advertising has a 35-character maximum limit for the host in URL. For example, if the URL is http://www.edu.bing.co.uk/pages/one, then the host is www.edu.bing.co.uk and it can’t be more than 35 characters. Google Ads allows more than 35 characters for the host in URL.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Ad labels|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|

> [!NOTE]
> If Expanded Text Ads missing from your import, be sure to select **Ad customizer feeds** under the **Feeds** section of your import options. Then try your import again.

## Product ads
|Items|Imported from Google Ads|Updated during re-import|
|---|---|---|
|Status|![green check mark](../images/Global_Icon_CheckMark.png)||
|Promotion|![green check mark](../images/Global_Icon_CheckMark.png)||
|Ad labels|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|

## Responsive search ads
|Items|Imported from Google Ads|Updated during re-import|
|---|---|---|
|Final URL: Microsoft Advertising has a 35-character maximum limit for the host in URL. For example, if the URL is http://www.edu.bing.co.uk/pages/one, then the host is www.edu.bing.co.uk and it can’t be more than 35 characters. Google Ads allows more than 35 characters for the host in URL.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Headlines|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Path: Microsoft Advertising and Google Ads allow 15 characters.|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Descriptions|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Mobile URL|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Tracking template|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Final URL suffix|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Custom parameters|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|

> [!NOTE]
> Please note there is a limit of three enabled responsive search ads per ad group. If you’re having trouble importing responsive search ads from Google Ads:
> - Manually pause or delete old responsive search ads to make room for other enabled ones.
> - Choose **Delete items that have been removed from your Google Ads** account in your [import options](./hlp_BA_PROC_ImportCampaign.md).

[Learn more about responsive search ads](./hlp_BA_CONC_ResponsiveSearchAds.md).
## Labels
|Items|Imported from Google Ads|Updated during re-import|
|---|---|---|
|Label name|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Label color|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|
|Label description|![green check mark](../images/Global_Icon_CheckMark.png)|![green check mark](../images/Global_Icon_CheckMark.png)|

Choosing the appropriate import options can determine which items get imported to Microsoft Advertising for the first time, updated from a previous import, or left untouched. Below, you can review both your import goals and the options you must choose to achieve them.

|What is your import goal?|What import options should I choose?|
|---|---|
|Import new labels and update existing ones.|Check **Labels** under both **Items not previously imported into Microsoft Advertising** and **Updates to existing items**.|
|Import new labels and ignore updating existing ones.|Check **Labels** under **Items not previously imported into Microsoft Advertising**. Uncheck **Labels** under **Updates to existing items**.|
|Ignore new labels and import updates to existing ones.|Check **Labels** under **Updates to existing items**. Uncheck **Labels** under **Items not previously imported into Microsoft Advertising**.|
|Ignore both new labels and updates to existing ones.|Uncheck **Labels** under both **Items not previously imported into Microsoft Advertising** and **Updates to existing items**.|

> [!NOTE]
> Please note that if you’ve removed labels in Google Ads and then select **Labels** under **Updates to existing items**, those labels will be deleted during the import.

## Ad extensions imported for search campaigns

## Campaign-level Call Extensions
- Campaign name
- Phone number
- Country code
- Is call only
- Is call tracking enabled
- Require toll free tracking number
- Device preference
- Start date
- End date
- Schedule

## Campaign-level Callout Extensions
- Campaign name
- Text
- Start date
- End date
- Schedule

## Campaign-level Location Extensions
- Campaign name
- Company name
- Street address
- Street address2
- City name
- Province code
- Postal code
- Country code
- Phone number
- Latitude
- Longitude
- Map icon:             We set to empty string during import.
- Start date
- End date
- Schedule

## Campaign-level Price Extensions
- Campaign name
- Price feed type
- Price qualifier
- Language
- Currency
- Item headers: Up to the first 8 are imported.
- Item descriptions: Up to first 8 are imported.
- Item prices: Up to the first 8 are imported.
- Item final URLs: Up to first 8 are imported.
- Item final mobile URLs: Up to the first 8 are imported.
- Custom parameters
- Start date
- End date
- Schedule

## Campaign-level Sitelink Extensions
- Campaign name
- Display text
- Description1
- Description2
- Device preference
- Final URL
- Mobile final URL
- Tracking template
- Custom parameters: Up to the first 3 are imported.
- Start date
- End date
- Schedule

## Campaign-level Structured Snippet Extensions
- Campaign name
- Header
- Values
- Start date
- End date
- Schedule

## Ad group-level Callout Extensions
- Campaign name
- Ad group name
- Text
- Start date
- End date
- Schedule

## Ad group-level Sitelink Extensions
- Campaign name
- Ad group name
- Display text
- Description1
- Description2
- Device preference
- Final URL
- Mobile final URL
- Tracking template
- Custom parameters
- Start date
- End date
- Schedule

## Ad group-level Structured Snippet Extensions
- Campaign name
- Ad group name
- Header
- Values
- Start date
- End date
- Schedule

Choosing the appropriate import options can determine which items get imported to Microsoft Advertising for the first time, updated from a previous import, or left untouched. Below, you can review both your import goals and the options you must choose to achieve them.

|What is your import goal?|What import options should I choose?|
|---|---|
|Import new ad extensions and update existing ones.|Check **Ad extensions** under both **Items not previously imported into Microsoft Advertising** and **Updates to existing items**.|
|Import new ad extensions and ignore updating existing ones.|Check **Ad extensions** under **Items not previously imported into Microsoft Advertising**. Uncheck **Ad extensions** under **Updates to existing items**.|
|Ignore new ad extensions and import updates to existing ones.|Check **Ad extensions** under **Updates to existing items**. Uncheck **Ad extensions** under **Items not previously imported into Microsoft Advertising**.|
|Ignore both ad extensions and updates to existing ones.|Uncheck **Ad extensions** under both **Items not previously imported into Microsoft Advertising** and **Updates to existing items**.|

> [!NOTE]
> Please note that a schedule update in Google Ads is treated the same as deleting the previous schedule and adding a new schedule. If you select ad extensions under **Updates to existing items**, and if any schedules were updated or removed in Google Ads, then those schedules will be deleted from Microsoft Advertising during the import.
> Please note that during an import, ad extensions removed in Google Ads will not be deleted in Microsoft Advertising during import.

## Targeting and exclusions imported for campaigns

## Campaign ad scheduling
- From hour
- From minutes
- To hour
- To minutes
- Bid adjustment:              On Par Range: -90% to +900%

## Campaign and ad group negative keywords
- Match type:             Broad match will be imported as phase match.
- Keyword text

## Campaign and ad group website exclusions
- Campaign placement exclusions:             To import campaign placement exclusions from Google Ads select **Website exclusions** in your **Advanced Import Options**.

## Campaign location targets
- Location:             If Google Ads location can't be mapped, we use the parent location and show a warning during import. If there is no parent location, an error will appear during import.
- Bid adjustment

## Campaign device targets
Mobile and tablet
- Bid adjustment:              Google Ads allows -100% to +900%. Microsoft Advertising allows -100% to +900% and -100% means opt out.

## Campaign negative location targets
- Location             If Google Ads location can't be mapped, an error message will appear during import.

## Campaign radius targets
- Radius location

Choosing the appropriate import options can determine which items get imported to Microsoft Advertising for the first time, updated from a previous import, or left untouched. Below, you can review both your import goals and the options you must choose to achieve them.

|What is your import goal?|What import options should I choose?|
|---|---|
|Import new campaign and ad group targets and update existing ones.|Check **Targeting** under both **Items not previously imported into Microsoft Advertising** and **Updates to existing items**.|
|Import new campaign and ad group targets and ignore updating existing ones.|Check **Targeting** under **Items not previously imported into Microsoft Advertising**. Uncheck **Targeting** under **Updates to existing items**.|
|Ignore new campaign and ad group targets and import updates to existing ones.|Check **Targeting** under **Updates to existing items**. Uncheck   **Targeting** under **Items not previously imported into Microsoft Advertising**.|
|Ignore both new campaign and ad group targets and updates to existing ones.|Uncheck **Targeting** under both **Items not previously imported into Microsoft Advertising** and **Updates to existing items**.|

> [!NOTE]
> Please note that an update in Google Ads is treated as deleting the previous target and adding a new target. If you select **Targeting** under **Updates to existing items**, and if the targets were updated or removed in Google Ads, then those targets will be deleted from Microsoft Advertising during the import.

## Main entities imported for Microsoft Shopping Campaigns

## Ad group product partitions
- Campaign name
- Ad group name
- Status
- Is excluded
- Parent node Id
- Product condition
- Product value
- Bid
- Tracking template
- Custom parameters

## Product scope campaign criterion
- Campaign name
- Product condition 1
- Product value 1
- Product condition 2
- Product value 2
- Product condition 3
- Product value 3
- Product condition 4
- Product value 4
- Product condition 5
- Product value 5
- Product condition 6
- Product value 6
- Product condition 7
- Product value 7


