---
title: GetAccountMigrationStatuses Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the migration status info for the specified accounts.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetAccountMigrationStatuses Service Operation - Campaign Management
Gets the migration status info for the specified accounts.

## <a name="request"></a>Request Elements
The *GetAccountMigrationStatusesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|The identifiers of each account to request migration status.<br/><br/>**Required**: Yes|**long** array|
|<a name="migrationtype"></a>MigrationType|Filters the returned migration status by migration type.<br/><br/>Currently the only supported migration type is *SiteLinkAdExtension*. During calendar year 2017, Bing Ads upgraded all [SiteLinksAdExtension](/bingads/campaign-management-service/sitelinksadextension.md) objects (contains multiple sitelinks per ad extension) to [Sitelink2AdExtension](/bingads/campaign-management-service/sitelink2adextension.md) objects (contains one sitelink per ad extension).<br/><br/>**Required**: Yes|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAccountMigrationStatusesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="migrationstatuses"></a>MigrationStatuses|An array of account migration statuses.<br /><br />For each account identifier specified in the request, an *AccountMigrationStatusesInfo* object is returned.|[AccountMigrationStatusesInfo](accountmigrationstatusesinfo.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetAccountMigrationStatuses</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAccountMigrationStatusesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AccountIds>
      <MigrationType i:nil="false">ValueHere</MigrationType>
    </GetAccountMigrationStatusesRequest>
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
    <GetAccountMigrationStatusesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <MigrationStatuses d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AccountMigrationStatusesInfo>
          <AccountId>ValueHere</AccountId>
          <MigrationStatusInfo d4p1:nil="false">
            <MigrationStatusInfo>
              <MigrationType d4p1:nil="false">ValueHere</MigrationType>
              <StartTimeInUtc d4p1:nil="false">ValueHere</StartTimeInUtc>
              <Status>ValueHere</Status>
            </MigrationStatusInfo>
          </MigrationStatusInfo>
        </AccountMigrationStatusesInfo>
      </MigrationStatuses>
    </GetAccountMigrationStatusesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
```csharp
public async Task<GetAccountMigrationStatusesResponse> GetAccountMigrationStatusesAsync(
	IList<long> accountIds,
	string migrationType)
{
	var request = new GetAccountMigrationStatusesRequest
	{
		AccountIds = accountIds,
		MigrationType = migrationType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAccountMigrationStatusesAsync(r), request));
}
```
```java
static GetAccountMigrationStatusesResponse getAccountMigrationStatuses(
	ArrayOflong accountIds,
	java.lang.String migrationType) throws RemoteException, Exception
{
	GetAccountMigrationStatusesRequest request = new GetAccountMigrationStatusesRequest();

	request.setAccountIds(accountIds);
	request.setMigrationType(migrationType);

	return CampaignManagementService.getService().getAccountMigrationStatuses(request);
}
```
```php
static function GetAccountMigrationStatuses(
	$accountIds,
	$migrationType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAccountMigrationStatusesRequest();

	$request->AccountIds = $accountIds;
	$request->MigrationType = $migrationType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAccountMigrationStatuses($request);
}
```
```python
response=campaignmanagement_service.GetAccountMigrationStatuses(
	AccountIds=AccountIds,
	MigrationType=MigrationType)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

