---
title: UpdateAdGroups Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the specified ad groups in a campaign.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# UpdateAdGroups Service Operation - Campaign Management
Updates the specified ad groups in a campaign.

## <a name="request"></a>Request Elements
The *UpdateAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroups"></a>AdGroups|An array that can contain a maximum of 1,000 [AdGroup](../campaign-management-service/adgroup.md) objects to update.|[AdGroup](adgroup.md) array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that owns the ad groups to update.|**long**|
|<a name="updatenativebidadjustment"></a>UpdateNativeBidAdjustment|Determines whether or not the service should use the *NativeBidAdjustment* element of each specified [AdGroup](../campaign-management-service/adgroup.md) during update.  If set to True, the *NativeBidAdjustment* will be used, and otherwise it will be ignored and your existing native bid adjustment setting will be retained during update.<br /><br />The default value is False if  this element is not set.|**boolean**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management-service/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">UpdateAdGroups</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateAdGroupsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <CampaignId>ValueHere</CampaignId>
      <AdGroups i:nil="false">
        <AdGroup>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdRotation i:nil="false">
            <EndDate i:nil="false">ValueHere</EndDate>
            <StartDate i:nil="false">ValueHere</StartDate>
            <Type i:nil="false">ValueHere</Type>
          </AdRotation>
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
          <ContentMatchBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </ContentMatchBid>
          <EndDate i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </EndDate>
          <ForwardCompatibilityMap xmlns:e280="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e280:KeyValuePairOfstringstring>
              <e280:key i:nil="false">ValueHere</e280:key>
              <e280:value i:nil="false">ValueHere</e280:value>
            </e280:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <Language i:nil="false">ValueHere</Language>
          <Name i:nil="false">ValueHere</Name>
          <NativeBidAdjustment i:nil="false">ValueHere</NativeBidAdjustment>
          <Network i:nil="false">ValueHere</Network>
          <PricingModel i:nil="false">ValueHere</PricingModel>
          <RemarketingTargetingSetting i:nil="false">ValueHere</RemarketingTargetingSetting>
          <SearchBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </SearchBid>
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
            </Setting>
          </Settings>
          <StartDate i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </StartDate>
          <Status i:nil="false">ValueHere</Status>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e281="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e281:Parameters i:nil="false">
              <e281:CustomParameter>
                <e281:Key i:nil="false">ValueHere</e281:Key>
                <e281:Value i:nil="false">ValueHere</e281:Value>
              </e281:CustomParameter>
            </e281:Parameters>
          </UrlCustomParameters>
        </AdGroup>
      </AdGroups>
      <UpdateNativeBidAdjustment>ValueHere</UpdateNativeBidAdjustment>
    </UpdateAdGroupsRequest>
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
    <UpdateAdGroupsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e282="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e282:KeyValuePairOfstringstring>
              <e282:key d4p1:nil="false">ValueHere</e282:key>
              <e282:value d4p1:nil="false">ValueHere</e282:value>
            </e282:KeyValuePairOfstringstring>
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
    </UpdateAdGroupsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateAdGroupsResponse> UpdateAdGroupsAsync(
	long campaignId,
	IList<AdGroup> adGroups,
	bool updateNativeBidAdjustment)
{
	var request = new UpdateAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroups = adGroups,
		UpdateNativeBidAdjustment = updateNativeBidAdjustment
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateAdGroupsAsync(r), request));
}
```
```java
static UpdateAdGroupsResponse updateAdGroups(
	java.lang.Long campaignId,
	ArrayOfAdGroup adGroups,
	boolean updateNativeBidAdjustment) throws RemoteException, Exception
{
	UpdateAdGroupsRequest request = new UpdateAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroups(adGroups);
	request.setUpdateNativeBidAdjustment(updateNativeBidAdjustment);

	return CampaignManagementService.getService().updateAdGroups(request);
}
```
```php
static function UpdateAdGroups(
	$campaignId,
	$adGroups,
	$updateNativeBidAdjustment)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroups = $adGroups;
	$request->UpdateNativeBidAdjustment = $updateNativeBidAdjustment;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateAdGroups($request);
}
```
```python
response=campaignmanagement_service.UpdateAdGroups(
	CampaignId=CampaignId,
	AdGroups=AdGroups,
	UpdateNativeBidAdjustment=UpdateNativeBidAdjustment)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: ```https://bingads.microsoft.com/CampaignManagement/v11```  

