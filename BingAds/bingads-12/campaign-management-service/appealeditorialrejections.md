---
title: AppealEditorialRejections Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Appeals the editorial rejections of one or more ads or keywords that failed editorial review.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AppealEditorialRejections Service Operation - Campaign Management
Appeals the editorial rejections of one or more ads or keywords that failed editorial review.

## <a name="request"></a>Request Elements
The *AppealEditorialRejectionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityidtoparentidassociations"></a>EntityIdToParentIdAssociations|A list of unique identifiers of the ads or keywords that failed editorial review. The list can contain a maximum of 1,000 [EntityIdToParentIdAssociation](entityidtoparentidassociation.md) objects.<br /><br />You submit each ad or keyword identifier with their respective ad group parent identifier in a [EntityIdToParentIdAssociation](entityidtoparentidassociation.md) object. The list of [EntityIdToParentIdAssociation](entityidtoparentidassociation.md) must include either ad identifiers or keyword identifiers. The list cannot include a mix ad and keyword entity identifiers.<br /><br />If an entity in the list has already been approved, the entity is ignored. If an entity in the list is not appealable, the call fails. If an entity in the list has an appeal pending, this request supersedes the pending request.|[EntityIdToParentIdAssociation](entityidtoparentidassociation.md) array|
|<a name="entitytype"></a>EntityType|The type of entity that the entity to parent list contains. The supported values are *Ad* and *Keyword*.|[EntityType](entitytype.md)|
|<a name="justificationtext"></a>JustificationText|The justification for the appeal. The string can contain a maximum of 1,000 characters. The justification applies to all of the specified entities.<br /><br /> A useful justification should include reasons why the ad or keyword is compliant with editorial policy for example, *JustificationText = "my ads for paint guns are not firearms, they are painting tools"*.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AppealEditorialRejectionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any appeals that were not successfully submitted.<br /><br />The list of errors corresponds directly to the list of [EntityIdToParentIdAssociation](entityidtoparentidassociation.md) in the request. Items of the list may be returned as null. For each list index where an appeal was successfully submitted, the corresponding error element will be null. Ideally all appeals are submitted successfully and all elements in this list are null.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">AppealEditorialRejections</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AppealEditorialRejectionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <EntityIdToParentIdAssociations i:nil="false">
        <EntityIdToParentIdAssociation>
          <EntityId>ValueHere</EntityId>
          <ParentId>ValueHere</ParentId>
        </EntityIdToParentIdAssociation>
      </EntityIdToParentIdAssociations>
      <EntityType>ValueHere</EntityType>
      <JustificationText i:nil="false">ValueHere</JustificationText>
    </AppealEditorialRejectionsRequest>
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
    <AppealEditorialRejectionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1080="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1080:KeyValuePairOfstringstring>
              <e1080:key d4p1:nil="false">ValueHere</e1080:key>
              <e1080:value d4p1:nil="false">ValueHere</e1080:value>
            </e1080:KeyValuePairOfstringstring>
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
    </AppealEditorialRejectionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AppealEditorialRejectionsResponse> AppealEditorialRejectionsAsync(
	IList<EntityIdToParentIdAssociation> entityIdToParentIdAssociations,
	EntityType entityType,
	string justificationText)
{
	var request = new AppealEditorialRejectionsRequest
	{
		EntityIdToParentIdAssociations = entityIdToParentIdAssociations,
		EntityType = entityType,
		JustificationText = justificationText
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AppealEditorialRejectionsAsync(r), request));
}
```
```java
static AppealEditorialRejectionsResponse appealEditorialRejections(
	ArrayOfEntityIdToParentIdAssociation entityIdToParentIdAssociations,
	EntityType entityType,
	java.lang.String justificationText) throws RemoteException, Exception
{
	AppealEditorialRejectionsRequest request = new AppealEditorialRejectionsRequest();

	request.setEntityIdToParentIdAssociations(entityIdToParentIdAssociations);
	request.setEntityType(entityType);
	request.setJustificationText(justificationText);

	return CampaignManagementService.getService().appealEditorialRejections(request);
}
```
```php
static function AppealEditorialRejections(
	$entityIdToParentIdAssociations,
	$entityType,
	$justificationText)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AppealEditorialRejectionsRequest();

	$request->EntityIdToParentIdAssociations = $entityIdToParentIdAssociations;
	$request->EntityType = $entityType;
	$request->JustificationText = $justificationText;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AppealEditorialRejections($request);
}
```
```python
response=campaignmanagement_service.AppealEditorialRejections(
	EntityIdToParentIdAssociations=EntityIdToParentIdAssociations,
	EntityType=EntityType,
	JustificationText=JustificationText)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

