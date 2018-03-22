---
title: GetSharedEntitiesByAccountId Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the negative keyword lists from the account's library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetSharedEntitiesByAccountId Service Operation - Campaign Management
Gets the negative keyword lists from the account's library.

## <a name="request"></a>Request Elements
The *GetSharedEntitiesByAccountIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="sharedentitytype"></a>SharedEntityType|The type of shared entity to get from the account's library.<br /><br />Currently the only supported value is NegativeKeywordList.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetSharedEntitiesByAccountIdResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="sharedentities"></a>SharedEntities|The shared entities from the account's shared library, for example negative keyword lists.|[SharedEntity](sharedentity.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetSharedEntitiesByAccountId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetSharedEntitiesByAccountIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <SharedEntityType i:nil="false">ValueHere</SharedEntityType>
    </GetSharedEntitiesByAccountIdRequest>
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
    <GetSharedEntitiesByAccountIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <SharedEntities d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <SharedEntity d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AssociationCount d4p1:nil="false">ValueHere</AssociationCount>
          <ForwardCompatibilityMap xmlns:e1140="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1140:KeyValuePairOfstringstring>
              <e1140:key d4p1:nil="false">ValueHere</e1140:key>
              <e1140:value d4p1:nil="false">ValueHere</e1140:value>
            </e1140:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--This field is applicable if the derived type attribute is set to SharedList-->
          <ItemCount d4p1:nil="false">ValueHere</ItemCount>
        </SharedEntity>
      </SharedEntities>
    </GetSharedEntitiesByAccountIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetSharedEntitiesByAccountIdResponse> GetSharedEntitiesByAccountIdAsync(
	string sharedEntityType)
{
	var request = new GetSharedEntitiesByAccountIdRequest
	{
		SharedEntityType = sharedEntityType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetSharedEntitiesByAccountIdAsync(r), request));
}
```
```java
static GetSharedEntitiesByAccountIdResponse getSharedEntitiesByAccountId(
	java.lang.String sharedEntityType) throws RemoteException, Exception
{
	GetSharedEntitiesByAccountIdRequest request = new GetSharedEntitiesByAccountIdRequest();

	request.setSharedEntityType(sharedEntityType);

	return CampaignManagementService.getService().getSharedEntitiesByAccountId(request);
}
```
```php
static function GetSharedEntitiesByAccountId(
	$sharedEntityType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetSharedEntitiesByAccountIdRequest();

	$request->SharedEntityType = $sharedEntityType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetSharedEntitiesByAccountId($request);
}
```
```python
response=campaignmanagement_service.GetSharedEntitiesByAccountId(
	SharedEntityType=SharedEntityType)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

