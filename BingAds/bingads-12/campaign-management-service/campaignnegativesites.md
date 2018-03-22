---
title: CampaignNegativeSites Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the negative site URLs of a campaign.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CampaignNegativeSites Data Object - Campaign Management
Defines an object that contains the negative site URLs of a campaign.

## Syntax
```xml
<xs:complexType name="CampaignNegativeSites" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CampaignId" type="xs:long" />
    <xs:element minOccurs="0" name="NegativeSites" nillable="true" type="q12:ArrayOfstring" xmlns:q12="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to which the negative site URLs belong.|**long**|
|<a name="negativesites"></a>NegativeSites|A list of URLs of the websites on which you do not want your ads displayed. You can specify a maximum of 2,500 URLs. Each URL must specify the domain name e.g., *contoso.com* which can include up to three subdomains and two subdirectories. The subdomain count includes the *www* prefix. For example *one.two.three.contoso.com/1/2*, *www.two.three.contoso.com/1/2*, and *one.two.contoso.co.uk/1/2* are valid URLs, whereas *one.two.three.contoso.co.uk/1/2* (too many subdomains) and *one.two.three.contoso.com/1/2/3* (too many subdirectories) are not. Duplicate URLs in the list are not added.<br /><br />You can only exclude websites for syndicated search websites. The ad group's network must be set to either *OwnedAndOperatedAndSyndicatedSearch* or *SyndicatedSearchOnly*. For more information about network distribution, see [Network](network.md).<br /><br />Negative site URLs specified at the ad group level are used instead of any negative site URLs specified at the campaign level.<br /><br />To remove all negative site URLs of the campaign, set this element to null.|**string** array|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetNegativeSitesByCampaignIds](getnegativesitesbycampaignids.md)  
[SetNegativeSitesToCampaigns](setnegativesitestocampaigns.md)  
