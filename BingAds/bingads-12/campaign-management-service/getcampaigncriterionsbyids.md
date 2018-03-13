---
title: GetCampaignCriterionsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the specified campaign criterions.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetCampaignCriterionsByIds Service Operation - Campaign Management
Gets the specified campaign criterions.

## <a name="request"></a>Request Elements
The *GetCampaignCriterionsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigncriterionids"></a>CampaignCriterionIds|A list of unique identifiers that identify the campaign criterions to get.<br/><br/>You can include up to 100 campaign criterion identifiers per request.<br /><br />If this element is null, all criterions for the specified *CampaignId* will be retrieved.|**long** array|
|<a name="campaignid"></a>CampaignId|The unique identifier of the campaign whose criterions you want to get.|**long**|
|<a name="criteriontype"></a>CriterionType|The type of criterion to get, for example *Webpage*. You can specify only one type. The *Targets* value is not allowed for this operation.|[CampaignCriterionType](campaigncriteriontype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetCampaignCriterionsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigncriterions"></a>CampaignCriterions|The list of campaign criterions that correspond directly to the identifiers specified in the request. Items of the list may be returned as null. For each list index where a criterion was not retrieved, the corresponding element will be null.|[CampaignCriterion](campaigncriterion.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetCampaignCriterionsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCampaignCriterionsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CampaignCriterionIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </CampaignCriterionIds>
      <CampaignId>ValueHere</CampaignId>
      <CriterionType>ValueHere</CriterionType>
    </GetCampaignCriterionsByIdsRequest>
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
    <GetCampaignCriterionsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CampaignCriterions d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <CampaignCriterion d4p1:type="-- derived type specified here with the appropriate prefix --">
          <CampaignId>ValueHere</CampaignId>
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
            <!--This field is applicable if the derived type attribute is set to Webpage-->
            <Parameter xmlns:e548="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" d4p1:nil="false">
              <e548:Conditions d4p1:nil="false">
                <e548:WebpageCondition>
                  <e548:Argument d4p1:nil="false">ValueHere</e548:Argument>
                  <e548:Operand>ValueHere</e548:Operand>
                </e548:WebpageCondition>
              </e548:Conditions>
              <e548:CriterionName d4p1:nil="false">ValueHere</e548:CriterionName>
            </Parameter>
          </Criterion>
          <ForwardCompatibilityMap xmlns:e549="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e549:KeyValuePairOfstringstring>
              <e549:key d4p1:nil="false">ValueHere</e549:key>
              <e549:value d4p1:nil="false">ValueHere</e549:value>
            </e549:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Status d4p1:nil="false">ValueHere</Status>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--No additional fields are applicable if the derived type attribute is set to NegativeCampaignCriterion-->
          <!--This field is applicable if the derived type attribute is set to BiddableCampaignCriterion-->
          <CriterionBid d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to FixedBid-->
            <Amount>ValueHere</Amount>
            <!--This field is applicable if the derived type attribute is set to BidMultiplier-->
            <Multiplier>ValueHere</Multiplier>
          </CriterionBid>
        </CampaignCriterion>
      </CampaignCriterions>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e550="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e550:KeyValuePairOfstringstring>
              <e550:key d4p1:nil="false">ValueHere</e550:key>
              <e550:value d4p1:nil="false">ValueHere</e550:value>
            </e550:KeyValuePairOfstringstring>
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
    </GetCampaignCriterionsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetCampaignCriterionsByIdsResponse> GetCampaignCriterionsByIdsAsync(
	IList<long> campaignCriterionIds,
	long campaignId,
	CampaignCriterionType criterionType)
{
	var request = new GetCampaignCriterionsByIdsRequest
	{
		CampaignCriterionIds = campaignCriterionIds,
		CampaignId = campaignId,
		CriterionType = criterionType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetCampaignCriterionsByIdsAsync(r), request));
}
```
```java
static GetCampaignCriterionsByIdsResponse getCampaignCriterionsByIds(
	ArrayOflong campaignCriterionIds,
	java.lang.Long campaignId,
	ArrayList<CampaignCriterionType> criterionType) throws RemoteException, Exception
{
	GetCampaignCriterionsByIdsRequest request = new GetCampaignCriterionsByIdsRequest();

	request.setCampaignCriterionIds(campaignCriterionIds);
	request.setCampaignId(campaignId);
	request.setCriterionType(criterionType);

	return CampaignManagementService.getService().getCampaignCriterionsByIds(request);
}
```
```php
static function GetCampaignCriterionsByIds(
	$campaignCriterionIds,
	$campaignId,
	$criterionType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetCampaignCriterionsByIdsRequest();

	$request->CampaignCriterionIds = $campaignCriterionIds;
	$request->CampaignId = $campaignId;
	$request->CriterionType = $criterionType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetCampaignCriterionsByIds($request);
}
```
```python
response=campaignmanagement_service.GetCampaignCriterionsByIds(
	CampaignCriterionIds=CampaignCriterionIds,
	CampaignId=CampaignId,
	CriterionType=CriterionType)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

