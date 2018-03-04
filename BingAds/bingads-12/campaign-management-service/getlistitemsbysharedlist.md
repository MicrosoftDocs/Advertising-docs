---
title: GetListItemsBySharedList Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the negative keywords of a negative keyword list.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetListItemsBySharedList Service Operation - Campaign Management
Gets the negative keywords of a negative keyword list.

> [!NOTE]
> The operation is only used for shared negative keyword lists. To get negative keywords that are exclusively used with one campaign or ad group, see [GetNegativeKeywordsByEntityIds](getnegativekeywordsbyentityids.md). 

## <a name="request"></a>Request Elements
The *GetListItemsBySharedListRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="sharedlist"></a>SharedList|The negative keyword list within the account's shared library, from which to get the negative keywords.|[SharedList](sharedlist.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetListItemsBySharedListResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="listitems"></a>ListItems|The list of negative keywords. If no negative keywords exist in the negative keyword list, an empty array is returned.|[SharedListItem](sharedlistitem.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetListItemsBySharedList</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetListItemsBySharedListRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <SharedList i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <ItemCount i:nil="false">ValueHere</ItemCount>
        <!--No additional fields are applicable if the derived type attribute is set to NegativeKeywordList-->
      </SharedList>
    </GetListItemsBySharedListRequest>
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
    <GetListItemsBySharedListResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <ListItems d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <SharedListItem d4p1:type="-- derived type specified here with the appropriate prefix --">
          <ForwardCompatibilityMap xmlns:e248="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e248:KeyValuePairOfstringstring>
              <e248:key d4p1:nil="false">ValueHere</e248:key>
              <e248:value d4p1:nil="false">ValueHere</e248:value>
            </e248:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to NegativeKeyword-->
          <Id d4p1:nil="false">ValueHere</Id>
          <MatchType>ValueHere</MatchType>
          <Text d4p1:nil="false">ValueHere</Text>
        </SharedListItem>
      </ListItems>
    </GetListItemsBySharedListResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetListItemsBySharedListResponse> GetListItemsBySharedListAsync(
	SharedList sharedList)
{
	var request = new GetListItemsBySharedListRequest
	{
		SharedList = sharedList
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetListItemsBySharedListAsync(r), request));
}
```
```java
static GetListItemsBySharedListResponse getListItemsBySharedList(
	SharedList sharedList) throws RemoteException, Exception
{
	GetListItemsBySharedListRequest request = new GetListItemsBySharedListRequest();

	request.setSharedList(sharedList);

	return CampaignManagementService.getService().getListItemsBySharedList(request);
}
```
```php
static function GetListItemsBySharedList(
	$sharedList)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetListItemsBySharedListRequest();

	$request->SharedList = $sharedList;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetListItemsBySharedList($request);
}
```
```python
response=campaignmanagement_service.GetListItemsBySharedList(
	SharedList=SharedList)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

