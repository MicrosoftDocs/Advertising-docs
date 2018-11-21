---
title: ActionAdExtensionActionType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible options for action text that can be displayed in an action ad extension.
---
# ActionAdExtensionActionType Value Set - Campaign Management
Defines the possible options for action text that can be displayed in an action ad extension. 

The displayed action text will vary depending on the [Language](actionadextension.md#language) that you define in your [ActionAdExtension](actionadextension.md). For example if you choose [ActNow](#actnow) from the values below, and set the action ad extension [Language](actionadextension.md) to *German*, the displayed action text is *Jetzt handeln*. For details about display action text per language see [Action Text for Action Ad Extensions](../guides/ad-languages.md#actionadextension-actiontext).

## Syntax
```xml
<xs:simpleType name="ActionAdExtensionActionType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="ActNow" />
    <xs:enumeration value="ApplyNow" />
    <xs:enumeration value="BetNow" />
    <xs:enumeration value="BidNow" />
    <xs:enumeration value="BookACar" />
    <xs:enumeration value="BookHotel" />
    <xs:enumeration value="BookNow" />
    <xs:enumeration value="Browse" />
    <xs:enumeration value="BuyNow" />
    <xs:enumeration value="ChatNow" />
    <xs:enumeration value="Compare" />
    <xs:enumeration value="ContactUs" />
    <xs:enumeration value="Coupon" />
    <xs:enumeration value="Donate" />
    <xs:enumeration value="Download" />
    <xs:enumeration value="EmailNow" />
    <xs:enumeration value="EnrollNow" />
    <xs:enumeration value="Explore" />
    <xs:enumeration value="FileNow" />
    <xs:enumeration value="FindJob" />
    <xs:enumeration value="FreePlay" />
    <xs:enumeration value="FreeQuote" />
    <xs:enumeration value="FreeTrial" />
    <xs:enumeration value="GetDeals" />
    <xs:enumeration value="GetOffer" />
    <xs:enumeration value="GetQuote" />
    <xs:enumeration value="JoinNow" />
    <xs:enumeration value="LearnMore" />
    <xs:enumeration value="ListenNow" />
    <xs:enumeration value="LogIn" />
    <xs:enumeration value="Message" />
    <xs:enumeration value="NewCars" />
    <xs:enumeration value="OrderNow" />
    <xs:enumeration value="PlayGame" />
    <xs:enumeration value="PlayNow" />
    <xs:enumeration value="PostJob" />
    <xs:enumeration value="Register" />
    <xs:enumeration value="RentACar" />
    <xs:enumeration value="RentNow" />
    <xs:enumeration value="Reserve" />
    <xs:enumeration value="Sale" />
    <xs:enumeration value="SaveNow" />
    <xs:enumeration value="Schedule" />
    <xs:enumeration value="SeeMenu" />
    <xs:enumeration value="SeeMore" />
    <xs:enumeration value="SeeOffer" />
    <xs:enumeration value="SellNow" />
    <xs:enumeration value="ShopNow" />
    <xs:enumeration value="Showtimes" />
    <xs:enumeration value="SignIn" />
    <xs:enumeration value="SignUp" />
    <xs:enumeration value="StartFree" />
    <xs:enumeration value="StartNow" />
    <xs:enumeration value="Subscribe" />
    <xs:enumeration value="TestDrive" />
    <xs:enumeration value="TryNow" />
    <xs:enumeration value="UsedCars" />
    <xs:enumeration value="ViewCars" />
    <xs:enumeration value="ViewNow" />
    <xs:enumeration value="ViewPlans" />
    <xs:enumeration value="VisitSite" />
    <xs:enumeration value="VoteNow" />
    <xs:enumeration value="Watch" />
    <xs:enumeration value="WatchMore" />
    <xs:enumeration value="WatchNow" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="actnow"></a>ActNow|Use the translated version of *ActNow* in the action ad extension.|
|<a name="applynow"></a>ApplyNow|Use the translated version of *ApplyNow* in the action ad extension.|
|<a name="betnow"></a>BetNow|Use the translated version of *BetNow* in the action ad extension.|
|<a name="bidnow"></a>BidNow|Use the translated version of *BidNow* in the action ad extension.|
|<a name="bookacar"></a>BookACar|Use the translated version of *BookACar* in the action ad extension.|
|<a name="bookhotel"></a>BookHotel|Use the translated version of *BookHotel* in the action ad extension.|
|<a name="booknow"></a>BookNow|Use the translated version of *BookNow* in the action ad extension.|
|<a name="browse"></a>Browse|Use the translated version of *Browse* in the action ad extension.|
|<a name="buynow"></a>BuyNow|Use the translated version of *BuyNow* in the action ad extension.|
|<a name="chatnow"></a>ChatNow|Use the translated version of *ChatNow* in the action ad extension.|
|<a name="compare"></a>Compare|Use the translated version of *Compare* in the action ad extension.|
|<a name="contactus"></a>ContactUs|Use the translated version of *ContactUs* in the action ad extension.|
|<a name="coupon"></a>Coupon|Use the translated version of *Coupon* in the action ad extension.|
|<a name="donate"></a>Donate|Use the translated version of *Donate* in the action ad extension.|
|<a name="download"></a>Download|Use the translated version of *Download* in the action ad extension.|
|<a name="emailnow"></a>EmailNow|Use the translated version of *EmailNow* in the action ad extension.|
|<a name="enrollnow"></a>EnrollNow|Use the translated version of *EnrollNow* in the action ad extension.|
|<a name="explore"></a>Explore|Use the translated version of *Explore* in the action ad extension.|
|<a name="filenow"></a>FileNow|Use the translated version of *FileNow* in the action ad extension.|
|<a name="findjob"></a>FindJob|Use the translated version of *FindJob* in the action ad extension.|
|<a name="freeplay"></a>FreePlay|Use the translated version of *FreePlay* in the action ad extension.|
|<a name="freequote"></a>FreeQuote|Use the translated version of *FreeQuote* in the action ad extension.|
|<a name="freetrial"></a>FreeTrial|Use the translated version of *FreeTrial* in the action ad extension.|
|<a name="getdeals"></a>GetDeals|Use the translated version of *GetDeals* in the action ad extension.|
|<a name="getoffer"></a>GetOffer|Use the translated version of *GetOffer* in the action ad extension.|
|<a name="getquote"></a>GetQuote|Use the translated version of *GetQuote* in the action ad extension.|
|<a name="joinnow"></a>JoinNow|Use the translated version of *JoinNow* in the action ad extension.|
|<a name="learnmore"></a>LearnMore|Use the translated version of *LearnMore* in the action ad extension.|
|<a name="listennow"></a>ListenNow|Use the translated version of *ListenNow* in the action ad extension.|
|<a name="login"></a>LogIn|Use the translated version of *LogIn* in the action ad extension.|
|<a name="message"></a>Message|Use the translated version of *Message* in the action ad extension.|
|<a name="newcars"></a>NewCars|Use the translated version of *NewCars* in the action ad extension.|
|<a name="ordernow"></a>OrderNow|Use the translated version of *OrderNow* in the action ad extension.|
|<a name="playgame"></a>PlayGame|Use the translated version of *PlayGame* in the action ad extension.|
|<a name="playnow"></a>PlayNow|Use the translated version of *PlayNow* in the action ad extension.|
|<a name="postjob"></a>PostJob|Use the translated version of *PostJob* in the action ad extension.|
|<a name="register"></a>Register|Use the translated version of *Register* in the action ad extension.|
|<a name="rentacar"></a>RentACar|Use the translated version of *RentACar* in the action ad extension.|
|<a name="rentnow"></a>RentNow|Use the translated version of *RentNow* in the action ad extension.|
|<a name="reserve"></a>Reserve|Use the translated version of *Reserve* in the action ad extension.|
|<a name="sale"></a>Sale|Use the translated version of *Sale* in the action ad extension.|
|<a name="savenow"></a>SaveNow|Use the translated version of *SaveNow* in the action ad extension.|
|<a name="schedule"></a>Schedule|Use the translated version of *Schedule* in the action ad extension.|
|<a name="seemenu"></a>SeeMenu|Use the translated version of *SeeMenu* in the action ad extension.|
|<a name="seemore"></a>SeeMore|Use the translated version of *SeeMore* in the action ad extension.|
|<a name="seeoffer"></a>SeeOffer|Use the translated version of *SeeOffer* in the action ad extension.|
|<a name="sellnow"></a>SellNow|Use the translated version of *SellNow* in the action ad extension.|
|<a name="shopnow"></a>ShopNow|Use the translated version of *ShopNOw* in the action ad extension.|
|<a name="showtimes"></a>Showtimes|Use the translated version of *Showtimes* in the action ad extension.|
|<a name="signin"></a>SignIn|Use the translated version of *SignIn* in the action ad extension.|
|<a name="signup"></a>SignUp|Use the translated version of *SignUp* in the action ad extension.|
|<a name="startfree"></a>StartFree|Use the translated version of *StartFree* in the action ad extension.|
|<a name="startnow"></a>StartNow|Use the translated version of *StartNow* in the action ad extension.|
|<a name="subscribe"></a>Subscribe|Use the translated version of *Subscribe* in the action ad extension.|
|<a name="testdrive"></a>TestDrive|Use the translated version of *TestDrive* in the action ad extension.|
|<a name="trynow"></a>TryNow|Use the translated version of *TryNow* in the action ad extension.|
|<a name="unknown"></a>Unknown|Reserved for future use.|
|<a name="usedcars"></a>UsedCars|Use the translated version of *UsedCars* in the action ad extension.|
|<a name="viewcars"></a>ViewCars|Use the translated version of *ViewCars* in the action ad extension.|
|<a name="viewnow"></a>ViewNow|Use the translated version of *ViewNow* in the action ad extension.|
|<a name="viewplans"></a>ViewPlans|Use the translated version of *ViewPlans* in the action ad extension.|
|<a name="visitsite"></a>VisitSite|Use the translated version of *VisitSite* in the action ad extension.|
|<a name="votenow"></a>VoteNow|Use the translated version of *VoteNow* in the action ad extension.|
|<a name="watch"></a>Watch|Use the translated version of *Watch* in the action ad extension.|
|<a name="watchmore"></a>WatchMore|Use the translated version of *WatchMore* in the action ad extension.|
|<a name="watchnow"></a>WatchNow|Use the translated version of *WatchNow* in the action ad extension.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[ActionAdExtension](actionadextension.md)  
