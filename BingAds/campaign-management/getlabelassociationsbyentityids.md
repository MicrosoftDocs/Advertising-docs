---
title: GetLabelAssociationsByEntityIds Service Operation
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetLabelAssociationsByEntityIds Service Operation
Gets label associations by entity identifiers.

## <a name="request"></a>Request Elements
The *GetLabelAssociationsByEntityIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityids"></a>EntityIds|The list of entity identifiers used to request label associations.<br /><br />The maximum size of the list is 100 items per service request.|**long**|
|<a name="entitytype"></a>EntityType|Filters the returned associations by entity type.<br/><br/>The supported entity type values are *Campaign*, *AdGroup*, *Ad*, and *Keyword*.|[EntityType](entitytype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetLabelAssociationsByEntityIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="labelassociations"></a>LabelAssociations|An array of label associations.<br /><br />For each entity identifier specified in the request, zero or more [LabelAssociation](labelassociation.md) objects are returned. Whereas the order of the returned [LabelAssociation](labelassociation.md) objects is guaranteed in the order of the requested entity identifiers, please note that multiple [LabelAssociation](labelassociation.md) objects can be returned for the same entity identifier.|[LabelAssociation](labelassociation.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management/batcherror.md) objects that contain details for any associations that were not successfully retrieved.<br /><br />The list of errors corresponds directly to the list of associations in the request. Items of the list may be returned as null. For each list index where an association was successfully retrieved, the corresponding error element will be null. Ideally all associations are retrieved successfully and all elements in this list are null.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetLabelAssociationsByEntityIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetLabelAssociationsByEntityIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <EntityIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </EntityIds>
      <EntityType>ValueHere</EntityType>
    </GetLabelAssociationsByEntityIdsRequest>
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
    <GetLabelAssociationsByEntityIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <LabelAssociations d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <LabelAssociation>
          <EntityId>ValueHere</EntityId>
          <LabelId>ValueHere</LabelId>
        </LabelAssociation>
      </LabelAssociations>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e651="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e651:KeyValuePairOfstringstring>
              <e651:key d4p1:nil="false">ValueHere</e651:key>
              <e651:value d4p1:nil="false">ValueHere</e651:value>
            </e651:KeyValuePairOfstringstring>
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
    </GetLabelAssociationsByEntityIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<GetLabelAssociationsByEntityIdsResponse> GetLabelAssociationsByEntityIdsAsync(
	IList<long> entityIds,
	EntityType entityType)
{
	var request = new GetLabelAssociationsByEntityIdsRequest
	{
		EntityIds = entityIds,
		EntityType = entityType
	};

	return (await CampaignManagement.CallAsync((s, r) => s.GetLabelAssociationsByEntityIdsAsync(r), request));
}
```
```java
static GetLabelAssociationsByEntityIdsResponse getLabelAssociationsByEntityIds(
	ArrayOflong entityIds,
	EntityType entityType)
{
	GetLabelAssociationsByEntityIdsRequest request = new GetLabelAssociationsByEntityIdsRequest();

	request.setEntityIds(entityIds);
	request.setEntityType(entityType);

	return CampaignManagement.getService().getLabelAssociationsByEntityIds(request);
}
```
```php
static function GetLabelAssociationsByEntityIds(
	$entityIds,
	$entityType)

	$getLabelAssociationsByEntityIdsRequest = new GetLabelAssociationsByEntityIdsRequest();

	$request->EntityIds = $entityIds;
	$request->EntityType = $entityType;

	return $CampaignManagementProxy->GetService()->GetLabelAssociationsByEntityIds($request);
}
```
```python
response=campaignmanagement.GetLabelAssociationsByEntityIds(
	EntityIds=EntityIdsHere,
	EntityType=EntityTypeHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

