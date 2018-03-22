---
title: GetAdGroupsByCampaignId Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the ad groups within the specified campaign.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAdGroupsByCampaignId Service Operation - Campaign Management
Gets the ad groups within the specified campaign.

## <a name="request"></a>Request Elements
The *GetAdGroupsByCampaignIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that contains the ad groups to get.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdGroupsByCampaignIdResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroups"></a>AdGroups|The list of ad groups within the specified campaign. If the campaign contains no ad groups, an empty array is returned.|[AdGroup](adgroup.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetAdGroupsByCampaignId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdGroupsByCampaignIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CampaignId>ValueHere</CampaignId>
    </GetAdGroupsByCampaignIdRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAdGroupsByCampaignIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroups d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdGroup>
          <AdRotation d4p1:nil="false">
            <EndDate d4p1:nil="false">ValueHere</EndDate>
            <StartDate d4p1:nil="false">ValueHere</StartDate>
            <Type d4p1:nil="false">ValueHere</Type>
          </AdRotation>
          <BiddingScheme d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to MaxClicksBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--This field is applicable if the derived type attribute is set to MaxConversionsBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--These fields are applicable if the derived type attribute is set to TargetCpaBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetCpa d4p1:nil="false">ValueHere</TargetCpa>
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpcBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to EnhancedCpcBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to InheritFromParentBiddingScheme-->
            <InheritedBidStrategyType d4p1:nil="false">ValueHere</InheritedBidStrategyType>
          </BiddingScheme>
          <CpcBid d4p1:nil="false">
            <Amount d4p1:nil="false">ValueHere</Amount>
          </CpcBid>
          <EndDate d4p1:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </EndDate>
          <ForwardCompatibilityMap xmlns:e1108="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1108:KeyValuePairOfstringstring>
              <e1108:key d4p1:nil="false">ValueHere</e1108:key>
              <e1108:value d4p1:nil="false">ValueHere</e1108:value>
            </e1108:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Language d4p1:nil="false">ValueHere</Language>
          <Name d4p1:nil="false">ValueHere</Name>
          <NativeBidAdjustment d4p1:nil="false">ValueHere</NativeBidAdjustment>
          <Network d4p1:nil="false">ValueHere</Network>
          <PrivacyStatus d4p1:nil="false">ValueHere</PrivacyStatus>
          <RemarketingTargetingSetting d4p1:nil="false">ValueHere</RemarketingTargetingSetting>
          <Settings d4p1:nil="false">
            <Setting d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Type d4p1:nil="false">ValueHere</Type>
              <!--These fields are applicable if the derived type attribute is set to ShoppingSetting-->
              <LocalInventoryAdsEnabled d4p1:nil="false">ValueHere</LocalInventoryAdsEnabled>
              <Priority d4p1:nil="false">ValueHere</Priority>
              <SalesCountryCode d4p1:nil="false">ValueHere</SalesCountryCode>
              <StoreId d4p1:nil="false">ValueHere</StoreId>
              <!--These fields are applicable if the derived type attribute is set to DynamicSearchAdsSetting-->
              <DomainName d4p1:nil="false">ValueHere</DomainName>
              <Language d4p1:nil="false">ValueHere</Language>
              <!--This field is applicable if the derived type attribute is set to TargetSetting-->
              <Details d4p1:nil="false">
                <TargetSettingDetail>
                  <CriterionTypeGroup>ValueHere</CriterionTypeGroup>
                  <TargetAll>ValueHere</TargetAll>
                </TargetSettingDetail>
              </Details>
              <!--These fields are applicable if the derived type attribute is set to CoOpSetting-->
              <BidBoostValue d4p1:nil="false">ValueHere</BidBoostValue>
              <BidMaxValue d4p1:nil="false">ValueHere</BidMaxValue>
              <BidOption d4p1:nil="false">ValueHere</BidOption>
            </Setting>
          </Settings>
          <StartDate d4p1:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </StartDate>
          <Status d4p1:nil="false">ValueHere</Status>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
        </AdGroup>
      </AdGroups>
    </GetAdGroupsByCampaignIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdGroupsByCampaignIdResponse> GetAdGroupsByCampaignIdAsync(
	long campaignId)
{
	var request = new GetAdGroupsByCampaignIdRequest
	{
		CampaignId = campaignId
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdGroupsByCampaignIdAsync(r), request));
}
```
```java
static GetAdGroupsByCampaignIdResponse getAdGroupsByCampaignId(
	java.lang.Long campaignId) throws RemoteException, Exception
{
	GetAdGroupsByCampaignIdRequest request = new GetAdGroupsByCampaignIdRequest();

	request.setCampaignId(campaignId);

	return CampaignManagementService.getService().getAdGroupsByCampaignId(request);
}
```
```php
static function GetAdGroupsByCampaignId(
	$campaignId)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdGroupsByCampaignIdRequest();

	$request->CampaignId = $campaignId;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdGroupsByCampaignId($request);
}
```
```python
response=campaignmanagement_service.GetAdGroupsByCampaignId(
	CampaignId=CampaignId)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

