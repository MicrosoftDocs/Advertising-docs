---
title: AddAdGroups Service Operation
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# AddAdGroups Service Operation
Adds new ad groups to a specified campaign.

## <a name="request"></a>Request Elements
The *AddAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to add the ad groups to.|**long**|
|<a name="adgroups"></a>AdGroups|An array of [AdGroup](../campaign-management/adgroup.md) objects to add to the specified campaign.<br /><br />You can add a maximum of 1,000 ad groups in a single call. Each campaign can have up to 20,000 ad groups.|[AdGroup](adgroup.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupids"></a>AdGroupIds|A list of unique system identifiers corresponding to the ad groups that were added.<br /><br />The list of identifiers corresponds directly to the list of ad groups in the request. Items of the list may be returned as null. For each list index where an ad group was not added, the corresponding element will be null.|**long**|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">AddAdGroups</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddAdGroupsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
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
          <ForwardCompatibilityMap xmlns:e118="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e118:KeyValuePairOfstringstring>
              <e118:key i:nil="false">ValueHere</e118:key>
              <e118:value i:nil="false">ValueHere</e118:value>
            </e118:KeyValuePairOfstringstring>
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
          <UrlCustomParameters xmlns:e119="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e119:Parameters i:nil="false">
              <e119:CustomParameter>
                <e119:Key i:nil="false">ValueHere</e119:Key>
                <e119:Value i:nil="false">ValueHere</e119:Value>
              </e119:CustomParameter>
            </e119:Parameters>
          </UrlCustomParameters>
        </AdGroup>
      </AdGroups>
    </AddAdGroupsRequest>
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
    <AddAdGroupsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdGroupIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </AdGroupIds>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e120="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e120:KeyValuePairOfstringstring>
              <e120:key d4p1:nil="false">ValueHere</e120:key>
              <e120:value d4p1:nil="false">ValueHere</e120:value>
            </e120:KeyValuePairOfstringstring>
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
    </AddAdGroupsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<AddAdGroupsResponse> AddAdGroupsAsync(
	long campaignId,
	IList<AdGroup> adGroups)
{
	var request = new AddAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroups = adGroups
	};

	return (await CampaignManagement.CallAsync((s, r) => s.AddAdGroupsAsync(r), request));
}
```
```java
static AddAdGroupsResponse addAdGroups(
	long campaignId,
	ArrayOfAdGroup adGroups)
{
	AddAdGroupsRequest request = new AddAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroups(adGroups);

	return CampaignManagement.getService().addAdGroups(request);
}
```
```php
static function AddAdGroups(
	$campaignId,
	$adGroups)

	$addAdGroupsRequest = new AddAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroups = $adGroups;

	return $CampaignManagementProxy->GetService()->AddAdGroups($request);
}
```
```python
response=campaignmanagement.AddAdGroups(
	CampaignId=CampaignIdHere,
	AdGroups=AdGroupsHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

