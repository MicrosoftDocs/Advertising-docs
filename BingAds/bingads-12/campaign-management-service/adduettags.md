---
title: AddUetTags Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds new Universal Event Tracking (UET) tags that you can add to your website to allow Bing Ads to collect actions people take on your website.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AddUetTags Service Operation - Campaign Management
Adds new Universal Event Tracking (UET) tags that you can add to your website to allow Bing Ads to collect actions people take on your website.

After you create a UET tag, the next step is to add the UET tag tracking code to your website. We recommend that you, or your website administrator, add it to your entire website in either the head or body sections. If your website has a master page, then that is the best place to add it because you add it once and it is included on all pages. For more information, see [How do I add the UET tag to my website?](https://help.bingads.microsoft.com/#apex/3/en/56688/2).

You can use one UET tag with all of your conversion goals and remarketing lists. Before you create multiple UET tags, see [Reasons for creating more than one UET tag](https://help.bingads.microsoft.com/#apex/3/en/56685/2).

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](../guides/universal-event-tracking.md) technical guide.

## <a name="request"></a>Request Elements
The *AddUetTagsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="uettags"></a>UetTags|An array of [UetTag](uettag.md) objects to add to the customer's shared UET tag library.<br/><br/>The customer is determined by the required *CustomerId* header element.<br /><br />You can add a maximum of 100 UET tags in a single call, although please note that you can use one UET tag with all of your conversion goals and remarketing lists. Before you create multiple UET tags, see [Reasons for creating more than one UET tag](https://help.bingads.microsoft.com/#apex/3/en/56685/2).<br/><br/> If the call is successful, the tracking script that you should add to your website is included in a corresponding [UetTag](uettag.md) within the response message.|[UetTag](uettag.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddUetTagsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|
|<a name="uettags"></a>UetTags|An array of [UetTag](uettag.md) objects to add to the customer's shared UET tag library.<br/><br/>The customer is determined by the required *CustomerId* header element.<br /><br />You can add a maximum of 100 UET tags in a single call, although please note that you can use one UET tag with all of your conversion goals and remarketing lists. Before you create multiple UET tags, see [Reasons for creating more than one UET tag](https://help.bingads.microsoft.com/#apex/3/en/56685/2).<br/><br/> If the call is successful, the tracking script that you should add to your website is included in a corresponding [UetTag](uettag.md) within the response message.|[UetTag](uettag.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">AddUetTags</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddUetTagsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <UetTags i:nil="false">
        <UetTag>
          <Description i:nil="false">ValueHere</Description>
          <Id i:nil="false">ValueHere</Id>
          <Name i:nil="false">ValueHere</Name>
          <TrackingNoScript i:nil="false">ValueHere</TrackingNoScript>
          <TrackingScript i:nil="false">ValueHere</TrackingScript>
          <TrackingStatus i:nil="false">ValueHere</TrackingStatus>
        </UetTag>
      </UetTags>
    </AddUetTagsRequest>
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
    <AddUetTagsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <UetTags d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <UetTag>
          <Description d4p1:nil="false">ValueHere</Description>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
          <TrackingNoScript d4p1:nil="false">ValueHere</TrackingNoScript>
          <TrackingScript d4p1:nil="false">ValueHere</TrackingScript>
          <TrackingStatus d4p1:nil="false">ValueHere</TrackingStatus>
        </UetTag>
      </UetTags>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1079="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1079:KeyValuePairOfstringstring>
              <e1079:key d4p1:nil="false">ValueHere</e1079:key>
              <e1079:value d4p1:nil="false">ValueHere</e1079:value>
            </e1079:KeyValuePairOfstringstring>
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
    </AddUetTagsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddUetTagsResponse> AddUetTagsAsync(
	IList<UetTag> uetTags)
{
	var request = new AddUetTagsRequest
	{
		UetTags = uetTags
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddUetTagsAsync(r), request));
}
```
```java
static AddUetTagsResponse addUetTags(
	ArrayOfUetTag uetTags) throws RemoteException, Exception
{
	AddUetTagsRequest request = new AddUetTagsRequest();

	request.setUetTags(uetTags);

	return CampaignManagementService.getService().addUetTags(request);
}
```
```php
static function AddUetTags(
	$uetTags)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddUetTagsRequest();

	$request->UetTags = $uetTags;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddUetTags($request);
}
```
```python
response=campaignmanagement_service.AddUetTags(
	UetTags=UetTags)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

