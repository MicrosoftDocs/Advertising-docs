---
title: ApplyProductPartitionActions Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Applies an add, update, or delete action to each of the specified BiddableAdGroupCriterion or NegativeAdGroupCriterion, which each contain a ProductPartition.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# ApplyProductPartitionActions Service Operation - Campaign Management
Applies an add, update, or delete action to each of the specified [BiddableAdGroupCriterion](biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](negativeadgroupcriterion.md), which each contain a [ProductPartition](productpartition.md).

## <a name="request"></a>Request Elements
The *ApplyProductPartitionActionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="criterionactions"></a>CriterionActions|A list of up to 5,000 *AdGroupCriterionAction* objects that each contain an *Action* element and either a [BiddableAdGroupCriterion](biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](negativeadgroupcriterion.md). <br/><br/>All of the ad group criterion actions must be for the same ad group. For more information including validation rules, please see [Create a Bing Shopping Campaign with the Campaign Management Service](../guides/product-ads.md#bingshopping-campaignservice).|[AdGroupCriterionAction](adgroupcriterionaction.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *ApplyProductPartitionActionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterionids"></a>AdGroupCriterionIds|A list of identifiers that identify the criterion that had the action applied. The list of identifiers corresponds directly to the list of criterion in the request.<br /><br /> If any criterion action failed, then all remaining criterion actions will be rejected, and all elements in this list will be null.|**long** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.<br /><br /> For criterion which failed due to user error, an actionable error code will be returned.<br /><br /> If any criterion action failed, then all remaining criterion actions will be rejected, and none of the elements in this list will be null. For criterion that might have otherwise succeeded,  a generic error will be returned which explains that a related entity failed.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">ApplyProductPartitionActions</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <ApplyProductPartitionActionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CriterionActions i:nil="false">
        <AdGroupCriterionAction>
          <Action>ValueHere</Action>
          <AdGroupCriterion i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
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
              <!--This field is applicable if the derived type attribute is set to Webpage-->
              <Parameter i:nil="false">
                <Conditions i:nil="false">
                  <WebpageCondition>
                    <Argument i:nil="false">ValueHere</Argument>
                    <Operand>ValueHere</Operand>
                  </WebpageCondition>
                </Conditions>
                <CriterionName i:nil="false">ValueHere</CriterionName>
              </Parameter>
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
            <FinalAppUrls i:nil="false">
              <AppUrl>
                <OsType i:nil="false">ValueHere</OsType>
                <Url i:nil="false">ValueHere</Url>
              </AppUrl>
            </FinalAppUrls>
            <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
              <a1:string>ValueHere</a1:string>
            </FinalMobileUrls>
            <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
              <a1:string>ValueHere</a1:string>
            </FinalUrls>
            <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
            <UrlCustomParameters i:nil="false">
              <Parameters i:nil="false">
                <CustomParameter>
                  <Key i:nil="false">ValueHere</Key>
                  <Value i:nil="false">ValueHere</Value>
                </CustomParameter>
              </Parameters>
            </UrlCustomParameters>
            <!--No additional fields are applicable if the derived type attribute is set to NegativeAdGroupCriterion-->
          </AdGroupCriterion>
        </AdGroupCriterionAction>
      </CriterionActions>
    </ApplyProductPartitionActionsRequest>
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
    <ApplyProductPartitionActionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupCriterionIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </AdGroupCriterionIds>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1082="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1082:KeyValuePairOfstringstring>
              <e1082:key d4p1:nil="false">ValueHere</e1082:key>
              <e1082:value d4p1:nil="false">ValueHere</e1082:value>
            </e1082:KeyValuePairOfstringstring>
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
    </ApplyProductPartitionActionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<ApplyProductPartitionActionsResponse> ApplyProductPartitionActionsAsync(
	IList<AdGroupCriterionAction> criterionActions)
{
	var request = new ApplyProductPartitionActionsRequest
	{
		CriterionActions = criterionActions
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.ApplyProductPartitionActionsAsync(r), request));
}
```
```java
static ApplyProductPartitionActionsResponse applyProductPartitionActions(
	ArrayOfAdGroupCriterionAction criterionActions) throws RemoteException, Exception
{
	ApplyProductPartitionActionsRequest request = new ApplyProductPartitionActionsRequest();

	request.setCriterionActions(criterionActions);

	return CampaignManagementService.getService().applyProductPartitionActions(request);
}
```
```php
static function ApplyProductPartitionActions(
	$criterionActions)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new ApplyProductPartitionActionsRequest();

	$request->CriterionActions = $criterionActions;

	return $GLOBALS['CampaignManagementProxy']->GetService()->ApplyProductPartitionActions($request);
}
```
```python
response=campaignmanagement_service.ApplyProductPartitionActions(
	CriterionActions=CriterionActions)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

