---
title: UpdateConversionGoals Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates conversion goals within the account's shared conversion goal library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UpdateConversionGoals Service Operation - Campaign Management
Updates conversion goals within the account's shared conversion goal library. 

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](../guides/universal-event-tracking.md) technical guide.

## <a name="request"></a>Request Elements
The *UpdateConversionGoalsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="conversiongoals"></a>ConversionGoals|An array of [ConversionGoal](conversiongoal.md) objects to update within the account's shared conversion goal library.<br /><br />You can update a maximum of 100 conversion goals in a single call. <br/><br/>The account is determined by the required *CustomerAccountId* header element.|[ConversionGoal](conversiongoal.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateConversionGoalsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">UpdateConversionGoals</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateConversionGoalsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <ConversionGoals i:nil="false">
        <ConversionGoal i:type="-- derived type specified here with the appropriate prefix --">
          <ConversionWindowInMinutes i:nil="false">ValueHere</ConversionWindowInMinutes>
          <CountType i:nil="false">ValueHere</CountType>
          <Id i:nil="false">ValueHere</Id>
          <Name i:nil="false">ValueHere</Name>
          <Revenue i:nil="false">
            <CurrencyCode i:nil="false">ValueHere</CurrencyCode>
            <Type i:nil="false">ValueHere</Type>
            <Value i:nil="false">ValueHere</Value>
          </Revenue>
          <Scope i:nil="false">ValueHere</Scope>
          <Status i:nil="false">ValueHere</Status>
          <TagId i:nil="false">ValueHere</TagId>
          <TrackingStatus i:nil="false">ValueHere</TrackingStatus>
          <Type i:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to UrlGoal-->
          <UrlExpression i:nil="false">ValueHere</UrlExpression>
          <UrlOperator i:nil="false">ValueHere</UrlOperator>
          <!--This field is applicable if the derived type attribute is set to DurationGoal-->
          <MinimumDurationInSeconds i:nil="false">ValueHere</MinimumDurationInSeconds>
          <!--This field is applicable if the derived type attribute is set to PagesViewedPerVisitGoal-->
          <MinimumPagesViewed i:nil="false">ValueHere</MinimumPagesViewed>
          <!--These fields are applicable if the derived type attribute is set to EventGoal-->
          <ActionExpression i:nil="false">ValueHere</ActionExpression>
          <ActionOperator i:nil="false">ValueHere</ActionOperator>
          <CategoryExpression i:nil="false">ValueHere</CategoryExpression>
          <CategoryOperator i:nil="false">ValueHere</CategoryOperator>
          <LabelExpression i:nil="false">ValueHere</LabelExpression>
          <LabelOperator i:nil="false">ValueHere</LabelOperator>
          <Value i:nil="false">ValueHere</Value>
          <ValueOperator i:nil="false">ValueHere</ValueOperator>
          <!--These fields are applicable if the derived type attribute is set to AppInstallGoal-->
          <AppPlatform i:nil="false">ValueHere</AppPlatform>
          <AppStoreId i:nil="false">ValueHere</AppStoreId>
          <!--No additional fields are applicable if the derived type attribute is set to OfflineConversionGoal-->
          <!--No additional fields are applicable if the derived type attribute is set to InStoreTransactionGoal-->
        </ConversionGoal>
      </ConversionGoals>
    </UpdateConversionGoalsRequest>
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
    <UpdateConversionGoalsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1240="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1240:KeyValuePairOfstringstring>
              <e1240:key d4p1:nil="false">ValueHere</e1240:key>
              <e1240:value d4p1:nil="false">ValueHere</e1240:value>
            </e1240:KeyValuePairOfstringstring>
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
    </UpdateConversionGoalsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateConversionGoalsResponse> UpdateConversionGoalsAsync(
	IList<ConversionGoal> conversionGoals)
{
	var request = new UpdateConversionGoalsRequest
	{
		ConversionGoals = conversionGoals
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateConversionGoalsAsync(r), request));
}
```
```java
static UpdateConversionGoalsResponse updateConversionGoals(
	ArrayOfConversionGoal conversionGoals) throws RemoteException, Exception
{
	UpdateConversionGoalsRequest request = new UpdateConversionGoalsRequest();

	request.setConversionGoals(conversionGoals);

	return CampaignManagementService.getService().updateConversionGoals(request);
}
```
```php
static function UpdateConversionGoals(
	$conversionGoals)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateConversionGoalsRequest();

	$request->ConversionGoals = $conversionGoals;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateConversionGoals($request);
}
```
```python
response=campaignmanagement_service.UpdateConversionGoals(
	ConversionGoals=ConversionGoals)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

