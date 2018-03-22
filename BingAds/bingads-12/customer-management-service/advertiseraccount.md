---
title: AdvertiserAccount Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an advertiser account.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AdvertiserAccount Data Object - Customer Management
Defines an advertiser account.

## Syntax
```xml
<xs:complexType name="AdvertiserAccount" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="BillToCustomerId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="CurrencyCode" nillable="true" type="tns:CurrencyCode" />
    <xs:element minOccurs="0" name="AccountFinancialStatus" nillable="true" type="tns:AccountFinancialStatus" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Language" nillable="true" type="tns:LanguageType" />
    <xs:element minOccurs="0" name="LastModifiedByUserId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="LastModifiedTime" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Number" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ParentCustomerId" type="xs:long" />
    <xs:element minOccurs="0" name="PaymentMethodId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="PaymentMethodType" nillable="true" type="tns:PaymentMethodType" />
    <xs:element minOccurs="0" name="PrimaryUserId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="AccountLifeCycleStatus" nillable="true" type="tns:AccountLifeCycleStatus" />
    <xs:element minOccurs="0" name="TimeStamp" nillable="true" type="xs:base64Binary" />
    <xs:element minOccurs="0" name="TimeZone" nillable="true" type="tns:TimeZoneType" />
    <xs:element minOccurs="0" name="PauseReason" nillable="true" type="xs:unsignedByte" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q1:ArrayOfKeyValuePairOfstringstring" xmlns:q1="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="LinkedAgencies" nillable="true" type="tns:ArrayOfCustomerInfo" />
    <xs:element minOccurs="0" name="SalesHouseCustomerId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="TaxInformation" nillable="true" type="q2:ArrayOfKeyValuePairOfstringstring" xmlns:q2="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="BackUpPaymentInstrumentId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="BillingThresholdAmount" nillable="true" type="xs:decimal" />
    <xs:element minOccurs="0" name="BusinessAddress" nillable="true" type="tns:Address" />
    <xs:element minOccurs="0" name="AutoTagType" nillable="true" type="tns:AutoTagType" />
    <xs:element minOccurs="0" name="SoldToPaymentInstrumentId" nillable="true" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountfinancialstatus"></a>AccountFinancialStatus|The financial status of the account. For example, the status can indicate whether the account is in good standing or is past due.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountFinancialStatus](accountfinancialstatus.md)|
|<a name="accountlifecyclestatus"></a>AccountLifeCycleStatus|The status of the account. You cannot set the status of the account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountLifeCycleStatus](accountlifecyclestatus.md)|
|<a name="autotagtype"></a>AutoTagType|Determines whether to append or replace the supported UTM tracking codes.<br/><br/>Bing Ads can automatically add UTM tags to your destination URL so you can use your website analytics tool, for example Google Analytics, to track how people got to your website. Auto-tags are applied for example to expanded text ads, keywords, Bing Shopping Campaigns, and Sitelink Extensions. For details about auto-tagging, please see the Bing Ads help article [How do I add UTM tags to my landing page URL?](http://help.bingads.microsoft.com/#apex/3/en/56762/-1).<br/><br/>**Add:** Optional. If not specified the default value is Inactive.<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[AutoTagType](autotagtype.md)|
|<a name="backuppaymentinstrumentid"></a>BackUpPaymentInstrumentId|The identifier of a backup  payment instrument to use to settle the account. This element is not applicable for invoiced accounts.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="billingthresholdamount"></a>BillingThresholdAmount|A customer specified amount for settling against the selected payment instrument.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**decimal**|
|<a name="billtocustomerid"></a>BillToCustomerId|The identifier of the customer that is billed for the charges that the account generates. This is either the reseller that manages this account on behalf of the owner or the identifier of the customer that owns the account.<br /><br />The service sets the identifier based on the owner of the payment instrument identified in the *PaymentMethodId* element.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="businessaddress"></a>BusinessAddress|The location where your business is legally registered. If you are an agency working as an agent for your customer, this is the location where your client is legally registered. If you are an agency working as a reseller, this is the legally registered business address of your company. The business address is used to determine your tax requirements.<br/><br/>**Add:** Required for [AddAccount](addaccount.md); Optional for [SignupCustomer](signupcustomer.md). For [SignupCustomer](signupcustomer.md) if the *CurrencyType* is set to *INR* or *BRL* and you do not specify the *BusinessAddress*, then the [CountryCode](address.md#countrycode) of the [Address](address.md) will be set to the corresponding default value as follows: If the currency is set to *INR* the business address country code will be set to *IN*. If the currency is set to *BRL* the business address country code will be set to *BR*. <br/>**Update:** Optional for accounts that are not billed by monthly invoice. Having said that, if you want to make any changes to the [Address](address.md) then you must set its BusinessName, City, CountryCode, Line1, and StateOrProvince elements (where applicable); Read-only for monthly invoice accounts. To update the *BusinessAddress* of an invoice account, contact your account manager or support.|[Address](address.md)|
|<a name="currencycode"></a>CurrencyCode|The ISO code for the currency that is used to settle the account.<br/><br/>The service uses the currency information for billing purposes.<br/><br/>**Add:** Required<br/>**Update:** Read-only|[CurrencyCode](currencycode.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The system generated identifier of the account.<br /><br />This is the identifier that you set the *AccountId* element and *CustomerAccountId* SOAP header to in many of the campaign requests.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="language"></a>Language|The language used to render the invoice (if you use an invoice as your payment method).<br /><br />If you specify a language value when signing up a customer, the value is ignored. The signup process instead gets the language value from the *Lcid* element of the [User](user.md). If the *Lcid* element is set to a value such as *FrenchCanada*, the *Language* element is set to *French*.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[LanguageType](languagetype.md)|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|The identifier of the last user to update the account's information.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the account was last updated. The value is in Coordinated Universal Time (UTC).<br /><br /> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**dateTime**|
|<a name="linkedagencies"></a>LinkedAgencies|The list of agencies linked to this account.<br/><br/>Currently only one agency customer is supported when you add the account. When you retrieve the account all linked agency customer info will be included. <br/><br/>**Add:** Optional. If the owner manages the account, set to NULL.<br/>**Update:** Read-only|[CustomerInfo](customerinfo.md) array|
|<a name="name"></a>Name|The name of the account. The string can contain between 3 and 100 characters and must be unique among all account names within the customer.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="number"></a>Number|The system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form *xxxxxxxx*, where *xxxxxxxx* is a series of any eight alphanumeric characters.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|
|<a name="parentcustomerid"></a>ParentCustomerId|The identifier of the customer that owns the account.<br /><br />In the campaign requests that require a customer identifier, this is the identifier that you set the *CustomerId* SOAP header to.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**long**|
|<a name="pausereason"></a>PauseReason|A flag value that indicates who paused the account. The following are the possible values:<br /><br />1 - The user paused the account.<br /><br />2 - The billing service paused the account.<br /><br />4 - The user and billing service paused the account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**unsignedByte**|
|<a name="paymentmethodid"></a>PaymentMethodId|The identifier of the payment instrument to use to settle the account.<br/><br/>**Add:** Optional for [AddAccount](addaccount.md); Read-only for [SignupCustomer](signupcustomer.md). When you call [SignupCustomer](signupcustomer.md) set this element to NULL. The service picks up the payment method identifier associated with the reseller's invoice automatically.<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="paymentmethodtype"></a>PaymentMethodType|The type of payment instrument to use to settle the account. You do not have to set this value because the type is determined by the payment instrument corresponding to the *PaymentMethodId* element.<br /><br />When you call the [GetAccount](getaccount.md) and [SearchAccounts](searchaccounts.md) to get the account data, *PaymentMethodType* is set to NULL, and you cannot determine the payment method that the account uses.<br /><br /> Reserved for internal use.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[PaymentMethodType](paymentmethodtype.md)|
|<a name="primaryuserid"></a>PrimaryUserId|The identifier of the account manager who is primarily responsible for managing this account.<br /><br />By default, the value is set to the reseller's user identifier.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="saleshousecustomerid"></a>SalesHouseCustomerId|The identifier of the third party that is responsible for a sales lead.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="soldtopaymentinstrumentid"></a>SoldToPaymentInstrumentId|The identifier of the payment instrument of your client (the sold-to customer) to use to settle the account.<br/><br/>**Add:** Required for [AddAccount](addaccount.md) if the [BillToCustomerId](#billtocustomerid) differs from the [ParentCustomerId](#parentcustomerid); Read-only and not applicable for [SignupCustomer](signupcustomer.md). <br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="taxinformation"></a>TaxInformation|For a list of valid key and value strings for this element, see [AdvertiserAccount TaxInformation](#taxinformation) in the section below.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove a key and value pair, set the key and then set the value to an empty string (*""*).|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="timestamp"></a>TimeStamp|The time-stamp value that the system uses internally to reconcile updates when you call the [UpdateAccount](updateaccount.md) and [DeleteAccount](deleteaccount.md) operations.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**base64Binary**|
|<a name="timezone"></a>TimeZone|The default time-zone value to use for campaigns in this account.<br /><br />If you do not specify a value when the account is added, the time zone will be set to *PacificTimeUSCanadaTijuana* by default.<br /><br /> This time-zone value is used by the Bing Ads web application to display the account time zone preference, and does not provide a default time-zone value for campaigns that are created by using the Bulk or Campaign Management API.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[TimeZoneType](timezonetype.md)|

## <a name="remarks"></a>Remarks
### <a name="taxinformation"></a>AdvertiserAccount TaxInformation
The following is the list of keys that are available for the *TaxInformation* element of an *AdvertiserAccount*.  

|TaxInformation Key|Description|Countries|
|---------|---------|---------|
|TaxId|The account's tax identifier The tax identifier must be valid in the country that you specified in the BusinessAddress element. Without a tax identifier, taxes might apply based on your business location.<br/><br/>**Add:** Required<br/>**Update:** Read-only|Brazil, Australia, Taiwan|
|GstInNumber|GSTINNumber	This number starts with two numbers representing the state code in which the business is registered followed by a maximum of 13 number and letters.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|India|
|NZGSTNumber|The NZGSTN Number is an 8 or 9 Digit long TaxID. Without a NZGSTN Number taxes might apply based on your business location.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|New Zealand|
|PanNumber|The PAN number.<br/><br/>**Add:** Required<br/>**Update:** Read-only|India|
|TaxType|You can indicate the type of tax. Possible values are Business and Personal.<br/><br/>**Add:** Optional<br/>**Update:** Optional|All|
|VATNumber|The account's Value Added Tax (VAT) registration number (also known as VAT identifier). This number starts with 2 letters that are specific to each country/region, followed by a maximum of 12 numbers or letters. The VAT number must be valid in the country that you specified in the BusinessAddress element. Without a VAT registration number or exemption certificate, taxes might apply based on your business location.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|Austria, Belgium, Bulgaria, Cyprus, Czech Republic, Germany, Denmark, Estonia, Greece, Spain, Finland, France, United Kingdom, Croatia, Hungary, Ireland, Italy, Lithuania, Luxembourg, Latvia, Malta, The Netherlands, Poland, Portugal, Romania, Sweden, Slovenia, Slovakia|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[AddAccount](addaccount.md)  
[GetAccount](getaccount.md)  
[SearchAccounts](searchaccounts.md)  
[SignupCustomer](signupcustomer.md)  
[UpdateAccount](updateaccount.md)  
