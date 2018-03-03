---
title: AdvertiserAccount Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an advertiser account.
---
# AdvertiserAccount Data Object - Customer Management
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
|<a name="backuppaymentinstrumentid"></a>BackUpPaymentInstrumentId|The identifier of a backup  payment instrument to use to settle the account. This element is not applicable for invoiced accounts.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="billingthresholdamount"></a>BillingThresholdAmount|A customer specified amount for settling against the selected payment instrument.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**decimal**|
|<a name="businessaddress"></a>BusinessAddress|The location where your business is legally registered. If you are an agency working as an agent for your customer, this is the location where your client is legally registered. If you are an agency working as a reseller, this is the legally registered business address of your company. The business address is used to determine your tax requirements.<br/><br/>**Add:** For [SignupCustomer](signupcustomer.md) if the *CurrencyType* is set to *INR* or *BRL* and you do not specify the *BusinessAddress*, then the *CountryCode* of the [Address](../customer-management-service/address.md) will be set to the corresponding default value as follows: If the currency is set to *INR* the business address country code will be set to *IN*. If the currency is set to *BRL* the business address country code will be set to *BR*. <br/>**Update:** Optional for accounts that are not billed by monthly invoice; Read-only for monthly invoice accounts. To update the *BusinessAddress* of an invoice account, contact your account manager or support.|[Address](address.md)|
|<a name="linkedagencies"></a>LinkedAgencies|The list of agencies linked to this account.<br/><br/>Currently only one agency customer is supported when you add the account. When you retrieve the account all linked agency customer info will be included. <br/><br/>**Add:** Optional. If the owner manages the account, set to NULL.<br/>**Update:** Read-only|[CustomerInfo](customerinfo.md) array|
|<a name="saleshousecustomerid"></a>SalesHouseCustomerId|The identifier of the third party that is responsible for a sales lead.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="taxinformation"></a>TaxInformation|For a list of valid key and value strings for this element, see [AdvertiserAccount TaxInformation](#taxinformation) in the section below.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove a key and value pair, set the key and then set the value to an empty string (*""*).|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|

The [AdvertiserAccount](advertiseraccount.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaccount"></a>Inherited Elements from Account
The [AdvertiserAccount](advertiseraccount.md) object derives from the [Account](account.md) object, and inherits the following elements. The descriptions below are specific to [AdvertiserAccount](advertiseraccount.md), and might not apply to other objects that inherit the same elements from the [Account](account.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountfinancialstatus"></a>AccountFinancialStatus|The financial status of the account. For example, the status can indicate whether the account is in good standing or is past due.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountFinancialStatus](accountfinancialstatus.md)|
|<a name="accountlifecyclestatus"></a>AccountLifeCycleStatus|The status of the account. You cannot set the status of the account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountLifeCycleStatus](accountlifecyclestatus.md)|
|<a name="accounttype"></a>AccountType|The type of the account. For example, whether the account is an advertiser account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AccountType](accounttype.md)|
|<a name="billtocustomerid"></a>BillToCustomerId|The identifier of the customer that is billed for the charges that the account generates. This is either the reseller that manages this account on behalf of the owner or the identifier of the customer that owns the account.<br /><br />The service sets the identifier based on the owner of the payment instrument identified in the *PaymentMethodId* element.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="countrycode"></a>CountryCode|The code that identifies the country/region in which the account operates. The service uses the country/region information for billing purposes.<br /><br />For a list of country code values, see [Ad Languages](../guides/ad-languages.md).<br/><br/>**Add:** Read-only for [SignupCustomer](signupcustomer.md). If you specify a country code value when signing up a customer, the value is ignored. The signup process instead gets the country code value from the *CountryCode* element of the customer's address. For more information, see the *CustomerAddress* element of the [Customer](../customer-management-service/customer.md).<br/>**Update:** Read-only|**string**|
|<a name="currencytype"></a>CurrencyType|The type of currency that is used to settle the account. The service uses the currency information for billing purposes.<br/><br/>**Add:** Required<br/>**Update:** Read-only|[CurrencyType](currencytype.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version. For a list of valid key and value strings for this element, see [Remarks](#remarks) below.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove a key and value pair, set the key and then set the value to an empty string (*""*).|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The system generated identifier of the account.<br /><br />This is the identifier that you set the *AccountId* element and *CustomerAccountId* SOAP header to in many of the campaign requests.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="language"></a>Language|The language used to render the invoice (if you use an invoice as your payment method).<br /><br />If you specify a language value when signing up a customer, the value is ignored. The signup process instead gets the language value from the *Lcid* element of the [User](../customer-management-service/user.md). If the *Lcid* element is set to a value such as *FrenchCanada*, the *Language* element is set to *French*.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[LanguageType](languagetype.md)|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|The identifier of the last user to update the account's information.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the account was last updated. The value is in Coordinated Universal Time (UTC).<br /><br /> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**dateTime**|
|<a name="name"></a>Name|The name of the account. The string can contain between 3 and 100 characters and must be unique among all account names within the customer.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="number"></a>Number|The system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form *xxxxxxxx*, where *xxxxxxxx* is a series of any eight alphanumeric characters.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|
|<a name="parentcustomerid"></a>ParentCustomerId|The identifier of the customer that owns the account.<br /><br />In the campaign requests that require a customer identifier, this is the identifier that you set the *CustomerId* SOAP header to.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**long**|
|<a name="pausereason"></a>PauseReason|A flag value that indicates who paused the account. The following are the possible values:<br /><br />1 - The user paused the account.<br /><br />2 - The billing service paused the account.<br /><br />4 - The user and billing service paused the account.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**unsignedByte**|
|<a name="paymentmethodid"></a>PaymentMethodId|The identifier of the payment instrument to use to settle the account.<br/><br/>**Add:** Read-only for [SignupCustomer](signupcustomer.md). When you call [SignupCustomer](signupcustomer.md) set this element to NULL. The service picks up the payment method identifier associated with the reseller's invoice automatically.<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="paymentmethodtype"></a>PaymentMethodType|The type of payment instrument to use to settle the account. You do not have to set this value because the type is determined by the payment instrument corresponding to the *PaymentMethodId* element.<br /><br />When you call the [GetAccount](../customer-management-service/getaccount.md) and [SearchAccounts](../customer-management-service/searchaccounts.md) to get the account data, *PaymentMethodType* is set to NULL, and you cannot determine the payment method that the account uses.<br /><br /> Reserved for internal use.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[PaymentMethodType](paymentmethodtype.md)|
|<a name="primaryuserid"></a>PrimaryUserId|The identifier of the account manager who is primarily responsible for managing this account.<br /><br />By default, the value is set to the reseller's user identifier.<br/><br/>**Add:** Read-only<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="timestamp"></a>TimeStamp|The time-stamp value that the system uses internally to reconcile updates when you call the [UpdateAccount](../customer-management-service/updateaccount.md) and [DeleteAccount](../customer-management-service/deleteaccount.md) operations.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**base64Binary**|
|<a name="timezone"></a>TimeZone|The default time-zone value to use for campaigns in this account.<br /><br />If you do not specify a value when the account is added, the time zone will be set to *PacificTimeUSCanadaTijuana* by default.<br /><br /> This time-zone value is used by the Bing Ads web application to display the account time zone preference, and does not provide a default time-zone value for campaigns that are created by using the Bulk or Campaign Management API.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[TimeZoneType](timezonetype.md)|

## <a name="remarks"></a>Remarks
### <a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap
The following is the list of keys that are available for the *ForwardCompatibilityMap* element of an *Account*.

-   [AutoTag](#autotag)

-   [TrackingUrlTemplate](#trackingurltemplate)

#### <a name="autotag"></a>AutoTag
Bing Ads can automatically add UTM tags to your destination URL so you can use your website analytics tool, for example Google Analytics, to track how people got to your website. Auto-tags are applied for example to expanded text ads, keywords, Bing Shopping Campaigns, and Sitelink Extensions. For details about auto-tagging, please see the Bing Ads help article [How do I add UTM tags to my landing page URL?](http://help.bingads.microsoft.com/#apex/3/en/56762/-1).

The  *AutoTag* key and value pair is an account level setting that determines whether to append or replace the supported UTM tracking codes. Tracking codes are inserted dynamically when each ad is shown, and the URL that you set up and stored in Bing Ads is not updated. 

The possible values for the *AutoTag* key are as follows. If the *AutoTag* key is not specified, the default value is 0.

* 0 - Bing Ads will not append any UTM tracking codes to your ad or keyword final URL.

* 1 - Bing Ads will automatically append the supported UTM tracking codes, and preserve any existing UTM tracking codes that you added to your ad or keyword's final URL.

* 2 - Bing Ads will automatically append the supported UTM tracking codes, and replace any of the existing and supported UTM tracking codes that you added to your ad or keyword's final URL.

#### <a name="trackingurltemplate"></a>TrackingUrlTemplate
The tracking template to use as a default for all URLs in your account. The value of the *TrackingUrlTemplate* key can be set to any valid string as described below.

The following validation rules apply to tracking templates.

-   Tracking templates defined for lower level entities e.g. keyword override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](http://go.microsoft.com/fwlink/?LinkID=627130).

-   The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

-   The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*.

-   You must include at least one of the following landing page URL parameters: *{lpurl}*, *{lpurl+2}*, *{lpurl+3}*, *{unescapedlpurl}*, *{escapedlpurl}*. Additionally, you can use any dynamic parameter supported by Bing Ads. For a list of supported parameters, see the *Available parameters* sections within the Bing Ads help article [Set up a tracking template](https://help.bingads.microsoft.com/#apex/3/en/56772/-1).

-   Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the final URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is  for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither {_season} or {_promocode}  are defined at the campaign, ad group, keyword, or ad level, then the final URL will be the same.

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
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

