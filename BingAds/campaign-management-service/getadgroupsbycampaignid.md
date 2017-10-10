---
title: GetAdGroupsByCampaignId Service Operation
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the ad groups within the specified campaign.
---
# GetAdGroupsByCampaignId Service Operation
Gets the ad groups within the specified campaign.

## <a name="request"></a>Request Elements
The *GetAdGroupsByCampaignIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that contains the ad groups to get.|**long**|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|The list of additional properties that you want included within each returned [AdGroup](../campaign-management-service/adgroup.md) object. This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding elements will be included by default.|[AdGroupAdditionalField](adgroupadditionalfield.md)|

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
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
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
    <GetAdGroupsByCampaignIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <CampaignId>ValueHere</CampaignId>
      <ReturnAdditionalFields i:nil="false">ValueHere</ReturnAdditionalFields>
    </GetAdGroupsByCampaignIdRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAdGroupsByCampaignIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdGroups d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdGroup>
          <AdDistribution d4p1:nil="false">ValueHere</AdDistribution>
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
          <ContentMatchBid d4p1:nil="false">
            <Amount d4p1:nil="false">ValueHere</Amount>
          </ContentMatchBid>
          <EndDate d4p1:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </EndDate>
          <ForwardCompatibilityMap xmlns:e815="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e815:KeyValuePairOfstringstring>
              <e815:key d4p1:nil="false">ValueHere</e815:key>
              <e815:value d4p1:nil="false">ValueHere</e815:value>
            </e815:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Language d4p1:nil="false">ValueHere</Language>
          <Name d4p1:nil="false">ValueHere</Name>
          <NativeBidAdjustment d4p1:nil="false">ValueHere</NativeBidAdjustment>
          <Network d4p1:nil="false">ValueHere</Network>
          <PricingModel d4p1:nil="false">ValueHere</PricingModel>
          <RemarketingTargetingSetting d4p1:nil="false">ValueHere</RemarketingTargetingSetting>
          <SearchBid d4p1:nil="false">
            <Amount d4p1:nil="false">ValueHere</Amount>
          </SearchBid>
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
            </Setting>
          </Settings>
          <StartDate d4p1:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </StartDate>
          <Status d4p1:nil="false">ValueHere</Status>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e816="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e816:Parameters d4p1:nil="false">
              <e816:CustomParameter>
                <e816:Key d4p1:nil="false">ValueHere</e816:Key>
                <e816:Value d4p1:nil="false">ValueHere</e816:Value>
              </e816:CustomParameter>
            </e816:Parameters>
          </UrlCustomParameters>
        </AdGroup>
      </AdGroups>
    </GetAdGroupsByCampaignIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdGroupsByCampaignIdResponse> GetAdGroupsByCampaignIdAsync(
	long campaignId,
	AdGroupAdditionalField? returnAdditionalFields)
{
	var request = new GetAdGroupsByCampaignIdRequest
	{
		CampaignId = campaignId,
		ReturnAdditionalFields = returnAdditionalFields
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdGroupsByCampaignIdAsync(r), request));
}
```
```java
static GetAdGroupsByCampaignIdResponse getAdGroupsByCampaignId(
	java.lang.Long campaignId,
	ArrayList<AdGroupAdditionalField> returnAdditionalFields) throws RemoteException, Exception
{
	GetAdGroupsByCampaignIdRequest request = new GetAdGroupsByCampaignIdRequest();

	request.setCampaignId(campaignId);
	request.setReturnAdditionalFields(returnAdditionalFields);

	return CampaignManagementService.getService().getAdGroupsByCampaignId(request);
}
```
```php
static function GetAdGroupsByCampaignId(
	$campaignId,
	$returnAdditionalFields)

	$getAdGroupsByCampaignIdRequest = new GetAdGroupsByCampaignIdRequest();

	$request->CampaignId = $campaignId;
	$request->ReturnAdditionalFields = $returnAdditionalFields;

	return $CampaignManagementProxy->GetService()->GetAdGroupsByCampaignId($request);
}
```
```python
response=campaignmanagement.GetAdGroupsByCampaignId(
	CampaignId=CampaignIdHere,
	ReturnAdditionalFields=ReturnAdditionalFieldsHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

