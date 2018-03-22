---
title: GetAdExtensionsEditorialReasons Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets editorial rejection reasons for the respective ad extension and entity associations.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAdExtensionsEditorialReasons Service Operation - Campaign Management
Gets editorial rejection reasons for the respective ad extension and entity associations.

## <a name="request"></a>Request Elements
The *GetAdExtensionsEditorialReasonsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the extensions.|**long**|
|<a name="adextensionidtoentityidassociations"></a>AdExtensionIdToEntityIdAssociations|The list of ad extensions and corresponding entity associations to get.|[AdExtensionIdToEntityIdAssociation](adextensionidtoentityidassociation.md) array|
|<a name="associationtype"></a>AssociationType|Filters the returned associations by entity type.|[AssociationType](associationtype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdExtensionsEditorialReasonsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="editorialreasons"></a>EditorialReasons|The collection of ad extension editorial reasons.|[AdExtensionEditorialReasonCollection](adextensioneditorialreasoncollection.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetAdExtensionsEditorialReasons</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdExtensionsEditorialReasonsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AccountId>ValueHere</AccountId>
      <AdExtensionIdToEntityIdAssociations i:nil="false">
        <AdExtensionIdToEntityIdAssociation>
          <AdExtensionId>ValueHere</AdExtensionId>
          <EntityId>ValueHere</EntityId>
        </AdExtensionIdToEntityIdAssociation>
      </AdExtensionIdToEntityIdAssociations>
      <AssociationType>ValueHere</AssociationType>
    </GetAdExtensionsEditorialReasonsRequest>
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
    <GetAdExtensionsEditorialReasonsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <EditorialReasons d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdExtensionEditorialReasonCollection>
          <AdExtensionId>ValueHere</AdExtensionId>
          <Reasons d4p1:nil="false">
            <AdExtensionEditorialReason>
              <Location d4p1:nil="false">ValueHere</Location>
              <PublisherCountries d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </PublisherCountries>
              <ReasonCode>ValueHere</ReasonCode>
              <Term d4p1:nil="false">ValueHere</Term>
            </AdExtensionEditorialReason>
          </Reasons>
        </AdExtensionEditorialReasonCollection>
      </EditorialReasons>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1107="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1107:KeyValuePairOfstringstring>
              <e1107:key d4p1:nil="false">ValueHere</e1107:key>
              <e1107:value d4p1:nil="false">ValueHere</e1107:value>
            </e1107:KeyValuePairOfstringstring>
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
    </GetAdExtensionsEditorialReasonsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdExtensionsEditorialReasonsResponse> GetAdExtensionsEditorialReasonsAsync(
	long accountId,
	IList<AdExtensionIdToEntityIdAssociation> adExtensionIdToEntityIdAssociations,
	AssociationType associationType)
{
	var request = new GetAdExtensionsEditorialReasonsRequest
	{
		AccountId = accountId,
		AdExtensionIdToEntityIdAssociations = adExtensionIdToEntityIdAssociations,
		AssociationType = associationType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdExtensionsEditorialReasonsAsync(r), request));
}
```
```java
static GetAdExtensionsEditorialReasonsResponse getAdExtensionsEditorialReasons(
	java.lang.Long accountId,
	ArrayOfAdExtensionIdToEntityIdAssociation adExtensionIdToEntityIdAssociations,
	AssociationType associationType) throws RemoteException, Exception
{
	GetAdExtensionsEditorialReasonsRequest request = new GetAdExtensionsEditorialReasonsRequest();

	request.setAccountId(accountId);
	request.setAdExtensionIdToEntityIdAssociations(adExtensionIdToEntityIdAssociations);
	request.setAssociationType(associationType);

	return CampaignManagementService.getService().getAdExtensionsEditorialReasons(request);
}
```
```php
static function GetAdExtensionsEditorialReasons(
	$accountId,
	$adExtensionIdToEntityIdAssociations,
	$associationType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdExtensionsEditorialReasonsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionIdToEntityIdAssociations = $adExtensionIdToEntityIdAssociations;
	$request->AssociationType = $associationType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdExtensionsEditorialReasons($request);
}
```
```python
response=campaignmanagement_service.GetAdExtensionsEditorialReasons(
	AccountId=AccountId,
	AdExtensionIdToEntityIdAssociations=AdExtensionIdToEntityIdAssociations,
	AssociationType=AssociationType)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

