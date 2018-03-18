---
title: UpdateAudiences Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the specified audiences.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UpdateAudiences Service Operation - Campaign Management
Updates the specified audiences.

## <a name="request"></a>Request Elements
The *UpdateAudiencesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiences"></a>Audiences|A list of audiences to update.<br /><br />The maximum size of the array is 100.<br/><br/>You can only update [RemarketingList](remarketinglist.md) and [CustomAudience](customaudience.md) objects. You cannot update [InMarketAudience](inmarketaudience.md) objects.|[Audience](audience.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAudiencesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">UpdateAudiences</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateAudiencesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <Audiences i:nil="false">
        <Audience i:type="-- derived type specified here with the appropriate prefix --">
          <Description i:nil="false">ValueHere</Description>
          <ForwardCompatibilityMap xmlns:e1229="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e1229:KeyValuePairOfstringstring>
              <e1229:key i:nil="false">ValueHere</e1229:key>
              <e1229:value i:nil="false">ValueHere</e1229:value>
            </e1229:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <MembershipDuration i:nil="false">ValueHere</MembershipDuration>
          <Name i:nil="false">ValueHere</Name>
          <ParentId i:nil="false">ValueHere</ParentId>
          <Scope i:nil="false">ValueHere</Scope>
          <SearchSize i:nil="false">ValueHere</SearchSize>
          <Type>ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to RemarketingList-->
          <Rule xmlns:e1230="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <e1230:Type i:nil="false">ValueHere</e1230:Type>
            <!--This field is applicable if the derived type attribute is set to PageVisitorsRule-->
            <e1230:RuleItemGroups i:nil="false">
              <e1230:RuleItemGroup>
                <e1230:Items i:nil="false">
                  <e1230:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e1230:Type i:nil="false">ValueHere</e1230:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e1230:Operand i:nil="false">ValueHere</e1230:Operand>
                    <e1230:Operator>ValueHere</e1230:Operator>
                    <e1230:Value i:nil="false">ValueHere</e1230:Value>
                  </e1230:RuleItem>
                </e1230:Items>
              </e1230:RuleItemGroup>
            </e1230:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoVisitedAnotherPageRule-->
            <e1230:AnotherRuleItemGroups i:nil="false">
              <e1230:RuleItemGroup>
                <e1230:Items i:nil="false">
                  <e1230:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e1230:Type i:nil="false">ValueHere</e1230:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e1230:Operand i:nil="false">ValueHere</e1230:Operand>
                    <e1230:Operator>ValueHere</e1230:Operator>
                    <e1230:Value i:nil="false">ValueHere</e1230:Value>
                  </e1230:RuleItem>
                </e1230:Items>
              </e1230:RuleItemGroup>
            </e1230:AnotherRuleItemGroups>
            <e1230:RuleItemGroups i:nil="false">
              <e1230:RuleItemGroup>
                <e1230:Items i:nil="false">
                  <e1230:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e1230:Type i:nil="false">ValueHere</e1230:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e1230:Operand i:nil="false">ValueHere</e1230:Operand>
                    <e1230:Operator>ValueHere</e1230:Operator>
                    <e1230:Value i:nil="false">ValueHere</e1230:Value>
                  </e1230:RuleItem>
                </e1230:Items>
              </e1230:RuleItemGroup>
            </e1230:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoDidNotVisitAnotherPageRule-->
            <e1230:ExcludeRuleItemGroups i:nil="false">
              <e1230:RuleItemGroup>
                <e1230:Items i:nil="false">
                  <e1230:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e1230:Type i:nil="false">ValueHere</e1230:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e1230:Operand i:nil="false">ValueHere</e1230:Operand>
                    <e1230:Operator>ValueHere</e1230:Operator>
                    <e1230:Value i:nil="false">ValueHere</e1230:Value>
                  </e1230:RuleItem>
                </e1230:Items>
              </e1230:RuleItemGroup>
            </e1230:ExcludeRuleItemGroups>
            <e1230:IncludeRuleItemGroups i:nil="false">
              <e1230:RuleItemGroup>
                <e1230:Items i:nil="false">
                  <e1230:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e1230:Type i:nil="false">ValueHere</e1230:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e1230:Operand i:nil="false">ValueHere</e1230:Operand>
                    <e1230:Operator>ValueHere</e1230:Operator>
                    <e1230:Value i:nil="false">ValueHere</e1230:Value>
                  </e1230:RuleItem>
                </e1230:Items>
              </e1230:RuleItemGroup>
            </e1230:IncludeRuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to CustomEventsRule-->
            <e1230:Action i:nil="false">ValueHere</e1230:Action>
            <e1230:ActionOperator>ValueHere</e1230:ActionOperator>
            <e1230:Category i:nil="false">ValueHere</e1230:Category>
            <e1230:CategoryOperator>ValueHere</e1230:CategoryOperator>
            <e1230:Label i:nil="false">ValueHere</e1230:Label>
            <e1230:LabelOperator>ValueHere</e1230:LabelOperator>
            <e1230:Value i:nil="false">ValueHere</e1230:Value>
            <e1230:ValueOperator>ValueHere</e1230:ValueOperator>
          </Rule>
          <TagId i:nil="false">ValueHere</TagId>
          <!--No additional fields are applicable if the derived type attribute is set to CustomAudience-->
          <!--No additional fields are applicable if the derived type attribute is set to InMarketAudience-->
        </Audience>
      </Audiences>
    </UpdateAudiencesRequest>
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
    <UpdateAudiencesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1231="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1231:KeyValuePairOfstringstring>
              <e1231:key d4p1:nil="false">ValueHere</e1231:key>
              <e1231:value d4p1:nil="false">ValueHere</e1231:value>
            </e1231:KeyValuePairOfstringstring>
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
    </UpdateAudiencesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateAudiencesResponse> UpdateAudiencesAsync(
	IList<Audience> audiences)
{
	var request = new UpdateAudiencesRequest
	{
		Audiences = audiences
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateAudiencesAsync(r), request));
}
```
```java
static UpdateAudiencesResponse updateAudiences(
	ArrayOfAudience audiences) throws RemoteException, Exception
{
	UpdateAudiencesRequest request = new UpdateAudiencesRequest();

	request.setAudiences(audiences);

	return CampaignManagementService.getService().updateAudiences(request);
}
```
```php
static function UpdateAudiences(
	$audiences)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateAudiencesRequest();

	$request->Audiences = $audiences;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateAudiences($request);
}
```
```python
response=campaignmanagement_service.UpdateAudiences(
	Audiences=Audiences)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

