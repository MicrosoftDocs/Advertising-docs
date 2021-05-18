---
title: About ad customizer feeds
description: Let your ads adapt to their audience based on dynamic parameters you can set with ad customizer feeds.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About ad customizer feeds

With ad customizers, your ads can dynamically update themselves to appeal to specific customers. All it takes is uploading an ad customizer feed that tells us what information you want to insert into your ads under which circumstances.

## Why use ad customizer feeds?

**Save time** . Transform a single text ad into hundreds of variations without having to manually update the ad.

**More relevant ads** . Customize ads based on what customers are searching for, when they're searching for it, where they are, what device they're using, and more.

**Better results** . See higher click-through and conversion rates.

**Tip** : Leverage other dynamic text, number, price, and date/time fields in the ad copy with [dynamic text parameters](./hlp_BA_CONC_AboutParameters.md).

## How ad customizer feeds work

An ad customizer feed is a spreadsheet. In this spreadsheet, each column is an attribute that tells Microsoft Advertising one of two things:

<table>
  <tr>
    <th scope="col">Attribute type</th>
    <th scope="col">What it tells Microsoft Advertising</th>
  </tr>
  <tr>
    <td>Custom attribute</td>
    <td>What information about your products or services you want to insert into your ads</td>
  </tr>
  <tr>
    <td>Targeting attribute</td>
    <td rowspan="2" style="vertical-align:middle">Under what conditions each piece of information should be inserted into your ads </td>
  </tr>
  <tr>
    <td>Standard attribute</td>
  </tr>
</table>

## About custom attributes
You can define custom attributes to insert any kind of information you like into your ads. Each custom attribute will need a unique name, followed by the attribute type in parentheses.

There are four different types of custom attributes you can use:

|Custom attribute type|For example|Column header must appear like this|Accepted values|
|---|---|---|---|
|Text|Product names, product categories, descriptions|Name ```(text)``` (for example, "Shoes ```(text)```")|Any letters, numbers, or symbols|
|Number|Inventory count, number of colors available|Name ```(number)``` (for example, "Colors ```(number)```")|Any whole number|
|Price|Product cost, sale discount|Name ```(price)``` (for example, "Base_Price ```(price)```")|Any number (including decimals) and valid currency characters|
|Date|Event start time, last day of a sale|Name ```(date)``` (for example, "Sale_Date ```(date)```")|yyyy/mm/dd hh:mm:ss (24-hour time; the hh:mm:ss is optional)|

> [!NOTE]
> You cannot give a custom attribute the same name as any standard attribute: ```Device preference```, ```Scheduling```, ```Start date```, ```End date```, or ```Custom ID```.

## About targeting attributes
Whereas custom attributes tell us what to insert into your ads, targeting attributes tell us **when** to insert that information. There are six different types of targeting attributes:

<table>
  <tr>
    <th scope="col">Targeting attribute type</th>
    <th scope="col">Column header must appear like this</th>
    <th scope="col">Accepted values</th>
    <th scope="col">Note</th>
  </tr>
  <tr>
    <td>Target keyword</td>
    <td>```Target keyword```</td>
    <td>Enter the keyword with your desired match-type syntax:
						<ul><li><strong>Broad match</strong> : <strong>keyword</strong></li><li><strong>Broad match modifier</strong> : <strong>+keyword</strong></li><li><strong>Phrase match</strong> : <strong>"keyword"</strong></li><li><strong>Exact match</strong> : <strong>[keyword]</strong></li></ul></td>
    <td>You can target keywords either with this attribute or with the <strong>Target keyword text</strong> and <strong>Target keyword match type</strong> attributes in conjunction.</td>
  </tr>
  <tr>
    <td>Target keyword text</td>
    <td>```Target keyword text```</td>
    <td>The keyword you want to target (<strong>without</strong> match type punctuation formatting). </td>
    <td>This attribute can only be used in conjunction with the <strong>Target keyword match type</strong> attribute. </td>
  </tr>
  <tr>
    <td>Target keyword match type</td>
    <td>```Target keyword match type```</td>
    <td>"```Broad```", "```Phrase```", or "```Exact```" </td>
    <td>This attribute can only be used in conjunction with the <strong>Target keyword text</strong> attribute. </td>
  </tr>
  <tr>
    <td>Target ad group</td>
    <td>```Target ad group```</td>
    <td>Existing ad group name</td>
    <td>To target by ad group, you need to use both <strong>Target ad group</strong> and <strong>Target campaign</strong> attributes. </td>
  </tr>
  <tr>
    <td>Target campaign</td>
    <td>```Target campaign```</td>
    <td>Existing campaign name</td>
    <td></td>
  </tr>
  <tr>
    <td>Target location</td>
    <td>```Target location```</td>
    <td>Name of location (English only)</td>
    <td>
      <ul>
        <li>Location names can be entered in any of the following formats:
							<ul><li>Miami, FL</li><li>Miami,Florida,United States</li><li>Miami | Florida | United States</li></ul></li>
        <li>If you want to target only people <strong>physically in</strong> a location, you will need to use the <strong>Target location restriction</strong> attribute as well.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Target location ID</td>
    <td>```Target location ID```</td>
    <td>A numeric Microsoft Advertising geographical location code.</td>
    <td>
      <ul>
        <li>[How to download the geographical location code file.](https://go.microsoft.com/fwlink?LinkId=536556)</li>
        <li>If you are using this attribute, do not also use the <strong>Target location</strong> attribute.</li>
        <li>If you want to target only people <strong>physically in</strong> a location, you will need to use the <strong>Target location restriction</strong> attribute as well.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>Target location restriction</td>
    <td>```Target location restriction```</td>
    <td>"```Physical location```" or empty</td>
    <td>This attribute can only be used in conjunction with the <strong>Target location</strong> or <strong>Target location ID</strong> attribute.</td>
  </tr>
  <tr>
    <td>Target audience ID</td>
    <td>```Target audience ID```</td>
    <td>Existing Microsoft Advertising audience ID (for any audience type supported by Microsoft Advertising)</td>
    <td>
      <ul>
        <li>Audience IDs can be found under <strong>Shared Library</strong>&nbsp;&gt;&nbsp;<strong>Audiences</strong>.</li>
        <li>[Available in-market audiences are listed here](https://go.microsoft.com/fwlink?LinkId=872520).</li>
      </ul>
    </td>
  </tr>
</table>

## About standard attributes
Standard attributes are advanced targeting configurations:

|Standard attribute type|Column header must appear like this|Accepted values|Note|
|---|---|---|---|
|Device preference|```Device preference```|"```mobile```" or "```all```"||
|Scheduling|```Scheduling```|"[day of the week] - [day of the week]" or "[day of the week], [start time] - [end time]"   					Day of the week = "```Monday```", "```Tuesday```", "```Wednesday```", "```Thursday```", "```Friday```", "```Saturday```", or "```Sunday```"   					Start/end time = yyyy/mm/dd hh:mm:ss (24-hour time)|If you wanted to schedule from 9:00 AM to 5:00 PM on Mondays, for example, you would enter "```Monday, 09:00:00 - 17:00:00```".   				  If you want to schedule for multiple days, separate your days with a semicolon. For example, you could schedule for both Monday and Tuesday using "```Monday, 09:00:00 - 17:00:00; Tuesday, 09:00:00 - 17:00:00```".  				  For start/end times, you can omit the hh:mm:ss part to set the time as midnight at the beginning of the day.|
|Start date|```Start date```|yyyy/mm/dd hh:mm:ss (24-hour time)|You can omit the hh:mm:ss part to set the start time as midnight at the beginning of the day.|
|End date|```End date```|yyyy/mm/dd hh:mm:ss (24-hour time)|You can omit the hh:mm:ss part to set the end time as midnight at the beginning of the day.|
|Custom ID|```Custom ID```|Any combination of letters and numerals|Use this attribute to create your own identifying IDs for feed items. If used, a feed item will have two IDs: a Custom ID and an Item ID (which is automatically assigned by Microsoft Advertising).|

## Examples of ad customizers in action

In these examples, let's say you sell sunglasses.

Ad customizers appear in Microsoft Advertising in the following syntax: ```{=FeedName.Attribute}```. So, if your feed name is "```Sunglasses```" and your attribute name is "```Type```", the syntax will be ```{=Sunglasses.Type}```.

## Target by keyword
Let's say you you want to highlight specific sunglasses features, depending on what a customer searches for. You might have a row of your ad customizer feed look like this:

|```Target keyword```|```Product (text)```|```Materials_Lightweight (text)```|```Description_Lightweight (text)```|```Finishes (number)```|```StartPrice (price)```|
|---|---|---|---|---|---|
|```lightweight sunglasses```|```Contoso 900```|```titanium or acetate```|```Stylish, lightweight shades```|```8```|```$24.99```|

Then...

|If you set up your ad like this in Microsoft Advertising...|...it could look like this for customers who searched for "```lightweight sunglasses```"|
|---|---|
|```					The latest {=Sunglasses.Product}s  					In {=Sunglasses.Materials_Lightweight}  					www.contoso.com/deals  					{=Sunglasses.Description_Lightweight} in {=Sunglasses.Finishes} finishes. Starting at only {=Sunglasses.StartPrice}!				  ```|![Bing Ad matching this setup](../images/BA_ScreenCap_AdCustomizerEx1.png)|

## Target by campaign or ad group
OK, now let's say your ad campaign has a different ad group for each brand of sunglasses you sell. You've found that customers who search for a specific series of a brand of sunglasses often end up purchasing a different series. So you want to highlight your series options within your brand's ad group. You might have a row of your ad customizer feed look like this:

|```Target campaign```|```Target ad group```|```Brand (text)```|```Series (number)```|```StartPrice (price)```|
|---|---|---|---|---|
|```Sunglasses```|```Contoso 900```|```Contoso```|```9```|```$24.99```|

Then...

|If you set up your ad like this in Microsoft Advertising...|...it could look like this for customers who searched for "```contoso 900```"|
|---|---|
|```					{=Sunglasses.Brand} brand sunglasses  					{=Sunglasses.Series} series to choose from  					www.contoso.com  					Browse our wide selection! Prices as low as {=Sunglasses.StartPrice}				  ```|![Bing Ad matching this setup](../images/BA_ScreenCap_AdCustomizerEx3.png)|

## Target by location
Uh-oh! It was a cloudy summer in Portland, and now your Portland store has way too many Contoso brand sunglasses. Time for a big sale to move that particular store's inventory. You might have a row of your ad customizer feed look like this:

|```Target location```|```Brand (text)```|```BlowoutSale_1 (text)```|```BlowoutSale_2 (text)```|
|---|---|---|---|
|```Portland, Oregon```|```Contoso```|```Up to 70% off at our Pearl District store.```|```40% off Contoso 800s!```|

Then...

|If you set up your ad like this in Microsoft Advertising...|...it could look like this for customers who searched for "```contoso portland```"|
|---|---|
|```					{=Sunglasses.Brand} sunglasses  					Blowout Sale!  					www.contoso.com/BlowoutSale  					{=Sunglasses.BlowoutSale_1} {=Sunglasses.BlowoutSale_2}				  ```|![Bing Ad matching this setup](../images/BA_ScreenCap_AdCustomizerEx4.png)|

## Target by audience
Now let's say you have a remarketing list of customers who looked at a specific type of sunglasses on your website. You might have a row of your ad customizer feed look like this:

|```Type (text)```|```Product (text)```|```Discount (text)```|```Colors (number)```|```Target audience ID```|
|---|---|---|---|---|
|```Polarized```|```Contoso 800```|```25% off```|```12```|```12345678```|

Then...

|If you set up your ad like this in Microsoft Advertising...|...it could look like this for customers who were in this remarketing list|
|---|---|
|```					{=Sunglasses.Type} sunglasses on sale  					{=Sunglasses.Product} series  					www.contoso.com/{=Sunglasses.Type}/OnSale  					{=Sunglasses.Discount} if you order today! Lenses come in {=Sunglasses.Colors} different colors.				  ```|![Bing Ad matching this setup](../images/BA_ScreenCap_AdCustomizerEx2.png)|

## Use ad customizers within countdowns
If you were having a sunglasses sale for a limited time, you could combine the power of ad customizers and [countdowns](./hlp_BA_CONC_Countdown.md). You might have a row of your ad customizer feed look like this:

|```Product (text)```|```Promo (text)```|```End_by (date)```|```StartPrice (price)```|
|---|---|---|---|
|```Contoso 700```|```30% off with free shipping```|```2019/08/14 23:59:59 ```|```$30```|

Then...

|If you set up your ad like this in Microsoft Advertising...|...it could look like this for customers who searched for "```contoso sunglasses```" on August 12, 2019|
|---|---|
|```					{=Sunglasses.Product}s  					Get {=Sunglasses.Promo}  					www.contoso.com/SummerSale  					Offer ends in {=COUNTDOWN(Sunglasses.End_by)}. Buy now as low as {=Sunglasses.StartPrice} 				  ```|![Bing Ad matching this setup](../images/BA_ScreenCap_AdCustomizerEx5.png)|

## Layout of an ad customizer feed

An ad customizer feed is a spreadsheet. The columns of the spreadsheet are feed attributes, and each one must have its name (as detailed in the previous "How ad customizer feeds work" section) in the header row. Each row after the header row is a feed item, a combination of custom attributes (telling Microsoft Advertising what information to insert into your ads) and targeting and/or standard attributes (telling Microsoft Advertising under what circumstances to insert this information).

<table type="type2">
  <tr>
    <td></td>
    <td>
      <para style="margin:10px 0 -10px 140px;">An attribute</para>
    </td>
  </tr>
  <tr>
    <td></td>
    <td rowspan="2" style="vertical-align:top;">![Illustration of an ad customizer feed](../images/BA_ScreenCap_ProductAdsFeed.png)</td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:top;">
      <para style="margin: 43px 10px 0 0;">Attribute names</para>
    </td>
  </tr>
  <tr>
    <td style="text-align:right;vertical-align:top;">
      <para style="margin: -60px 10px 0 0;">A feed item</para>
    </td>
  </tr>
</table>

> [!NOTE]
> For details on uploading and managing ad customizer feeds, take a look at [Setting up and managing feeds](./hlp_BA_PROC_Feeds_WorkingWith.md).

 
## Adding ad customizers to Expanded Text Ads

You can add ad customizers to any Expanded Text Ad field except the final URL.

1. When creating or editing an Expanded Text Ad, enter a left curly bracket ( { ) where you want the ad customizer to appear.
1. In the resulting drop-down menu, select **Ad customizer**.
1. In the resulting drop-down menu, select the appropriate ad customizer feed.
1. In the resulting drop-down menu, select the appropriate custom attribute from that feed.
1. **Default text** is optional. If you want your ad to appear **even if the circumstances defined by the feed's targeting and/or standard attributes are not met**, enter a word, phrase, or number to appear instead of the custom attribute value. Note: If a single ad customizer in an ad has default text defined, every other ad customizer in the same ad must also have default text defined.
1. Click **Set**.

> [!NOTE]
> The ad customizer will appear in Microsoft Advertising in the following syntax: {=FeedName.Attribute:DefaultText}. So, if your feed name is "Accessories", your attribute name is "Type", and your default text is "sunglasses", the syntax will be {=Accessories.Type:sunglasses}.

## How to add ad customizer feeds to ad text manually
You can also add an ad customizer feed to ad text manually, either by typing directly in the **Create ad** input boxes, by using a [bulk upload](./hlp_BA_CONC_AboutBulk.md) spreadsheet, or by using [Microsoft Advertising Editor](./hlp_BA_CONC_AboutDesktop.md).

To make sure you enter it correctly, let's look at the components of an ad customizer feed's syntax:

**{=FeedName.Attribute:DefaultText}**

|Component|What you need to know|
|---|---|
|{ ... }|**Mandatory** . The entire ad customizer syntax must be within a pair of braces (also called curly brackets).|
|=FeedName|**Mandatory** . An equals symbol immediately followed by the name you gave your ad customizer feed.|
|.Attribute|**Mandatory** . A period immediately followed by the name you gave your custom attribute.|
|:DefaultText|**Optional** . If you want your ad to appear **even if the circumstances defined by the feed's targeting and/or standard attributes are not met**, enter a colon immediately followed by a word, phrase, or number to appear instead of the custom attribute value. Note: If a single ad customizer in an ad has default text defined, every other ad customizer in the same ad must also have default text defined.|


