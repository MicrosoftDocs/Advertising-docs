---
title: "Bulk File Schema"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the schema for records in a Bulk file.
---
# Bulk File Schema
The bulk schema defines the contents of the file for download or upload with the Bing Ads Bulk service. For both download and upload, the Bulk service supports the file types and corresponding schemas in the [DownloadEntity](downloadentity.md) value set.

For more information about using the Bulk service to manage your campaigns, see [Bulk Download and Upload](../guides/bulk-download-upload.md). For more information about understanding the data file contents, see the sections below.

-   [File Schema](#fileschema)  
-   [Format Versions](#formatversions)  
-   [Record Types](#recordtypes)  
-   [Type Hierarchy](#typehierarchy)  
-   [Reference Keys](#referencekeys)  
-   [Client Identifiers](#clientid)  
-   [Errors](#errors)

## <a name="fileschema"></a>File Schema
You can choose to download either a tab or comma delimited set of records (rows) and fields (columns). The first column header is named *Type*.  The rest of the column names map to properties within or associated with the corresponding record type.

> [!IMPORTANT]
> New record types (rows) and fields (columns) may be added anytime, and you should not depend on record or field order in the bulk download or bulk upload results file. Similarly during upload you may submit the fields in any order. The upload record order is important when creating new entities, as described below within [Type Hierarchy](#typehierarchy).

## <a name="formatversions"></a>Format Versions
The bulk format version is separate from the Bing Ads API version.  Format version enables a flexible upgrade path to adopt the latest supported features without breaking your application. As a best practice you should always upgrade to the latest format version. Currently Bing Ads API Version 11 only supports format version 5.0.

To specify the file format version using bulk download, set *FormatVersion* to 5.0 in either the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) request.

To specify the version using bulk upload, set the *Name* field of the [Format Version](format-version.md) record to 5.0.

## <a name="recordtypes"></a>Record Types
Records available for upload and download using [Format Version](#formatversions) 5.0 are detailed in the table below. 

> [!IMPORTANT]
> New record types (rows) and fields (columns) may be added anytime, and you should not depend on record or field order in the bulk download or bulk upload results file.

Record Type  |Supported Campaign Types  
---------|---------
[Account](account.md)|All         
[Account App Ad Extension](account-app-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Account Callout Ad Extension](account-callout-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Account Image Ad Extension](account-image-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Account Location Ad Extension](account-location-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Account Price Ad Extension](account-price-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Account Sitelink2 Ad Extension](account-sitelink2-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Account Structured Snippet Ad Extension](account-structured-snippet-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Ad Group](ad-group.md)|All         
[Ad Group Age Criterion](ad-group-age-criterion.md)|All         
[Ad Group App Ad Extension](ad-group-app-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Ad Group Callout Ad Extension](ad-group-callout-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Ad Group Custom Audience Association](ad-group-custom-audience-association.md)|All         
[Ad Group DayTime Criterion](ad-group-daytime-criterion.md)|All         
[Ad Group DeviceOS Criterion](ad-group-deviceos-criterion.md)|All         
[Ad Group Dynamic Search Ad Target](ad-group-dynamic-search-ad-target.md)|DynamicSearchAds         
[Ad Group Gender Criterion](ad-group-gender-criterion.md)|All         
[Ad Group Image Ad Extension](ad-group-image-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Ad Group In Market Audience Association](ad-group-in-market-audience-association.md)|All         
[Ad Group Label](ad-group-label.md)|All         
[Ad Group Location Criterion](ad-group-location-criterion.md)|All         
[Ad Group Location Intent Criterion](ad-group-location-intent-criterion.md)|All         
[Ad Group Negative Custom Audience Association](ad-group-negative-custom-audience-association.md)|All         
[Ad Group Negative Dynamic Search Ad Target](ad-group-negative-dynamic-search-ad-target.md)|DynamicSearchAds         
[Ad Group Negative In Market Audience Association](ad-group-negative-in-market-audience-association.md)|All         
[Ad Group Negative Keyword](ad-group-negative-keyword.md)|All         
[Ad Group Negative Location Criterion](ad-group-negative-location-criterion.md)|All         
[Ad Group Negative Remarketing List Association](ad-group-negative-remarketing-list-association.md)|All         
[Ad Group Negative Site](ad-group-negative-site.md)|All         
[Ad Group Price Ad Extension](ad-group-price-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Ad Group Product Partition](ad-group-product-partition.md)|Shopping         
[Ad Group Radius Criterion](ad-group-radius-criterion.md)|All         
[Ad Group Remarketing List Association](ad-group-remarketing-list-association.md)|All         
[Ad Group Review Ad Extension](ad-group-review-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[AdGroup Sitelink Ad Extension](adgroup-sitelink-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Ad Group Sitelink2 Ad Extension](ad-group-sitelink2-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Ad Group Structured Snippet Ad Extension](ad-group-structured-snippet-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[App Ad Extension](app-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[App Install Ad](app-install-ad.md)|SearchAndContent         
[App Install Ad Label](app-install-ad-label.md)|SearchAndContent         
[Budget](budget.md)|All         
[Call Ad Extension](call-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Callout Ad Extension](callout-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign](campaign.md)|All         
[Campaign Age Criterion](campaign-age-criterion.md)|All         
[Campaign App Ad Extension](campaign-app-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign Call Ad Extension](campaign-call-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign Callout Ad Extension](campaign-callout-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign DayTime Criterion](campaign-daytime-criterion.md)|All         
[Campaign DeviceOS Criterion](campaign-deviceos-criterion.md)|All         
[Campaign Gender Criterion](campaign-gender-criterion.md)|All         
[Campaign Label](campaign-label.md)|All         
[Campaign Location Ad Extension](campaign-location-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign Location Criterion](campaign-location-criterion.md)|All         
[Campaign Location Intent Criterion](campaign-location-intent-criterion.md)|All         
[Campaign Negative Dynamic Search Ad Target](campaign-negative-dynamic-search-ad-target.md)|DynamicSearchAds         
[Campaign Negative Keyword](campaign-negative-keyword.md)|All         
[Campaign Negative Keyword List Association](campaign-negative-keyword-list-association.md)|All         
[Campaign Negative Location Criterion](campaign-negative-location-criterion.md)|All         
[Campaign Negative Site](campaign-negative-site.md)|All         
[Campaign Price Ad Extension](campaign-price-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign Product Scope](campaign-product-scope.md)|Shopping         
[Campaign Radius Criterion](campaign-radius-criterion.md)|All         
[Campaign Review Ad Extension](campaign-review-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign Sitelink Ad Extension](campaign-sitelink-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign Sitelink2 Ad Extension](campaign-sitelink2-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Campaign Structured Snippet Ad Extension](campaign-structured-snippet-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Custom Audience](custom-audience.md)<br /><br />Only update is supported for upload. You cannot add or delete a custom audience using the Bing Ads API.|All         
[Dynamic Search Ad](dynamic-search-ad.md)|DynamicSearchAds         
[Dynamic Search Ad Label](dynamic-search-ad-label.md)|DynamicSearchAds         
[Expanded Text Ad](expanded-text-ad.md)|SearchAndContent         
[Expanded Text Ad Label](expanded-text-ad-label.md)|SearchAndContent         
[Format Version](format-version.md)|All         
[Image Ad Extension](image-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[In Market Audience](in-market-audience.md)<br /><br />Bulk upload is not supported. You cannot add, update, or delete an in-market audience using the Bing Ads API.|All         
[Keyword](keyword.md)|SearchAndContent         
[Keyword Label](keyword-label.md)|SearchAndContent         
[Keyword Best Position Bid](keyword-best-position-bid.md)|SearchAndContent         
[Keyword First Page Bid](keyword-first-page-bid.md)|SearchAndContent         
[Keyword Main Line Bid](keyword-main-line-bid.md)|SearchAndContent         
[Label](label.md)|All         
[Location Ad Extension](location-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Negative Keyword List](negative-keyword-list.md)|All         
[Offline Conversion](offline-conversion.md)<br /><br />Bulk upload only supports adding new offline conversion data. Bulk download, bulk upload update, and bulk upload delete  operations are not supported. |All         
[Price Ad Extension](price-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Product Ad](product-ad.md)|Shopping         
[Product Ad Label](product-ad-label.md)|Shopping         
[Remarketing List](remarketing-list.md)|All         
[Review Ad Extension](review-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Shared Negative Keyword](shared-negative-keyword.md)|All         
[Sitelink Ad Extension](sitelink-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Sitelink2 Ad Extension](sitelink2-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Structured Snippet Ad Extension](structured-snippet-ad-extension.md)|SearchAndContent<br/>DynamicSearchAds         
[Text Ad](text-ad.md)|SearchAndContent         
[Text Ad Label](text-ad-label.md)|SearchAndContent         

## <a name="typehierarchy"></a>Type Hierarchy
The download file will always include a record for the [Format Version](format-version.md) and [Account](account.md) record types. For upload, the [Format Version](format-version.md) is required and must precede all other record types in the bulk file.  

-  If a parent entity is created in the same file, it should precede any dependent child records in the bulk file. For example as shown in the diagram below, when associating a site link ad extension with a campaign, the [Campaign Sitelink Ad Extension](campaign-sitelink-ad-extension.md) record must be included in the file after both the [Campaign](campaign.md) and [Sitelink Ad Extension](sitelink-ad-extension.md) records. The *Id* and *Parent Id* fields of the [Campaign Sitelink Ad Extension](campaign-sitelink-ad-extension.md) record should be set to the identifier of the [Sitelink Ad Extension](sitelink-ad-extension.md) and [Campaign](campaign.md) records respectively. If the [Sitelink Ad Extension](sitelink-ad-extension.md) and [Campaign](campaign.md) records are also new and do not yet have assigned Bing Ads identifiers, then you should use [Reference Keys](#referencekeys).  

  ![Record Type Hierarchy](media/bulkrecordhierarchy.gif)

-  It is not required to include the record for a parent entity that already has been assigned a valid Bing Ads identifier.

-  Partial success is supported when adding, updating, and deleting bulk file records. For example if you try to add three campaigns and only two are correctly specified in the file, then two will be added. The results file will include details for both successful [Campaign](campaign.md) records, one attempted [Campaign](campaign.md) record, and one *Campaign Error* record.

-  If the new campaign identifier is not yet known, for example when adding a campaign, ad group, text ad, and keyword in the same file, specify the *Campaign* name as the [Logical Reference Key](#logicalkey) for any child records. It is not necessary to specify an existing parent in the upload.

-  Partial updates are supported for bulk records including negative keywords, negative sites, and target criterions. For example you can update the bid of a single location criterion, and you do not need to download and upload the entire set of target criterions for the campaign or ad group. 
-  When updating a record, the *Id* field for the updated record is required. The *Parent Id* or [Reference Keys](#referencekeys) to the parent record is also required.

-  When updating the campaign or ad group name, it is optional to specify the new name for the child records if the correct *Parent Id* is provided.

-  Use the reserved *delete_value* string to delete or empty the existing value of an optional field. If you use *delete_value* in required fields, please note the following.

-  If you use the reserved *delete_value* string in place of a required string value, *delete_value* will be ignored and the results file will show *delete_value* in that field. For example if you set the *Budget* field of the [Campaign](campaign.md) record to *delete_value*, then the *Budget* field would be set to *delete_value* in the results file. In this example the campaign's budget would not be updated.

-  If you use the reserved *delete_value* string in place of a required value set, the results file will return the default value. For example if you set the *Network Distribution* field of the [Ad Group](ad-group.md) record to *delete_value*, then the *Network Distribution* field would be set to *OwnedAndOperatedAndSyndicatedSearch* in the results file.  In this example the ad group's network distribution would be set to *OwnedAndOperatedAndSyndicatedSearch*.

-  If you are replacing one set of records with another set then you must specify the deleted records prior to the new set. For example to replace all existing [Campaign Negative Keyword](campaign-negative-keyword.md) for a given campaign, first include a [Campaign Negative Keyword](campaign-negative-keyword.md) with *Status* set to Deleted and *Parent Id* set to the campaign ID. If you do not specify any *Id* i.e., do not attempt to delete a specific camapaign negative keyword, this will effectively delete all [Campaign Negative Keyword](campaign-negative-keyword.md) for that campaign. Below the "delete all" record, you can include one or more new [Campaign Negative Keyword](campaign-negative-keyword.md) records with all of the required properties for the upload add operation. 
  > [!NOTE]
  > Target criterion records do not support "delete all" for bulk upload; however, you might observe a null *Id* field because Bing Ads API version 10 supported "delete all" for targets.

-  If you are replacing an existing record with a new record that has the same unique properties, then you must specify the deleted record prior to the new record. For example to replace an existing [Ad Group Dynamic Search Ad Target](ad-group-dynamic-search-ad-target.md) for a given ad group, first include an [Ad Group Dynamic Search Ad Target](ad-group-dynamic-search-ad-target.md) with *Status* set to Deleted, *Id* set to the existing dynamic ad target (webpage criterion) ID, and *Parent Id* set to the ad group ID. Below the deleted record, you can include a new [Ad Group Dynamic Search Ad Target](ad-group-dynamic-search-ad-target.md) record (presumably with new webpage conditions). 
  > [!NOTE]
  > In most cases you can update the existing record instead of submitting separate delete and add records, for example you can update the *Bid Adjustment* field of an existing [Campaign Gender Criterion](campaign-gender-criterion.md). 

-  When deleting a record the *Id* field is required. A reference to the parent entity, whether the value is a Bing Ads assigned system identifier or a [Reference Keys](#referencekeys) for the parent record, is also required. For example when deleting an ad group, either the *Parent Id* field of the  [Ad Group](ad-group.md) record should match the *Id* field in the [Campaign](campaign.md) record or the *Campaign* field of the  [Ad Group](ad-group.md) record should match the *Campaign* field in the [Campaign](campaign.md) record. If both are provided then the *Parent Id* field of the  [Ad Group](ad-group.md) record ([Reference Keys](#referencekeys)) is ignored.

-  With a few exceptions the result file will only include the columns that you uploaded. For example if you upload a new [Ad Group Negative Keyword](ad-group-negative-keyword.md) without the *Id* column header, then the result file will not include the assigned identifier for the new negative keyword. The bulk file should contain the *Id* column; however, you should leave the *Id* empty for each new [Ad Group Negative Keyword](ad-group-negative-keyword.md). The exceptions to this rule are campaigns, ad groups, ads, and keywords in which case the result file will contain all columns regardless of the uploaded columns.  

## <a name="referencekeys"></a>Reference Keys
When referring to a preceding record in the bulk file that does not yet have an assigned Bing Ads identifier, you may use either a logical reference key or negative reference key depending on the record type.

> [!NOTE]
> If the parent entity is created in the same file, it should precede any dependent child records in the bulk file.

### <a name="negativekey"></a>Negative Reference Key
When referring to a preceding record in the bulk file that does not yet have an assigned Bing Ads identifier, you can set the extension's *Id* field to a negative number of your choice. This custom Id is known as a negative reference key. Then you may use the negative reference key within the *Id* field of a dependent record.

The first example shows how to create an [Ad Group](ad-group.md) for a new [Campaign](campaign.md). Set the *Parent Id* field in the [Ad Group](ad-group.md) record to the negative reference key of the [Campaign](campaign.md) (-111). If you will add additional records in the same file that should have the [Ad Group](ad-group.md) as their parent (e.g. [Keyword](keyword.md) or [Ad Group Callout Ad Extension](ad-group-callout-ad-extension.md)), then you should also set the *Id* field in the [Ad Group](ad-group.md) to a negative value e.g. *-1111* which can be referenced from the child records.

|Type|Id|Parent Id|
|--------|------|-------------|
|Campaign|-111||
|Ad Group|-1111|-111|

The second example shows how to create a [Campaign Callout Ad Extension](campaign-callout-ad-extension.md) for a new [Campaign](campaign.md) and a new [Callout Ad Extension](callout-ad-extension.md). The example also shows how to create an [Ad Group Callout Ad Extension](ad-group-callout-ad-extension.md) for a new [Ad Group](ad-group.md) and another new [Callout Ad Extension](callout-ad-extension.md). 
-  Set the *Parent Id* field in the [Campaign Callout Ad Extension](campaign-callout-ad-extension.md) record to the negative reference key of the [Campaign](campaign.md) (-111), and set the *Id* field in the [Campaign Callout Ad Extension](campaign-callout-ad-extension.md) record to the negative reference key of the [Callout Ad Extension](callout-ad-extension.md) (-11).
-  Set the *Parent Id* field in the [Ad Group Callout Ad Extension](ad-group-callout-ad-extension.md) record to the negative reference key of the [Ad Group](ad-group.md) (-1111), and set the *Id* field in the [Ad Group Callout Ad Extension](ad-group-callout-ad-extension.md) record to the negative reference key of the [Callout Ad Extension](callout-ad-extension.md) (-12).

|Type|Id|Parent Id|
|--------|------|-------------|
|Callout Ad Extension|-11||
|Callout Ad Extension|-12||
|Campaign|-111||
|Ad Group|-1111|-111|
|Campaign Callout Ad Extension|-11|-111|
|Ad Group Callout Ad Extension|-12|-1111|

### <a name="logicalkey"></a>Logical Reference Key
When referring to a new [Campaign](campaign.md) or [Ad Group](ad-group.md) record you can use the campaign and ad group name instead of setting the *Parent Id* field to a [Negative Reference Key](#negativekey) within the child record. For example to add a new ad group to a new campaign, and add a new keyword to the new ad group, set the *Campaign* and *Ad Group* fields in the child records as shown in the following example.

|Type|Campaign|Ad Group|
|--------|------------|------------|
|Campaign|Women's Shoes||
|Ad Group|Women's Shoes|Women's Red Shoe Sale|

## <a name="clientid"></a>Client Identifiers
Client identifiers may be used to associate input records in the bulk upload file with output records in the results file. For example when adding new records you may set the *Client Id* field to a string value of your choosing. The Bing Ads system makes no modifications to your client identifiers and passes them through to the results file for the corresponding record.

## <a name="errors"></a>Errors
The bulk download file or the bulk upload results file may contain records where the corresponding *Type* field includes the Error suffix. For example a product ad error record would have *Product Ad Error* as the *Type* field. The *Error* and *Error Number* columns will contain details about the error.

> [!NOTE]
> The upload results file may include multiple error records corresponding to the same uploaded record.

Errors related to new features such as Final URLs will include additional details about where the error occurred in the *Field Path* column. Each field path name corresponds to an element of one of the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md) data objects. For example if the *Tracking Template* field of a [Campaign](campaign.md) record does not begin with http:// or https://, {lpurl}, or {unescapedlpurl}, the value of this *Field Path* value is TrackingTemplate. The *TrackingUrlTemplate* is an element of the [Campaign](../campaign-management-service/campaign.md) data object available with the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md).

|Type|Tracking Template|Error|Error Number|Field Path|
|--------|---------------------|---------|----------------|--------------|
|Campaign Error|tracker.example.com/?season={_season}&amp;promocode={_promocode}&amp;u={lpurl}|InvalidUrlScheme|4600|TrackingTemplate|
|Campaign Error|tracker.example.com/?season={_season}&amp;promocode={_promocode}&amp;u={lpurl}|CampaignServiceInvalidUrl|2611|TrackingTemplate|
> [!IMPORTANT]
> The *Field Path* value is subject to change, so you should not take a dependency on the current string format.
> The *Field Path* is not supported for all errors. It is supported for *Mobile Final Url*, *Final Url*, *Tracking Template*, and *Custom Parameter* fields of the respective [Campaign](campaign.md), [Ad Group](ad-group.md), [Expanded Text Ad](expanded-text-ad.md), [Product Ad](product-ad.md), [Ad Group Product Partition](ad-group-product-partition.md), [Keyword](keyword.md), and [Sitelink Ad Extension](sitelink-ad-extension.md) records. It is also supported for errors related to all fields of the [Callout Ad Extension](callout-ad-extension.md) and [Review Ad Extension](review-ad-extension.md) records.

If the issue is related to an editorial error, then the *Editorial Location*, *Editorial Term*, *Editorial Reason Code*, and *Publisher Countries* columns may also contain more information about the error.

For example if you attempt to set the *Promotion* for *Product Ad* to www.bing.com, the file returned will include the following columns with corresponding values for the record.

|Type|Promotion|Editorial Location|Editorial Term|Editorial Reason Code|Error|Error Number|
|--------|-------------|----------------------|------------------|-------------------------|---------|----------------|
|Product Ad Error|www.bing.com|AdDescription|bing|17|CampaignServiceEditorialValidationError|1042|
For more information, see [Bing Ads Operation Error Codes](../guides/operation-error-codes.md) and [Bing Ads Editorial Failure Reason Codes](../guides/editorial-failure-reason-codes.md).

