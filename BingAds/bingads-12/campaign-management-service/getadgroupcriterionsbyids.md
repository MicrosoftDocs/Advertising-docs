---
title: GetAdGroupCriterionsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets ad group criterions by identifiers and types.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAdGroupCriterionsByIds Service Operation - Campaign Management
Gets ad group criterions by identifiers and types.

## <a name="request"></a>Request Elements
The *GetAdGroupCriterionsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterionids"></a>AdGroupCriterionIds|A list of unique identifiers that identify the criterions to get.<br/><br/>You can include up to 1,000 ad group criterion identifiers per request. <br /><br />If this element is null, all criterions for the specified *AdGroupId* will be retrieved.|**long** array|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that owns the criterions to get.|**long**|
|<a name="criteriontype"></a>CriterionType|The type of criterion to get, for example *Webpage*. You can specify only one type. The *Targets* and *Audience* values are not allowed for this operation.|[AdGroupCriterionType](adgroupcriteriontype.md)|
|<a name="returnagegenderunknownvalue"></a>ReturnAgeGenderUnknownValue|Reserved.|**boolean**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdGroupCriterionsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterions"></a>AdGroupCriterions|The list of criterions that correspond directly to the identifiers specified in the request. If an identifier in the list is not valid, the corresponding item in the response is set to null.|[AdGroupCriterion](adgroupcriterion.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetAdGroupCriterionsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdGroupCriterionsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupCriterionIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdGroupCriterionIds>
      <ReturnAgeGenderUnknownValue i:nil="false">ValueHere</ReturnAgeGenderUnknownValue>
      <AdGroupId>ValueHere</AdGroupId>
      <CriterionType>ValueHere</CriterionType>
    </GetAdGroupCriterionsByIdsRequest>
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
    <GetAdGroupCriterionsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupCriterions d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdGroupCriterion d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AdGroupId>ValueHere</AdGroupId>
          <Criterion d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--These fields are applicable if the derived type attribute is set to ProductPartition-->
            <Condition d4p1:nil="false">
              <Attribute d4p1:nil="false">ValueHere</Attribute>
              <Operand d4p1:nil="false">ValueHere</Operand>
            </Condition>
            <ParentCriterionId d4p1:nil="false">ValueHere</ParentCriterionId>
            <PartitionType>ValueHere</PartitionType>
            <!--This field is applicable if the derived type attribute is set to ProductScope-->
            <Conditions d4p1:nil="false">
              <ProductCondition>
                <Attribute d4p1:nil="false">ValueHere</Attribute>
                <Operand d4p1:nil="false">ValueHere</Operand>
              </ProductCondition>
            </Conditions>
            <!--This field is applicable if the derived type attribute is set to Webpage-->
            <Parameter d4p1:nil="false">
              <Conditions d4p1:nil="false">
                <WebpageCondition>
                  <Argument d4p1:nil="false">ValueHere</Argument>
                  <Operand>ValueHere</Operand>
                </WebpageCondition>
              </Conditions>
              <CriterionName d4p1:nil="false">ValueHere</CriterionName>
            </Parameter>
            <!--This field is applicable if the derived type attribute is set to AgeCriterion-->
            <AgeRange d4p1:nil="false">ValueHere</AgeRange>
            <!--These fields are applicable if the derived type attribute is set to DeviceCriterion-->
            <DeviceName d4p1:nil="false">ValueHere</DeviceName>
            <OSName d4p1:nil="false">ValueHere</OSName>
            <!--These fields are applicable if the derived type attribute is set to DayTimeCriterion-->
            <Day d4p1:nil="false">ValueHere</Day>
            <FromHour d4p1:nil="false">ValueHere</FromHour>
            <FromMinute d4p1:nil="false">ValueHere</FromMinute>
            <ToHour d4p1:nil="false">ValueHere</ToHour>
            <ToMinute d4p1:nil="false">ValueHere</ToMinute>
            <!--This field is applicable if the derived type attribute is set to GenderCriterion-->
            <GenderType d4p1:nil="false">ValueHere</GenderType>
            <!--These fields are applicable if the derived type attribute is set to RadiusCriterion-->
            <LatitudeDegrees d4p1:nil="false">ValueHere</LatitudeDegrees>
            <LongitudeDegrees d4p1:nil="false">ValueHere</LongitudeDegrees>
            <Name d4p1:nil="false">ValueHere</Name>
            <Radius d4p1:nil="false">ValueHere</Radius>
            <RadiusUnit d4p1:nil="false">ValueHere</RadiusUnit>
            <!--These fields are applicable if the derived type attribute is set to LocationCriterion-->
            <DisplayName d4p1:nil="false">ValueHere</DisplayName>
            <EnclosedLocationIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
              <a1:long>ValueHere</a1:long>
            </EnclosedLocationIds>
            <LocationId d4p1:nil="false">ValueHere</LocationId>
            <LocationType d4p1:nil="false">ValueHere</LocationType>
            <!--This field is applicable if the derived type attribute is set to LocationIntentCriterion-->
            <IntentOption d4p1:nil="false">ValueHere</IntentOption>
            <!--These fields are applicable if the derived type attribute is set to AudienceCriterion-->
            <AudienceId d4p1:nil="false">ValueHere</AudienceId>
            <AudienceType d4p1:nil="false">ValueHere</AudienceType>
            <!--These fields are applicable if the derived type attribute is set to ProfileCriterion-->
            <ProfileId>ValueHere</ProfileId>
            <ProfileType>ValueHere</ProfileType>
          </Criterion>
          <Id d4p1:nil="false">ValueHere</Id>
          <Status d4p1:nil="false">ValueHere</Status>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to BiddableAdGroupCriterion-->
          <CriterionBid d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to FixedBid-->
            <Amount>ValueHere</Amount>
            <!--This field is applicable if the derived type attribute is set to BidMultiplier-->
            <Multiplier>ValueHere</Multiplier>
          </CriterionBid>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls d4p1:nil="false">
            <AppUrl>
              <OsType d4p1:nil="false">ValueHere</OsType>
              <Url d4p1:nil="false">ValueHere</Url>
            </AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--No additional fields are applicable if the derived type attribute is set to NegativeAdGroupCriterion-->
        </AdGroupCriterion>
      </AdGroupCriterions>
    </GetAdGroupCriterionsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdGroupCriterionsByIdsResponse> GetAdGroupCriterionsByIdsAsync(
	IList<long> adGroupCriterionIds,
	bool? returnAgeGenderUnknownValue,
	long adGroupId,
	AdGroupCriterionType criterionType)
{
	var request = new GetAdGroupCriterionsByIdsRequest
	{
		AdGroupCriterionIds = adGroupCriterionIds,
		ReturnAgeGenderUnknownValue = returnAgeGenderUnknownValue,
		AdGroupId = adGroupId,
		CriterionType = criterionType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdGroupCriterionsByIdsAsync(r), request));
}
```
```java
static GetAdGroupCriterionsByIdsResponse getAdGroupCriterionsByIds(
	ArrayOflong adGroupCriterionIds,
	boolean returnAgeGenderUnknownValue,
	java.lang.Long adGroupId,
	ArrayList<AdGroupCriterionType> criterionType) throws RemoteException, Exception
{
	GetAdGroupCriterionsByIdsRequest request = new GetAdGroupCriterionsByIdsRequest();

	request.setAdGroupCriterionIds(adGroupCriterionIds);
	request.setReturnAgeGenderUnknownValue(returnAgeGenderUnknownValue);
	request.setAdGroupId(adGroupId);
	request.setCriterionType(criterionType);

	return CampaignManagementService.getService().getAdGroupCriterionsByIds(request);
}
```
```php
static function GetAdGroupCriterionsByIds(
	$adGroupCriterionIds,
	$returnAgeGenderUnknownValue,
	$adGroupId,
	$criterionType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdGroupCriterionsByIdsRequest();

	$request->AdGroupCriterionIds = $adGroupCriterionIds;
	$request->ReturnAgeGenderUnknownValue = $returnAgeGenderUnknownValue;
	$request->AdGroupId = $adGroupId;
	$request->CriterionType = $criterionType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdGroupCriterionsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdGroupCriterionsByIds(
	AdGroupCriterionIds=AdGroupCriterionIds,
	ReturnAgeGenderUnknownValue=ReturnAgeGenderUnknownValue,
	AdGroupId=AdGroupId,
	CriterionType=CriterionType)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

