---
title: GetBMCStoresByCustomerId Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the Bing Merchant Center stores for the specified customer.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetBMCStoresByCustomerId Service Operation - Campaign Management
Gets the Bing Merchant Center stores for the specified customer.

## <a name="request"></a>Request Elements
The *GetBMCStoresByCustomerIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements
There are not any elements in the operation's request body.

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBMCStoresByCustomerIdResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bmcstores"></a>BMCStores|The list of Bing Merchant Center stores for the specified customer.|[BMCStore](bmcstore.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetBMCStoresByCustomerId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBMCStoresByCustomerIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11" />
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
    <GetBMCStoresByCustomerIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <BMCStores d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BMCStore>
          <HasCatalog>ValueHere</HasCatalog>
          <Id>ValueHere</Id>
          <IsActive>ValueHere</IsActive>
          <IsProductAdsEnabled>ValueHere</IsProductAdsEnabled>
          <Name d4p1:nil="false">ValueHere</Name>
        </BMCStore>
      </BMCStores>
    </GetBMCStoresByCustomerIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBMCStoresByCustomerIdResponse> GetBMCStoresByCustomerIdAsync()
{
	var request = new GetBMCStoresByCustomerIdRequest
	{
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetBMCStoresByCustomerIdAsync(r), request));
}
```
```java
static GetBMCStoresByCustomerIdResponse getBMCStoresByCustomerId() throws RemoteException, Exception
{
	GetBMCStoresByCustomerIdRequest request = new GetBMCStoresByCustomerIdRequest();


	return CampaignManagementService.getService().getBMCStoresByCustomerId(request);
}
```
```php
static function GetBMCStoresByCustomerId()
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetBMCStoresByCustomerIdRequest();


	return $GLOBALS['CampaignManagementProxy']->GetService()->GetBMCStoresByCustomerId($request);
}
```
```python
response=campaignmanagement_service.GetBMCStoresByCustomerId()
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

