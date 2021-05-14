---
title: What gets imported from Google Ads?
description: Most of the information in your campaigns is included when you import it from Google Ads. Here's a list of what gets imported, as well as some exceptions.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What gets imported from Google Ads?

Now that you’ve imported your campaigns from Google Ads, you can check the status of your import, review error logs, and edit, pause, or delete your import schedule. Keep in mind that not all information will be imported, but that doesn’t mean it’s not supported within Microsoft Advertising. So, after you import, be sure to review your campaigns to make sure everything is good to go and add the missing information back to your campaigns.

## Items you should check after import

Some specific situations require special attention during import. If you are importing any of the items below, make sure to review the following information.

## Ad distribution (Network)
Ad distribution is where you want your ads to show. When a Google Ads ad group is imported, it is mapped in the following ways:

- If the network is the **Search and Display Network**, we set it to **Search**.
- If the network is the **Google Search Network**, we set it to **Search**.

> [!NOTE]
> If the network is the **Google Search Network**, and **Include search partners** is selected, then Bing will target all search networks. (Bing, AOL, and Yahoo search and syndicated search partners)
> Syndicated search is only available in certain countries.
> Microsoft Advertising stopped serving ads on the content network.

## Age and gender targeting
By importing your age and gender targeting, you can reach customers who’re likely to be within the demographic range you choose. Microsoft Advertising matches most of your Google Ads age and gender targets, however, there are a few differences that you can review in the tables below.

<table>
  <tr>
    <th style="width:300px" scope="col">
            Google Ads age groups
          </th>
    <th style="width:450px" scope="col">
            Microsoft Advertising age groups
          </th>
  </tr>
  <tr>
    <td>
            18-24
          </td>
    <td style="text-align:left">
            18-24
          </td>
  </tr>
  <tr>
    <td>
           25-34
          </td>
    <td style="text-align:left">
           25-34
          </td>
  </tr>
  <tr>
    <td>
            35-44
          </td>
    <td style="text-align:left">
           35-49
          </td>
  </tr>
  <tr>
    <td>
           55-64
          </td>
    <td style="text-align:left">
           50-64
          </td>
  </tr>
  <tr>
    <td>
            65+
          </td>
    <td style="text-align:left">
           65+
          </td>
  </tr>
  <tr>
    <td>
            Unknown
          </td>
    <td style="text-align:left">
            Not imported
          </td>
  </tr>
</table>

<table>
  <tr>
    <th style="width:300px" scope="col">
            Google Ads gender groups
          </th>
    <th style="width:450px" scope="col">
            Microsoft Advertising gender groups
          </th>
  </tr>
  <tr>
    <td>
            Male
          </td>
    <td style="text-align:left">
            Male
          </td>
  </tr>
  <tr>
    <td>
            Female
          </td>
    <td style="text-align:left">
            Female
          </td>
  </tr>
  <tr>
    <td>
            Unknown
          </td>
    <td style="text-align:left">
            Not imported
          </td>
  </tr>
</table>

> [!IMPORTANT]
> The Google Ads age group of 45-54 will not be imported into Microsoft Advertising.

## Audience targeting
Audiences are groups of potential customers that you can target. By importing your audiences from Google Ads, you can boost your campaign performance by reaching people browsing your website through Bing.

## Audience targeting: FAQ

## Which audience types can I import from Google Ads?
> [!NOTE]
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
    <th style="width:220px" scope="col">
                    More details
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
    <td style="text-align:left">
                    N/A
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
    <td style="text-align:left">
                    N/A
                  </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
                    Custom combination lists:
                  </th>
    <td style="text-align:left">
                    Lists that use AND, OR, and NOT conditions
                  </td>
    <td style="text-align:left">
                    Lists that only use the NOT condition
                  </td>
    <td style="text-align:left">
                    Not everyone has this feature yet.
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
    <td style="text-align:left">
                    N/A
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
    <td style="text-align:left">
                    N/A
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
    <td style="text-align:left">
                    N/A
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
                      </li></ul></td>
    <td style="text-align:left">
      <ul>
        <li>
                        Any membership duration that is greater than 180 days will be lowered to 180 days during import.
                      </li>
        <li>
                        Not everyone has this feature yet.
                      </li>
      </ul>
    </td>
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
    <td style="text-align:left">
                    N/A
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
> [!IMPORTANT]
> Not everyone has this feature yet. If you don't, don't worry—it's coming soon!

A Universal Event Tracking (UET) tag records what customers do on your website and sends that information to Microsoft Advertising. If you’re importing remarketing lists or audiences, you’ll need to associate a specific UET tag with each. If you don’t have a UET tag in Microsoft Advertising yet, we will create one for you if you select this option.

1. At the top of the page, click **Import Campaigns** and then click **                    Import from Google Ads                  ** (or from the global menu at the top of the page, click **Import** and then click **                    Import from Google Ads                  **).
1. If you have imported from Google Ads in the past 90 days, you will see a table that shows you the **Date/Time** and                  **                    Google Ads account                  ** that was imported along with:
<table>
  <tr>
    <th scope="col">Column Name</th>
    <th scope="col">Description</th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Summary</th>
    <td>
                        Shows how many entities were imported successfully and how many had errors. Click the ellipsis ![ellipse](../images/BA_ScreenCap_DeliveryDetails.png) to see details.
                      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Actions</th>
    <td>If you had errors, you will see a link to download the error file which you can review.</td>
  </tr>
</table>

1. Click **Sign in to Google**.
1. Enter your Google Ads sign-in information, click **Sign in**. If you’re having trouble signing in to Google Ads:
- Clear your browser's cache and cookies.
- Try another browser.
- [Contact support](https://go.microsoft.com/fwlink?LinkId=398371).

1. Select if you want to import all existing and new campaigns from your Google Ads account or specific campaigns and ad groups in that account. Then click **Continue**.
If the currencies you set for your Google Ads and Microsoft Advertising account do not match, you can either convert your currency data to match Microsoft Advertising or opt out. If you choose to opt out, you can manually adjust your bids and budgets using the import options or after your import is complete.

1. Under **Choose Import Options**, do the following:
  - Under **What gets imported**, check **UET tags**.
  - Select either the remarketing list or audience you want to associate your UET tag to.
  - Choose the appropriate options for **What to import**, **Bids and budgets**, and **Other options**.
  - You can delete items that have been removed from your Google Ads account by clicking **What to import** and selecting **Delete items that have been removed from your Google Ads account**. Please note that removed Google Ads items will be deleted along with their associated sub-items. For example, if you previously removed a Google Ads campaign, its ads groups, ads, and keywords will also be deleted during this import. Ad extensions removed in Google Ads will not be deleted in Microsoft Advertising during this import.

1. Optional: Under **Schedule Imports**, click **When** and then set the schedule you want, which can be **Once**, **Daily**, **Weekly**, or **Monthly**.
1. Click **Import** or if you want to set a schedule, click **Schedule**.

> [!NOTE]
> Campaign-level associations will only be imported for search network campaigns.
> If any ad group-level associations already exists for a particular campaign in Microsoft Advertising, its campaign-level associations will not be imported from Google Ads.

## Bids and budgets
> [!IMPORTANT]
> Please note that the import option **Update bids and bid strategies** is now split into **Update bids** and **Update bid strategies**. Even with this change, your original bid settings will remain the same. You can review the **Bids and budgets** section of your import options to customize your settings at anytime.

Both Microsoft Advertising and Google Ads offer you the ability to limit your campaign spend on a daily basis.

Microsoft Advertising has different minimum bid and budget requirements than Google Ads. To help you import all of your data quickly, any bids or budgets that are too low will be raised to meet our minimums. These minimums can be found in the table below. Keep in the mind that while you can opt out of these increases during the import setup, the campaigns that don’t meet these minimums won’t get imported.

## Minimum bids and budgets

<table>
  <tr>
    <th style="width:450px" scope="col">
              Currency
            </th>
    <th style="width:300px" scope="col">
              Search campaign
              <para>
                minimum bid
              </para></th>
    <th style="width:300px" scope="col">
              Shopping campaign
              <para>
                minimum bid
              </para></th>
    <th style="width:300px" scope="col">
              Search and shopping campaigns
              <para>
                minimum budget
              </para></th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Argentine Peso (ARS)
            </th>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Australian Dollar (AUD)
            </th>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Thai Baht (THB)
            </th>
    <td style="text-align:left">
              0.14
            </td>
    <td style="text-align:left">
              0.14
            </td>
    <td style="text-align:left">
              2.00
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Brazilian real (BRL)
            </th>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.10
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Canadian dollar (CAD)
            </th>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Chilean peso (CLP)
            </th>
    <td style="text-align:left">
              5.10
            </td>
    <td style="text-align:left">
              5.10
            </td>
    <td style="text-align:left">
              5.10
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Colombian peso (COP)
            </th>
    <td style="text-align:left">
              18.05
            </td>
    <td style="text-align:left">
              18.05
            </td>
    <td style="text-align:left">
              18.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Danish krone (DKK)
            </th>
    <td style="text-align:left">
              0.06
            </td>
    <td style="text-align:left">
              0.06
            </td>
    <td style="text-align:left">
              0.06
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Euro (EUR)
            </th>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.01 (France, Germany, Spain, Switzerland, Austria, Belgium, Netherlands, Italy, and Sweden only)
            </td>
    <td style="text-align:left">
              0.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Hong Kong dollar (HKD)
            </th>
    <td style="text-align:left">
              1.00
            </td>
    <td style="text-align:left">
              1.00
            </td>
    <td style="text-align:left">
              1.00
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Indian rupee (INR)
            </th>
    <td style="text-align:left">
              0.50
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.82
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Malaysian ringgit (MYR)
            </th>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.15
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Mexican peso (MXN)
            </th>
    <td style="text-align:left">
              0.14
            </td>
    <td style="text-align:left">
              0.14
            </td>
    <td style="text-align:left">
              0.14
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              New Taiwan dollar (TWD)
            </th>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              100.00
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              New Zealand dollar (NZD)
            </th>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Norwegian krone (NOK)
            </th>
    <td style="text-align:left">
              0.06
            </td>
    <td style="text-align:left">
              0.06
            </td>
    <td style="text-align:left">
              0.06
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Peruvian nuevo sol (PEN)
            </th>
    <td style="text-align:left">
              0.03
            </td>
    <td style="text-align:left">
              0.03
            </td>
    <td style="text-align:left">
              0.03
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Philippine peso (PHP)
            </th>
    <td style="text-align:left">
              0.20
            </td>
    <td style="text-align:left">
              0.20
            </td>
    <td style="text-align:left">
              2.00
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Indonesian rupiah (IDR)
            </th>
    <td style="text-align:left">
              35.00
            </td>
    <td style="text-align:left">
              35.00
            </td>
    <td style="text-align:left">
              480.00
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Singapore dollar (SGD)
            </th>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.11
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Swedish krona (SEK)
            </th>
    <td style="text-align:left">
              0.07
            </td>
    <td style="text-align:left">
              0.07
            </td>
    <td style="text-align:left">
              0.07
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Swiss franc (CHF)
            </th>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Pound sterling (GBP)
            </th>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
              0.05
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              U.S. dollar (USD)
            </th>
    <td style="text-align:left">
              0.05
            </td>
    <td style="text-align:left">
              0.01
            </td>
    <td style="text-align:left">
            0.05
          </td>
  </tr>
</table>

## Currency mismatch

If the currencies you set for your Google Ads and Microsoft Advertising account do not match, you can either convert your currency data to match Microsoft Advertising, or opt out. If you choose to opt out, you can manually adjust your bids and budgets using the import options or after your import is complete. If you set up an account and need to change the currency, you will need to set up a new account. If you have campaigns, ad groups, ads, and settings in the old account, then you will want to export them from the old account and import them into the new one.

## Bid strategies
> [!IMPORTANT]
> Please note that the import option **Update bids and bid strategies** is now split into **Update bids** and **Update bid strategies**. All new and scheduled imports have the **Update bid strategies** option enabled by default. To opt out, uncheck **Update bid strategies** under **Bids and budgets** in your import options.

Some bid strategies are not supported in Microsoft Advertising. For unsupported bid strategies, your campaign bid strategy will be set to Enhanced CPC and bids will be set to an amount we recommend. Please note that you can update these bids after you import them to Microsoft Advertising.

## Dynamic search ads
> [!IMPORTANT]
> This feature is currently available in Australia, Canada, France, Germany, the United Kingdom, and the United States.

Dynamic search ads provide a streamlined, low-touch way to make sure customers searching on the Microsoft Search Network find your products or services.

## Mixed mode campaigns

Mixed mode campaigns from Google Ads are campaigns that contain both dynamic search ads and other types (e.g., Expanded Text Ads). Since mixed mode campaigns are not supported in Microsoft Advertising at this time, we must choose which ads to fetch from them and then import into Microsoft Advertising.  You can use the table below to determine whether or not your ads will be imported from mixed mode campaigns.

<table>
  <tr>
    <th style="width:220px" scope="col">
              Your market
            </th>
    <th style="width:220px" scope="col">
              Import only dynamic search ads
            </th>
    <th style="width:220px" scope="col">
              Import only other ad types
            </th>
    <th scope="col">
              Import both dynamic search ads and other ad types
            </th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Supports dynamic search ads
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![red X mark](../images/Global_Icon_Xmark.png)
            </td>
    <td style="text-align:left">
              ![red X mark](../images/Global_Icon_Xmark.png)
            </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
              Does not support dynamic search ads
            </th>
    <td style="text-align:left">
                ![red X mark](../images/Global_Icon_Xmark.png)
              </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![red X mark](../images/Global_Icon_Xmark.png)
            </td>
  </tr>
</table>

However, if you’re in a market that supports dynamic search ads but only want to import the other ad types from your mixed mode campaigns, check **Import search and DSA mixed campaigns as search campaigns** under your import options.

> [!NOTE]
> Please note that campaign types cannot be changed after they are imported from Google Ads. If you want to change your campaign type, you will need to delete the campaign in Microsoft Advertising, and re-import it as your desired campaign type.
> By creating two separate Microsoft Advertising accounts, you can import campaigns containing dynamic search ads into one account and campaigns containing other ad types (Expanded Text Ads or standard text ads) into another.
> If you import dynamic search ads containing display URL paths that exceed 15 characters, the paths will be dropped. The rest of the ad, including the URL without the excessive paths, will stay the same.

## Language targeting
## Campaign and ad group languages

Targeting multiple languages allows you to have different ad groups in the same campaign show ads on websites in different languages. During an import, campaign languages are set to the Google Ads’ target languages that we support and ad group languages are automatically set to **Use the campaign settings**.

Microsoft Advertising supports the following ad languages:

<table>
  <tr>
    <td>
					Danish
				  </td>
    <td></td>
    <td>
					Italian
				  </td>
  </tr>
  <tr>
    <td>
					Dutch
				  </td>
    <td></td>
    <td>
					Norwegian
				  </td>
  </tr>
  <tr>
    <td>
					English
				  </td>
    <td></td>
    <td>
					Portuguese
				  </td>
  </tr>
  <tr>
    <td>
					Finnish
				  </td>
    <td></td>
    <td>
					Spanish
				  </td>
  </tr>
  <tr>
    <td>
					French
				  </td>
    <td></td>
    <td>
					Swedish
				  </td>
  </tr>
  <tr>
    <td>
					German
				  </td>
    <td></td>
    <td>
					Traditional Chinese
				  </td>
  </tr>
</table>

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
Shopping Campaigns and product ads are available only in the United States, United Kingdom, Australia, France, Germany, India, and Canada (English only and excluding Quebec) and cannot be imported from other countries. Before you import your Google shopping campaigns into Microsoft Advertising Shopping Campaigns, make sure to create a Microsoft Merchant Center store. Then, when you import, you must link your store to the incoming shopping campaign.

If you will be using an existing Google catalog, make sure the catalog has valid data in the **Country of sale** field. Microsoft Advertising supports the following countries for this field:
- United States
- United Kingdom
- Australia
- France
- Germany
- India
- Canada (English only and excluding Quebec)

> [!NOTE]
> Please note that we do not import Smart Shopping campaigns from Google Ads at this time.

## URL Tracking - **utm_source** parameter
If your Google Ads campaign uses the utm_source parameter, the value for that parameter is likely "Google," "GoogleAds," or a close variant such as "googleshopping" or "GoogleAdsIndia." These values will be replaced by "bing."

For example, **http://www.example.com/?utm_source=google** will be imported as **http://www.example.com/?utm_source=bing**.

This will prevent your imported campaigns from reporting incorrect source information.

## Items that can’t be imported but can be re-created using Microsoft Advertising

- Account-level App Extensions
- Ad group-level App Extensions
- Automated rules
- IP exclusions
- Not everyone is eligible to import remarketing lists and associations yet.  If you aren't, don't worry—it's coming soon!

> [!NOTE]
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
              Campaign name: Campaign names in Microsoft Advertising are not case-sensitive. If you import or re-import campaigns named “Coffee Sales” and “coffee sales” from Google Ads, you will see an error for a duplicate campaign name. However, if you import a campaign named “Coffee Sales” under an account that already contains a campaign named “coffee sales”, we recognize them as the same, and will update accordingly.
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
              Campaign labels
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
              Budget amount
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
              Budget type
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
              Bid strategy:
              Manual CPC, Enhanced CPC, Maximize Clicks, and Target CPA are imported. Target ROAS is not available in Microsoft Advertising, so campaigns with this bid strategy or any other bid strategy are set to Enhanced CPC when imported.
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
              Start/End date: Please note that Google Ads supports start and end dates at the campaign-level, while Microsoft Advertising supports them only at the ad group-level.  That means that the start and end dates you import will override the existing ones in your ad groups. If you import a campaign that is already past its end date, it’s status will be set to <strong>Paused</strong>. Not everyone has this feature yet. If you don’t, don’t worry. It's coming soon!
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
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Time zone:
              When you import a campaign for the first time, the time zone at account-level is used. After that, the time zone doesn’t change.
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Campaign type
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
              Sales country
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
              Start/End date: Please note that Google Ads supports start and end dates at the campaign-level, while Microsoft Advertising supports them only at the ad group-level.  That means that the start and end dates you import will override the existing ones in your ad groups. If you import a campaign that is already past its end date, it’s status will be set to <strong>Paused</strong>. Not everyone has this feature yet. If you don’t, don’t worry. It's coming soon!
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
              Keyword text
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
              Match type: When you import a campaign for the first time, the match type is imported. After that, the match type is not updated.
            </th>
    <td style="text-align:left">
               ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Bid
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
              Bid strategy: Keywords will use the ad group’s bid strategy. If the keyword is explicitly set to Manual CPC, then it will be imported with Manual CPC.
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
              Param1
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Param2
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Param3
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Final URL
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
              Final mobile URL
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

## Standard text ads
> [!NOTE]
> Microsoft Advertising no longer supports importing standard text ads from Google Ads. However, if you imported standard text ads before August 3rd, 2017 and choose to re-import them, we will import status changes (Pause/Unpause) from Google Ads.

## Expanded Text Ads
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
              Title part 1: Microsoft Advertising and Google Ads allow 30 characters. Google Ads calls this headline 1.
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
              Title part 2: Microsoft Advertising and Google Ads allow 30 characters. Google Ads calls this headline 2.
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
              Title part 3: Microsoft Advertising and Google Ads allow 30 characters. Google Ads calls this headline 3.
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
              Description: Microsoft Advertising and Google Ads allow 90 characters.
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
              Description 2: Microsoft Advertising and Google Ads allow 90 characters.
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
              Path 1: Microsoft Advertising and Google Ads allow 15 characters.
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
              Path 2: Microsoft Advertising and Google Ads allow 15 characters.
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
              URL custom parameters
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
              Final URL: Microsoft Advertising has a 35-character maximum limit for the host in URL. For example, if the URL is http://www.edu.bing.co.uk/pages/one, then the host is www.edu.bing.co.uk and it can’t be more than 35 characters. Google Ads allows more than 35 characters for the host in URL.
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
              Ad labels
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
> If Expanded Text Ads missing from your import, be sure to select **Ad customizer feeds** under the **Feeds** section of your import options. Then try your import again.

## Product ads
<table>
  <tr>
    <th style="width:260px" scope="col">
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
              Status
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Promotion
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left"></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent;font-weight: normal">
              Ad labels
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
</table>

## Responsive search ads
> [!IMPORTANT]
> Not everyone has this feature yet. If you don't, don't worry—it's coming soon!

<table>
  <tr>
    <th style="width:260px" scope="col">
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
              Final URL: Microsoft Advertising has a 35-character maximum limit for the host in URL. For example, if the URL is http://www.edu.bing.co.uk/pages/one, then the host is www.edu.bing.co.uk and it can’t be more than 35 characters. Google Ads allows more than 35 characters for the host in URL.
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
              Headlines
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
              Path: Microsoft Advertising and Google Ads allow 15 characters.
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
              Descriptions
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
               Mobile URL 
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
              Final URL suffix
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
> - Manually pause or delete old responsive search ads to make room for other enabled ones.
> - Choose **Delete items that have been removed from your Google Ads** account in your import options.

## Labels
<table>
  <tr>
    <th style="width:260px" scope="col">
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
              Label name
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
              Label color
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
              Label description
            </th>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
    <td style="text-align:left">
              ![green check mark](../images/Global_Icon_CheckMark.png)
            </td>
  </tr>
</table>

Choosing the appropriate import options can determine which items get imported to Microsoft Advertising for the first time, updated from a previous import, or left untouched. Below, you can review both your import goals and the options you must choose to achieve them.

<table>
  <tr>
    <th style="width:300px" scope="col">
        What is your import goal?
      </th>
    <th style="width:300x" scope="col">
        What import options should I choose?
      </th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Import new labels and update existing ones.
      </th>
    <td style="text-align:left">
        Check <strong>Labels</strong> under both <strong>Items not previously imported into Microsoft Advertising</strong> and <strong>Updates to existing items</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Import new labels and ignore updating existing ones.
      </th>
    <td style="text-align:left">
       Check <strong>Labels</strong> under <strong>Items not previously imported into Microsoft Advertising</strong>. Uncheck <strong>Labels</strong> under <strong>Updates to existing items</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Ignore new labels and import updates to existing ones.
      </th>
    <td style="text-align:left">
        Check <strong>Labels</strong> under <strong>Updates to existing items</strong>. Uncheck <strong>Labels</strong> under <strong>Items not previously imported into Microsoft Advertising</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Ignore both new labels and updates to existing ones.
      </th>
    <td style="text-align:left">
        Uncheck <strong>Labels</strong> under both <strong>Items not previously imported into Microsoft Advertising</strong> and <strong>Updates to existing items</strong>.
      </td>
  </tr>
</table>

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

<table>
  <tr>
    <th style="width:300px" scope="col">
        What is your import goal?
      </th>
    <th style="width:300x" scope="col">
        What import options should I choose?
      </th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Import new ad extensions and update existing ones.
      </th>
    <td style="text-align:left">
        Check <strong>Ad extensions</strong> under both <strong>Items not previously imported into Microsoft Advertising</strong> and <strong>Updates to existing items</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Import new ad extensions and ignore updating existing ones.
      </th>
    <td style="text-align:left">
       Check <strong>Ad extensions</strong> under <strong>Items not previously imported into Microsoft Advertising</strong>. Uncheck <strong>Ad extensions</strong> under <strong>Updates to existing items</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Ignore new ad extensions and import updates to existing ones.
      </th>
    <td style="text-align:left">
        Check <strong>Ad extensions</strong> under <strong>Updates to existing items</strong>. Uncheck <strong>Ad extensions</strong> under <strong>Items not previously imported into Microsoft Advertising</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Ignore both ad extensions and updates to existing ones.
      </th>
    <td style="text-align:left">
        Uncheck <strong>Ad extensions</strong> under both <strong>Items not previously imported into Microsoft Advertising</strong> and <strong>Updates to existing items</strong>.
      </td>
  </tr>
</table>

> [!NOTE]
> Please note that if you’ve removed ad extensions in Google Ads and then select **Ad extensions** under **Updates to existing items**, those ad extensions will be deleted during the import.
> Please note that during an import, you cannot disassociate an ad extension from a campaign or ad group. However, you **can** replace it with another ad extension in Google Ads, then re-import to Microsoft Advertising.

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

<table>
  <tr>
    <th style="width:300px" scope="col">
        What is your import goal?
      </th>
    <th style="width:300x" scope="col">
        What import options should I choose?
      </th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Import new campaign and ad group targets and update existing ones.
      </th>
    <td style="text-align:left">
        Check <strong>Targeting</strong> under both <strong>Items not previously imported into Microsoft Advertising</strong> and <strong>Updates to existing items</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Import new campaign and ad group targets and ignore updating existing ones.
      </th>
    <td style="text-align:left">
       Check <strong>Targeting</strong> under <strong>Items not previously imported into Microsoft Advertising</strong>. Uncheck <strong>Targeting</strong> under <strong>Updates to existing items</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Ignore new campaign and ad group targets and import updates to existing ones.
      </th>
    <td style="text-align:left">
        Check <strong>Targeting</strong> under <strong>Updates to existing items</strong>. Uncheck   <strong>Targeting</strong> under <strong>Items not previously imported into Microsoft Advertising</strong>.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">
        Ignore both new campaign and ad group targets and updates to existing ones.
      </th>
    <td style="text-align:left">
        Uncheck <strong>Targeting</strong> under both <strong>Items not previously imported into Microsoft Advertising</strong> and <strong>Updates to existing items</strong>.
      </td>
  </tr>
</table>

> [!NOTE]
> Please note that if you’ve removed targets in Google Ads and then select **Targeting** under **Updates to existing items**, those targets will be deleted during the import.

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


