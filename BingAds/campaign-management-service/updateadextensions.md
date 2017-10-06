---
title: UpdateAdExtensions Service Operation
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates one or more ad extensions within an account?s ad extension library.
---
# UpdateAdExtensions Service Operation
Updates one or more ad extensions within an account?s ad extension library.

## <a name="request"></a>Request Elements
The *UpdateAdExtensionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account which contains the extensions.|**long**|
|<a name="adextensions"></a>AdExtensions|The list of ad extensions of any type, to update within the account. You may specify a maximum of 100 extensions per call.|[AdExtension](adextension.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAdExtensionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="nestedpartialerrors"></a>NestedPartialErrors|An array of [BatchErrorCollection](../campaign-management-service/batcherrorcollection.md) objects that contain details for any ad extensions that were not successfully updated. The top level error within each [BatchErrorCollection](../campaign-management-service/batcherrorcollection.md) object corresponds to potential ad extension errors. The nested list of [BatchError](../campaign-management-service/batcherror.md) objects would include any errors specific to the list items within an ad extension (if applicable).<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchErrorCollection](batcherrorcollection.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">UpdateAdExtensions</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateAdExtensionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <AdExtensions i:nil="false">
        <AdExtension i:type="-- derived type specified here with the appropriate prefix --">
          <DevicePreference i:nil="false">ValueHere</DevicePreference>
          <ForwardCompatibilityMap xmlns:e213="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e213:KeyValuePairOfstringstring>
              <e213:key i:nil="false">ValueHere</e213:key>
              <e213:value i:nil="false">ValueHere</e213:value>
            </e213:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <Scheduling i:nil="false">
            <DayTimeRanges i:nil="false">
              <DayTime>
                <Day>ValueHere</Day>
                <EndHour>ValueHere</EndHour>
                <EndMinute>ValueHere</EndMinute>
                <StartHour>ValueHere</StartHour>
                <StartMinute>ValueHere</StartMinute>
              </DayTime>
            </DayTimeRanges>
            <EndDate i:nil="false">
              <Day>ValueHere</Day>
              <Month>ValueHere</Month>
              <Year>ValueHere</Year>
            </EndDate>
            <StartDate i:nil="false">
              <Day>ValueHere</Day>
              <Month>ValueHere</Month>
              <Year>ValueHere</Year>
            </StartDate>
            <UseSearcherTimeZone i:nil="false">ValueHere</UseSearcherTimeZone>
          </Scheduling>
          <Status i:nil="false">ValueHere</Status>
          <Type i:nil="false">ValueHere</Type>
          <Version i:nil="false">ValueHere</Version>
          <!--This field is applicable if the derived type attribute is set to SiteLinksAdExtension-->
          <SiteLinks i:nil="false">
            <SiteLink>
              <Description1 i:nil="false">ValueHere</Description1>
              <Description2 i:nil="false">ValueHere</Description2>
              <DestinationUrl i:nil="false">ValueHere</DestinationUrl>
              <DevicePreference i:nil="false">ValueHere</DevicePreference>
              <DisplayText i:nil="false">ValueHere</DisplayText>
              <FinalAppUrls xmlns:e214="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
                <e214:AppUrl>
                  <e214:OsType i:nil="false">ValueHere</e214:OsType>
                  <e214:Url i:nil="false">ValueHere</e214:Url>
                </e214:AppUrl>
              </FinalAppUrls>
              <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalMobileUrls>
              <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalUrls>
              <Scheduling i:nil="false">
                <DayTimeRanges i:nil="false">
                  <DayTime>
                    <Day>ValueHere</Day>
                    <EndHour>ValueHere</EndHour>
                    <EndMinute>ValueHere</EndMinute>
                    <StartHour>ValueHere</StartHour>
                    <StartMinute>ValueHere</StartMinute>
                  </DayTime>
                </DayTimeRanges>
                <EndDate i:nil="false">
                  <Day>ValueHere</Day>
                  <Month>ValueHere</Month>
                  <Year>ValueHere</Year>
                </EndDate>
                <StartDate i:nil="false">
                  <Day>ValueHere</Day>
                  <Month>ValueHere</Month>
                  <Year>ValueHere</Year>
                </StartDate>
                <UseSearcherTimeZone i:nil="false">ValueHere</UseSearcherTimeZone>
              </Scheduling>
              <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
              <UrlCustomParameters xmlns:e215="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
                <e215:Parameters i:nil="false">
                  <e215:CustomParameter>
                    <e215:Key i:nil="false">ValueHere</e215:Key>
                    <e215:Value i:nil="false">ValueHere</e215:Value>
                  </e215:CustomParameter>
                </e215:Parameters>
              </UrlCustomParameters>
            </SiteLink>
          </SiteLinks>
          <!--These fields are applicable if the derived type attribute is set to LocationAdExtension-->
          <Address i:nil="false">
            <CityName i:nil="false">ValueHere</CityName>
            <CountryCode i:nil="false">ValueHere</CountryCode>
            <PostalCode i:nil="false">ValueHere</PostalCode>
            <ProvinceCode i:nil="false">ValueHere</ProvinceCode>
            <ProvinceName i:nil="false">ValueHere</ProvinceName>
            <StreetAddress i:nil="false">ValueHere</StreetAddress>
            <StreetAddress2 i:nil="false">ValueHere</StreetAddress2>
          </Address>
          <CompanyName i:nil="false">ValueHere</CompanyName>
          <GeoCodeStatus i:nil="false">ValueHere</GeoCodeStatus>
          <GeoPoint i:nil="false">
            <LatitudeInMicroDegrees>ValueHere</LatitudeInMicroDegrees>
            <LongitudeInMicroDegrees>ValueHere</LongitudeInMicroDegrees>
          </GeoPoint>
          <IconMediaId i:nil="false">ValueHere</IconMediaId>
          <ImageMediaId i:nil="false">ValueHere</ImageMediaId>
          <PhoneNumber i:nil="false">ValueHere</PhoneNumber>
          <!--These fields are applicable if the derived type attribute is set to CallAdExtension-->
          <CountryCode i:nil="false">ValueHere</CountryCode>
          <IsCallOnly i:nil="false">ValueHere</IsCallOnly>
          <IsCallTrackingEnabled i:nil="false">ValueHere</IsCallTrackingEnabled>
          <PhoneNumber i:nil="false">ValueHere</PhoneNumber>
          <RequireTollFreeTrackingNumber i:nil="false">ValueHere</RequireTollFreeTrackingNumber>
          <!--These fields are applicable if the derived type attribute is set to ImageAdExtension-->
          <AlternativeText i:nil="false">ValueHere</AlternativeText>
          <Description i:nil="false">ValueHere</Description>
          <DestinationUrl i:nil="false">ValueHere</DestinationUrl>
          <FinalAppUrls xmlns:e216="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e216:AppUrl>
              <e216:OsType i:nil="false">ValueHere</e216:OsType>
              <e216:Url i:nil="false">ValueHere</e216:Url>
            </e216:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <ImageMediaIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </ImageMediaIds>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e217="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e217:Parameters i:nil="false">
              <e217:CustomParameter>
                <e217:Key i:nil="false">ValueHere</e217:Key>
                <e217:Value i:nil="false">ValueHere</e217:Value>
              </e217:CustomParameter>
            </e217:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to AppAdExtension-->
          <AppPlatform i:nil="false">ValueHere</AppPlatform>
          <AppStoreId i:nil="false">ValueHere</AppStoreId>
          <DestinationUrl i:nil="false">ValueHere</DestinationUrl>
          <DisplayText i:nil="false">ValueHere</DisplayText>
          <FinalAppUrls xmlns:e218="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e218:AppUrl>
              <e218:OsType i:nil="false">ValueHere</e218:OsType>
              <e218:Url i:nil="false">ValueHere</e218:Url>
            </e218:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e219="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e219:Parameters i:nil="false">
              <e219:CustomParameter>
                <e219:Key i:nil="false">ValueHere</e219:Key>
                <e219:Value i:nil="false">ValueHere</e219:Value>
              </e219:CustomParameter>
            </e219:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to ReviewAdExtension-->
          <IsExact>ValueHere</IsExact>
          <Source i:nil="false">ValueHere</Source>
          <Text i:nil="false">ValueHere</Text>
          <Url i:nil="false">ValueHere</Url>
          <!--This field is applicable if the derived type attribute is set to CalloutAdExtension-->
          <Text i:nil="false">ValueHere</Text>
          <!--These fields are applicable if the derived type attribute is set to Sitelink2AdExtension-->
          <Description1 i:nil="false">ValueHere</Description1>
          <Description2 i:nil="false">ValueHere</Description2>
          <DestinationUrl i:nil="false">ValueHere</DestinationUrl>
          <DisplayText i:nil="false">ValueHere</DisplayText>
          <FinalAppUrls xmlns:e220="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e220:AppUrl>
              <e220:OsType i:nil="false">ValueHere</e220:OsType>
              <e220:Url i:nil="false">ValueHere</e220:Url>
            </e220:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e221="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e221:Parameters i:nil="false">
              <e221:CustomParameter>
                <e221:Key i:nil="false">ValueHere</e221:Key>
                <e221:Value i:nil="false">ValueHere</e221:Value>
              </e221:CustomParameter>
            </e221:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to StructuredSnippetAdExtension-->
          <Header i:nil="false">ValueHere</Header>
          <Values i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Values>
          <!--These fields are applicable if the derived type attribute is set to PriceAdExtension-->
          <Language i:nil="false">ValueHere</Language>
          <PriceExtensionType>ValueHere</PriceExtensionType>
          <TableRows i:nil="false">
            <PriceTableRow>
              <CurrencyCode i:nil="false">ValueHere</CurrencyCode>
              <Description i:nil="false">ValueHere</Description>
              <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalMobileUrls>
              <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalUrls>
              <Header i:nil="false">ValueHere</Header>
              <Price>ValueHere</Price>
              <PriceQualifier>ValueHere</PriceQualifier>
              <PriceUnit>ValueHere</PriceUnit>
              <TermsAndConditions i:nil="false">ValueHere</TermsAndConditions>
              <TermsAndConditionsUrl i:nil="false">ValueHere</TermsAndConditionsUrl>
            </PriceTableRow>
          </TableRows>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e222="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e222:Parameters i:nil="false">
              <e222:CustomParameter>
                <e222:Key i:nil="false">ValueHere</e222:Key>
                <e222:Value i:nil="false">ValueHere</e222:Value>
              </e222:CustomParameter>
            </e222:Parameters>
          </UrlCustomParameters>
        </AdExtension>
      </AdExtensions>
    </UpdateAdExtensionsRequest>
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
    <UpdateAdExtensionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <NestedPartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchErrorCollection>
          <BatchErrors d4p1:nil="false">
            <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Code>ValueHere</Code>
              <Details d4p1:nil="false">ValueHere</Details>
              <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
              <FieldPath d4p1:nil="false">ValueHere</FieldPath>
              <ForwardCompatibilityMap xmlns:e223="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
                <e223:KeyValuePairOfstringstring>
                  <e223:key d4p1:nil="false">ValueHere</e223:key>
                  <e223:value d4p1:nil="false">ValueHere</e223:value>
                </e223:KeyValuePairOfstringstring>
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
          </BatchErrors>
          <Code d4p1:nil="false">ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e224="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e224:KeyValuePairOfstringstring>
              <e224:key d4p1:nil="false">ValueHere</e224:key>
              <e224:value d4p1:nil="false">ValueHere</e224:value>
            </e224:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
        </BatchErrorCollection>
      </NestedPartialErrors>
    </UpdateAdExtensionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateAdExtensionsResponse> UpdateAdExtensionsAsync(
	long accountId,
	IList<AdExtension> adExtensions)
{
	var request = new UpdateAdExtensionsRequest
	{
		AccountId = accountId,
		AdExtensions = adExtensions
	};

	return (await CampaignManagement.CallAsync((s, r) => s.UpdateAdExtensionsAsync(r), request));
}
```
```java
static UpdateAdExtensionsResponse updateAdExtensions(
	java.lang.Long accountId,
	ArrayOfAdExtension adExtensions) throws RemoteException, Exception
{
	UpdateAdExtensionsRequest request = new UpdateAdExtensionsRequest();

	request.setAccountId(accountId);
	request.setAdExtensions(adExtensions);

	return CampaignManagement.getService().updateAdExtensions(request);
}
```
```php
static function UpdateAdExtensions(
	$accountId,
	$adExtensions)

	$updateAdExtensionsRequest = new UpdateAdExtensionsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensions = $adExtensions;

	return $CampaignManagementProxy->GetService()->UpdateAdExtensions($request);
}
```
```python
response=campaignmanagement.UpdateAdExtensions(
	AccountId=AccountIdHere,
	AdExtensions=AdExtensionsHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

