---
title: ApplyOfflineConversions Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Applies offline conversions for the account with Microsoft Click Id among other offline conversion data.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# ApplyOfflineConversions Service Operation - Campaign Management
Applies offline conversions for the account with Microsoft Click Id among other offline conversion data.

Let's say a customer sees your ad, clicks on it, but ends up calling you, leading to a sale that was taken offline. How can you track when your search ad leads to a conversion offline and outside of your website? You can import offline conversions, to better measure what happens after your ad was clicked.

After creating an [OfflineConversionGoal](offlineconversiongoal.md), you'll need to wait two hours before sending Bing Ads any offline conversions. If you do not wait two hours, then your offline conversion data might not be applied. After you send Bing Ads the offline conversions, it can take up to five hours to view conversion data.

Each offline conversion needs to be associated to a single click ID. A single click ID can, however, be associated with multiple conversion goals and also be associated with the same goal multiple times, as long as the conversion time is different. Also, the same conversion can't be imported more than once. If more than one is attempted, the first instance will be used and the others will be ignored.

The value of the conversion can be included in the import file along with a custom currency. If no currency is stated, the conversion goal's default will be used.

For more information, see [Tracking offline conversions](https://help.bingads.microsoft.com/#apex/3/en/help:app54554/1/en-US/#ext:ConversionTracking_Load).

## <a name="request"></a>Request Elements
The *ApplyOfflineConversionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="offlineconversions"></a>OfflineConversions|The list of offline conversions for the account.<br /><br />You can add a maximum of 1,000 offline conversions per service request.<br/><br/>Each offline conversion needs to be associated to a single click ID. A single click ID can, however, be associated with multiple conversion goals and also be associated with the same goal multiple times, as long as the conversion time is different. Also, the same conversion can't be applied more than once. If you send Bing Ads duplicates, the first instance will be used and the others will be ignored.|[OfflineConversion](offlineconversion.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *ApplyOfflineConversionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <Action mustUnderstand="1">ApplyOfflineConversions</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <ApplyOfflineConversionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <OfflineConversions i:nil="false">
        <OfflineConversion>
          <ConversionCurrencyCode i:nil="false">ValueHere</ConversionCurrencyCode>
          <ConversionName i:nil="false">ValueHere</ConversionName>
          <ConversionTime>ValueHere</ConversionTime>
          <ConversionValue i:nil="false">ValueHere</ConversionValue>
          <MicrosoftClickId i:nil="false">ValueHere</MicrosoftClickId>
        </OfflineConversion>
      </OfflineConversions>
    </ApplyOfflineConversionsRequest>
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
    <ApplyOfflineConversionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1081="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1081:KeyValuePairOfstringstring>
              <e1081:key d4p1:nil="false">ValueHere</e1081:key>
              <e1081:value d4p1:nil="false">ValueHere</e1081:value>
            </e1081:KeyValuePairOfstringstring>
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
    </ApplyOfflineConversionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<ApplyOfflineConversionsResponse> ApplyOfflineConversionsAsync(
	IList<OfflineConversion> offlineConversions)
{
	var request = new ApplyOfflineConversionsRequest
	{
		OfflineConversions = offlineConversions
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.ApplyOfflineConversionsAsync(r), request));
}
```
```java
static ApplyOfflineConversionsResponse applyOfflineConversions(
	ArrayOfOfflineConversion offlineConversions) throws RemoteException, Exception
{
	ApplyOfflineConversionsRequest request = new ApplyOfflineConversionsRequest();

	request.setOfflineConversions(offlineConversions);

	return CampaignManagementService.getService().applyOfflineConversions(request);
}
```
```php
static function ApplyOfflineConversions(
	$offlineConversions)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new ApplyOfflineConversionsRequest();

	$request->OfflineConversions = $offlineConversions;

	return $GLOBALS['CampaignManagementProxy']->GetService()->ApplyOfflineConversions($request);
}
```
```python
response=campaignmanagement_service.ApplyOfflineConversions(
	OfflineConversions=OfflineConversions)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

