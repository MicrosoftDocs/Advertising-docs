---
title: SetLabelAssociations Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Sets label associations.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SetLabelAssociations Service Operation - Campaign Management
Sets label associations.

## <a name="request"></a>Request Elements
The *SetLabelAssociationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entitytype"></a>EntityType|Indicates the entity type associated with the label.<br/><br/>The supported entity type values are *Campaign*, *AdGroup*, *Ad*, and *Keyword*.|[EntityType](entitytype.md)|
|<a name="labelassociations"></a>LabelAssociations|The list of label associations to set.<br/><br/>Each label association includes label and entity identifiers.<br /><br />The maximum size of the list is 100 items per service request.<br/><br/>Each entity can be associated with a maximum of 50 labels. For example *Campaign A* can be associated with up to 50 labels.|[LabelAssociation](labelassociation.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SetLabelAssociationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any associations that were not successfully retrieved.<br /><br />The list of errors corresponds directly to the list of associations in the request. Items of the list may be returned as null. For each list index where an association was successfully retrieved, the corresponding error element will be null. Ideally all associations are retrieved successfully and all elements in this list are null.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">SetLabelAssociations</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SetLabelAssociationsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <EntityType>ValueHere</EntityType>
      <LabelAssociations i:nil="false">
        <LabelAssociation>
          <EntityId>ValueHere</EntityId>
          <LabelId>ValueHere</LabelId>
        </LabelAssociation>
      </LabelAssociations>
    </SetLabelAssociationsRequest>
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
    <SetLabelAssociationsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1145="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1145:KeyValuePairOfstringstring>
              <e1145:key d4p1:nil="false">ValueHere</e1145:key>
              <e1145:value d4p1:nil="false">ValueHere</e1145:value>
            </e1145:KeyValuePairOfstringstring>
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
    </SetLabelAssociationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SetLabelAssociationsResponse> SetLabelAssociationsAsync(
	EntityType entityType,
	IList<LabelAssociation> labelAssociations)
{
	var request = new SetLabelAssociationsRequest
	{
		EntityType = entityType,
		LabelAssociations = labelAssociations
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.SetLabelAssociationsAsync(r), request));
}
```
```java
static SetLabelAssociationsResponse setLabelAssociations(
	EntityType entityType,
	ArrayOfLabelAssociation labelAssociations) throws RemoteException, Exception
{
	SetLabelAssociationsRequest request = new SetLabelAssociationsRequest();

	request.setEntityType(entityType);
	request.setLabelAssociations(labelAssociations);

	return CampaignManagementService.getService().setLabelAssociations(request);
}
```
```php
static function SetLabelAssociations(
	$entityType,
	$labelAssociations)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new SetLabelAssociationsRequest();

	$request->EntityType = $entityType;
	$request->LabelAssociations = $labelAssociations;

	return $GLOBALS['CampaignManagementProxy']->GetService()->SetLabelAssociations($request);
}
```
```python
response=campaignmanagement_service.SetLabelAssociations(
	EntityType=EntityType,
	LabelAssociations=LabelAssociations)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

