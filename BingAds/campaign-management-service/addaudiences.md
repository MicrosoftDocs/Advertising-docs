---
title: AddAudiences Service Operation
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds one or more audiences.
---
# AddAudiences Service Operation
Adds one or more audiences.

## <a name="request"></a>Request Elements
The *AddAudiencesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiences"></a>Audiences|The list of audiences to add.<br/><br/>The maximum size of the list is 100.<br/><br/>You can only add [RemarketingList](../campaign-management-service/remarketinglist.md) objects. You cannot add [CustomAudience](../campaign-management-service/customaudience.md) or [InMarketAudience](../campaign-management-service/inmarketaudience.md) objects. |[Audience](audience.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddAudiencesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audienceids"></a>AudienceIds|A list of unique system identifiers corresponding to the audiences that were added.<br /><br />The list of identifiers corresponds directly to the list of audiences in the request. Items of the list may be returned as null. For each list index where an audience was not added, the corresponding element will be null.|**long**|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management-service/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">AddAudiences</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddAudiencesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Audiences i:nil="false">
        <Audience i:type="-- derived type specified here with the appropriate prefix --">
          <Description i:nil="false">ValueHere</Description>
          <ForwardCompatibilityMap xmlns:e125="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e125:KeyValuePairOfstringstring>
              <e125:key i:nil="false">ValueHere</e125:key>
              <e125:value i:nil="false">ValueHere</e125:value>
            </e125:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <MembershipDuration i:nil="false">ValueHere</MembershipDuration>
          <Name i:nil="false">ValueHere</Name>
          <ParentId i:nil="false">ValueHere</ParentId>
          <Scope i:nil="false">ValueHere</Scope>
          <Type>ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to RemarketingList-->
          <Rule xmlns:e126="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <e126:Type i:nil="false">ValueHere</e126:Type>
            <!--This field is applicable if the derived type attribute is set to PageVisitorsRule-->
            <e126:RuleItemGroups i:nil="false">
              <e126:RuleItemGroup>
                <e126:Items i:nil="false">
                  <e126:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e126:Type i:nil="false">ValueHere</e126:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e126:Operand i:nil="false">ValueHere</e126:Operand>
                    <e126:Operator>ValueHere</e126:Operator>
                    <e126:Value i:nil="false">ValueHere</e126:Value>
                  </e126:RuleItem>
                </e126:Items>
              </e126:RuleItemGroup>
            </e126:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoVisitedAnotherPageRule-->
            <e126:AnotherRuleItemGroups i:nil="false">
              <e126:RuleItemGroup>
                <e126:Items i:nil="false">
                  <e126:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e126:Type i:nil="false">ValueHere</e126:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e126:Operand i:nil="false">ValueHere</e126:Operand>
                    <e126:Operator>ValueHere</e126:Operator>
                    <e126:Value i:nil="false">ValueHere</e126:Value>
                  </e126:RuleItem>
                </e126:Items>
              </e126:RuleItemGroup>
            </e126:AnotherRuleItemGroups>
            <e126:RuleItemGroups i:nil="false">
              <e126:RuleItemGroup>
                <e126:Items i:nil="false">
                  <e126:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e126:Type i:nil="false">ValueHere</e126:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e126:Operand i:nil="false">ValueHere</e126:Operand>
                    <e126:Operator>ValueHere</e126:Operator>
                    <e126:Value i:nil="false">ValueHere</e126:Value>
                  </e126:RuleItem>
                </e126:Items>
              </e126:RuleItemGroup>
            </e126:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoDidNotVisitAnotherPageRule-->
            <e126:ExcludeRuleItemGroups i:nil="false">
              <e126:RuleItemGroup>
                <e126:Items i:nil="false">
                  <e126:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e126:Type i:nil="false">ValueHere</e126:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e126:Operand i:nil="false">ValueHere</e126:Operand>
                    <e126:Operator>ValueHere</e126:Operator>
                    <e126:Value i:nil="false">ValueHere</e126:Value>
                  </e126:RuleItem>
                </e126:Items>
              </e126:RuleItemGroup>
            </e126:ExcludeRuleItemGroups>
            <e126:IncludeRuleItemGroups i:nil="false">
              <e126:RuleItemGroup>
                <e126:Items i:nil="false">
                  <e126:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e126:Type i:nil="false">ValueHere</e126:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e126:Operand i:nil="false">ValueHere</e126:Operand>
                    <e126:Operator>ValueHere</e126:Operator>
                    <e126:Value i:nil="false">ValueHere</e126:Value>
                  </e126:RuleItem>
                </e126:Items>
              </e126:RuleItemGroup>
            </e126:IncludeRuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to CustomEventsRule-->
            <e126:Action i:nil="false">ValueHere</e126:Action>
            <e126:ActionOperator>ValueHere</e126:ActionOperator>
            <e126:Category i:nil="false">ValueHere</e126:Category>
            <e126:CategoryOperator>ValueHere</e126:CategoryOperator>
            <e126:Label i:nil="false">ValueHere</e126:Label>
            <e126:LabelOperator>ValueHere</e126:LabelOperator>
            <e126:Value i:nil="false">ValueHere</e126:Value>
            <e126:ValueOperator>ValueHere</e126:ValueOperator>
          </Rule>
          <TagId i:nil="false">ValueHere</TagId>
          <!--No additional fields are applicable if the derived type attribute is set to CustomAudience-->
          <!--No additional fields are applicable if the derived type attribute is set to InMarketAudience-->
        </Audience>
      </Audiences>
    </AddAudiencesRequest>
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
    <AddAudiencesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AudienceIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </AudienceIds>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e127="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e127:KeyValuePairOfstringstring>
              <e127:key d4p1:nil="false">ValueHere</e127:key>
              <e127:value d4p1:nil="false">ValueHere</e127:value>
            </e127:KeyValuePairOfstringstring>
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
    </AddAudiencesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<AddAudiencesResponse> AddAudiencesAsync(
	IList<Audience> audiences)
{
	var request = new AddAudiencesRequest
	{
		Audiences = audiences
	};

	return (await CampaignManagement.CallAsync((s, r) => s.AddAudiencesAsync(r), request));
}
```
```java
static AddAudiencesResponse addAudiences(
	ArrayOfAudience audiences) throws RemoteException, Exception
{
	AddAudiencesRequest request = new AddAudiencesRequest();

	request.setAudiences(audiences);

	return CampaignManagement.getService().addAudiences(request);
}
```
```php
static function AddAudiences(
	$audiences)

	$addAudiencesRequest = new AddAudiencesRequest();

	$request->Audiences = $audiences;

	return $CampaignManagementProxy->GetService()->AddAudiences($request);
}
```
```python
response=campaignmanagement.AddAudiences(
	Audiences=AudiencesHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

