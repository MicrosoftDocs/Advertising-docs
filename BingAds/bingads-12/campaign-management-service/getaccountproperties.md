---
title: GetAccountProperties Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets account level properties by name.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAccountProperties Service Operation - Campaign Management
Gets account level properties by name.

## <a name="request"></a>Request Elements
The *GetAccountPropertiesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountpropertynames"></a>AccountPropertyNames|The names of account properties that you want to get.<br/><br/>To determine whether or not Microsoft Click Id auto-tagging is enabled, include the *MSCLKIDAutoTaggingEnabled* value in your request.<br/><br/>**Required**: Yes|[AccountPropertyName](accountpropertyname.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAccountPropertiesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountproperties"></a>AccountProperties|An array of account properties.<br /><br />For each account property name specified in the request, an [AccountProperty](accountproperty.md) object is returned.|[AccountProperty](accountproperty.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetAccountProperties</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAccountPropertiesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AccountPropertyNames i:nil="false">
        <AccountPropertyName>ValueHere</AccountPropertyName>
      </AccountPropertyNames>
    </GetAccountPropertiesRequest>
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
    <GetAccountPropertiesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AccountProperties d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AccountProperty>
          <Name>ValueHere</Name>
          <Value d4p1:nil="false">ValueHere</Value>
        </AccountProperty>
      </AccountProperties>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1102="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1102:KeyValuePairOfstringstring>
              <e1102:key d4p1:nil="false">ValueHere</e1102:key>
              <e1102:value d4p1:nil="false">ValueHere</e1102:value>
            </e1102:KeyValuePairOfstringstring>
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
    </GetAccountPropertiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAccountPropertiesResponse> GetAccountPropertiesAsync(
	IList<AccountPropertyName> accountPropertyNames)
{
	var request = new GetAccountPropertiesRequest
	{
		AccountPropertyNames = accountPropertyNames
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAccountPropertiesAsync(r), request));
}
```
```java
static GetAccountPropertiesResponse getAccountProperties(
	ArrayOfAccountPropertyName accountPropertyNames) throws RemoteException, Exception
{
	GetAccountPropertiesRequest request = new GetAccountPropertiesRequest();

	request.setAccountPropertyNames(accountPropertyNames);

	return CampaignManagementService.getService().getAccountProperties(request);
}
```
```php
static function GetAccountProperties(
	$accountPropertyNames)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAccountPropertiesRequest();

	$request->AccountPropertyNames = $accountPropertyNames;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAccountProperties($request);
}
```
```python
response=campaignmanagement_service.GetAccountProperties(
	AccountPropertyNames=AccountPropertyNames)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

