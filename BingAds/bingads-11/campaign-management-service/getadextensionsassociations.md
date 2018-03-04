---
title: GetAdExtensionsAssociations Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the respective ad extension associations by the specified campaign and ad group identifiers.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetAdExtensionsAssociations Service Operation - Campaign Management
Gets the respective ad extension associations by the specified campaign and ad group identifiers.

## <a name="request"></a>Request Elements
The *GetAdExtensionsAssociationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the extensions.|**long**|
|<a name="adextensiontype"></a>AdExtensionType|Filters the returned associations by ad extension type.|[AdExtensionsTypeFilter](adextensionstypefilter.md)|
|<a name="associationtype"></a>AssociationType|Filters the returned associations by entity type.|[AssociationType](associationtype.md)|
|<a name="entityids"></a>EntityIds|The list of entity identifiers by which you may request the respective ad extension associations.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdExtensionsAssociationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensionassociationcollection"></a>AdExtensionAssociationCollection|An array of ad extension association collections.<br /><br />For each entity identifier specified in the request, an *AdExtensionAssociationCollection* is returned.|[AdExtensionAssociationCollection](adextensionassociationcollection.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any associations that were not successfully retrieved.<br /><br />The list of errors corresponds directly to the list of associations in the request. Items of the list may be returned as null. For each list index where an association was successfully retrieved, the corresponding error element will be null. Ideally all associations are retrieved successfully and all elements in this list are null.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetAdExtensionsAssociations</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdExtensionsAssociationsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <AdExtensionType>ValueHere</AdExtensionType>
      <AssociationType>ValueHere</AssociationType>
      <EntityIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </EntityIds>
    </GetAdExtensionsAssociationsRequest>
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
    <GetAdExtensionsAssociationsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdExtensionAssociationCollection d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdExtensionAssociationCollection>
          <AdExtensionAssociations d4p1:nil="false">
            <AdExtensionAssociation>
              <AdExtension d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
                <ForwardCompatibilityMap xmlns:e177="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
                  <e177:KeyValuePairOfstringstring>
                    <e177:key d4p1:nil="false">ValueHere</e177:key>
                    <e177:value d4p1:nil="false">ValueHere</e177:value>
                  </e177:KeyValuePairOfstringstring>
                </ForwardCompatibilityMap>
                <Id d4p1:nil="false">ValueHere</Id>
                <Scheduling d4p1:nil="false">
                  <DayTimeRanges d4p1:nil="false">
                    <DayTime>
                      <Day>ValueHere</Day>
                      <EndHour>ValueHere</EndHour>
                      <EndMinute>ValueHere</EndMinute>
                      <StartHour>ValueHere</StartHour>
                      <StartMinute>ValueHere</StartMinute>
                    </DayTime>
                  </DayTimeRanges>
                  <EndDate d4p1:nil="false">
                    <Day>ValueHere</Day>
                    <Month>ValueHere</Month>
                    <Year>ValueHere</Year>
                  </EndDate>
                  <StartDate d4p1:nil="false">
                    <Day>ValueHere</Day>
                    <Month>ValueHere</Month>
                    <Year>ValueHere</Year>
                  </StartDate>
                  <UseSearcherTimeZone d4p1:nil="false">ValueHere</UseSearcherTimeZone>
                </Scheduling>
                <Status d4p1:nil="false">ValueHere</Status>
                <Type d4p1:nil="false">ValueHere</Type>
                <Version d4p1:nil="false">ValueHere</Version>
                <!--This field is applicable if the derived type attribute is set to SiteLinksAdExtension-->
                <SiteLinks d4p1:nil="false">
                  <SiteLink>
                    <Description1 d4p1:nil="false">ValueHere</Description1>
                    <Description2 d4p1:nil="false">ValueHere</Description2>
                    <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
                    <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
                    <DisplayText d4p1:nil="false">ValueHere</DisplayText>
                    <FinalAppUrls xmlns:e178="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                      <e178:AppUrl>
                        <e178:OsType d4p1:nil="false">ValueHere</e178:OsType>
                        <e178:Url d4p1:nil="false">ValueHere</e178:Url>
                      </e178:AppUrl>
                    </FinalAppUrls>
                    <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                      <a1:string>ValueHere</a1:string>
                    </FinalMobileUrls>
                    <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                      <a1:string>ValueHere</a1:string>
                    </FinalUrls>
                    <Scheduling d4p1:nil="false">
                      <DayTimeRanges d4p1:nil="false">
                        <DayTime>
                          <Day>ValueHere</Day>
                          <EndHour>ValueHere</EndHour>
                          <EndMinute>ValueHere</EndMinute>
                          <StartHour>ValueHere</StartHour>
                          <StartMinute>ValueHere</StartMinute>
                        </DayTime>
                      </DayTimeRanges>
                      <EndDate d4p1:nil="false">
                        <Day>ValueHere</Day>
                        <Month>ValueHere</Month>
                        <Year>ValueHere</Year>
                      </EndDate>
                      <StartDate d4p1:nil="false">
                        <Day>ValueHere</Day>
                        <Month>ValueHere</Month>
                        <Year>ValueHere</Year>
                      </StartDate>
                      <UseSearcherTimeZone d4p1:nil="false">ValueHere</UseSearcherTimeZone>
                    </Scheduling>
                    <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
                    <UrlCustomParameters xmlns:e179="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                      <e179:Parameters d4p1:nil="false">
                        <e179:CustomParameter>
                          <e179:Key d4p1:nil="false">ValueHere</e179:Key>
                          <e179:Value d4p1:nil="false">ValueHere</e179:Value>
                        </e179:CustomParameter>
                      </e179:Parameters>
                    </UrlCustomParameters>
                  </SiteLink>
                </SiteLinks>
                <!--These fields are applicable if the derived type attribute is set to LocationAdExtension-->
                <Address d4p1:nil="false">
                  <CityName d4p1:nil="false">ValueHere</CityName>
                  <CountryCode d4p1:nil="false">ValueHere</CountryCode>
                  <PostalCode d4p1:nil="false">ValueHere</PostalCode>
                  <ProvinceCode d4p1:nil="false">ValueHere</ProvinceCode>
                  <ProvinceName d4p1:nil="false">ValueHere</ProvinceName>
                  <StreetAddress d4p1:nil="false">ValueHere</StreetAddress>
                  <StreetAddress2 d4p1:nil="false">ValueHere</StreetAddress2>
                </Address>
                <CompanyName d4p1:nil="false">ValueHere</CompanyName>
                <GeoCodeStatus d4p1:nil="false">ValueHere</GeoCodeStatus>
                <GeoPoint d4p1:nil="false">
                  <LatitudeInMicroDegrees>ValueHere</LatitudeInMicroDegrees>
                  <LongitudeInMicroDegrees>ValueHere</LongitudeInMicroDegrees>
                </GeoPoint>
                <IconMediaId d4p1:nil="false">ValueHere</IconMediaId>
                <ImageMediaId d4p1:nil="false">ValueHere</ImageMediaId>
                <PhoneNumber d4p1:nil="false">ValueHere</PhoneNumber>
                <!--These fields are applicable if the derived type attribute is set to CallAdExtension-->
                <CountryCode d4p1:nil="false">ValueHere</CountryCode>
                <IsCallOnly d4p1:nil="false">ValueHere</IsCallOnly>
                <IsCallTrackingEnabled d4p1:nil="false">ValueHere</IsCallTrackingEnabled>
                <PhoneNumber d4p1:nil="false">ValueHere</PhoneNumber>
                <RequireTollFreeTrackingNumber d4p1:nil="false">ValueHere</RequireTollFreeTrackingNumber>
                <!--These fields are applicable if the derived type attribute is set to ImageAdExtension-->
                <AlternativeText d4p1:nil="false">ValueHere</AlternativeText>
                <Description d4p1:nil="false">ValueHere</Description>
                <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
                <FinalAppUrls xmlns:e180="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                  <e180:AppUrl>
                    <e180:OsType d4p1:nil="false">ValueHere</e180:OsType>
                    <e180:Url d4p1:nil="false">ValueHere</e180:Url>
                  </e180:AppUrl>
                </FinalAppUrls>
                <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </FinalMobileUrls>
                <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </FinalUrls>
                <ImageMediaIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:long>ValueHere</a1:long>
                </ImageMediaIds>
                <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
                <UrlCustomParameters xmlns:e181="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                  <e181:Parameters d4p1:nil="false">
                    <e181:CustomParameter>
                      <e181:Key d4p1:nil="false">ValueHere</e181:Key>
                      <e181:Value d4p1:nil="false">ValueHere</e181:Value>
                    </e181:CustomParameter>
                  </e181:Parameters>
                </UrlCustomParameters>
                <!--These fields are applicable if the derived type attribute is set to AppAdExtension-->
                <AppPlatform d4p1:nil="false">ValueHere</AppPlatform>
                <AppStoreId d4p1:nil="false">ValueHere</AppStoreId>
                <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
                <DisplayText d4p1:nil="false">ValueHere</DisplayText>
                <FinalAppUrls xmlns:e182="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                  <e182:AppUrl>
                    <e182:OsType d4p1:nil="false">ValueHere</e182:OsType>
                    <e182:Url d4p1:nil="false">ValueHere</e182:Url>
                  </e182:AppUrl>
                </FinalAppUrls>
                <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </FinalMobileUrls>
                <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </FinalUrls>
                <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
                <UrlCustomParameters xmlns:e183="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                  <e183:Parameters d4p1:nil="false">
                    <e183:CustomParameter>
                      <e183:Key d4p1:nil="false">ValueHere</e183:Key>
                      <e183:Value d4p1:nil="false">ValueHere</e183:Value>
                    </e183:CustomParameter>
                  </e183:Parameters>
                </UrlCustomParameters>
                <!--These fields are applicable if the derived type attribute is set to ReviewAdExtension-->
                <IsExact>ValueHere</IsExact>
                <Source d4p1:nil="false">ValueHere</Source>
                <Text d4p1:nil="false">ValueHere</Text>
                <Url d4p1:nil="false">ValueHere</Url>
                <!--This field is applicable if the derived type attribute is set to CalloutAdExtension-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to Sitelink2AdExtension-->
                <Description1 d4p1:nil="false">ValueHere</Description1>
                <Description2 d4p1:nil="false">ValueHere</Description2>
                <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
                <DisplayText d4p1:nil="false">ValueHere</DisplayText>
                <FinalAppUrls xmlns:e184="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                  <e184:AppUrl>
                    <e184:OsType d4p1:nil="false">ValueHere</e184:OsType>
                    <e184:Url d4p1:nil="false">ValueHere</e184:Url>
                  </e184:AppUrl>
                </FinalAppUrls>
                <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </FinalMobileUrls>
                <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </FinalUrls>
                <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
                <UrlCustomParameters xmlns:e185="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                  <e185:Parameters d4p1:nil="false">
                    <e185:CustomParameter>
                      <e185:Key d4p1:nil="false">ValueHere</e185:Key>
                      <e185:Value d4p1:nil="false">ValueHere</e185:Value>
                    </e185:CustomParameter>
                  </e185:Parameters>
                </UrlCustomParameters>
                <!--These fields are applicable if the derived type attribute is set to StructuredSnippetAdExtension-->
                <Header d4p1:nil="false">ValueHere</Header>
                <Values d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </Values>
                <!--These fields are applicable if the derived type attribute is set to PriceAdExtension-->
                <Language d4p1:nil="false">ValueHere</Language>
                <PriceExtensionType>ValueHere</PriceExtensionType>
                <TableRows d4p1:nil="false">
                  <PriceTableRow>
                    <CurrencyCode d4p1:nil="false">ValueHere</CurrencyCode>
                    <Description d4p1:nil="false">ValueHere</Description>
                    <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                      <a1:string>ValueHere</a1:string>
                    </FinalMobileUrls>
                    <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                      <a1:string>ValueHere</a1:string>
                    </FinalUrls>
                    <Header d4p1:nil="false">ValueHere</Header>
                    <Price>ValueHere</Price>
                    <PriceQualifier>ValueHere</PriceQualifier>
                    <PriceUnit>ValueHere</PriceUnit>
                    <TermsAndConditions d4p1:nil="false">ValueHere</TermsAndConditions>
                    <TermsAndConditionsUrl d4p1:nil="false">ValueHere</TermsAndConditionsUrl>
                  </PriceTableRow>
                </TableRows>
                <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
                <UrlCustomParameters xmlns:e186="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                  <e186:Parameters d4p1:nil="false">
                    <e186:CustomParameter>
                      <e186:Key d4p1:nil="false">ValueHere</e186:Key>
                      <e186:Value d4p1:nil="false">ValueHere</e186:Value>
                    </e186:CustomParameter>
                  </e186:Parameters>
                </UrlCustomParameters>
              </AdExtension>
              <AssociationType>ValueHere</AssociationType>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <EntityId>ValueHere</EntityId>
            </AdExtensionAssociation>
          </AdExtensionAssociations>
        </AdExtensionAssociationCollection>
      </AdExtensionAssociationCollection>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e187="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e187:KeyValuePairOfstringstring>
              <e187:key d4p1:nil="false">ValueHere</e187:key>
              <e187:value d4p1:nil="false">ValueHere</e187:value>
            </e187:KeyValuePairOfstringstring>
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
    </GetAdExtensionsAssociationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdExtensionsAssociationsResponse> GetAdExtensionsAssociationsAsync(
	long accountId,
	AdExtensionsTypeFilter adExtensionType,
	AssociationType associationType,
	IList<long> entityIds)
{
	var request = new GetAdExtensionsAssociationsRequest
	{
		AccountId = accountId,
		AdExtensionType = adExtensionType,
		AssociationType = associationType,
		EntityIds = entityIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdExtensionsAssociationsAsync(r), request));
}
```
```java
static GetAdExtensionsAssociationsResponse getAdExtensionsAssociations(
	java.lang.Long accountId,
	ArrayList<AdExtensionsTypeFilter> adExtensionType,
	AssociationType associationType,
	ArrayOflong entityIds) throws RemoteException, Exception
{
	GetAdExtensionsAssociationsRequest request = new GetAdExtensionsAssociationsRequest();

	request.setAccountId(accountId);
	request.setAdExtensionType(adExtensionType);
	request.setAssociationType(associationType);
	request.setEntityIds(entityIds);

	return CampaignManagementService.getService().getAdExtensionsAssociations(request);
}
```
```php
static function GetAdExtensionsAssociations(
	$accountId,
	$adExtensionType,
	$associationType,
	$entityIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdExtensionsAssociationsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionType = $adExtensionType;
	$request->AssociationType = $associationType;
	$request->EntityIds = $entityIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdExtensionsAssociations($request);
}
```
```python
response=campaignmanagement_service.GetAdExtensionsAssociations(
	AccountId=AccountId,
	AdExtensionType=AdExtensionType,
	AssociationType=AssociationType,
	EntityIds=EntityIds)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

