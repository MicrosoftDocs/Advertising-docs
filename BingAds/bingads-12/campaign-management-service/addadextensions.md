---
title: AddAdExtensions Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds one or more ad extensions to an account's ad extension library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# AddAdExtensions Service Operation - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Adds one or more ad extensions to an account's ad extension library.

## <a name="request"></a>Request Elements
The *AddAdExtensionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account to add the extensions to.|**long**|
|<a name="adextensions"></a>AdExtensions|The list of ad extensions of any type to add to the account. You can specify a maximum of 100 extensions per call.|[AdExtension](adextension.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddAdExtensionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensionidentities"></a>AdExtensionIdentities|The identities of the extensions that were added. The list corresponds directly to the list of extensions specified in the request.|[AdExtensionIdentity](adextensionidentity.md) array|
|<a name="nestedpartialerrors"></a>NestedPartialErrors|An array of [BatchErrorCollection](../campaign-management-service/batcherrorcollection.md) objects that contain details for any ad extensions that were not successfully added. The top level error within each [BatchErrorCollection](../campaign-management-service/batcherrorcollection.md) object corresponds to potential ad extension errors. The nested list of [BatchError](../campaign-management-service/batcherror.md) objects would include any errors specific to the list items within an ad extension (if applicable).<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchErrorCollection](batcherrorcollection.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">AddAdExtensions</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddAdExtensionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <AdExtensions i:nil="false">
        <AdExtension i:type="-- derived type specified here with the appropriate prefix --">
          <DevicePreference i:nil="false">ValueHere</DevicePreference>
          <ForwardCompatibilityMap xmlns:e772="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e772:KeyValuePairOfstringstring>
              <e772:key i:nil="false">ValueHere</e772:key>
              <e772:value i:nil="false">ValueHere</e772:value>
            </e772:KeyValuePairOfstringstring>
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
              <FinalAppUrls xmlns:e773="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
                <e773:AppUrl>
                  <e773:OsType i:nil="false">ValueHere</e773:OsType>
                  <e773:Url i:nil="false">ValueHere</e773:Url>
                </e773:AppUrl>
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
              <UrlCustomParameters xmlns:e774="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
                <e774:Parameters i:nil="false">
                  <e774:CustomParameter>
                    <e774:Key i:nil="false">ValueHere</e774:Key>
                    <e774:Value i:nil="false">ValueHere</e774:Value>
                  </e774:CustomParameter>
                </e774:Parameters>
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
          <FinalAppUrls xmlns:e775="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e775:AppUrl>
              <e775:OsType i:nil="false">ValueHere</e775:OsType>
              <e775:Url i:nil="false">ValueHere</e775:Url>
            </e775:AppUrl>
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
          <UrlCustomParameters xmlns:e776="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e776:Parameters i:nil="false">
              <e776:CustomParameter>
                <e776:Key i:nil="false">ValueHere</e776:Key>
                <e776:Value i:nil="false">ValueHere</e776:Value>
              </e776:CustomParameter>
            </e776:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to AppAdExtension-->
          <AppPlatform i:nil="false">ValueHere</AppPlatform>
          <AppStoreId i:nil="false">ValueHere</AppStoreId>
          <DestinationUrl i:nil="false">ValueHere</DestinationUrl>
          <DisplayText i:nil="false">ValueHere</DisplayText>
          <FinalAppUrls xmlns:e777="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e777:AppUrl>
              <e777:OsType i:nil="false">ValueHere</e777:OsType>
              <e777:Url i:nil="false">ValueHere</e777:Url>
            </e777:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e778="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e778:Parameters i:nil="false">
              <e778:CustomParameter>
                <e778:Key i:nil="false">ValueHere</e778:Key>
                <e778:Value i:nil="false">ValueHere</e778:Value>
              </e778:CustomParameter>
            </e778:Parameters>
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
          <FinalAppUrls xmlns:e779="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e779:AppUrl>
              <e779:OsType i:nil="false">ValueHere</e779:OsType>
              <e779:Url i:nil="false">ValueHere</e779:Url>
            </e779:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e780="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e780:Parameters i:nil="false">
              <e780:CustomParameter>
                <e780:Key i:nil="false">ValueHere</e780:Key>
                <e780:Value i:nil="false">ValueHere</e780:Value>
              </e780:CustomParameter>
            </e780:Parameters>
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
          <UrlCustomParameters xmlns:e781="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e781:Parameters i:nil="false">
              <e781:CustomParameter>
                <e781:Key i:nil="false">ValueHere</e781:Key>
                <e781:Value i:nil="false">ValueHere</e781:Value>
              </e781:CustomParameter>
            </e781:Parameters>
          </UrlCustomParameters>
        </AdExtension>
      </AdExtensions>
    </AddAdExtensionsRequest>
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
    <AddAdExtensionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdExtensionIdentities d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdExtensionIdentity>
          <Id>ValueHere</Id>
          <Version d4p1:nil="false">ValueHere</Version>
        </AdExtensionIdentity>
      </AdExtensionIdentities>
      <NestedPartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchErrorCollection>
          <BatchErrors d4p1:nil="false">
            <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Code>ValueHere</Code>
              <Details d4p1:nil="false">ValueHere</Details>
              <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
              <FieldPath d4p1:nil="false">ValueHere</FieldPath>
              <ForwardCompatibilityMap xmlns:e782="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
                <e782:KeyValuePairOfstringstring>
                  <e782:key d4p1:nil="false">ValueHere</e782:key>
                  <e782:value d4p1:nil="false">ValueHere</e782:value>
                </e782:KeyValuePairOfstringstring>
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
          <ForwardCompatibilityMap xmlns:e783="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e783:KeyValuePairOfstringstring>
              <e783:key d4p1:nil="false">ValueHere</e783:key>
              <e783:value d4p1:nil="false">ValueHere</e783:value>
            </e783:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
        </BatchErrorCollection>
      </NestedPartialErrors>
    </AddAdExtensionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddAdExtensionsResponse> AddAdExtensionsAsync(
	long accountId,
	IList<AdExtension> adExtensions)
{
	var request = new AddAdExtensionsRequest
	{
		AccountId = accountId,
		AdExtensions = adExtensions
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddAdExtensionsAsync(r), request));
}
```
```java
static AddAdExtensionsResponse addAdExtensions(
	java.lang.Long accountId,
	ArrayOfAdExtension adExtensions) throws RemoteException, Exception
{
	AddAdExtensionsRequest request = new AddAdExtensionsRequest();

	request.setAccountId(accountId);
	request.setAdExtensions(adExtensions);

	return CampaignManagementService.getService().addAdExtensions(request);
}
```
```php
static function AddAdExtensions(
	$accountId,
	$adExtensions)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddAdExtensionsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensions = $adExtensions;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddAdExtensions($request);
}
```
```python
response=campaignmanagement_service.AddAdExtensions(
	AccountId=AccountId,
	AdExtensions=AdExtensions)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

