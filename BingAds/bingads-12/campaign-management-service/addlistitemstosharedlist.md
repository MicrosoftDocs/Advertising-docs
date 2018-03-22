---
title: AddListItemsToSharedList Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds negative keywords to the shared negative keyword list.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AddListItemsToSharedList Service Operation - Campaign Management
Adds negative keywords to the shared negative keyword list.

> [!NOTE]
> The operation is only used for shared negative keyword lists. To add negative keywords that are exclusively used with one campaign or ad group, see [AddNegativeKeywordsToEntities](addnegativekeywordstoentities.md). 

## <a name="request"></a>Request Elements
The *AddListItemsToSharedListRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="listitems"></a>ListItems|The negative keywords to add to the negative keyword list.<br /><br />The list can contain a maximum of 5,000 items.|[SharedListItem](sharedlistitem.md) array|
|<a name="sharedlist"></a>SharedList|The negative keyword list to add to the account's shared library.|[SharedList](sharedlist.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddListItemsToSharedListResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="listitemids"></a>ListItemIds|A list of *long* values that represents the identifiers for the list items that were added.<br /><br />Items of the list may be returned as null. For each list index where a list item was not added, the corresponding element will be null.|**long** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">AddListItemsToSharedList</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddListItemsToSharedListRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <ListItems i:nil="false">
        <SharedListItem i:type="-- derived type specified here with the appropriate prefix --">
          <ForwardCompatibilityMap xmlns:e1072="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e1072:KeyValuePairOfstringstring>
              <e1072:key i:nil="false">ValueHere</e1072:key>
              <e1072:value i:nil="false">ValueHere</e1072:value>
            </e1072:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Type i:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to NegativeKeyword-->
          <Id i:nil="false">ValueHere</Id>
          <MatchType>ValueHere</MatchType>
          <Text i:nil="false">ValueHere</Text>
        </SharedListItem>
      </ListItems>
      <SharedList i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <ItemCount i:nil="false">ValueHere</ItemCount>
        <!--No additional fields are applicable if the derived type attribute is set to NegativeKeywordList-->
      </SharedList>
    </AddListItemsToSharedListRequest>
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
    <AddListItemsToSharedListResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <ListItemIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </ListItemIds>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1073="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1073:KeyValuePairOfstringstring>
              <e1073:key d4p1:nil="false">ValueHere</e1073:key>
              <e1073:value d4p1:nil="false">ValueHere</e1073:value>
            </e1073:KeyValuePairOfstringstring>
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
    </AddListItemsToSharedListResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddListItemsToSharedListResponse> AddListItemsToSharedListAsync(
	IList<SharedListItem> listItems,
	SharedList sharedList)
{
	var request = new AddListItemsToSharedListRequest
	{
		ListItems = listItems,
		SharedList = sharedList
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddListItemsToSharedListAsync(r), request));
}
```
```java
static AddListItemsToSharedListResponse addListItemsToSharedList(
	ArrayOfSharedListItem listItems,
	SharedList sharedList) throws RemoteException, Exception
{
	AddListItemsToSharedListRequest request = new AddListItemsToSharedListRequest();

	request.setListItems(listItems);
	request.setSharedList(sharedList);

	return CampaignManagementService.getService().addListItemsToSharedList(request);
}
```
```php
static function AddListItemsToSharedList(
	$listItems,
	$sharedList)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddListItemsToSharedListRequest();

	$request->ListItems = $listItems;
	$request->SharedList = $sharedList;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddListItemsToSharedList($request);
}
```
```python
response=campaignmanagement_service.AddListItemsToSharedList(
	ListItems=ListItems,
	SharedList=SharedList)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

