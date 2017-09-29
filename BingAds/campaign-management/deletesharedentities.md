---
title: DeleteSharedEntities Service Operation
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# DeleteSharedEntities Service Operation
Deletes negative keyword lists from the account's library.

## <a name="request"></a>Request Elements
The *DeleteSharedEntitiesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="sharedentities"></a>SharedEntities|The negative keyword lists to delete from the account's shared library, for example negative keyword lists.<br /><br />This array can contain a maximum of 20 elements.|[SharedEntity](sharedentity.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteSharedEntitiesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">DeleteSharedEntities</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteSharedEntitiesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <SharedEntities i:nil="false">
        <SharedEntity i:type="-- derived type specified here with the appropriate prefix --">
          <AssociationCount i:nil="false">ValueHere</AssociationCount>
          <ForwardCompatibilityMap xmlns:e579="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e579:KeyValuePairOfstringstring>
              <e579:key i:nil="false">ValueHere</e579:key>
              <e579:value i:nil="false">ValueHere</e579:value>
            </e579:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <Name i:nil="false">ValueHere</Name>
          <Type i:nil="false">ValueHere</Type>
          <!--This field is applicable if the derived type attribute is set to SharedList-->
          <ItemCount i:nil="false">ValueHere</ItemCount>
        </SharedEntity>
      </SharedEntities>
    </DeleteSharedEntitiesRequest>
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
    <DeleteSharedEntitiesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e580="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e580:KeyValuePairOfstringstring>
              <e580:key d4p1:nil="false">ValueHere</e580:key>
              <e580:value d4p1:nil="false">ValueHere</e580:value>
            </e580:KeyValuePairOfstringstring>
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
    </DeleteSharedEntitiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<DeleteSharedEntitiesResponse> DeleteSharedEntitiesAsync(
	IList<SharedEntity> sharedEntities)
{
	var request = new DeleteSharedEntitiesRequest
	{
		SharedEntities = sharedEntities
	};

	return (await CampaignManagement.CallAsync((s, r) => s.DeleteSharedEntitiesAsync(r), request));
}
```
```java
static DeleteSharedEntitiesResponse deleteSharedEntities(
	ArrayOfSharedEntity sharedEntities)
{
	DeleteSharedEntitiesRequest request = new DeleteSharedEntitiesRequest();

	request.setSharedEntities(sharedEntities);

	return CampaignManagement.getService().deleteSharedEntities(request);
}
```
```php
static function DeleteSharedEntities(
	$sharedEntities)

	$deleteSharedEntitiesRequest = new DeleteSharedEntitiesRequest();

	$request->SharedEntities = $sharedEntities;

	return $CampaignManagementProxy->GetService()->DeleteSharedEntities($request);
}
```
```python
response=campaignmanagement.DeleteSharedEntities(
	SharedEntities=SharedEntitiesHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

