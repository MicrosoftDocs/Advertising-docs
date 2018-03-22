---
title: AddBudgets Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds new budgets to the account's shared budget library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AddBudgets Service Operation - Campaign Management
Adds new budgets to the account's shared budget library.

## <a name="request"></a>Request Elements
The *AddBudgetsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="budgets"></a>Budgets|An array of [Budget](budget.md) objects to add to the account's shared budget library.<br /><br />You can add a maximum of 100 budgets in a single call. Each account's shared budget library can have up to 11,000 shared budgets.<br/><br/>The account is determined by the required *CustomerAccountId* header element.|[Budget](budget.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddBudgetsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="budgetids"></a>BudgetIds|A list of unique system identifiers corresponding to the budgets that were added.<br /><br />The list of identifiers corresponds directly to the list of budgets in the request. Items of the list may be returned as null. For each list index where a budget was not added, the corresponding element will be null.|**long** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">AddBudgets</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddBudgetsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <Budgets i:nil="false">
        <Budget>
          <Amount i:nil="false">ValueHere</Amount>
          <AssociationCount i:nil="false">ValueHere</AssociationCount>
          <BudgetType i:nil="false">ValueHere</BudgetType>
          <Id i:nil="false">ValueHere</Id>
          <Name i:nil="false">ValueHere</Name>
        </Budget>
      </Budgets>
    </AddBudgetsRequest>
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
    <AddBudgetsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <BudgetIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </BudgetIds>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1062="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1062:KeyValuePairOfstringstring>
              <e1062:key d4p1:nil="false">ValueHere</e1062:key>
              <e1062:value d4p1:nil="false">ValueHere</e1062:value>
            </e1062:KeyValuePairOfstringstring>
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
    </AddBudgetsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddBudgetsResponse> AddBudgetsAsync(
	IList<Budget> budgets)
{
	var request = new AddBudgetsRequest
	{
		Budgets = budgets
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddBudgetsAsync(r), request));
}
```
```java
static AddBudgetsResponse addBudgets(
	ArrayOfBudget budgets) throws RemoteException, Exception
{
	AddBudgetsRequest request = new AddBudgetsRequest();

	request.setBudgets(budgets);

	return CampaignManagementService.getService().addBudgets(request);
}
```
```php
static function AddBudgets(
	$budgets)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddBudgetsRequest();

	$request->Budgets = $budgets;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddBudgets($request);
}
```
```python
response=campaignmanagement_service.AddBudgets(
	Budgets=Budgets)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

