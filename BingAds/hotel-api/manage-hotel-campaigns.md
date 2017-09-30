---
title: "Manage Hotel Ad Campaigns"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Manage Hotel Ad Campaigns
> [!NOTE]
> Hotel Ads is under pilot and available to pilot participants only.  Please contact your account manager for details.
>
> The API and documenation are subject to change.

The Hotel API lets you manage your hotel ad campaigns and bidding.

If you haven't already done so, familiarize yourself with the following topics:

- [The basics](../hotel-api/hotel-api.md#thebasics)
- [Get Started](../transaction-message/get-started.md)
- [API reference](../hotel-api/reference.md)

<a name="workingwithsubaccounts" />
## Working with subaccounts

Subaccounts are the top-level organization of Hotel Ads. Bing creates the default subaccount for you when you sign up for Hotel Ads. The API lets you list subaccounts, get a specific subaccount, and update a subaccount.

> [!NOTE]
> The API provides the ability to add subaccounts but Bing currently restricts accounts to one subaccount.

The following are the REST templates that you use to manage subaccounts.

- `/SubAccounts` &mdash; [GET](../hotel-api/reference.md#listsubaccounts) | [POST](../hotel-api/reference.md#addsubaccounts)
- `/SubAccounts('{subAccountId}')` &mdash; [GET](../hotel-api/reference.md#getsubaccount) | [PATCH](../hotel-api/reference.md#updatesubaccount)

For an example that gets and updates subaccounts, see [C# example](../hotel-api/subaccount-csharp-example.md).

<a name="listingsubaccounts" />
### Listing subaccounts

To get the list of subaccounts, send the following request.

```
GET https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
```

The response contains a [collectionresponse](../hotel-api/reference.md#collectionresponse) object. The `context` field identifies the type of object in the `value` array. In this case, `value` contains a list of [SubAccount](../hotel-api/reference.md#subaccount) objects.

```
HTTP/1.1 200 OK
x-ms-requestid: a21451ae-f86b-4a19-a00e-9265b59a99ec
x-ms-trackingid: 7cd2710c-821a-48e8-99af-efdc05aebe86

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#subaccounts",
  "@odata.count":1,"value":[
    {
      "Id":"1902000002",
	  "Name":"DefaultSubAccount1",
	  "Status":"Active",
	  "Bid":{
        "@odata.type":"#Model.FixedBid",
		"Amount":2.75
      },
	  "BidMultipliers":[],
	  "DailyBudget":{
        "Amount":125.25
      },
	  "MaximumBid":{
        "Amount":10.0
      }
    }
  ]
}
```

<a name="updatingasubaccount" />
### Updating a subaccount

The subaccount specifies the default bid and bid multipliers to use for hotel groups and hotels that don't specify a bid or multipliers. The subaccount also specifies the budget that's spread throughout the day, and the maximum bid that you want all bids not to exceed.

For details about the valid bid range and budget for your market, see the Currency Value table in the [Currencies](~/guides/currencies.md) topic.

To pause a subaccount, set the `Bid` or `Budget` property to zero (0.0). All hotels in the paused subaccount will not serve. To activate the subaccount, set `Bid` and `Budget` to a value greater than zero.  

To update any of these properties, send the following request. The body of the request contains a [subaccount](../hotel-api/reference.md#subaccount) object with only the properties that you want to update. This example shows adding multipliers.

```
PATCH https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>') HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Content-Type: application/json
Host: <host>
Content-Length: 682

{
  "Id":"1902000002",
  "BidMultipliers":[
    { 
	  "Countries":["US"],
	  "Factor":1.1,
	  "@odata.type":"#Model.UserCountryMultiplier"
	},
	{
	  "Sites":["LocalUniversal","MapResults"],
	  "Factor":0.85,
	  "@odata.type":"#Model.SiteMultiplier"
	},
	{
	  "DeviceTypes":["Desktop"],
	  "Factor":0.65,
	  "@odata.type":"#Model.DeviceMultiplier"
	},
	{
	  "MinimumNumberOfNights":5,
	  "Factor":1.3,
	  "@odata.type":"#Model.LengthOfStayMultiplier"
	},
	{
	  "DaysOfWeek":["Thursday","Friday","Saturday"],
	  "Factor":1.2,
	  "@odata.type":"#Model.CheckinDayOfWeekMultiplier"
	},
	{
	  "DaysOfWeek":["Sunday","Monday"],
	  "Factor":0.9,
	  "@odata.type":"#Model.CheckinDayOfWeekMultiplier"
	},
	{
	  "MinimumNumberOfDays":3,
	  "Factor":1.3,
	  "@odata.type":"#Model.AdvanceBookingWindowMultiplier"
	} 
  ]
}
```

<a name="gettingsubaccounts" />
### Getting a subaccount

To get a specific subaccount, send the following request. The subaccount ID must be wrapped in single quotes as shown.

```
GET https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>') HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
```

The response contains a contains a [subaccount](../hotel-api/reference.md#subaccount) object.

```
HTTP/1.1 200 OK
x-ms-requestid: 58d37dd1-78ae-4ced-91e4-7f57e647ddee
x-ms-trackingid: 5345bf4f-e64a-47a6-8d1e-43cc0231dc1b

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#subaccounts/$entity",
  "Id":"1902000002",
  "Name":"DefaultSubAccount1",
  "Status":"Active",
  "Bid":{
    "@odata.type":"#Model.FixedBid",
	"Amount":2.75
  },
  "BidMultipliers":[
    {
      "@odata.type":"#Model.DeviceMultiplier",
	  "Factor":0.65,
	  "DeviceTypes":["Desktop"]
    },
	{
      "@odata.type":"#Model.LengthOfStayMultiplier",
	  "Factor":1.3,
	  "MinimumNumberOfNights":5
    },
	{
      "@odata.type":"#Model.UserCountryMultiplier",
	  "Factor":1.1,
	  "Countries":["US"]
    },
	{
      "@odata.type":"#Model.AdvanceBookingWindowMultiplier",
	  "Factor":1.3,
	  "MinimumNumberOfDays":3
    },
	{
      "@odata.type":"#Model.CheckinDayOfWeekMultiplier",
	  "Factor":0.9,
	  "DaysOfWeek":["Monday","Sunday"]
    },
	{
      "@odata.type":"#Model.CheckinDayOfWeekMultiplier",
	  "Factor":1.2,
	  "DaysOfWeek":["Thursday","Friday","Saturday"]
    },
	{
      "@odata.type":"#Model.SiteMultiplier",
	  "Factor":0.85,
	  "Sites":["MapResults","LocalUniversal"]
    }
  ],
  "DailyBudget":{
    "Amount":125.25
  },
  "MaximumBid":{
    "Amount":10.0
  },
  "HotelAssociationCount":39540
}
```

<a name="workingwithhotelgroups" />
## Working with hotel groups

Hotel groups are the second level of organization that you use to group hotels. When you create a subaccount, Bing creates a default hotel group under the subaccount named, Ungrouped. The API lets you list, get, update, and add hotel groups.

The following are the REST templates that you use to manage hotel groups.

- `/SubAccounts('{subAccountId}')/HotelGroups` &mdash; [GET](../hotel-api/reference.md#listhotelgroups) | [POST](../hotel-api/reference.md#addhotelgroup)
- `/SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')` &mdash; [GET](../hotel-api/reference.md#gethotelgroup) | [PATCH](../hotel-api/reference.md#updatehotelgroup)

For an example that gets, adds, and updates hotel groups, see [C# example](../hotel-api/hotel-group-csharp-example.md).

<a name="listinghotelgroups" />
### Listing hotel groups

To get the list of hotel groups under a subaccount, send the following request.

```
GET https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/HotelGroups HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
```

The response contains a [collectionresponse](../hotel-api/reference.md#collectionresponse) object. The `context` field identifies the type of object in the `value` array. In this case, `value` contains a list of [HotelGroup](../hotel-api/reference.md#hotelgroup) objects. This example shows the default Ungrouped group.

```
HTTP/1.1 200 OK
Content-Type: application/json; odata.metadata=minimal
x-ms-requestid: f526c0e6-f7d8-48c7-9270-8fb0a0465153
x-ms-trackingid: 21fafae0-4053-46e0-8271-87bc5fce6312

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#hotelgroups",
  "@odata.count":6,
  "value":[
    {
      "Id":"55113020342274",
	  "Name":"UnGrouped",
	  "Status":"Active",
	  "Bid":null,
	  "BidSource":null,
	  "BidMultipliers":[]
    },
	
	. . .
	
    {
      "Id":"55113020351605",
	  "Name":"test-2",
	  "Status":"Active",
	  "Bid":null,
	  "BidSource":null,
	  "BidMultipliers":[]
    }
  ]
}
```

<a name="addingahotelgroup" />
### Adding a hotel group

You would create a new hotel group if you want to create a new logical grouping of hotels. To specify the hotel group, use the [hotelgroup](../hotel-api/reference.md#hotelgroup) object. The only required field is `Name`. Use a descriptive name that indicates the grouping. The `Bid` and `BidMultipliers` fields are optional. If you don't specify them, the group uses the bid and bid multipliers from the subaccount. Specify them if you want to override the subaccount values. You can specify the bid, multipliers, or both.

For details about the valid bid range for your market, see the Currency Value table in the [Currencies](~/guides/currencies.md) topic.

The following example creates a hotel group that inherits the bid and bid multipliers from the subaccount.

```
POST https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/HotelGroups HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
Content-Length: 26

{"Name":"test-3"}
```

The response is an [addresponse](../hotel-api/reference.md#addresponse) object that contains the ID of the added hotel group.

```
HTTP/1.1 200 OK
Content-Length: 140
Content-Type: application/json; odata.metadata=minimal
x-ms-requestid: 8a2e2026-e170-4607-b4fe-06954a67b80a
x-ms-trackingid: e86fcdbd-613e-44a9-b5fc-528cfa87297a

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#Edm.String",
  "value":"55113020351606"
}
```

After adding a hotel group, use the [associate](../hotel-api/reference.md#associate) template to add hotels to the group. For information, see [Associating a hotel with a hotel group](#associatinghotels).

<a name="updatingahotelgroup" />
### Updating a hotel group

The hotel group specifies the default bid and bid multipliers to use for hotels in the group. The group either explicitly specifies them or inherits them from the subaccount it belongs to. You can use the API to update the bid and bid multipliers to use for hotels that do not specify a bid or multipliers.

For details about the valid bid range and budget for your market, see the Currency Value table in the [Currencies](~/guides/currencies.md) topic.

If the subaccount specifies the a maximum bid, the hotel group's bid must be less than the subaccount's maximum bid.

To pause a hotel group, set the `Bid` property to zero (0.0). All hotels in the paused hotel group will not serve. To activate the hotel group, set `Bid` to a value greater than zero.  

To update any of these properties, send the following request. The body of the request contains a [hotelgroup](../hotel-api/reference.md#hotelgroup) object with only the properties that you want to update. This example shows adding a bid and multipliers.

```
PATCH https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/HotelGroups('<hotelgroupid>') HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Content-Type: application/json
Content-Length: 474
Host: <host>

{
  "Id":"55113020351606",
  "Bid":{
    "Amount":4.75,
    "@odata.type":"#Model.FixedBid"
  },
  "BidMultipliers":[
    {
      "DeviceTypes":["Desktop"],
      "Factor":0.65,
      "@odata.type":"#Model.DeviceMultiplier"
    },
    {
      "MinimumNumberOfNights":7,
      "Factor":1.3,
      "@odata.type":"#Model.LengthOfStayMultiplier"
    },
    {
      "DaysOfWeek":["Thursday","Friday","Saturday"],
      "Factor":1.5,
      "@odata.type":"#Model.CheckinDayOfWeekMultiplier"
    },
    {
      "DaysOfWeek":["Sunday","Monday"],
      "Factor":2.5,
      "@odata.type":"#Model.CheckinDayOfWeekMultiplier"
    }
  ]
}
```

<a name="gettingahotelgroup" />
### Getting a hotel group

To get a specific hotel group, send the following request. The hotel group ID must be wrapped in single quotes as shown.

```
GET https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/HotelGroups('<hotelgroupid>') HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
```

The response contains a [hotelgroup](../hotel-api/reference.md#hotelgroup) object.

```
HTTP/1.1 200 OK
Content-Length: 813
Content-Type: application/json; odata.metadata=minimal
x-ms-requestid: 3be2a39c-723c-41bd-9e74-0a9e44c4fa3c
x-ms-trackingid: e5eba818-2ef7-4fe6-9225-9e2325414e3b

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#hotelgroups/$entity",
  "Id":"55113020351606",
  "Name":"test-2",
  "Status":"Active",
  "Bid":{
    "@odata.type":"#Model.FixedBid",
    "Amount":4.75
  },
  "BidSource":null,
  "BidMultipliers":[
    {
      "@odata.type":"#Model.DeviceMultiplier",
      "Factor":0.65,
      "DeviceTypes":["Desktop"]
    },
    {
      "@odata.type":"#Model.LengthOfStayMultiplier",
      "Factor":1.3,
      "MinimumNumberOfNights":7
    },
    {
      "@odata.type":"#Model.CheckinDayOfWeekMultiplier",
      "Factor":2.5,
      "DaysOfWeek":["Monday","Sunday"]
    },
    {
      "@odata.type":"#Model.CheckinDayOfWeekMultiplier",
      "Factor":1.5,
      "DaysOfWeek":["Thursday","Friday","Saturday"]
    }
  ],
  "HotelAssociationCount":0
}
```


<a name="workingwithhotels" />
## Working with hotels

Hotels represent the hotels in your hotel feed. The API lets you list, get, and update hotels. You cannot use the API to add hotels; to add hotels, use the hotel feed.

The following are the REST templates that you use to manage hotels.

- `/SubAccounts('{subAccountId}')/Hotels` &mdash; [GET](../hotel-api/reference.md#listallhotels)
- `/SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')/Hotels` &mdash; [GET](../hotel-api/reference.md#listhotels)
- `/SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')/Hotels('{hotelGroupId}')` &mdash; [GET](../hotel-api/reference.md#gethotel) | [PATCH](../hotel-api/reference.md#updatehotel)

For an example that gets and updates hotels, see [C# example](../hotel-api/hotel-csharp-example.md).


<a name="listinghotels" />
### Listing hotels

To get the list of hotels in a hotel group, send the following request.

```
GET https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/HotelGroups('<hotelgroupid>')/Hotels HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
```

The response contains a [collectionresponse](../hotel-api/reference.md#collectionresponse) object. The `context` field identifies the type of object in the `value` array. In this case, `value` contains a list of [Hotel](../hotel-api/reference.md#hotel) objects.

```
HTTP/1.1 200 OK
Content-Length: 1611
Content-Type: application/json; odata.metadata=minimal
x-ms-requestid: d836f741-8083-4d54-b49e-e1f14287b944
x-ms-trackingid: 3787a393-eca3-4ad0-be3d-dd4c7ae08906

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#hotels",
  "@odata.count":2,
  "value":[
    {
      "Id":"55113020344013",
      "Name":"Contoso Inn Singer",
      "PartnerHotelId":"942909",
      "Status":"Active",
      "CountryCode":"US",
      "Bid":{
        "@odata.type":"#Model.FixedBid",
        "Amount":2.75
      },
      "BidSource":"HotelGroup",
      "BidMultipliers":[
        {
          "@odata.type":"#Model.DeviceMultiplier",
          "Factor":2.65,
          "DeviceTypes":["Desktop"]
        },
        {
          "@odata.type":"#Model.LengthOfStayMultiplier",
          "Factor":1.3,
          "MinimumNumberOfNights":8
        },
        {
          "@odata.type":"#Model.UserCountryMultiplier",
          "Factor":1.1,
          "Countries":["US"]
        },
        {
          "@odata.type":"#Model.AdvanceBookingWindowMultiplier",
          "Factor":1.3,
          "MinimumNumberOfDays":3
        },
        {
          "@odata.type":"#Model.CheckinDayOfWeekMultiplier",
          "Factor":0.9,
          "DaysOfWeek":["Monday","Sunday"]
        },
        {
          "@odata.type":"#Model.CheckinDayOfWeekMultiplier",
          "Factor":1.2,
          "DaysOfWeek":["Thursday","Friday","Saturday"]
        },
        {
          "@odata.type":"#Model.SiteMultiplier",
          "Factor":0.85,"Sites":["MapResults","LocalUniversal"]
        }
      ]
    },
    {
      "Id":"55113020351595",
      "Name":"Contoso Inn Casino Center",
      "PartnerHotelId":"60278",
      "Status":"Active",
      "CountryCode":"US",
      "Bid":{
        "@odata.type":"#Model.FixedBid",
        "Amount":2.75
      },
      "BidSource":"HotelGroup",
      "BidMultipliers":[]
    }
  ]
}
```

<a name="updatingahotel" />
### Updating a hotel

The hotel specifies the bid and bid multipliers to use for hotel ads. The hotel either explicitly specifies them or inherits them from the hotel group or subaccount, in that order. You can use the API to update the bid and bid multipliers to use for the hotel's ad.

For details about the valid bid range for your market, see the Currency Value table in the [Currencies](~/guides/currencies.md) topic.

If the subaccount specifies the a maximum bid, the hotel's bid must be less than the subaccount's maximum bid.

To pause a hotel, set the `Bid` property to zero (0.0). Paused hotels will not serve. To activate the hotel, set `Bid` to a value greater than zero. A hotel will also not serve if the hotel group or subaccount that it belongs to is paused. 

To update any of these properties, send the following request. The body of the request contains a [hotel](../hotel-api/reference.md#hotel) object with only the properties that you want to update. This example shows updating the multipliers.

```
{
  "BidMultipliers":[
    {
      "Countries":["US"],
      "Factor":1.1,
      "@odata.type":"#Model.UserCountryMultiplier"
    },
    {
      "DeviceTypes":["Desktop"],
      "Factor":2.65,
      "@odata.type":"#Model.DeviceMultiplier"
    }
  ]
}
```

<a name="gettingahotel" />
### Getting a hotel

To get a specific hotel, send the following request. The hotel ID must be wrapped in single quotes as shown.

```
GET https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/HotelGroups('<hotelgroupid>')/Hotels('<hotelid>') HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
```

The response contains a [hotel](../hotel-api/reference.md#hotel) object.

```
HTTP/1.1 200 OK
Content-Length: 1122
Content-Type: application/json; odata.metadata=minimal
x-ms-requestid: a9a591c2-01c1-4e1c-8a6a-5cdece574460
x-ms-trackingid: ceb70eb3-36ca-4b99-a5f7-b1a04de1e4ae

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#hotels/$entity",
  "Id":"55113020344013",
  "Name":"Contoso Inn Singer",
  "PartnerHotelId":"942909",
  "Status":"Active",
  "CountryCode":"US",
  "Bid":null,
  "BidSource":null,
  "BidMultipliers":[
    {
      "@odata.type":"#Model.DeviceMultiplier",
      "Factor":2.65,
      "DeviceTypes":["Desktop"]
    },
    {
      "@odata.type":"#Model.UserCountryMultiplier",
      "Factor":1.1,
      "Countries":["US"]
    }
  ]
}
```

<a name="associatinghotels" />
## Associating a hotel with a hotel group

When you import your hotel feed file, the hotels go in the default Ungrouped hotel group. If you create new hotel groups so you can logically organize your hotel, you'll need to move them from the Ungrouped hotel group to one of the groups you created.

To move a hotel from one group to another, send the following request. The body of the request is an [associationcollection](../hotel-api/reference.md#associationcollection) object. 
```
POST https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/Associate HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Content-Type: application/json
Host: <host>
Content-Length: 169

{
  "HotelAssociations":[
    {
      "HotelGroupId":"55113020351226",
      "HotelId":"55113020351595"
    },
    {
      "HotelGroupId":"55113020351226",
      "HotelId":"55113020344013"
    }
  ]
}
``` 

The Associate method should always return success. If one or more of the associations fail, the response will contain the input association of the failed associations, and the reason for the failure. 

The response contains a [collectionresponse](../hotel-api/reference.md#collectionresponse) object. If the all associations succeeded, the `value` array is empty. Otherwise, `value` contains a [HotelAssociation](../hotel-api/reference.md#hotelassociation) object for each association that failed. The association's `Errors` field contains the reasons for the failure.

```
HTTP/1.1 200 OK
Content-Length: 770
Content-Type: application/json; odata.metadata=minimal
x-ms-requestid: 574fe6c6-503d-427d-8921-a259f76de0ed
x-ms-trackingid: a5f2510e-709a-4370-876e-bfb05ef2b8df

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#Collection(Model.HotelAssociation)",
  "value":[
    {
      "HotelId":"55113020351595",
      "HotelName":null,
      "PartnerHotelId":null,
      "HotelGroupId":"55113020351226",
      "HotelGroupName":null,
      "Errors@odata.type":"#Collection(Model.AdsApiError)",
      "Errors":[
        {
          "Code":"<code>","Property":"<propertyname>","Message":"<messagestring>"
        }
      ]
    }
  ]
}
```

To get a list of all hotel and hotel group associations for a subaccount, send the following request:

```
GET https://<host>/Travel/V1/Customers(<customerid>)/Accounts(<accountid>)/SubAccounts('<subaccountid>')/Associations HTTP/1.1
Authorization: Bearer <oauthaccesstoken>
Accept: application/json
Host: <host>
```

The response contains a [collectionresponse](../hotel-api/reference.md#collectionresponse) object. The `context` field identifies the type of object in the `value` array. In this case, `value` contains a list of [HotelAsssociation](../hotel-api/reference.md#hotelassociation) objects.

```
HTTP/1.1 200 OK
Content-Length: 6880
Content-Type: application/json; odata.metadata=minimal
x-ms-requestid: 50bb9a63-f324-4c28-84f9-733b24ab3d0f
x-ms-trackingid: 4fa56e03-7e86-4f44-b671-8e00a67c2eed

{
  "@odata.context":"http://<host>/Travel/v1/$metadata#Collection(Model.HotelAssociation)",
  "@odata.count":39540,
  "value":[
    {
      "HotelId":"55113020342273",
      "HotelName":"Contoso Inn Downtown DC/Convention Center",
      "PartnerHotelId":"99995",
      "HotelGroupId":"55113020342274",
      "HotelGroupName":"UnGrouped"
    },
    {
      "HotelId":"55113020342274",
      "HotelName":"The Contoso Hotel",
      "PartnerHotelId":"999896",
      "HotelGroupId":"55113020342274",
      "HotelGroupName":"UnGrouped"
    },
    
    . . .
    
  ]
}
```




