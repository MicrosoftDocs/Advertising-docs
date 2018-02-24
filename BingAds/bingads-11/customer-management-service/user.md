---
title: User Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a user.
---
# User Data Object - Customer Management
Defines a user.

## Syntax
```xml
<xs:complexType name="User" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="ContactInfo" nillable="true" type="tns:ContactInfo" />
    <xs:element minOccurs="0" name="CustomerAppScope" nillable="true" type="tns:ApplicationType" />
    <xs:element minOccurs="0" name="CustomerId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="JobTitle" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="LastModifiedByUserId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="LastModifiedTime" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Lcid" nillable="true" type="tns:LCID" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="tns:PersonName" />
    <xs:element minOccurs="0" name="Password" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="SecretAnswer" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="SecretQuestion" type="tns:SecretQuestion" />
    <xs:element minOccurs="0" name="UserLifeCycleStatus" nillable="true" type="tns:UserLifeCycleStatus" />
    <xs:element minOccurs="0" name="TimeStamp" nillable="true" type="xs:base64Binary" />
    <xs:element minOccurs="0" name="UserName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="IsMigratedToMicrosoftAccount" type="xs:boolean" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="contactinfo"></a>ContactInfo|The user's contact information.<br/><br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[ContactInfo](contactinfo.md)|
|<a name="customerappscope"></a>CustomerAppScope|Confirms that the customer to whom this user belongs is an advertiser.<br/><br/>**Update:** Read-only|[ApplicationType](applicationtype.md)|
|<a name="customerid"></a>CustomerId|The identifier of the customer to whom this user belongs.<br/><br/>**Update:** Read-only|**long**|
|<a name="id"></a>Id|The system generated identifier of the user.<br/><br/>**Update:** Required|**long**|
|<a name="ismigratedtomicrosoftaccount"></a>IsMigratedToMicrosoftAccount|If *true*, the user can be authenticated using  a Microsoft Account. For more information, see [Authentication with OAuth](bingads/guides/authentication-oauth.md).<br/><br/>**Update:** Read-only|**boolean**|
|<a name="jobtitle"></a>JobTitle|The user's job title. The title can contain a maximum of 50 characters.<br/><br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|The identifier of the last user to update the user's information.<br/><br/>**Update:** Read-only|**long**|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that that the user information was last updated. The value is in Coordinated Universal Time (UTC).<br /><br />The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Update:** Read-only|**dateTime**|
|<a name="lcid"></a>Lcid|The locale to use when sending correspondence to the user by email or postal mail. The default is EnglishUS.<br/><br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[LCID](lcid.md)|
|<a name="name"></a>Name|The name of the user.<br/><br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[PersonName](personname.md)|
|<a name="password"></a>Password|The user's Bing Ads managed sign-in password.<br /><br />The [GetUser](bingads/customer-management-service/getuser.md) operation does not return the password.<br/><br/>**Update:** Read-only|**string**|
|<a name="secretanswer"></a>SecretAnswer|The answer to the secret question that is specified in the *SecretQuestion* element. The answer must contain a minimum of five characters and a maximum of 64 characters.<br/><br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="secretquestion"></a>SecretQuestion|A question from a list of predefined questions that the user selects to use as his or her secret question. The *SecretAnswer* element contains the user's answer to the question. The secret question and answer are used to validate the user in case the user forgets his or her password, and requests it.<br/><br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[SecretQuestion](secretquestion.md)|
|<a name="timestamp"></a>TimeStamp|A time-stamp value that the system uses internally to reconcile updates when you call [UpdateUser](bingads/customer-management-service/updateuser.md) or [DeleteUser](bingads/customer-management-service/deleteuser.md).<br/><br/>**Update:** Required|**base64Binary**|
|<a name="userlifecyclestatus"></a>UserLifeCycleStatus|The status of the user.<br/><br/>**Update:** Read-only|[UserLifeCycleStatus](userlifecyclestatus.md)|
|<a name="username"></a>UserName|If the value of *IsMigratedToMicrosoftAccount* is false, this element contains the user's Bing Ads managed sign-in user name. The name is case-insensitive.<br /><br />If the value of *IsMigratedToMicrosoftAccount* is true, this element contains the email address corresponding to the authenticated Microsoft Account.<br /><br /> The email address of the Microsoft Account may differ from the Email element of the [ContactInfo](bingads/customer-management-service/contactinfo.md) object.<br/><br/>**Update:** Read-only|**string**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[GetUser](getuser.md)  
[UpdateUser](updateuser.md)  
