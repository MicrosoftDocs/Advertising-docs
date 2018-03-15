---
title: GetBudgetsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the specified budgets from the account's shared budget library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetBudgetsByIds Service Operation - Campaign Management
Gets the specified budgets from the account's shared budget library.

## <a name="request"></a>Request Elements
The *GetBudgetsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="budgetids"></a>BudgetIds|A list of unique budget identifiers that identify the budgets to get. You can specify a maximum of 100 IDs. <br/><br/>The budget IDs must be in the same account that you specified in the required *CustomerAccountId* header element.<br/><br/>If you leave this element nil or empty, then the operation will return all budgets that are available to be shared with campaigns in the account.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBudgetsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="budgets"></a>Budgets|An array of [Budget](budget.md) objects that corresponds directly to the budget identifiers that you specified in the request. Items of the list may be returned as null. For each list index where a budget was not retrieved, the corresponding element will be null.|[Budget](budget.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetBudgetsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBudgetsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <BudgetIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </BudgetIds>
    </GetBudgetsByIdsRequest>
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
    <GetBudgetsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <Budgets d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Budget>
          <Amount d4p1:nil="false">ValueHere</Amount>
          <AssociationCount d4p1:nil="false">ValueHere</AssociationCount>
          <BudgetType d4p1:nil="false">ValueHere</BudgetType>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
        </Budget>
      </Budgets>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1797="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1797:KeyValuePairOfstringstring>
              <e1797:key d4p1:nil="false">ValueHere</e1797:key>
              <e1797:value d4p1:nil="false">ValueHere</e1797:value>
            </e1797:KeyValuePairOfstringstring>
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
    </GetBudgetsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBudgetsByIdsResponse> GetBudgetsByIdsAsync(
	IList<long> budgetIds)
{
	var request = new GetBudgetsByIdsRequest
	{
		BudgetIds = budgetIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetBudgetsByIdsAsync(r), request));
}
```
```java
static GetBudgetsByIdsResponse getBudgetsByIds(
	ArrayOflong budgetIds) throws RemoteException, Exception
{
	GetBudgetsByIdsRequest request = new GetBudgetsByIdsRequest();

	request.setBudgetIds(budgetIds);

	return CampaignManagementService.getService().getBudgetsByIds(request);
}
```
```php
static function GetBudgetsByIds(
	$budgetIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetBudgetsByIdsRequest();

	$request->BudgetIds = $budgetIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetBudgetsByIds($request);
}
```
```python
response=campaignmanagement_service.GetBudgetsByIds(
	BudgetIds=BudgetIds)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

