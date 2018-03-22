---
title: DeleteListItemsFromSharedList Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Deletes negative keywords from a negative keyword list.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# DeleteListItemsFromSharedList Service Operation - Campaign Management
Deletes negative keywords from a negative keyword list.

> [!NOTE]
> The operation is only used for shared negative keyword lists. To delete negative keywords that are exclusively used with one campaign or ad group, see [DeleteNegativeKeywordsFromEntities](deletenegativekeywordsfromentities.md). 

## <a name="request"></a>Request Elements
The *DeleteListItemsFromSharedListRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="listitemids"></a>ListItemIds|The list of identifiers of negative keywords to delete from the negative keyword list.<br /><br />This array can contain a maximum of 5,000 elements.|**long** array|
|<a name="sharedlist"></a>SharedList|The negative keyword list within the account's shared library, from which to delete the specified negative keywords.|[SharedList](sharedlist.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteListItemsFromSharedListResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <Action mustUnderstand="1">DeleteListItemsFromSharedList</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteListItemsFromSharedListRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <ListItemIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </ListItemIds>
      <SharedList i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <ItemCount i:nil="false">ValueHere</ItemCount>
        <!--No additional fields are applicable if the derived type attribute is set to NegativeKeywordList-->
      </SharedList>
    </DeleteListItemsFromSharedListRequest>
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
    <DeleteListItemsFromSharedListResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1095="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1095:KeyValuePairOfstringstring>
              <e1095:key d4p1:nil="false">ValueHere</e1095:key>
              <e1095:value d4p1:nil="false">ValueHere</e1095:value>
            </e1095:KeyValuePairOfstringstring>
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
    </DeleteListItemsFromSharedListResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DeleteListItemsFromSharedListResponse> DeleteListItemsFromSharedListAsync(
	IList<long> listItemIds,
	SharedList sharedList)
{
	var request = new DeleteListItemsFromSharedListRequest
	{
		ListItemIds = listItemIds,
		SharedList = sharedList
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.DeleteListItemsFromSharedListAsync(r), request));
}
```
```java
static DeleteListItemsFromSharedListResponse deleteListItemsFromSharedList(
	ArrayOflong listItemIds,
	SharedList sharedList) throws RemoteException, Exception
{
	DeleteListItemsFromSharedListRequest request = new DeleteListItemsFromSharedListRequest();

	request.setListItemIds(listItemIds);
	request.setSharedList(sharedList);

	return CampaignManagementService.getService().deleteListItemsFromSharedList(request);
}
```
```php
static function DeleteListItemsFromSharedList(
	$listItemIds,
	$sharedList)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new DeleteListItemsFromSharedListRequest();

	$request->ListItemIds = $listItemIds;
	$request->SharedList = $sharedList;

	return $GLOBALS['CampaignManagementProxy']->GetService()->DeleteListItemsFromSharedList($request);
}
```
```python
response=campaignmanagement_service.DeleteListItemsFromSharedList(
	ListItemIds=ListItemIds,
	SharedList=SharedList)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

