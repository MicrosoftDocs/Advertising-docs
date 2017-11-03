---
title: SetAccountProperties Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Sets account level properties by name.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SetAccountProperties Service Operation - Campaign Management
Sets account level properties by name.

## <a name="request"></a>Request Elements
The *SetAccountPropertiesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountproperties"></a>AccountProperties|The list of account properties that you want to set.<br/><br/>For example you can enable Microsoft Click Id auto-tagging for tracking offline conversions.<br/><br/>Partial success is not supported i.e., if any account property cannot be set, then none of the account properties will be set.<br/><br/>**Required**: Yes|[AccountProperty](accountproperty.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SetAccountPropertiesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements
There are not any elements in the operation's response body.

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">SetAccountProperties</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SetAccountPropertiesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountProperties i:nil="false">
        <AccountProperty>
          <Name>ValueHere</Name>
          <Value i:nil="false">ValueHere</Value>
        </AccountProperty>
      </AccountProperties>
    </SetAccountPropertiesRequest>
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
    <SetAccountPropertiesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11" />
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SetAccountPropertiesResponse> SetAccountPropertiesAsync(
	IList<AccountProperty> accountProperties)
{
	var request = new SetAccountPropertiesRequest
	{
		AccountProperties = accountProperties
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.SetAccountPropertiesAsync(r), request));
}
```
```java
static SetAccountPropertiesResponse setAccountProperties(
	ArrayOfAccountProperty accountProperties) throws RemoteException, Exception
{
	SetAccountPropertiesRequest request = new SetAccountPropertiesRequest();

	request.setAccountProperties(accountProperties);

	return CampaignManagementService.getService().setAccountProperties(request);
}
```
```php
static function SetAccountProperties(
	$accountProperties)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new SetAccountPropertiesRequest();

	$request->AccountProperties = $accountProperties;

	return $GLOBALS['CampaignManagementProxy']->GetService()->SetAccountProperties($request);
}
```
```python
response=campaignmanagement_service.SetAccountProperties(
	AccountProperties=AccountProperties)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

