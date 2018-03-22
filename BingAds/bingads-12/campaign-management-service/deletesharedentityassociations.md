---
title: DeleteSharedEntityAssociations Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Removes the association between a negative keyword list and an entity such as a campaign.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# DeleteSharedEntityAssociations Service Operation - Campaign Management
Removes the association between a negative keyword list and an entity such as a campaign.

## <a name="request"></a>Request Elements
The *DeleteSharedEntityAssociationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="associations"></a>Associations|An array of objects that associate a negative keyword list and an entity such as a campaign.<br /><br />This array can contain a maximum of 10,000 elements.|[SharedEntityAssociation](sharedentityassociation.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteSharedEntityAssociationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any associations that were not successfully deleted.<br /><br />The list of errors corresponds directly to the list of associations in the request. Items of the list may be returned as null. For each list index where an association was successfully deleted, the corresponding error element will be null. Ideally all associations are deleted successfully and all elements in this list are null.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">DeleteSharedEntityAssociations</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteSharedEntityAssociationsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <Associations i:nil="false">
        <SharedEntityAssociation>
          <EntityId>ValueHere</EntityId>
          <EntityType i:nil="false">ValueHere</EntityType>
          <SharedEntityId>ValueHere</SharedEntityId>
          <SharedEntityType i:nil="false">ValueHere</SharedEntityType>
        </SharedEntityAssociation>
      </Associations>
    </DeleteSharedEntityAssociationsRequest>
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
    <DeleteSharedEntityAssociationsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1101="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1101:KeyValuePairOfstringstring>
              <e1101:key d4p1:nil="false">ValueHere</e1101:key>
              <e1101:value d4p1:nil="false">ValueHere</e1101:value>
            </e1101:KeyValuePairOfstringstring>
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
    </DeleteSharedEntityAssociationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DeleteSharedEntityAssociationsResponse> DeleteSharedEntityAssociationsAsync(
	IList<SharedEntityAssociation> associations)
{
	var request = new DeleteSharedEntityAssociationsRequest
	{
		Associations = associations
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.DeleteSharedEntityAssociationsAsync(r), request));
}
```
```java
static DeleteSharedEntityAssociationsResponse deleteSharedEntityAssociations(
	ArrayOfSharedEntityAssociation associations) throws RemoteException, Exception
{
	DeleteSharedEntityAssociationsRequest request = new DeleteSharedEntityAssociationsRequest();

	request.setAssociations(associations);

	return CampaignManagementService.getService().deleteSharedEntityAssociations(request);
}
```
```php
static function DeleteSharedEntityAssociations(
	$associations)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new DeleteSharedEntityAssociationsRequest();

	$request->Associations = $associations;

	return $GLOBALS['CampaignManagementProxy']->GetService()->DeleteSharedEntityAssociations($request);
}
```
```python
response=campaignmanagement_service.DeleteSharedEntityAssociations(
	Associations=Associations)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

