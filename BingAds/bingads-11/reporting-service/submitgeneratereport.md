---
title: SubmitGenerateReport Service Operation - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Submits a report request.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SubmitGenerateReport Service Operation - Reporting
Submits a report request.

> [!NOTE]
> You must use the same user credentials for the [SubmitGenerateReport](../reporting-service/submitgeneratereport.md) and [PollGenerateReport](../reporting-service/pollgeneratereport.md).

## <a name="request"></a>Request Elements
The *SubmitGenerateReportRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="reportrequest"></a>ReportRequest|The report request. The request must be an object that derives from [ReportRequest](../reporting-service/reportrequest.md). For a list of report request types, see [Report Types](~/guides/report-types.md).|[ReportRequest](reportrequest.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SubmitGenerateReportResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="reportrequestid"></a>ReportRequestId|The identifier of the report request. Use this identifier when calling the [PollGenerateReport](../reporting-service/pollgeneratereport.md) to determine the status of the report request. Once returned, the identifier is valid for two days.<br /><br />The *string* has a length up to 40 and can contain any character.|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Reporting/v11">
    <Action mustUnderstand="1">SubmitGenerateReport</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SubmitGenerateReportRequest xmlns="https://bingads.microsoft.com/Reporting/v11">
      <ReportRequest i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <ExcludeColumnHeaders i:nil="false">ValueHere</ExcludeColumnHeaders>
        <ExcludeReportFooter i:nil="false">ValueHere</ExcludeReportFooter>
        <ExcludeReportHeader i:nil="false">ValueHere</ExcludeReportHeader>
        <Format i:nil="false">ValueHere</Format>
        <Language i:nil="false">ValueHere</Language>
        <ReportName i:nil="false">ValueHere</ReportName>
        <ReturnOnlyCompleteData i:nil="false">ValueHere</ReturnOnlyCompleteData>
        <!--These fields are applicable if the derived type attribute is set to AccountPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AccountPerformanceReportColumn>ValueHere</AccountPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <DeviceOS i:nil="false">ValueHere</DeviceOS>
          <DeviceType i:nil="false">ValueHere</DeviceType>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to CampaignPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <CampaignPerformanceReportColumn>ValueHere</CampaignPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <DeviceOS i:nil="false">ValueHere</DeviceOS>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <Status i:nil="false">ValueHere</Status>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AdDynamicTextPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AdDynamicTextPerformanceReportColumn>ValueHere</AdDynamicTextPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <AdType i:nil="false">ValueHere</AdType>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AdGroupPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AdGroupPerformanceReportColumn>ValueHere</AdGroupPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceOS i:nil="false">ValueHere</DeviceOS>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
          <Status i:nil="false">ValueHere</Status>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AdPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AdPerformanceReportColumn>ValueHere</AdPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <AdType i:nil="false">ValueHere</AdType>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to KeywordPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <KeywordPerformanceReportColumn>ValueHere</KeywordPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdRelevance i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:int>ValueHere</a1:int>
          </AdRelevance>
          <AdType i:nil="false">ValueHere</AdType>
          <BidMatchType i:nil="false">ValueHere</BidMatchType>
          <BidStrategyType i:nil="false">ValueHere</BidStrategyType>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeliveredMatchType i:nil="false">ValueHere</DeliveredMatchType>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <ExpectedCtr i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:int>ValueHere</a1:int>
          </ExpectedCtr>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
          <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Keywords>
          <LandingPageExperience i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:int>ValueHere</a1:int>
          </LandingPageExperience>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
          <QualityScore i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:int>ValueHere</a1:int>
          </QualityScore>
        </Filter>
        <MaxRows>ValueHere</MaxRows>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Sort i:nil="false">
          <KeywordPerformanceReportSort>
            <SortColumn>ValueHere</SortColumn>
            <SortOrder>ValueHere</SortOrder>
          </KeywordPerformanceReportSort>
        </Sort>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to DestinationUrlPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <DestinationUrlPerformanceReportColumn>ValueHere</DestinationUrlPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to BudgetSummaryReportRequest-->
        <Columns i:nil="false">
          <BudgetSummaryReportColumn>ValueHere</BudgetSummaryReportColumn>
        </Columns>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AgeGenderDemographicReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AgeGenderDemographicReportColumn>ValueHere</AgeGenderDemographicReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to UserLocationPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <UserLocationPerformanceReportColumn>ValueHere</UserLocationPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <CountryCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </CountryCode>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to PublisherUsagePerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <PublisherUsagePerformanceReportColumn>ValueHere</PublisherUsagePerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to SearchQueryPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <SearchQueryPerformanceReportColumn>ValueHere</SearchQueryPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <AdType i:nil="false">ValueHere</AdType>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeliveredMatchType i:nil="false">ValueHere</DeliveredMatchType>
          <ExcludeZeroClicks>ValueHere</ExcludeZeroClicks>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
          <SearchQueries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </SearchQueries>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to ConversionPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <ConversionPerformanceReportColumn>ValueHere</ConversionPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
          <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Keywords>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to GoalsAndFunnelsReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <GoalsAndFunnelsReportColumn>ValueHere</GoalsAndFunnelsReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceOS i:nil="false">ValueHere</DeviceOS>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <GoalIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </GoalIds>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to NegativeKeywordConflictReportRequest-->
        <Columns i:nil="false">
          <NegativeKeywordConflictReportColumn>ValueHere</NegativeKeywordConflictReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <!--These fields are applicable if the derived type attribute is set to SearchCampaignChangeHistoryReportRequest-->
        <Columns i:nil="false">
          <SearchCampaignChangeHistoryReportColumn>ValueHere</SearchCampaignChangeHistoryReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <HowChanged i:nil="false">ValueHere</HowChanged>
          <ItemChanged i:nil="false">ValueHere</ItemChanged>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AdExtensionByAdReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AdExtensionByAdReportColumn>ValueHere</AdExtensionByAdReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceOS i:nil="false">ValueHere</DeviceOS>
          <DeviceType i:nil="false">ValueHere</DeviceType>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AdExtensionByKeywordReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AdExtensionByKeywordReportColumn>ValueHere</AdExtensionByKeywordReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceOS i:nil="false">ValueHere</DeviceOS>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AudiencePerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AudiencePerformanceReportColumn>ValueHere</AudiencePerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to AdExtensionDetailReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <AdExtensionDetailReportColumn>ValueHere</AdExtensionDetailReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceOS i:nil="false">ValueHere</DeviceOS>
          <DeviceType i:nil="false">ValueHere</DeviceType>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to ShareOfVoiceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <ShareOfVoiceReportColumn>ValueHere</ShareOfVoiceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <BidMatchType i:nil="false">ValueHere</BidMatchType>
          <BidStrategyType i:nil="false">ValueHere</BidStrategyType>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeliveredMatchType i:nil="false">ValueHere</DeliveredMatchType>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <KeywordStatus i:nil="false">ValueHere</KeywordStatus>
          <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Keywords>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to ProductDimensionPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <ProductDimensionPerformanceReportColumn>ValueHere</ProductDimensionPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to ProductPartitionPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <ProductPartitionPerformanceReportColumn>ValueHere</ProductPartitionPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to ProductPartitionUnitPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <ProductPartitionUnitPerformanceReportColumn>ValueHere</ProductPartitionUnitPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DeviceType i:nil="false">ValueHere</DeviceType>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to ProductSearchQueryPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <ProductSearchQueryPerformanceReportColumn>ValueHere</ProductSearchQueryPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <AdType i:nil="false">ValueHere</AdType>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <ExcludeZeroClicks>ValueHere</ExcludeZeroClicks>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
          <SearchQueries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </SearchQueries>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to CallDetailReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <CallDetailReportColumn>ValueHere</CallDetailReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to GeographicPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <GeographicPerformanceReportColumn>ValueHere</GeographicPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdDistribution i:nil="false">ValueHere</AdDistribution>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <CountryCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </CountryCode>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to DSASearchQueryPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <DSASearchQueryPerformanceReportColumn>ValueHere</DSASearchQueryPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <ExcludeZeroClicks>ValueHere</ExcludeZeroClicks>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
          <SearchQueries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </SearchQueries>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to DSAAutoTargetPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <DSAAutoTargetPerformanceReportColumn>ValueHere</DSAAutoTargetPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <BidStrategyType i:nil="false">ValueHere</BidStrategyType>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <DynamicAdTargetStatus i:nil="false">ValueHere</DynamicAdTargetStatus>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
        <!--These fields are applicable if the derived type attribute is set to DSACategoryPerformanceReportRequest-->
        <Aggregation>ValueHere</Aggregation>
        <Columns i:nil="false">
          <DSACategoryPerformanceReportColumn>ValueHere</DSACategoryPerformanceReportColumn>
        </Columns>
        <Filter i:nil="false">
          <AccountStatus i:nil="false">ValueHere</AccountStatus>
          <AdGroupStatus i:nil="false">ValueHere</AdGroupStatus>
          <AdStatus i:nil="false">ValueHere</AdStatus>
          <CampaignStatus i:nil="false">ValueHere</CampaignStatus>
          <LanguageCode i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </LanguageCode>
        </Filter>
        <Scope i:nil="false">
          <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </AccountIds>
          <AdGroups i:nil="false">
            <AdGroupReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
              <AdGroupId>ValueHere</AdGroupId>
            </AdGroupReportScope>
          </AdGroups>
          <Campaigns i:nil="false">
            <CampaignReportScope>
              <AccountId>ValueHere</AccountId>
              <CampaignId>ValueHere</CampaignId>
            </CampaignReportScope>
          </Campaigns>
        </Scope>
        <Time i:nil="false">
          <CustomDateRangeEnd i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeEnd>
          <CustomDateRangeStart i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </CustomDateRangeStart>
          <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
        </Time>
      </ReportRequest>
    </SubmitGenerateReportRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Reporting/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <SubmitGenerateReportResponse xmlns="https://bingads.microsoft.com/Reporting/v11">
      <ReportRequestId d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</ReportRequestId>
    </SubmitGenerateReportResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SubmitGenerateReportResponse> SubmitGenerateReportAsync(
	ReportRequest reportRequest)
{
	var request = new SubmitGenerateReportRequest
	{
		ReportRequest = reportRequest
	};

	return (await ReportingService.CallAsync((s, r) => s.SubmitGenerateReportAsync(r), request));
}
```
```java
static SubmitGenerateReportResponse submitGenerateReport(
	ReportRequest reportRequest) throws RemoteException, Exception
{
	SubmitGenerateReportRequest request = new SubmitGenerateReportRequest();

	request.setReportRequest(reportRequest);

	return ReportingService.getService().submitGenerateReport(request);
}
```
```php
static function SubmitGenerateReport(
	$reportRequest)
{

	$GLOBALS['Proxy'] = $GLOBALS['ReportingProxy'];

	$request = new SubmitGenerateReportRequest();

	$request->ReportRequest = $reportRequest;

	return $GLOBALS['ReportingProxy']->GetService()->SubmitGenerateReport($request);
}
```
```python
response=reporting_service.SubmitGenerateReport(
	ReportRequest=ReportRequest)
```

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

