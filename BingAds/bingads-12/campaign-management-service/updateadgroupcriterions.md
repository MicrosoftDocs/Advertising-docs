---
title: UpdateAdGroupCriterions Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates one or more ad group criterions.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UpdateAdGroupCriterions Service Operation - Campaign Management
Updates one or more ad group criterions.

## <a name="request"></a>Request Elements
The *UpdateAdGroupCriterionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterions"></a>AdGroupCriterions|The list of criterions to update.<br/><br/>You can include up to 1,000 ad group criterions per request.<br /><br />Within each [AdGroupCriterion](adgroupcriterion.md) object, you must specify the criterion's ID and the ID of the ad group that it belongs to.|[AdGroupCriterion](adgroupcriterion.md) array|
|<a name="criteriontype"></a>CriterionType|The type of criterion to update, for example *Webpage*. You can specify only one criterion type value per call.<br/><br/>To add, delete, or update target criterions i.e., age, day and time, device, gender, location, location intent, and radius criterions, you must specify the *CriterionType* value as *Targets*. You can add, delete, and update multiple target criterion types in the same operation. To retrieve these target criterions via [GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md) you must request the specific type individually i.e., *Age*, *DayTime*, *Device*, *Gender*, *Location*, *LocationIntent*, and *Radius*.<br/><br/>To add, delete, or update audience criterions i.e., custom audiences, in-market audiences, and remarketing lists, you must specify the *CriterionType* value as *Audience*.  You can add, delete, and update multiple target criterion types in the same operation. To retrieve these audience criterions via [GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md) you must request the specific type individually i.e., *Custom*, *InMarket*, and *RemarketingList*.<br/><br/> You cannot update a [ProductPartition](productpartition.md) with this operation. Instead, you should use [ApplyProductPartitionActions](applyproductpartitionactions.md).|[AdGroupCriterionType](adgroupcriteriontype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAdGroupCriterionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ismigrated"></a>IsMigrated|Indicates whether or not the ad group where you updated target criterions previously shared target criterions with another campaign or ad group. In that case this operation migrates the shared target associations and assigns new ad group criterion IDs.<br/><br/>If this value is true and if you already have criterion IDs for targets such as age, day and time, device, gender, and location, then you should replace those IDs with all of the new IDs returned by the [GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md) operation (specify *TargetCriterions* as the *CriterionType*). You only need to sync target criterion IDs, and this is not applicable for other criterion types such as webpage criterions. |**boolean**|
|<a name="nestedpartialerrors"></a>NestedPartialErrors|An array of [BatchErrorCollection](batcherrorcollection.md) objects that contain details for any criterion that were not successfully updated. The top level error within each [BatchErrorCollection](batcherrorcollection.md) object corresponds to potential criterion errors. The nested list of [BatchError](batcherror.md) objects would include any errors specific to the list of items a criterion can have.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchErrorCollection](batcherrorcollection.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">UpdateAdGroupCriterions</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateAdGroupCriterionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupCriterions i:nil="false">
        <AdGroupCriterion i:type="-- derived type specified here with the appropriate prefix --">
          <AdGroupId>ValueHere</AdGroupId>
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
            <!--These fields are applicable if the derived type attribute is set to ProfileCriterion-->
            <ProfileId>ValueHere</ProfileId>
            <ProfileType>ValueHere</ProfileType>
            <!--This field is applicable if the derived type attribute is set to Webpage-->
            <Parameter xmlns:e601="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" i:nil="false">
              <e601:Conditions i:nil="false">
                <e601:WebpageCondition>
                  <e601:Argument i:nil="false">ValueHere</e601:Argument>
                  <e601:Operand>ValueHere</e601:Operand>
                </e601:WebpageCondition>
              </e601:Conditions>
              <e601:CriterionName i:nil="false">ValueHere</e601:CriterionName>
            </Parameter>
          </Criterion>
          <Id i:nil="false">ValueHere</Id>
          <Status i:nil="false">ValueHere</Status>
          <Type i:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to BiddableAdGroupCriterion-->
          <CriterionBid i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to FixedBid-->
            <Amount>ValueHere</Amount>
            <!--This field is applicable if the derived type attribute is set to BidMultiplier-->
            <Multiplier>ValueHere</Multiplier>
          </CriterionBid>
          <DestinationUrl i:nil="false">ValueHere</DestinationUrl>
          <EditorialStatus i:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls xmlns:e602="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" i:nil="false">
            <e602:AppUrl>
              <e602:OsType i:nil="false">ValueHere</e602:OsType>
              <e602:Url i:nil="false">ValueHere</e602:Url>
            </e602:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e603="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" i:nil="false">
            <e603:Parameters i:nil="false">
              <e603:CustomParameter>
                <e603:Key i:nil="false">ValueHere</e603:Key>
                <e603:Value i:nil="false">ValueHere</e603:Value>
              </e603:CustomParameter>
            </e603:Parameters>
          </UrlCustomParameters>
          <!--No additional fields are applicable if the derived type attribute is set to NegativeAdGroupCriterion-->
        </AdGroupCriterion>
      </AdGroupCriterions>
      <CriterionType>ValueHere</CriterionType>
    </UpdateAdGroupCriterionsRequest>
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
    <UpdateAdGroupCriterionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <IsMigrated>ValueHere</IsMigrated>
      <NestedPartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchErrorCollection>
          <BatchErrors d4p1:nil="false">
            <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Code>ValueHere</Code>
              <Details d4p1:nil="false">ValueHere</Details>
              <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
              <FieldPath d4p1:nil="false">ValueHere</FieldPath>
              <ForwardCompatibilityMap xmlns:e604="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
                <e604:KeyValuePairOfstringstring>
                  <e604:key d4p1:nil="false">ValueHere</e604:key>
                  <e604:value d4p1:nil="false">ValueHere</e604:value>
                </e604:KeyValuePairOfstringstring>
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
          <ForwardCompatibilityMap xmlns:e605="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e605:KeyValuePairOfstringstring>
              <e605:key d4p1:nil="false">ValueHere</e605:key>
              <e605:value d4p1:nil="false">ValueHere</e605:value>
            </e605:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
        </BatchErrorCollection>
      </NestedPartialErrors>
    </UpdateAdGroupCriterionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateAdGroupCriterionsResponse> UpdateAdGroupCriterionsAsync(
	IList<AdGroupCriterion> adGroupCriterions,
	AdGroupCriterionType criterionType)
{
	var request = new UpdateAdGroupCriterionsRequest
	{
		AdGroupCriterions = adGroupCriterions,
		CriterionType = criterionType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateAdGroupCriterionsAsync(r), request));
}
```
```java
static UpdateAdGroupCriterionsResponse updateAdGroupCriterions(
	ArrayOfAdGroupCriterion adGroupCriterions,
	ArrayList<AdGroupCriterionType> criterionType) throws RemoteException, Exception
{
	UpdateAdGroupCriterionsRequest request = new UpdateAdGroupCriterionsRequest();

	request.setAdGroupCriterions(adGroupCriterions);
	request.setCriterionType(criterionType);

	return CampaignManagementService.getService().updateAdGroupCriterions(request);
}
```
```php
static function UpdateAdGroupCriterions(
	$adGroupCriterions,
	$criterionType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateAdGroupCriterionsRequest();

	$request->AdGroupCriterions = $adGroupCriterions;
	$request->CriterionType = $criterionType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateAdGroupCriterions($request);
}
```
```python
response=campaignmanagement_service.UpdateAdGroupCriterions(
	AdGroupCriterions=AdGroupCriterions,
	CriterionType=CriterionType)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

