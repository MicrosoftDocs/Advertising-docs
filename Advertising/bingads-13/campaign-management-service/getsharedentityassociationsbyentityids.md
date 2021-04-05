---
title: GetSharedEntityAssociationsByEntityIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the negative keyword list to campaign associations by campaign IDs, or website exclusion list to ad account associations by ad account IDs.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetSharedEntityAssociationsByEntityIds Service Operation - Campaign Management
Gets the negative keyword list to campaign associations by campaign IDs, or website exclusion list to ad account associations by ad account IDs.

> [!TIP] 
> For an overview, see the [Negative Keywords](../guides/negative-keywords.md) and [Negative Sites](../guides/negative-sites.md) technical guides. 

> [!IMPORTANT]
> Only the users of the manager account (customer) that owns a website exclusion list ([PlacementExclusionList](placementexclusionlist.md)) can update or delete the list, add or delete list items, and associate the list with ad accounts. If your ad account is associated with a website exclusion list that you do not own, you can disassociate the list from your account, but the list and list items are read-only. The owner of the list is determined by the association's [SharedEntityCustomerId](sharedentityassociation.md#sharedentitycustomerid) element.
> 
> If you have access to multiple manager accounts in an account hierarchy, the operation's results can vary depending on the CustomerId [request header](#request-header) element that you set. 

## <a name="request"></a>Request Elements
The *GetSharedEntityAssociationsByEntityIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityids"></a>EntityIds|The list of either campaign or ad account identifiers.<br/><br/>This array can contain a maximum of 100 elements.|**long** array|
|<a name="entitytype"></a>EntityType|The type of entity corresponding to the specified [EntityIds](#entityids) element.<br/><br/>Set this element to "Campaign" to get negative keyword list to campaign associations in your ad account shared library.<br/><br/>Set this element to "Account" to get website exclusion list to ad account associations in your manager account (customer) shared library.|**string**|
|<a name="sharedentityscope"></a>SharedEntityScope|Indicates whether the shared entity is available at the ad account ([Account](entityscope.md#account)) or manager account ([Customer](entityscope.md#customer)) level.<br/><br/>This element is optional and defaults to [Account](entityscope.md#account) scope. The ad account scope is only applicable for negative keyword list to campaign associations.<br/><br/>Set this element to [Customer](entityscope.md#customer) to get website exclusion list to ad account associations in your manager account (customer) shared library.|[EntityScope](entityscope.md)|
|<a name="sharedentitytype"></a>SharedEntityType|The type of shared entity to get associations.<br/><br/>Set this element to "NegativeKeywordList" to get negative keyword list to campaign associations in your ad account shared library.<br/><br/>Set this element to "PlacementExclusionList" to get website exclusion list to ad account associations in your manager account (customer) shared library.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetSharedEntityAssociationsByEntityIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="associations"></a>Associations|An array of [SharedEntityAssociation](sharedentityassociation.md) objects that corresponds directly to the entity identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an association was not retrieved, the corresponding element will be null.|[SharedEntityAssociation](sharedentityassociation.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetSharedEntityAssociationsByEntityIds</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetSharedEntityAssociationsByEntityIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <EntityIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </EntityIds>
      <EntityType i:nil="false">ValueHere</EntityType>
      <SharedEntityType i:nil="false">ValueHere</SharedEntityType>
      <SharedEntityScope i:nil="false">ValueHere</SharedEntityScope>
    </GetSharedEntityAssociationsByEntityIdsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetSharedEntityAssociationsByEntityIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <Associations d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <SharedEntityAssociation>
          <EntityId>ValueHere</EntityId>
          <EntityType d4p1:nil="false">ValueHere</EntityType>
          <SharedEntityCustomerId d4p1:nil="false">ValueHere</SharedEntityCustomerId>
          <SharedEntityId>ValueHere</SharedEntityId>
          <SharedEntityType d4p1:nil="false">ValueHere</SharedEntityType>
        </SharedEntityAssociation>
      </Associations>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e125="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e125:KeyValuePairOfstringstring>
              <e125:key d4p1:nil="false">ValueHere</e125:key>
              <e125:value d4p1:nil="false">ValueHere</e125:value>
            </e125:KeyValuePairOfstringstring>
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
    </GetSharedEntityAssociationsByEntityIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetSharedEntityAssociationsByEntityIdsResponse> GetSharedEntityAssociationsByEntityIdsAsync(
	IList<long> entityIds,
	string entityType,
	string sharedEntityType,
	EntityScope? sharedEntityScope)
{
	var request = new GetSharedEntityAssociationsByEntityIdsRequest
	{
		EntityIds = entityIds,
		EntityType = entityType,
		SharedEntityType = sharedEntityType,
		SharedEntityScope = sharedEntityScope
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetSharedEntityAssociationsByEntityIdsAsync(r), request));
}
```
```java
static GetSharedEntityAssociationsByEntityIdsResponse getSharedEntityAssociationsByEntityIds(
	ArrayOflong entityIds,
	java.lang.String entityType,
	java.lang.String sharedEntityType,
	EntityScope sharedEntityScope) throws RemoteException, Exception
{
	GetSharedEntityAssociationsByEntityIdsRequest request = new GetSharedEntityAssociationsByEntityIdsRequest();

	request.setEntityIds(entityIds);
	request.setEntityType(entityType);
	request.setSharedEntityType(sharedEntityType);
	request.setSharedEntityScope(sharedEntityScope);

	return CampaignManagementService.getService().getSharedEntityAssociationsByEntityIds(request);
}
```
```php
static function GetSharedEntityAssociationsByEntityIds(
	$entityIds,
	$entityType,
	$sharedEntityType,
	$sharedEntityScope)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetSharedEntityAssociationsByEntityIdsRequest();

	$request->EntityIds = $entityIds;
	$request->EntityType = $entityType;
	$request->SharedEntityType = $sharedEntityType;
	$request->SharedEntityScope = $sharedEntityScope;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetSharedEntityAssociationsByEntityIds($request);
}
```
```python
response=campaignmanagement_service.GetSharedEntityAssociationsByEntityIds(
	EntityIds=EntityIds,
	EntityType=EntityType,
	SharedEntityType=SharedEntityType,
	SharedEntityScope=SharedEntityScope)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

