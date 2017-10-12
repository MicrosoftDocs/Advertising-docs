---
title: GetCampaignsByAccountId Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the campaigns within an account.
---
# GetCampaignsByAccountId Service Operation - Campaign Management
Gets the campaigns within an account.

## <a name="request"></a>Request Elements
The *GetCampaignsByAccountIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that contains the campaigns to get.|**long**|
|<a name="campaigntype"></a>CampaignType|The type of campaign to get, for example *SearchAndContent*, *Shopping*, or *DynamicSearchAds*. You can specify one or more types.|[CampaignType](campaigntype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetCampaignsByAccountIdResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigns"></a>Campaigns|The list of campaigns that were retrieved. If no campaigns exist, an empty array is returned.|[Campaign](campaign.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetCampaignsByAccountId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCampaignsByAccountIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <CampaignType>ValueHere</CampaignType>
    </GetCampaignsByAccountIdRequest>
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
    <GetCampaignsByAccountIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Campaigns d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Campaign>
          <BiddingScheme d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to MaxClicksBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--This field is applicable if the derived type attribute is set to MaxConversionsBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--These fields are applicable if the derived type attribute is set to TargetCpaBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetCpa d4p1:nil="false">ValueHere</TargetCpa>
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpcBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to EnhancedCpcBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to InheritFromParentBiddingScheme-->
            <InheritedBidStrategyType d4p1:nil="false">ValueHere</InheritedBidStrategyType>
          </BiddingScheme>
          <BudgetType d4p1:nil="false">ValueHere</BudgetType>
          <DailyBudget d4p1:nil="false">ValueHere</DailyBudget>
          <Description d4p1:nil="false">ValueHere</Description>
          <ForwardCompatibilityMap xmlns:e226="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e226:KeyValuePairOfstringstring>
              <e226:key d4p1:nil="false">ValueHere</e226:key>
              <e226:value d4p1:nil="false">ValueHere</e226:value>
            </e226:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
          <NativeBidAdjustment d4p1:nil="false">ValueHere</NativeBidAdjustment>
          <Status d4p1:nil="false">ValueHere</Status>
          <TimeZone d4p1:nil="false">ValueHere</TimeZone>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e227="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e227:Parameters d4p1:nil="false">
              <e227:CustomParameter>
                <e227:Key d4p1:nil="false">ValueHere</e227:Key>
                <e227:Value d4p1:nil="false">ValueHere</e227:Value>
              </e227:CustomParameter>
            </e227:Parameters>
          </UrlCustomParameters>
          <CampaignType d4p1:nil="false">ValueHere</CampaignType>
          <Settings d4p1:nil="false">
            <Setting d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Type d4p1:nil="false">ValueHere</Type>
              <!--These fields are applicable if the derived type attribute is set to ShoppingSetting-->
              <LocalInventoryAdsEnabled d4p1:nil="false">ValueHere</LocalInventoryAdsEnabled>
              <Priority d4p1:nil="false">ValueHere</Priority>
              <SalesCountryCode d4p1:nil="false">ValueHere</SalesCountryCode>
              <StoreId d4p1:nil="false">ValueHere</StoreId>
              <!--These fields are applicable if the derived type attribute is set to DynamicSearchAdsSetting-->
              <DomainName d4p1:nil="false">ValueHere</DomainName>
              <Language d4p1:nil="false">ValueHere</Language>
            </Setting>
          </Settings>
          <BudgetId d4p1:nil="false">ValueHere</BudgetId>
          <Languages d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Languages>
        </Campaign>
      </Campaigns>
    </GetCampaignsByAccountIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetCampaignsByAccountIdResponse> GetCampaignsByAccountIdAsync(
	long accountId,
	CampaignType campaignType)
{
	var request = new GetCampaignsByAccountIdRequest
	{
		AccountId = accountId,
		CampaignType = campaignType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetCampaignsByAccountIdAsync(r), request));
}
```
```java
static GetCampaignsByAccountIdResponse getCampaignsByAccountId(
	java.lang.Long accountId,
	ArrayList<CampaignType> campaignType) throws RemoteException, Exception
{
	GetCampaignsByAccountIdRequest request = new GetCampaignsByAccountIdRequest();

	request.setAccountId(accountId);
	request.setCampaignType(campaignType);

	return CampaignManagementService.getService().getCampaignsByAccountId(request);
}
```
```php
static function GetCampaignsByAccountId(
	$accountId,
	$campaignType)

	$getCampaignsByAccountIdRequest = new GetCampaignsByAccountIdRequest();

	$request->AccountId = $accountId;
	$request->CampaignType = $campaignType;

	return $CampaignManagementProxy->GetService()->GetCampaignsByAccountId($request);
}
```
```python
response=campaignmanagement.GetCampaignsByAccountId(
	AccountId=AccountIdHere,
	CampaignType=CampaignTypeHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

