---
title: GetDomainCategories Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the list of categories available for the website domain and language.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetDomainCategories Service Operation - Ad Insight
Gets the list of categories available for the website domain and language.

## <a name="request"></a>Request Elements
The *GetDomainCategoriesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="categoryname"></a>CategoryName|The category name filter.<br/><br/>If you already know one or more of the categories, then you can optionally filter the list of results by sub-category. Up to three category levels can be specified, and must be separated by a forward slash ("/"). For example you can format the filter as *CategoryL1 / CategoryL2 / CategoryL3*.<br/><br/>If you do not include any category name, then all categories for the domain and language will be returned. |**string**|
|<a name="domainname"></a>DomainName|The website name corresponding to the pages you want your ads to target.<br /><br />The maximum length of the domain is 2,048 characters. You do not need to include the *http*, *https*, or *www* prefix.|**string**|
|<a name="language"></a>Language|The language of the website domain. Currently only English is supported, so you must set this element to *EN*.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetDomainCategoriesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="categories"></a>Categories|The list of domain categories.|[DomainCategory](domaincategory.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetDomainCategories</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetDomainCategoriesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <CategoryName i:nil="false">ValueHere</CategoryName>
      <DomainName i:nil="false">ValueHere</DomainName>
      <Language i:nil="false">ValueHere</Language>
    </GetDomainCategoriesRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetDomainCategoriesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Categories xmlns:e1295="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1295:DomainCategory>
          <e1295:Bid>ValueHere</e1295:Bid>
          <e1295:CategoryName d4p1:nil="false">ValueHere</e1295:CategoryName>
          <e1295:Coverage>ValueHere</e1295:Coverage>
        </e1295:DomainCategory>
      </Categories>
    </GetDomainCategoriesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetDomainCategoriesResponse> GetDomainCategoriesAsync(
	string categoryName,
	string domainName,
	string language)
{
	var request = new GetDomainCategoriesRequest
	{
		CategoryName = categoryName,
		DomainName = domainName,
		Language = language
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetDomainCategoriesAsync(r), request));
}
```
```java
static GetDomainCategoriesResponse getDomainCategories(
	java.lang.String categoryName,
	java.lang.String domainName,
	java.lang.String language) throws RemoteException, Exception
{
	GetDomainCategoriesRequest request = new GetDomainCategoriesRequest();

	request.setCategoryName(categoryName);
	request.setDomainName(domainName);
	request.setLanguage(language);

	return AdInsightService.getService().getDomainCategories(request);
}
```
```php
static function GetDomainCategories(
	$categoryName,
	$domainName,
	$language)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetDomainCategoriesRequest();

	$request->CategoryName = $categoryName;
	$request->DomainName = $domainName;
	$request->Language = $language;

	return $GLOBALS['AdInsightProxy']->GetService()->GetDomainCategories($request);
}
```
```python
response=adinsight_service.GetDomainCategories(
	CategoryName=CategoryName,
	DomainName=DomainName,
	Language=Language)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

