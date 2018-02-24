---
title: ContactInfo Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the contact information for a user.
---
# ContactInfo Data Object - Customer Management
Defines the contact information for a user.

## Syntax
```xml
<xs:complexType name="ContactInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Address" nillable="true" type="tns:Address" />
    <xs:element minOccurs="0" name="ContactByPhone" nillable="true" type="xs:boolean" />
    <xs:element minOccurs="0" name="ContactByPostalMail" nillable="true" type="xs:boolean" />
    <xs:element minOccurs="0" name="Email" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="EmailFormat" nillable="true" type="tns:EmailFormat" />
    <xs:element minOccurs="0" name="Fax" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="HomePhone" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Mobile" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Phone1" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Phone2" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="address"></a>Address|The address of the user.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[Address](address.md)|
|<a name="contactbyphone"></a>ContactByPhone|A value that determines whether the user should be contacted by telephone. If **true**, the telephone number specified in the *Phone1* element is used to contact the user.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**boolean**|
|<a name="contactbypostalmail"></a>ContactByPostalMail|A value that determines whether the user should be contacted by postal mail. If **true**, correspondence is sent to the address specified in the *Address* element.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**boolean**|
|<a name="email"></a>Email|The email address is used to send the account activation notification to the user, and can contain a maximum of 100 characters.<br /><br />If the user should be contacted by email, set the *EmailFormat* element to a valid format value.<br /><br /> The contact info email address may differ from the email address corresponding to the authenticated Microsoft Account. For more information, see the *IsMigratedToMicrosoftAccount* and *UserName* elements of the [User](../customer-management-service/user.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="emailformat"></a>EmailFormat|The format of the body of an email message to use when correspondence is sent to the user (this does not apply to the activation notification email message).<br /><br />You must set this element if you want the user contacted via email.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[EmailFormat](emailformat.md)|
|<a name="fax"></a>Fax|The fax telephone number of the user. The telephone number can contain a maximum of 100 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="homephone"></a>HomePhone|The home telephone number of the user. The telephone number can contain a maximum of 100 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="id"></a>Id|The system generated identifier of the object.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="mobile"></a>Mobile|The mobile telephone number of the user. The telephone number can contain a maximum of 100 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="phone1"></a>Phone1|The primary telephone number of the user. The telephone number can contain a maximum of 100 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="phone2"></a>Phone2|An alternate telephone number for the user. The telephone number can contain a maximum of 100 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[User](user.md)  
