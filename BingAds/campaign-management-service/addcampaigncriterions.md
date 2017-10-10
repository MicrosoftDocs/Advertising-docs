---
title: AddCampaignCriterions Service Operation
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds one or more campaign criterions that help determine whether ads in each campaign get served.
---
# AddCampaignCriterions Service Operation
Adds one or more campaign criterions that help determine whether ads in each campaign get served.

## <a name="request"></a>Request Elements
The *AddCampaignCriterionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigncriterions"></a>CampaignCriterions|A list of criterions that help determine whether ads in each campaign get served.<br/><br/>You can include up to 100 campaign criterions per request.|[CampaignCriterion](campaigncriterion.md) array|
|<a name="criteriontype"></a>CriterionType|The type of criterion to add, for example *Webpage*. You can specify only one criterion type value per call.<br/><br/>To add, delete, or update target criterions i.e., age, day and time, device, gender, location, location intent, and radius criterions, you must specify the *CriterionType* value as *Targets*. You can add, delete, and update multiple target criterion types in the same operation. To retrieve these target criterions via [GetCampaignCriterionsByIds](../campaign-management-service/getcampaigncriterionsbyids.md) you must request the specific type individually i.e., *Age*, *DayTime*, *Device*, *Gender*, *Location*, *LocationIntent*, and *Radius*.|[CampaignCriterionType](campaigncriteriontype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddCampaignCriterionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigncriterionids"></a>CampaignCriterionIds|A list of unique system identifiers corresponding to the criterion that were added.<br /><br />The list of identifiers corresponds directly to the list of criterion in the request. Items of the list may be returned as null. For each list index where a criterion was not added, the corresponding element will be null.|**long**|
|<a name="ismigrated"></a>IsMigrated|Indicates whether or not the campaign where you added target criterions previously shared target criterions with another campaign or ad group. In that case this operation migrates the shared target associations and assigns new campaign criterion IDs.<br/><br/>If this value is true and if you already have criterion IDs for targets such as age, day and time, device, gender, and location, then you should replace those IDs with all of the new IDs returned by the [GetCampaignCriterionsByIds](../campaign-management-service/getcampaigncriterionsbyids.md) operation (specify *TargetCriterions* as the *CriterionType*). You only need to sync target criterion IDs, and this is not applicable for other criterion types such as webpage criterions. |**boolean**|
|<a name="nestedpartialerrors"></a>NestedPartialErrors|An array of [BatchErrorCollection](../campaign-management-service/batcherrorcollection.md) objects that contain details for any criterion that were not successfully added. The top level error within each [BatchErrorCollection](../campaign-management-service/batcherrorcollection.md) object corresponds to potential criterion errors. The nested list of [BatchError](../campaign-management-service/batcherror.md) objects would include any errors specific to the list of items a criterion can have.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchErrorCollection](batcherrorcollection.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">AddCampaignCriterions</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddCampaignCriterionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <CampaignCriterions i:nil="false">
        <CampaignCriterion i:type="-- derived type specified here with the appropriate prefix --">
          <CampaignId>ValueHere</CampaignId>
          <Criterion i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--These fields are applicable if the derived type attribute is set to ProductPartition-->
            <Condition i:nil="false">
              <Attribute i:nil="false">ValueHere</Attribute>
              <Operand i:nil="false">ValueHere</Operand>
            </Condition>
            <ParentCriterionId i:nil="false">ValueHere</ParentCriterionId>
            <PartitionType>ValueHere</PartitionType>
            <!--This field is applicable if the derived type attribute is set to ProductScope-->
            <Conditions i:nil="false">
              <ProductCondition>
                <Attribute i:nil="false">ValueHere</Attribute>
                <Operand i:nil="false">ValueHere</Operand>
              </ProductCondition>
            </Conditions>
            <!--This field is applicable if the derived type attribute is set to AgeCriterion-->
            <AgeRange i:nil="false">ValueHere</AgeRange>
            <!--These fields are applicable if the derived type attribute is set to DeviceCriterion-->
            <DeviceName i:nil="false">ValueHere</DeviceName>
            <OSName i:nil="false">ValueHere</OSName>
            <!--These fields are applicable if the derived type attribute is set to DayTimeCriterion-->
            <Day i:nil="false">ValueHere</Day>
            <FromHour i:nil="false">ValueHere</FromHour>
            <FromMinute i:nil="false">ValueHere</FromMinute>
            <ToHour i:nil="false">ValueHere</ToHour>
            <ToMinute i:nil="false">ValueHere</ToMinute>
            <!--This field is applicable if the derived type attribute is set to GenderCriterion-->
            <GenderType i:nil="false">ValueHere</GenderType>
            <!--These fields are applicable if the derived type attribute is set to RadiusCriterion-->
            <LatitudeDegrees i:nil="false">ValueHere</LatitudeDegrees>
            <LongitudeDegrees i:nil="false">ValueHere</LongitudeDegrees>
            <Name i:nil="false">ValueHere</Name>
            <Radius i:nil="false">ValueHere</Radius>
            <RadiusUnit i:nil="false">ValueHere</RadiusUnit>
            <!--These fields are applicable if the derived type attribute is set to LocationCriterion-->
            <DisplayName i:nil="false">ValueHere</DisplayName>
            <EnclosedLocationIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
              <a1:long>ValueHere</a1:long>
            </EnclosedLocationIds>
            <LocationId i:nil="false">ValueHere</LocationId>
            <LocationType i:nil="false">ValueHere</LocationType>
            <!--This field is applicable if the derived type attribute is set to LocationIntentCriterion-->
            <IntentOption i:nil="false">ValueHere</IntentOption>
            <!--These fields are applicable if the derived type attribute is set to AudienceCriterion-->
            <AudienceId i:nil="false">ValueHere</AudienceId>
            <AudienceType i:nil="false">ValueHere</AudienceType>
            <!--This field is applicable if the derived type attribute is set to Webpage-->
            <Parameter xmlns:e741="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
              <e741:Conditions i:nil="false">
                <e741:WebpageCondition>
                  <e741:Argument i:nil="false">ValueHere</e741:Argument>
                  <e741:Operand>ValueHere</e741:Operand>
                </e741:WebpageCondition>
              </e741:Conditions>
              <e741:CriterionName i:nil="false">ValueHere</e741:CriterionName>
            </Parameter>
          </Criterion>
          <ForwardCompatibilityMap xmlns:e742="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e742:KeyValuePairOfstringstring>
              <e742:key i:nil="false">ValueHere</e742:key>
              <e742:value i:nil="false">ValueHere</e742:value>
            </e742:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <Status i:nil="false">ValueHere</Status>
          <Type i:nil="false">ValueHere</Type>
          <!--No additional fields are applicable if the derived type attribute is set to NegativeCampaignCriterion-->
          <!--This field is applicable if the derived type attribute is set to BiddableCampaignCriterion-->
          <CriterionBid i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to FixedBid-->
            <Amount>ValueHere</Amount>
            <!--This field is applicable if the derived type attribute is set to BidMultiplier-->
            <Multiplier>ValueHere</Multiplier>
          </CriterionBid>
        </CampaignCriterion>
      </CampaignCriterions>
      <CriterionType>ValueHere</CriterionType>
    </AddCampaignCriterionsRequest>
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
    <AddCampaignCriterionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <CampaignCriterionIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </CampaignCriterionIds>
      <IsMigrated>ValueHere</IsMigrated>
      <NestedPartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchErrorCollection>
          <BatchErrors d4p1:nil="false">
            <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Code>ValueHere</Code>
              <Details d4p1:nil="false">ValueHere</Details>
              <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
              <FieldPath d4p1:nil="false">ValueHere</FieldPath>
              <ForwardCompatibilityMap xmlns:e743="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
                <e743:KeyValuePairOfstringstring>
                  <e743:key d4p1:nil="false">ValueHere</e743:key>
                  <e743:value d4p1:nil="false">ValueHere</e743:value>
                </e743:KeyValuePairOfstringstring>
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
          </BatchErrors>
          <Code d4p1:nil="false">ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e744="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e744:KeyValuePairOfstringstring>
              <e744:key d4p1:nil="false">ValueHere</e744:key>
              <e744:value d4p1:nil="false">ValueHere</e744:value>
            </e744:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
        </BatchErrorCollection>
      </NestedPartialErrors>
    </AddCampaignCriterionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<AddCampaignCriterionsResponse> AddCampaignCriterionsAsync(
	IList<CampaignCriterion> campaignCriterions,
	CampaignCriterionType criterionType)
{
	var request = new AddCampaignCriterionsRequest
	{
		CampaignCriterions = campaignCriterions,
		CriterionType = criterionType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddCampaignCriterionsAsync(r), request));
}
```
```java
static AddCampaignCriterionsResponse addCampaignCriterions(
	ArrayOfCampaignCriterion campaignCriterions,
	ArrayList<CampaignCriterionType> criterionType) throws RemoteException, Exception
{
	AddCampaignCriterionsRequest request = new AddCampaignCriterionsRequest();

	request.setCampaignCriterions(campaignCriterions);
	request.setCriterionType(criterionType);

	return CampaignManagementService.getService().addCampaignCriterions(request);
}
```
```php
static function AddCampaignCriterions(
	$campaignCriterions,
	$criterionType)

	$addCampaignCriterionsRequest = new AddCampaignCriterionsRequest();

	$request->CampaignCriterions = $campaignCriterions;
	$request->CriterionType = $criterionType;

	return $CampaignManagementProxy->GetService()->AddCampaignCriterions($request);
}
```
```python
response=campaignmanagement.AddCampaignCriterions(
	CampaignCriterions=CampaignCriterionsHere,
	CriterionType=CriterionTypeHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

