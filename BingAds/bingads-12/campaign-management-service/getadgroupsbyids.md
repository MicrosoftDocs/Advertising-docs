---
title: GetAdGroupsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the specified ad groups within the specified campaign.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAdGroupsByIds Service Operation - Campaign Management
Gets the specified ad groups within the specified campaign.

## <a name="request"></a>Request Elements
The *GetAdGroupsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupids"></a>AdGroupIds|A maximum of 1,000 identifiers of the ad groups to get.|**long** array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that contains the ad groups to get.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdGroupsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroups"></a>AdGroups|The list of ad groups that correspond directly to the ad group identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an ad group was not retrieved, the corresponding element will be null.|[AdGroup](adgroup.md) array|
|<a name="partialerrors"></a>PartialErrors|The list of batch errors that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetAdGroupsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdGroupsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CampaignId>ValueHere</CampaignId>
      <AdGroupIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdGroupIds>
    </GetAdGroupsByIdsRequest>
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
    <GetAdGroupsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
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
          <ForwardCompatibilityMap xmlns:e1109="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1109:KeyValuePairOfstringstring>
              <e1109:key d4p1:nil="false">ValueHere</e1109:key>
              <e1109:value d4p1:nil="false">ValueHere</e1109:value>
            </e1109:KeyValuePairOfstringstring>
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
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1110="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1110:KeyValuePairOfstringstring>
              <e1110:key d4p1:nil="false">ValueHere</e1110:key>
              <e1110:value d4p1:nil="false">ValueHere</e1110:value>
            </e1110:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to EditorialError-->
          <Appealable d4p1:nil="false">ValueHere</Appealable>
          <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
          <Location d4p1:nil="false">ValueHere</Location>
          <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
          <ReasonCode>ValueHere</ReasonCode>
        </BatchError>
      </PartialErrors>
    </GetAdGroupsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdGroupsByIdsResponse> GetAdGroupsByIdsAsync(
	long campaignId,
	IList<long> adGroupIds)
{
	var request = new GetAdGroupsByIdsRequest
	{
		CampaignId = campaignId,
		AdGroupIds = adGroupIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdGroupsByIdsAsync(r), request));
}
```
```java
static GetAdGroupsByIdsResponse getAdGroupsByIds(
	java.lang.Long campaignId,
	ArrayOflong adGroupIds) throws RemoteException, Exception
{
	GetAdGroupsByIdsRequest request = new GetAdGroupsByIdsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroupIds(adGroupIds);

	return CampaignManagementService.getService().getAdGroupsByIds(request);
}
```
```php
static function GetAdGroupsByIds(
	$campaignId,
	$adGroupIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdGroupsByIdsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroupIds = $adGroupIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdGroupsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdGroupsByIds(
	CampaignId=CampaignId,
	AdGroupIds=AdGroupIds)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

