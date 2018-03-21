---
title: "Release notes"
description: Identifies the changes made to Hotel Ads for each release.
ms.service: "hotel-ads"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Release notes

For information about changes that were included with each release, see the following sections.



## March 21, 2018

### Nonbreaking change

- Added [SiteMultiplier](../hotel-service/reference.md#sitemultiplier), which you use to adjust the base bid if the user is searching for hotels on one of the specified Bing sites.


## March 16, 2018

- Added the \<ExpirationTimestamp\> element to the [Transaction](../transaction-message/reference.md#resulttype) message. You use this element to specify an expiry date for the itinerary. When the expiry date passes, Bing stops serving the itinerary. 



## March 5, 2018

### Nonbreaking change

- Added the [IncludeNonPerformingHotels](../hotel-service/reference.md#includenonperforminghotels) field to the [ReportJob](../hotel-service/reference.md#reportjob) object. By default, performance reports don't include hotels that have no impressions during the reporting period. To include non-performing hotels in the report, set `IncludeNonPerformingHotels` to **true**. For limitations, see [Including non-performing hotels in the report](../hotel-service/reporting.md#including-non-performing-hotels-in-the-report).



## February 22, 2018

### Nonbreaking change

- Changed the sandbox URL that you use to get your initial sandbox account from si.bingads.microsoft.com to sandbox.bingads.microsoft.com (see [Getting sandbox credentials](../hotel-service/get-started.md#getting-sandbox-credentials)). 


## February 1, 2018

### Nonbreaking changes

- Added the following dynamic query parameters to the [URL](../pos-feed/reference.md#postype_url) element of the Points of Sale (POS) feed. [Read more](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).  
  
  - SUBACCOUNT_ID  
  - HOTELGROUP_ID  
  - SLOT_TYPE



## January 23, 2018

### Breaking changes

- Changed the Performance Report's file name from dimensionrow-\<request ID\> to performance-\<request ID\>. 


## January 18, 2018

### Nonbreaking changes

- Added support for sending [Hotel feeds](../hotel-feed/hotel-feed.md) in TSV and CSV file format. For details, see [Creating a CSV Hotel Feed](../hotel-feed/create-csv-hotel-feed.md).




## January 17, 2018

### Breaking changes coming

- If you download performance reports, be aware that the file name will soon change from dimensionrow-\<request ID\> to performance-\<request ID\>. 



## January 15, 2018

### Nonbreaking changes

- Added support for compressing the report data. Use this feature to improve download performance. For information about requesting compression, see the report job's [Compression](../hotel-service/reference.md#compression) field.


## January 8, 2018

### Nonbreaking changes

- Added support for using the OData $filter query parameter with the [/Associations](../hotel-service/reference.md#associations) resource. For information about using $filter to return associations by hotel ID, see [Filtering hotel associations](../hotel-service/manage-hotel-campaigns.md#filterassociations).


## December 15, 2017

### Nonbreaking changes

- Added [SpendUSD](../hotel-service/reporting.md#measure-columns) Performance Report column.

- Added [AverageCPCUSD](../hotel-service/reporting.md#measure-columns) Performance Report column.

## December 1, 2017

### Breaking changes

- Renamed the SpendUSD Performance Report column to [Spend](../hotel-service/reporting.md#measure-columns).  
  
- Changed the length of time that the download URL is valid. The URL now expires in seven days instead of five minutes.
  
- Changed the length of time that the report job is available. The job now expires in about seven days instead of two days.

### Documentation changes  

- Added reporting example code (see [Reporting code example](../hotel-service/code-example-reporting.md)).



## November 21, 2017

### Nonbreaking changes

- Added the Reporting API  
  
  - Added the following new URI templates:  
    - POST [/ReportJobs](../hotel-service/reference.md#addreportjob) used to add a report request to the report queue
    - GET [/ReportJobs('{jobId}')](../hotel-service/reference.md#getreportjob) used to check the status of the report job  

  - Added the [ReportJob](../hotel-service/reference.md#reportjob) object that you use to specify your report request  

  - Added the [Hotel Ads Reporting API](../hotel-service/reporting.md) overview, which details the reporting workflow.



## November 17, 2017

### Nonbreaking changes

- Added the Delete URI template for hotel groups (see [SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')](../hotel-service/reference.md#deletehotelgroup)).  



## November 8, 2017

### Nonbreaking changes

- Added the production endpoint (see [Endpoints](../hotel-service/reference.md#endpoints)).  
  
- Fixed documentation error: Removed Paused as a possible value from the `Status` field of [Hotel](../hotel-service/reference.md#hotel), [HotelGroup](../hotel-service/reference.md#hotelgroup), and [Subaccount](../hotel-service/reference.md#subaccount). 



## October 15, 2017

Released the Beta version of Hotel Ads.

### Nonbreaking changes

- Added the following ways to send Bing your transaction messages.  
  - Pull requests  
  If you sign up for pull requests, Bing sends the endpoint that you specify a [Query](../query-message/query-message.md) message that specifies the itinerary data that you should send back in a [Transaction](../transaction-message/transaction-message.md) message. With this option, you provide Bing all of your itinerary data.  
  - Pull with hints requests  
  If you sign up for pull with hints requests, Bing sends the endpoint that you specify a Query message that specifies the itinerary data that you should send back in a Transaction message. However, the query message specifies only the itinerary data that you said changed in your [Hint](../hint-message/hint-message.md) message. 
  
- Added the following messages to support the two types of pull requests.  
  - [QueryControl](../query-control-message/query-control-message.md) message  
  - [Hint](../hint-message/hint-message.md) message
  - [Query](../query-message/query-message.md) message  
  
- Increased the number of days prior to check in that users can book (advanced booking window) from 90 days to 180 days. 

## September 28, 2017

### Hotel API

#### Breaking changes

- Set default and maximum limits for the [$top](../hotel-service/reference.md#top-param) query parameter. The default value is 1,000 and the maximum value that you may specify is 5,000.  


## September 27, 2017

### Hotel API

#### Nonbreaking changes

- Added the `BidMultiplierSource` field to the [Hotel](../hotel-service/reference.md#hotel) and  [HotelGroup](../hotel-service/reference.md#hotelgroup) objects. The source field indicates whether the object inherits or defines the bid multipliers. For example, if hotel object inherits the multipliers from the subaccount, `BidMultiplierSource` is SubAccount.  
  
- Added support for the [$select](../hotel-service/reference.md#select-param) OData query parameter. You can use the parameter to select the fields that you want the response to include.  
  
- Added the steps for getting a Microsoft account to use in the sandbox environment. See [Getting SI (sandbox) credentials](../hotel-service/get-started.md#getsicredentials).



## September 8, 2017

### Hotel API

#### Breaking changes

- Limited the list of hotel associations that you may specify in a single request to 500. For information, see the [/Associate](../hotel-service/reference.md#associate) template.  
  
- Removed the `@odata.context` field from response objects. For example, the [AddResponse](../hotel-service/reference.md#addresponse) and [CollectionResponse](../hotel-service/reference.md#collectionresponse) objects no longer include the `@odata.context` field.

## August 16, 2017

Released the Alpha version of Hotel Ads. 
