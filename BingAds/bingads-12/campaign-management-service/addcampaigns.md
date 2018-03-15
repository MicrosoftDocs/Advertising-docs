---
title: AddCampaigns Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds one or more campaigns to the specified account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AddCampaigns Service Operation - Campaign Management
Adds one or more campaigns to the specified account.

## <a name="request"></a>Request Elements
The *AddCampaignsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account to add the campaigns to.|**long**|
|<a name="campaigns"></a>Campaigns|The list of campaigns to add to the specified account.<br /><br />You can add 100 campaigns per service request.|[Campaign](campaign.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddCampaignsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignids"></a>CampaignIds|A list of unique system identifiers corresponding to the campaigns that were added.<br /><br />The list of identifiers corresponds directly to the list of campaigns in the request. Items of the list may be returned as null. For each list index where a campaign was not added, the corresponding element will be null.|**long** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">AddCampaigns</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddCampaignsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AccountId>ValueHere</AccountId>
      <Campaigns i:nil="false">
        <Campaign>
          <BiddingScheme i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to MaxClicksBiddingScheme-->
            <MaxCpc i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--This field is applicable if the derived type attribute is set to MaxConversionsBiddingScheme-->
            <MaxCpc i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--These fields are applicable if the derived type attribute is set to TargetCpaBiddingScheme-->
            <MaxCpc i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetCpa i:nil="false">ValueHere</TargetCpa>
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpcBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to EnhancedCpcBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to InheritFromParentBiddingScheme-->
            <InheritedBidStrategyType i:nil="false">ValueHere</InheritedBidStrategyType>
          </BiddingScheme>
          <BudgetType i:nil="false">ValueHere</BudgetType>
          <DailyBudget i:nil="false">ValueHere</DailyBudget>
          <Description i:nil="false">ValueHere</Description>
          <ForwardCompatibilityMap xmlns:e1713="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e1713:KeyValuePairOfstringstring>
              <e1713:key i:nil="false">ValueHere</e1713:key>
              <e1713:value i:nil="false">ValueHere</e1713:value>
            </e1713:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <Name i:nil="false">ValueHere</Name>
          <NativeBidAdjustment i:nil="false">ValueHere</NativeBidAdjustment>
          <Status i:nil="false">ValueHere</Status>
          <SubType i:nil="false">ValueHere</SubType>
          <TimeZone i:nil="false">ValueHere</TimeZone>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e1714="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" i:nil="false">
            <e1714:Parameters i:nil="false">
              <e1714:CustomParameter>
                <e1714:Key i:nil="false">ValueHere</e1714:Key>
                <e1714:Value i:nil="false">ValueHere</e1714:Value>
              </e1714:CustomParameter>
            </e1714:Parameters>
          </UrlCustomParameters>
          <CampaignType i:nil="false">ValueHere</CampaignType>
          <Settings i:nil="false">
            <Setting i:type="-- derived type specified here with the appropriate prefix --">
              <Type i:nil="false">ValueHere</Type>
              <!--These fields are applicable if the derived type attribute is set to ShoppingSetting-->
              <LocalInventoryAdsEnabled i:nil="false">ValueHere</LocalInventoryAdsEnabled>
              <Priority i:nil="false">ValueHere</Priority>
              <SalesCountryCode i:nil="false">ValueHere</SalesCountryCode>
              <StoreId i:nil="false">ValueHere</StoreId>
              <!--These fields are applicable if the derived type attribute is set to DynamicSearchAdsSetting-->
              <DomainName i:nil="false">ValueHere</DomainName>
              <Language i:nil="false">ValueHere</Language>
              <!--This field is applicable if the derived type attribute is set to TargetSetting-->
              <Details i:nil="false">
                <TargetSettingDetail>
                  <CriterionTypeGroup>ValueHere</CriterionTypeGroup>
                  <TargetAll>ValueHere</TargetAll>
                </TargetSettingDetail>
              </Details>
              <!--These fields are applicable if the derived type attribute is set to CoOpSetting-->
              <BidBoostValue i:nil="false">ValueHere</BidBoostValue>
              <BidMaxValue i:nil="false">ValueHere</BidMaxValue>
              <BidOption i:nil="false">ValueHere</BidOption>
            </Setting>
          </Settings>
          <BudgetId i:nil="false">ValueHere</BudgetId>
          <Languages i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Languages>
        </Campaign>
      </Campaigns>
    </AddCampaignsRequest>
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
    <AddCampaignsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CampaignIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </CampaignIds>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1715="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1715:KeyValuePairOfstringstring>
              <e1715:key d4p1:nil="false">ValueHere</e1715:key>
              <e1715:value d4p1:nil="false">ValueHere</e1715:value>
            </e1715:KeyValuePairOfstringstring>
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
    </AddCampaignsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddCampaignsResponse> AddCampaignsAsync(
	long accountId,
	IList<Campaign> campaigns)
{
	var request = new AddCampaignsRequest
	{
		AccountId = accountId,
		Campaigns = campaigns
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddCampaignsAsync(r), request));
}
```
```java
static AddCampaignsResponse addCampaigns(
	java.lang.Long accountId,
	ArrayOfCampaign campaigns) throws RemoteException, Exception
{
	AddCampaignsRequest request = new AddCampaignsRequest();

	request.setAccountId(accountId);
	request.setCampaigns(campaigns);

	return CampaignManagementService.getService().addCampaigns(request);
}
```
```php
static function AddCampaigns(
	$accountId,
	$campaigns)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddCampaignsRequest();

	$request->AccountId = $accountId;
	$request->Campaigns = $campaigns;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddCampaigns($request);
}
```
```python
response=campaignmanagement_service.AddCampaigns(
	AccountId=AccountId,
	Campaigns=Campaigns)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

