---
title: GetConversionGoalsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the specified conversion goals.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetConversionGoalsByIds Service Operation - Campaign Management
Gets the specified conversion goals. 

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](../guides/universal-event-tracking.md) technical guide.

## <a name="request"></a>Request Elements
The *GetConversionGoalsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="conversiongoalids"></a>ConversionGoalIds|A maximum of 100 identifiers of the conversion goals that you want to get. <br /><br />If *ConversionGoalIds* is null or empty, then you are effectively requesting all conversion goals of the specified types for the account. |**long** array|
|<a name="conversiongoaltypes"></a>ConversionGoalTypes|One or more types of conversion goals to return. |[ConversionGoalType](conversiongoaltype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetConversionGoalsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="conversiongoals"></a>ConversionGoals|An array of [ConversionGoal](conversiongoal.md) objects that corresponds directly to the conversion goal identifiers that you specified in the request. Items of the array may be returned as null. For each array index where a conversion goal was not retrieved, the corresponding element will be null.|[ConversionGoal](conversiongoal.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetConversionGoalsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetConversionGoalsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <ConversionGoalIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </ConversionGoalIds>
      <ConversionGoalTypes>ValueHere</ConversionGoalTypes>
    </GetConversionGoalsByIdsRequest>
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
    <GetConversionGoalsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <ConversionGoals d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <ConversionGoal d4p1:type="-- derived type specified here with the appropriate prefix --">
          <ConversionWindowInMinutes d4p1:nil="false">ValueHere</ConversionWindowInMinutes>
          <CountType d4p1:nil="false">ValueHere</CountType>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
          <Revenue d4p1:nil="false">
            <CurrencyCode d4p1:nil="false">ValueHere</CurrencyCode>
            <Type d4p1:nil="false">ValueHere</Type>
            <Value d4p1:nil="false">ValueHere</Value>
          </Revenue>
          <Scope d4p1:nil="false">ValueHere</Scope>
          <Status d4p1:nil="false">ValueHere</Status>
          <TagId d4p1:nil="false">ValueHere</TagId>
          <TrackingStatus d4p1:nil="false">ValueHere</TrackingStatus>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to UrlGoal-->
          <UrlExpression d4p1:nil="false">ValueHere</UrlExpression>
          <UrlOperator d4p1:nil="false">ValueHere</UrlOperator>
          <!--This field is applicable if the derived type attribute is set to DurationGoal-->
          <MinimumDurationInSeconds d4p1:nil="false">ValueHere</MinimumDurationInSeconds>
          <!--This field is applicable if the derived type attribute is set to PagesViewedPerVisitGoal-->
          <MinimumPagesViewed d4p1:nil="false">ValueHere</MinimumPagesViewed>
          <!--These fields are applicable if the derived type attribute is set to EventGoal-->
          <ActionExpression d4p1:nil="false">ValueHere</ActionExpression>
          <ActionOperator d4p1:nil="false">ValueHere</ActionOperator>
          <CategoryExpression d4p1:nil="false">ValueHere</CategoryExpression>
          <CategoryOperator d4p1:nil="false">ValueHere</CategoryOperator>
          <LabelExpression d4p1:nil="false">ValueHere</LabelExpression>
          <LabelOperator d4p1:nil="false">ValueHere</LabelOperator>
          <Value d4p1:nil="false">ValueHere</Value>
          <ValueOperator d4p1:nil="false">ValueHere</ValueOperator>
          <!--These fields are applicable if the derived type attribute is set to AppInstallGoal-->
          <AppPlatform d4p1:nil="false">ValueHere</AppPlatform>
          <AppStoreId d4p1:nil="false">ValueHere</AppStoreId>
          <!--No additional fields are applicable if the derived type attribute is set to OfflineConversionGoal-->
          <!--No additional fields are applicable if the derived type attribute is set to InStoreTransactionGoal-->
        </ConversionGoal>
      </ConversionGoals>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1124="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1124:KeyValuePairOfstringstring>
              <e1124:key d4p1:nil="false">ValueHere</e1124:key>
              <e1124:value d4p1:nil="false">ValueHere</e1124:value>
            </e1124:KeyValuePairOfstringstring>
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
    </GetConversionGoalsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetConversionGoalsByIdsResponse> GetConversionGoalsByIdsAsync(
	IList<long> conversionGoalIds,
	ConversionGoalType conversionGoalTypes)
{
	var request = new GetConversionGoalsByIdsRequest
	{
		ConversionGoalIds = conversionGoalIds,
		ConversionGoalTypes = conversionGoalTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetConversionGoalsByIdsAsync(r), request));
}
```
```java
static GetConversionGoalsByIdsResponse getConversionGoalsByIds(
	ArrayOflong conversionGoalIds,
	ArrayList<ConversionGoalType> conversionGoalTypes) throws RemoteException, Exception
{
	GetConversionGoalsByIdsRequest request = new GetConversionGoalsByIdsRequest();

	request.setConversionGoalIds(conversionGoalIds);
	request.setConversionGoalTypes(conversionGoalTypes);

	return CampaignManagementService.getService().getConversionGoalsByIds(request);
}
```
```php
static function GetConversionGoalsByIds(
	$conversionGoalIds,
	$conversionGoalTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetConversionGoalsByIdsRequest();

	$request->ConversionGoalIds = $conversionGoalIds;
	$request->ConversionGoalTypes = $conversionGoalTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetConversionGoalsByIds($request);
}
```
```python
response=campaignmanagement_service.GetConversionGoalsByIds(
	ConversionGoalIds=ConversionGoalIds,
	ConversionGoalTypes=ConversionGoalTypes)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

