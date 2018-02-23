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
# UpdateAudiences Service Operation - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Updates the specified audiences.

## <a name="request"></a>Request Elements
The *UpdateAudiencesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiences"></a>Audiences|A list of audiences to update.<br /><br />The maximum size of the array is 100.<br/><br/>You can only update [RemarketingList](../campaign-management-service/remarketinglist.md) and [CustomAudience](../campaign-management-service/customaudience.md) objects. You cannot update [InMarketAudience](../campaign-management-service/inmarketaudience.md) objects.|[Audience](audience.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAudiencesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <UpdateAudiencesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Audiences i:nil="false">
        <Audience i:type="-- derived type specified here with the appropriate prefix --">
          <Description i:nil="false">ValueHere</Description>
          <ForwardCompatibilityMap xmlns:e958="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e958:KeyValuePairOfstringstring>
              <e958:key i:nil="false">ValueHere</e958:key>
              <e958:value i:nil="false">ValueHere</e958:value>
            </e958:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <MembershipDuration i:nil="false">ValueHere</MembershipDuration>
          <Name i:nil="false">ValueHere</Name>
          <ParentId i:nil="false">ValueHere</ParentId>
          <Scope i:nil="false">ValueHere</Scope>
          <SearchSize i:nil="false">ValueHere</SearchSize>
          <Type>ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to RemarketingList-->
          <Rule xmlns:e959="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <e959:Type i:nil="false">ValueHere</e959:Type>
            <!--This field is applicable if the derived type attribute is set to PageVisitorsRule-->
            <e959:RuleItemGroups i:nil="false">
              <e959:RuleItemGroup>
                <e959:Items i:nil="false">
                  <e959:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e959:Type i:nil="false">ValueHere</e959:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e959:Operand i:nil="false">ValueHere</e959:Operand>
                    <e959:Operator>ValueHere</e959:Operator>
                    <e959:Value i:nil="false">ValueHere</e959:Value>
                  </e959:RuleItem>
                </e959:Items>
              </e959:RuleItemGroup>
            </e959:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoVisitedAnotherPageRule-->
            <e959:AnotherRuleItemGroups i:nil="false">
              <e959:RuleItemGroup>
                <e959:Items i:nil="false">
                  <e959:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e959:Type i:nil="false">ValueHere</e959:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e959:Operand i:nil="false">ValueHere</e959:Operand>
                    <e959:Operator>ValueHere</e959:Operator>
                    <e959:Value i:nil="false">ValueHere</e959:Value>
                  </e959:RuleItem>
                </e959:Items>
              </e959:RuleItemGroup>
            </e959:AnotherRuleItemGroups>
            <e959:RuleItemGroups i:nil="false">
              <e959:RuleItemGroup>
                <e959:Items i:nil="false">
                  <e959:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e959:Type i:nil="false">ValueHere</e959:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e959:Operand i:nil="false">ValueHere</e959:Operand>
                    <e959:Operator>ValueHere</e959:Operator>
                    <e959:Value i:nil="false">ValueHere</e959:Value>
                  </e959:RuleItem>
                </e959:Items>
              </e959:RuleItemGroup>
            </e959:RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoDidNotVisitAnotherPageRule-->
            <e959:ExcludeRuleItemGroups i:nil="false">
              <e959:RuleItemGroup>
                <e959:Items i:nil="false">
                  <e959:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e959:Type i:nil="false">ValueHere</e959:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e959:Operand i:nil="false">ValueHere</e959:Operand>
                    <e959:Operator>ValueHere</e959:Operator>
                    <e959:Value i:nil="false">ValueHere</e959:Value>
                  </e959:RuleItem>
                </e959:Items>
              </e959:RuleItemGroup>
            </e959:ExcludeRuleItemGroups>
            <e959:IncludeRuleItemGroups i:nil="false">
              <e959:RuleItemGroup>
                <e959:Items i:nil="false">
                  <e959:RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <e959:Type i:nil="false">ValueHere</e959:Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <e959:Operand i:nil="false">ValueHere</e959:Operand>
                    <e959:Operator>ValueHere</e959:Operator>
                    <e959:Value i:nil="false">ValueHere</e959:Value>
                  </e959:RuleItem>
                </e959:Items>
              </e959:RuleItemGroup>
            </e959:IncludeRuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to CustomEventsRule-->
            <e959:Action i:nil="false">ValueHere</e959:Action>
            <e959:ActionOperator>ValueHere</e959:ActionOperator>
            <e959:Category i:nil="false">ValueHere</e959:Category>
            <e959:CategoryOperator>ValueHere</e959:CategoryOperator>
            <e959:Label i:nil="false">ValueHere</e959:Label>
            <e959:LabelOperator>ValueHere</e959:LabelOperator>
            <e959:Value i:nil="false">ValueHere</e959:Value>
            <e959:ValueOperator>ValueHere</e959:ValueOperator>
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
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <UpdateAudiencesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e960="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e960:KeyValuePairOfstringstring>
              <e960:key d4p1:nil="false">ValueHere</e960:key>
              <e960:value d4p1:nil="false">ValueHere</e960:value>
            </e960:KeyValuePairOfstringstring>
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
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
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
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

