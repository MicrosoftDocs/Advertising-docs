---
title: AdvertiserAccount Data Object
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# AdvertiserAccount Data Object
Defines an advertiser account.

## Syntax
```xml
<xs:complexType name="AdvertiserAccount" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Account">
      <xs:sequence>
        <xs:element minOccurs="0" name="LinkedAgencies" nillable="true" type="tns:ArrayOfCustomerInfo" />
        <xs:element minOccurs="0" name="SalesHouseCustomerId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="TaxInformation" nillable="true" type="q2:ArrayOfKeyValuePairOfstringstring" xmlns:q2="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
        <xs:element minOccurs="0" name="BackUpPaymentInstrumentId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="BillingThresholdAmount" nillable="true" type="xs:decimal" />
        <xs:element minOccurs="0" name="BusinessAddress" nillable="true" type="tns:Address">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="linkedagencies"></a>LinkedAgencies|The list of agencies linked to this account.<br/><br/>Currently only one agency customer is supported. <br/><br/>**Add:** Optional. If the owner manages the account, set to NULL.<br/>**Update:** Read-only|[CustomerInfo](customerinfo.md) array|
|<a name="saleshousecustomerid"></a>SalesHouseCustomerId|The identifier of the third party that is responsible for a sales lead.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="taxinformation"></a>TaxInformation|For a list of valid key and value strings for this element, see [AdvertiserAccount TaxInformation](#taxinformation) in the section below.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove a key and value pair, set the key and then set the value to an empty string (*""*).|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="backuppaymentinstrumentid"></a>BackUpPaymentInstrumentId|The identifier of a backup  payment instrument to use to settle the account. This element is not applicable for invoiced accounts.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="billingthresholdamount"></a>BillingThresholdAmount|A customer specified amount for settling against the selected payment instrument.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**decimal**|
|<a name="businessaddress"></a>BusinessAddress|The location where your business is legally registered. If you are an agency working as an agent for your customer, this is the location where your client is legally registered. If you are an agency working as a reseller, this is the legally registered business address of your company. The business address is used to determine your tax requirements.<br/><br/>**Note:** To update the *BusinessAddress* of an invoice account, contact your account manager or support.<br/><br/>**Add:** Optional. If the *CurrencyType* is set to *INR* or *BRL* and you do not specify the *BusinessAddress*, then the *CountryCode* of the [Address](../customer-management/address.md) will be set to the corresponding default value as follows: If the currency is set to *INR* the business address country code will be set to *IN*. If the currency is set to *BRL* the business address country code will be set to *BR*. <br/>**Update:** Read-only|[Address](address.md)|

The [AdvertiserAccount](advertiseraccount.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaccount"></a>Inherited Elements from Account
The [AdvertiserAccount](advertiseraccount.md) object derives from the [Account](account.md) object, and inherits the following elements. The descriptions below are specific to [AdvertiserAccount](advertiseraccount.md), and might not apply to other objects that inherit the same elements from the [Account](account.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accounttype"></a>AccountType|The type of the account. For example, whether the account is an advertiser account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountType](accounttype.md)|
|<a name="billtocustomerid"></a>BillToCustomerId|The identifier of the customer that is billed for the charges that the account generates. This is either the reseller that manages this account on behalf of the owner or the identifier of the customer that owns the account.<br /><br />The service sets the identifier based on the owner of the payment instrument identified in the *PaymentMethodId* element.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="countrycode"></a>CountryCode|The code that identifies the country/region in which the account operates. The service uses the country/region information for billing purposes.<br /><br />For a list of country code values, see [Common Market Values](~/guides/common-market-values.md).<br /><br />**Note:** If you specify a country code value when signing up a customer, the value is ignored. The signup process instead gets the country code value from the *CountryCode* element of the customer?s address. For more information, see the *CustomerAddress* element of the [Customer](../customer-management/customer.md).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|
|<a name="currencytype"></a>CurrencyType|The type of currency that is used to settle the account. The service uses the currency information for billing purposes.<br/><br/>**Add:** Required<br/>**Update:** Read-only|[CurrencyType](currencytype.md)|
|<a name="accountfinancialstatus"></a>AccountFinancialStatus|The financial status of the account. For example, the status can indicate whether the account is in good standing or is past due.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountFinancialStatus](accountfinancialstatus.md)|
|<a name="id"></a>Id|The system generated identifier of the account.<br /><br />This is the identifier that you set the *AccountId* element and *CustomerAccountId* SOAP header to in many of the campaign requests.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="language"></a>Language|The language used to render the invoice (if you use an invoice as your payment method).<br /><br />If you specify a language value when signing up a customer, the value is ignored. The signup process instead gets the language value from the *Lcid* element of the [User](../customer-management/user.md). If the *Lcid* element is set to a value such as *FrenchCanada*, the *Language* element is set to *French*.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[LanguageType](languagetype.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|For a list of valid key and value strings for this element, see [Account ForwardCompatibilityMap](#ForwardCompatibilityMap) in the section below.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove a key and value pair, set the key and then set the value to an empty string (*""*).|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|The identifier of the last user to update the account?s information.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the account was last updated. The value is in Coordinated Universal Time (UTC).<br /><br />**Note:** The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**dateTime**|
|<a name="name"></a>Name|The name of the account. The name can contain a maximum of 100 characters and must be unique within the customer.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="number"></a>Number|The system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form *xxxxxxxx*, where *xxxxxxxx* is a series of any eight alphanumeric characters.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|
|<a name="parentcustomerid"></a>ParentCustomerId|The identifier of the customer that owns the account.<br /><br />In the campaign requests that require a customer identifier, this is the identifier that you set the *CustomerId* SOAP header to.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**long**|
|<a name="paymentmethodid"></a>PaymentMethodId|The identifier of the payment instrument to use to settle the account.<br /><br />When signing up a customer, set this element to NULL. The service picks up the payment method identifier associated with the reseller?s invoice automatically.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="paymentmethodtype"></a>PaymentMethodType|The type of payment instrument to use to settle the account. You do not have to set this value because the type is determined by the payment instrument corresponding to the *PaymentMethodId* element.<br /><br />When you call the [GetAccount](../customer-management/getaccount.md) and [SearchAccounts](../customer-management/searchaccounts.md) to get the account data, *PaymentMethodType* is set to NULL, and you cannot determine the payment method that the account uses.<br /><br />**Note:** Reserved for internal use.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[PaymentMethodType](paymentmethodtype.md)|
|<a name="primaryuserid"></a>PrimaryUserId|The identifier of the account manager who is primarily responsible for managing this account.<br /><br />By default, the value is set to the reseller?s user identifier.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="accountlifecyclestatus"></a>AccountLifeCycleStatus|The status of the account. You cannot set the status of the account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountLifeCycleStatus](accountlifecyclestatus.md)|
|<a name="timestamp"></a>TimeStamp|The time-stamp value that the system uses internally to reconcile updates when you call the [UpdateAccount](../customer-management/updateaccount.md) and [DeleteAccount](../customer-management/deleteaccount.md) operations.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**base64Binary**|
|<a name="timezone"></a>TimeZone|The default time-zone value to use for campaigns in this account.<br /><br />If you do not specify a value when the account is added, the time zone will be set to *PacificTimeUSCanadaTijuana* by default.<br /><br />**Note:** This time-zone value is used by the Bing Ads web application to display the account time zone preference, and does not provide a default time-zone value for campaigns that are created by using the Campaign Management API.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[TimeZoneType](timezonetype.md)|
|<a name="pausereason"></a>PauseReason|A flag value that indicates who paused the account. The following are the possible values:<br /><br />1 ? The user paused the account.<br /><br />2 ? The billing service paused the account.<br /><br />4 ? The user and billing service paused the account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**unsignedByte**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11/Entities  

