---
title: "Responsive Ad Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Responsive Ad fields in a Bulk file.
dev_langs:
  - csharp
---
# Responsive Ad Record - Bulk
Defines a responsive ad that can be downloaded and uploaded in a bulk file.

Responsive ads automatically adjust to accommodate the sizes and shapes of native ad formats.

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Responsive Ad* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Business Name](#businessname)
- [Call To Action](#calltoaction)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Custom Parameter](#customparameter)
- [Editorial Appeal Status](#editorialappealstatus)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [Final Url](#finalurl)
- [Headline](#headline)
- [Id](#id)
- [Landscape Image Media Id](#landscapeimagemediaid)
- [Landscape Logo Media Id](#landscapelogomediaid)
- [Long Headline](#longheadline)
- [Mobile Final Url](#mobilefinalurl)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Publisher Countries](#publishercountries)
- [Status](#status)
- [Square Image Media Id](#squareimagemediaid)
- [Square Logo Media Id](#squarelogomediaid)
- [Text](#text)
- [Tracking Template](#trackingtemplate)

You can download all fields of the *Responsive Ad* record by including the [DownloadEntity](downloadentity.md) value of *ResponsiveAds* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new responsive ad given a valid ad group ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Sync Time,Client Id,Modified Time,Tracking Template,Custom Parameter,Final Url,Mobile Final Url,Text,Business Name,Device Preference,Ad Format Preference,Name,Call To Action,Headline,Long Headline,Landscape Image Media Id,Square Image Media Id,Landscape Logo Media Id,Square Logo Media Id
Format Version,,,,,,,,,,,,,,,,,6,,,,,,,
Responsive Ad,Active,,-1111,ParentCampaignNameGoesHere,AdGroupNameHere,ClientIdGoesHere,,,{_promoCode}=PROMO1; {_season}=summer,,http://www.contoso.com/womenshoesale,http://mobile.contoso.com/womenshoesale,Find New Customers & Increase Sales! Start Advertising on Contoso Today.,Contoso,,,,,Short Headline Here,Long Headline Here,LandscapeImageMediaIdGoesHere,SquareImageMediaIdGoesHere,Landscape LogoMediaIdGoesHere,SquareLogoMediaIdGoesHere
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkResponsiveAd* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkResponsiveAd
var bulkResponsiveAd = new BulkResponsiveAd
{
    // 'Parent Id' column header in the Bulk file
    AdGroupId = adGroupIdKey,
    // 'Ad Group' column header in the Bulk file
    AdGroupName = "AdGroupNameHere",
    // 'Campaign' column header in the Bulk file
    CampaignName = "ParentCampaignNameGoesHere",
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // ResponsiveAd object of the Campaign Management service.
    ResponsiveAd = new ResponsiveAd
    {
        // 'Call To Action' column header in the Bulk file
        CallToAction = CallToAction.AddToCart,
        // 'Mobile Final Url' column header in the Bulk file
        FinalMobileUrls = new[] {
            // Each Url is delimited by a semicolon (;) in the Bulk file
            "http://mobile.contoso.com/womenshoesale"
        },
        // 'Final Url' column header in the Bulk file
        FinalUrls = new[] {
            // Each Url is delimited by a semicolon (;) in the Bulk file
            "http://www.contoso.com/womenshoesale"
        },
        // 'Headline' column header in the Bulk file
        Headline = "Short Headline Here",
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Landscape Image Media Id' column header in the Bulk file
        LandscapeImageMediaId = 0, // Replace '0' with your media ID
        // 'Landscape Logo Media Id' column header in the Bulk file
        LandscapeLogoMediaId = 0, // Replace '0' with your media ID
        // 'Long Headline' column header in the Bulk file
        LongHeadline = "Long Headline Here",
        // 'Status' column header in the Bulk file
        Status = AdStatus.Active,
        // 'Square Image Media Id' column header in the Bulk file
        SquareImageMediaId = 0, // Replace '0' with your media ID
        // 'Square Logo Media Id' column header in the Bulk file
        SquareLogoMediaId = 0, // Replace '0' with your media ID
        // 'Text' column header in the Bulk file
        Text = "Find New Customers & Increase Sales! Start Advertising on Contoso Today.",
        // 'Tracking Template' column header in the Bulk file
        TrackingUrlTemplate = null,
        // 'Custom Parameter' column header in the Bulk file
        UrlCustomParameters = new CustomParameters
        {
            // Each custom parameter is delimited by a semicolon (;) in the Bulk file
            Parameters = new[] {
                new CustomParameter(){
                    Key = "promoCode",
                    Value = "PROMO1"
                },
                new CustomParameter(){
                    Key = "season",
                    Value = "summer"
                },
            }
        },
    },
};

uploadEntities.Add(bulkResponsiveAd);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkService.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

### <a name="adgroup"></a>Ad Group
The name of the ad group that contains the ad.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="businessname"></a>Business Name
The name of the business.

Depending on your audience ad's placement, your business's name may appear in your ad. 

The length of the string is limited to 25 characters.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="calltoaction"></a>Call To Action
A brief, punchy reason for customers to click your ad right now. 

The possible values are AddToCart, ApplyNow, BookNow, BookTravel, Buy, BuyNow, ContactUs, Download, GetQuote, Install, LearnMore, NoButton, OpenLink, OrderNow, RegisterNow, SeeMore, ShopNow, SignUp, Subscribe, and VisitSite.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group and ad.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="customparameter"></a>Custom Parameter
Your custom collection of key and value parameters for URL tracking.

In a bulk file, the list of custom parameters are formatted as follows.

- Format each custom parameter pair as Key=Value, for example {_promoCode}=PROMO1.

- You may include up to 3 custom parameter key and value pairs. Each key and value pair are delimited by a semicolon and space ("; "), for example {_promoCode}=PROMO1; {_season}=summer.

- A Key cannot contain a semicolon. If a Value contains a semicolon it must be escaped as '\;'. Additionally if the Value contains a backslash it must also be escaped as '\\'.

- The Key cannot exceed 16 UTF-8 bytes, and the Value cannot exceed 200 UTF-8 bytes. The maximum size of the Key does not include the braces and underscore i.e., '{', '_', and '}'. 

    > [!NOTE] 
    > With the Bulk service the Key must be formatted with surrounding braces and a leading underscore, for example if the Key is promoCode, it must be formatted as {_promoCode}. With the Campaign Management service you cannot specify the surrounding braces and underscore.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove all custom parameters, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of custom parameters, specify the custom parameters that you want to keep and omit any that you do not want to keep. The new set of custom parameters will replace any previous custom parameter set.    
**Delete:** Read-only  

### <a name="editorialappealstatus"></a>Editorial Appeal Status
Determines whether you can appeal the issues found by the editorial review.

Possible values include *Appealable*, *AppealPending*, and *NotAppealable*. For more details, see [AppealStatus Value Set](../campaign-management-service/appealstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the ad that failed editorial review. 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Reason Codes](../guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the ad.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [AdEditorialStatus Value Set](../campaign-management-service/adeditorialstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialterm"></a>Editorial Term
The term that failed editorial review.

This field will not be set if a combination of terms caused the failure or if the failure was based on a policy violation.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="finalurl"></a>Final Url
The landing page URL.

The domain portion of the URL in combination with the path 1 and path 2 strings cannot exceed 67 characters.

The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    > [!NOTE]
    > The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url.

Also note that  if the *Tracking Template* or *Custom Parameter* fields are set, then at least one Final URL is required.

> [!NOTE]
> This URL is used only if the keyword does not specify a final URL.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="headline"></a>Headline
This is one of two possible headlines that could appear in your audience ads. 

Because audience ads are responsive, we require multiple headlines so they can flexibly serve across a variety of publishers and placements. 

The length of the string is limited to 25 characters.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="id"></a>Id
The system generated identifier of the ad.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="landscapeimagemediaid"></a>Landscape Image Media Id
This is the identifier of the media corresponding to one of two possible aspect ratios for images that could appear in your audience ads.

Because audience ads are responsive, we require multiple images so they can flexibly display across a variety of publishers and placements.

Wide or landscape images have an aspect ratio of 1.91:1. 

Media for responsive ads are provisioned via the [Image](../campaign-management-service/image.md) object using the Campaign Management service. When you call the [AddMedia](../campaign-management-service/addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](../campaign-management-service/image.md#remarks).

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="landscapelogomediaid"></a>Landscape Logo Media Id
This is the identifier of the media corresponding to one of two possible aspect ratios for logos that could appear in your audience ads.

Because audience ads are responsive, we require multiple logos so they can flexibly display across a variety of publishers and placements.

Wide or landscape logos have an aspect ratio of 1.91:1. 

Media for responsive ads are provisioned via the [Image](../campaign-management-service/image.md) object using the Campaign Management service. When you call the [AddMedia](../campaign-management-service/addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](../campaign-management-service/image.md#remarks).

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="longheadline"></a>Long Headline
This is one of two possible headlines that could appear in your audience ads. 

Because audience ads are responsive, we require multiple headlines so they can flexibly serve across a variety of publishers and placements. 

The length of the string is limited to 90 characters.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="mobilefinalurl"></a>Mobile Final Url
The mobile landing page URL.

The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    > [!NOTE]
    > The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url.

> [!NOTE]
> This URL is used only if the keyword does not specify a *Mobile Final Url*.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the ad group that contains the ad.

This bulk field maps to the *Id* field of the [Ad Group](ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](ad-group.md) record. This is recommended if you are adding new ads to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="publishercountries"></a>Publisher Countries
The list of publisher countries whose editorial guidelines do not allow the specified [term](#editorialterm).

In a bulk file, the list of publisher countries are delimited with a semicolon (;).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="status"></a>Status
The status of the ad.

Possible values are *Active*, *Paused*, or *Deleted*. 

**Add:** Optional. The default value is *Active*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Required. The Status must be set to *Deleted*.

### <a name="squareimagemediaid"></a>Square Image Media Id
This is one of two possible aspect ratios for images that could appear in your audience ads.

Because audience ads are responsive, we require multiple images so they can flexibly display across a variety of publishers and placements.

Square images have an aspect ratio of 1:1. 

Media for responsive ads are provisioned via the [Image](../campaign-management-service/image.md) object using the Campaign Management service. When you call the [AddMedia](../campaign-management-service/addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](../campaign-management-service/image.md#remarks).

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="squarelogomediaid"></a>Square Logo Media Id
This is one of two possible aspect ratios for logos that could appear in your audience ads.

Because audience ads are responsive, we require multiple logos so they can flexibly display across a variety of publishers and placements.

Square logos have an aspect ratio of 1:1. 

Media for responsive ads are provisioned via the [Image](../campaign-management-service/image.md) object using the Campaign Management service. When you call the [AddMedia](../campaign-management-service/addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](../campaign-management-service/image.md#remarks).

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only 

### <a name="text"></a>Text
Depending on your audience ad's placement, this text will appear below or adjacent to your ad's long or short headline.  

You have more character space to work with in the ad text than in the headline. So once the imagery and headline have a potential customer's attention, the ad text needs to convince them to click it. What sets your product or service apart?

The text must contain at least one word.

The length of the string is limited to 90 characters.

The text cannot contain the newline (\n) character.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for the URL specified with FinalUrls.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  
