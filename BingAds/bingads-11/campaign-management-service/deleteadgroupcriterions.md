---
title: DeleteAdGroupCriterions Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Deletes the specified ad group criterions.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# DeleteAdGroupCriterions Service Operation - Campaign Management
Deletes the specified ad group criterions.

## <a name="request"></a>Request Elements
The *DeleteAdGroupCriterionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterionids"></a>AdGroupCriterionIds|A list of unique identifiers that identify the criterions to delete.<br/><br/>You can include up to 1,000 ad group criterion identifiers per request. |**long** array|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that has the criterions you want to delete.|**long**|
|<a name="criteriontype"></a>CriterionType|The type of criterion to delete, for example *Webpage*. You can specify only one criterion type value per call.<br/><br/>To add, delete, or update target criterions i.e., age, company name, day and time, device, gender, industry, job function, location, location intent, and radius criterions, you must specify the *CriterionType* value as *Targets*. You can add, delete, and update multiple target criterion types in the same operation. To retrieve these target criterions via [GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md) you must request the specific type individually i.e., *Age*, *CompanyName*, *DayTime*, *Device*, *Gender*, *Industry*, *JobFunction*, *Location*, *LocationIntent*, and *Radius*.<br/><br/>To add, delete, or update audience criterions i.e., custom audiences, in-market audiences, and remarketing lists, you must specify the *CriterionType* value as *Audience*.  You can add, delete, and update multiple target criterion types in the same operation. To retrieve these audience criterions via [GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md) you must request the specific type individually i.e., *CustomAudience*, *InMarketAudience*, *ProductAudience*, and *RemarketingList*.<br/><br/>You cannot delete a [ProductPartition](productpartition.md) with this operation. Instead, you should use [ApplyProductPartitionActions](applyproductpartitionactions.md).|[AdGroupCriterionType](adgroupcriteriontype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteAdGroupCriterionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ismigrated"></a>IsMigrated|Indicates whether or not the ad group where you deleted target criterions previously shared target criterions with another campaign or ad group. In that case this operation migrates the shared target associations and assigns new ad group criterion IDs.<br/><br/>If this value is true and if you already have criterion IDs for targets such as age, day and time, device, gender, and location, then you should replace those IDs with all of the new IDs returned by the [GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md) operation (specify *TargetCriterions* as the *CriterionType*). You only need to sync target criterion IDs, and this is not applicable for other criterion types such as webpage criterions. |**boolean**|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">DeleteAdGroupCriterions</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteAdGroupCriterionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdGroupCriterionIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdGroupCriterionIds>
      <AdGroupId>ValueHere</AdGroupId>
      <CriterionType>ValueHere</CriterionType>
    </DeleteAdGroupCriterionsRequest>
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
    <DeleteAdGroupCriterionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <IsMigrated>ValueHere</IsMigrated>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e712="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e712:KeyValuePairOfstringstring>
              <e712:key d4p1:nil="false">ValueHere</e712:key>
              <e712:value d4p1:nil="false">ValueHere</e712:value>
            </e712:KeyValuePairOfstringstring>
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
    </DeleteAdGroupCriterionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DeleteAdGroupCriterionsResponse> DeleteAdGroupCriterionsAsync(
	IList<long> adGroupCriterionIds,
	long adGroupId,
	AdGroupCriterionType criterionType)
{
	var request = new DeleteAdGroupCriterionsRequest
	{
		AdGroupCriterionIds = adGroupCriterionIds,
		AdGroupId = adGroupId,
		CriterionType = criterionType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.DeleteAdGroupCriterionsAsync(r), request));
}
```
```java
static DeleteAdGroupCriterionsResponse deleteAdGroupCriterions(
	ArrayOflong adGroupCriterionIds,
	java.lang.Long adGroupId,
	ArrayList<AdGroupCriterionType> criterionType) throws RemoteException, Exception
{
	DeleteAdGroupCriterionsRequest request = new DeleteAdGroupCriterionsRequest();

	request.setAdGroupCriterionIds(adGroupCriterionIds);
	request.setAdGroupId(adGroupId);
	request.setCriterionType(criterionType);

	return CampaignManagementService.getService().deleteAdGroupCriterions(request);
}
```
```php
static function DeleteAdGroupCriterions(
	$adGroupCriterionIds,
	$adGroupId,
	$criterionType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new DeleteAdGroupCriterionsRequest();

	$request->AdGroupCriterionIds = $adGroupCriterionIds;
	$request->AdGroupId = $adGroupId;
	$request->CriterionType = $criterionType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->DeleteAdGroupCriterions($request);
}
```
```python
response=campaignmanagement_service.DeleteAdGroupCriterions(
	AdGroupCriterionIds=AdGroupCriterionIds,
	AdGroupId=AdGroupId,
	CriterionType=CriterionType)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

