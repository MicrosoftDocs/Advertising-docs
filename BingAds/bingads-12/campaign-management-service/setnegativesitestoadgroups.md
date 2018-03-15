---
title: SetNegativeSitesToAdGroups Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Sets the negative site URLs of the specified ad groups.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SetNegativeSitesToAdGroups Service Operation - Campaign Management
Sets the negative site URLs of the specified ad groups.

## <a name="request"></a>Request Elements
The *SetNegativeSitesToAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupnegativesites"></a>AdGroupNegativeSites|An array of [AdGroupNegativeSites](adgroupnegativesites.md) objects that identify the ad groups to update with the specified negative site URLs.<br /><br />The array can contain a maximum of 5,000 objects.<br /><br />The total number of URLs that you can specify per request for all ad groups combined is 30,000. For example, if you specify 2,500 URLs per ad group, the maximum number of [AdGroupNegativeSites](adgroupnegativesites.md) objects that you should pass is 12.|[AdGroupNegativeSites](adgroupnegativesites.md) array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that contains the ad groups.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SetNegativeSitesToAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <Action mustUnderstand="1">SetNegativeSitesToAdGroups</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SetNegativeSitesToAdGroupsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CampaignId>ValueHere</CampaignId>
      <AdGroupNegativeSites i:nil="false">
        <AdGroupNegativeSites>
          <AdGroupId>ValueHere</AdGroupId>
          <NegativeSites i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </NegativeSites>
        </AdGroupNegativeSites>
      </AdGroupNegativeSites>
    </SetNegativeSitesToAdGroupsRequest>
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
    <SetNegativeSitesToAdGroupsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1836="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1836:KeyValuePairOfstringstring>
              <e1836:key d4p1:nil="false">ValueHere</e1836:key>
              <e1836:value d4p1:nil="false">ValueHere</e1836:value>
            </e1836:KeyValuePairOfstringstring>
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
    </SetNegativeSitesToAdGroupsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SetNegativeSitesToAdGroupsResponse> SetNegativeSitesToAdGroupsAsync(
	long campaignId,
	IList<AdGroupNegativeSites> adGroupNegativeSites)
{
	var request = new SetNegativeSitesToAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroupNegativeSites = adGroupNegativeSites
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.SetNegativeSitesToAdGroupsAsync(r), request));
}
```
```java
static SetNegativeSitesToAdGroupsResponse setNegativeSitesToAdGroups(
	java.lang.Long campaignId,
	ArrayOfAdGroupNegativeSites adGroupNegativeSites) throws RemoteException, Exception
{
	SetNegativeSitesToAdGroupsRequest request = new SetNegativeSitesToAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroupNegativeSites(adGroupNegativeSites);

	return CampaignManagementService.getService().setNegativeSitesToAdGroups(request);
}
```
```php
static function SetNegativeSitesToAdGroups(
	$campaignId,
	$adGroupNegativeSites)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new SetNegativeSitesToAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroupNegativeSites = $adGroupNegativeSites;

	return $GLOBALS['CampaignManagementProxy']->GetService()->SetNegativeSitesToAdGroups($request);
}
```
```python
response=campaignmanagement_service.SetNegativeSitesToAdGroups(
	CampaignId=CampaignId,
	AdGroupNegativeSites=AdGroupNegativeSites)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

