---
title: GetAudiencesByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Retrieves the specified audiences from the specified account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetAudiencesByIds Service Operation - Campaign Management
Retrieves the specified audiences from the specified account.

## <a name="request"></a>Request Elements
The *GetAudiencesByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audienceids"></a>AudienceIds|A maximum of 100 identifiers of the requested audiences.<br/><br/>This request element is optional. If this element is null or empty, then you are effectively requesting all customer and account scoped audiences for the specified account.<br/><br/>If the audience identifiers do not match the requested audience types, then the operation will return a batch error for each requested audience ID.|**long** array|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|The list of additional properties that you want included within each returned [Audience](audience.md) object. This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding elements will be included by default.<br/><br/>This request element is optional.|[AudienceAdditionalField](audienceadditionalfield.md)|
|<a name="returnsupportedcampaigntypes"></a>ReturnSupportedCampaignTypes|Determines whether or not to return the list of campaign types that support this audience.<br/><br/>The in-market audience objects that are supported for Audience campaigns are not returned at all unless you set ReturnSupportedCampaignTypes true. Additionally the SupportedCampaignTypes element for all audience types is not returned unless you set ReturnSupportedCampaignTypes true.<br/><br/>This request element is optional.|**boolean**|
|<a name="type"></a>Type|One or more types of audiences to return.<br/><br/>This request element is required.|[AudienceType](audiencetype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAudiencesByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiences"></a>Audiences|The list of audiences that corresponds directly to the audience identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an audience was not retrieved, the corresponding element will be null.|[Audience](audience.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetAudiencesByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAudiencesByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AudienceIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AudienceIds>
      <Type>ValueHere</Type>
      <ReturnAdditionalFields i:nil="false">ValueHere</ReturnAdditionalFields>
      <ReturnSupportedCampaignTypes i:nil="false">ValueHere</ReturnSupportedCampaignTypes>
    </GetAudiencesByIdsRequest>
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
    <GetAudiencesByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Audiences d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Audience d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AudienceNetworkSize d4p1:nil="false">ValueHere</AudienceNetworkSize>
          <Description d4p1:nil="false">ValueHere</Description>
          <ForwardCompatibilityMap xmlns:e223="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e223:KeyValuePairOfstringstring>
              <e223:key d4p1:nil="false">ValueHere</e223:key>
              <e223:value d4p1:nil="false">ValueHere</e223:value>
            </e223:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <MembershipDuration d4p1:nil="false">ValueHere</MembershipDuration>
          <Name d4p1:nil="false">ValueHere</Name>
          <ParentId d4p1:nil="false">ValueHere</ParentId>
          <Scope d4p1:nil="false">ValueHere</Scope>
          <SearchSize d4p1:nil="false">ValueHere</SearchSize>
          <SupportedCampaignTypes d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </SupportedCampaignTypes>
          <Type>ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to RemarketingList-->
          <Rule xmlns:e224="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <e224:Type d4p1:nil="false">ValueHere</e224:Type>
            <!--This field is applicable if the derived type attribute is set to PageVisitorsRule-->
            <e224:RuleItemGroups d4p1:nil="false">
              <e224:RuleItemGroup>
                <e224:Items d4p1:nil="false">
                  <e224:RuleItem d4p1:type="-- derived type specified here with the appropriate prefix --">
                    <e224:Type d4p1:nil="false">ValueHere</e224:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e224:Operand d4p1:nil="false">ValueHere</e224:Operand>
                    <e224:Operator>ValueHere</e224:Operator>
                    <e224:Value d4p1:nil="false">ValueHere</e224:Value>
                  </e224:RuleItem>
                </e224:Items>
              </e224:RuleItemGroup>
            </e224:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoVisitedAnotherPageRule-->
            <e224:AnotherRuleItemGroups d4p1:nil="false">
              <e224:RuleItemGroup>
                <e224:Items d4p1:nil="false">
                  <e224:RuleItem d4p1:type="-- derived type specified here with the appropriate prefix --">
                    <e224:Type d4p1:nil="false">ValueHere</e224:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e224:Operand d4p1:nil="false">ValueHere</e224:Operand>
                    <e224:Operator>ValueHere</e224:Operator>
                    <e224:Value d4p1:nil="false">ValueHere</e224:Value>
                  </e224:RuleItem>
                </e224:Items>
              </e224:RuleItemGroup>
            </e224:AnotherRuleItemGroups>
            <e224:RuleItemGroups d4p1:nil="false">
              <e224:RuleItemGroup>
                <e224:Items d4p1:nil="false">
                  <e224:RuleItem d4p1:type="-- derived type specified here with the appropriate prefix --">
                    <e224:Type d4p1:nil="false">ValueHere</e224:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e224:Operand d4p1:nil="false">ValueHere</e224:Operand>
                    <e224:Operator>ValueHere</e224:Operator>
                    <e224:Value d4p1:nil="false">ValueHere</e224:Value>
                  </e224:RuleItem>
                </e224:Items>
              </e224:RuleItemGroup>
            </e224:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoDidNotVisitAnotherPageRule-->
            <e224:ExcludeRuleItemGroups d4p1:nil="false">
              <e224:RuleItemGroup>
                <e224:Items d4p1:nil="false">
                  <e224:RuleItem d4p1:type="-- derived type specified here with the appropriate prefix --">
                    <e224:Type d4p1:nil="false">ValueHere</e224:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e224:Operand d4p1:nil="false">ValueHere</e224:Operand>
                    <e224:Operator>ValueHere</e224:Operator>
                    <e224:Value d4p1:nil="false">ValueHere</e224:Value>
                  </e224:RuleItem>
                </e224:Items>
              </e224:RuleItemGroup>
            </e224:ExcludeRuleItemGroups>
            <e224:IncludeRuleItemGroups d4p1:nil="false">
              <e224:RuleItemGroup>
                <e224:Items d4p1:nil="false">
                  <e224:RuleItem d4p1:type="-- derived type specified here with the appropriate prefix --">
                    <e224:Type d4p1:nil="false">ValueHere</e224:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e224:Operand d4p1:nil="false">ValueHere</e224:Operand>
                    <e224:Operator>ValueHere</e224:Operator>
                    <e224:Value d4p1:nil="false">ValueHere</e224:Value>
                  </e224:RuleItem>
                </e224:Items>
              </e224:RuleItemGroup>
            </e224:IncludeRuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to CustomEventsRule-->
            <e224:Action d4p1:nil="false">ValueHere</e224:Action>
            <e224:ActionOperator>ValueHere</e224:ActionOperator>
            <e224:Category d4p1:nil="false">ValueHere</e224:Category>
            <e224:CategoryOperator>ValueHere</e224:CategoryOperator>
            <e224:Label d4p1:nil="false">ValueHere</e224:Label>
            <e224:LabelOperator>ValueHere</e224:LabelOperator>
            <e224:Value d4p1:nil="false">ValueHere</e224:Value>
            <e224:ValueOperator>ValueHere</e224:ValueOperator>
          </Rule>
          <TagId d4p1:nil="false">ValueHere</TagId>
          <!--No additional fields are applicable if the derived type attribute is set to CustomAudience-->
          <!--No additional fields are applicable if the derived type attribute is set to InMarketAudience-->
          <!--These fields are applicable if the derived type attribute is set to ProductAudience-->
          <ProductAudienceType d4p1:nil="false">ValueHere</ProductAudienceType>
          <TagId d4p1:nil="false">ValueHere</TagId>
        </Audience>
      </Audiences>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e225="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e225:KeyValuePairOfstringstring>
              <e225:key d4p1:nil="false">ValueHere</e225:key>
              <e225:value d4p1:nil="false">ValueHere</e225:value>
            </e225:KeyValuePairOfstringstring>
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
    </GetAudiencesByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAudiencesByIdsResponse> GetAudiencesByIdsAsync(
	IList<long> audienceIds,
	AudienceType type,
	AudienceAdditionalField? returnAdditionalFields,
	bool? returnSupportedCampaignTypes)
{
	var request = new GetAudiencesByIdsRequest
	{
		AudienceIds = audienceIds,
		Type = type,
		ReturnAdditionalFields = returnAdditionalFields,
		ReturnSupportedCampaignTypes = returnSupportedCampaignTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAudiencesByIdsAsync(r), request));
}
```
```java
static GetAudiencesByIdsResponse getAudiencesByIds(
	ArrayOflong audienceIds,
	ArrayList<AudienceType> type,
	ArrayList<AudienceAdditionalField> returnAdditionalFields,
	boolean returnSupportedCampaignTypes) throws RemoteException, Exception
{
	GetAudiencesByIdsRequest request = new GetAudiencesByIdsRequest();

	request.setAudienceIds(audienceIds);
	request.setType(type);
	request.setReturnAdditionalFields(returnAdditionalFields);
	request.setReturnSupportedCampaignTypes(returnSupportedCampaignTypes);

	return CampaignManagementService.getService().getAudiencesByIds(request);
}
```
```php
static function GetAudiencesByIds(
	$audienceIds,
	$type,
	$returnAdditionalFields,
	$returnSupportedCampaignTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAudiencesByIdsRequest();

	$request->AudienceIds = $audienceIds;
	$request->Type = $type;
	$request->ReturnAdditionalFields = $returnAdditionalFields;
	$request->ReturnSupportedCampaignTypes = $returnSupportedCampaignTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAudiencesByIds($request);
}
```
```python
response=campaignmanagement_service.GetAudiencesByIds(
	AudienceIds=AudienceIds,
	Type=Type,
	ReturnAdditionalFields=ReturnAdditionalFields,
	ReturnSupportedCampaignTypes=ReturnSupportedCampaignTypes)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

