# Ad
Represents an ad in the Bing Ads system.

Example usage:
```javascript
 var stats = ad.getStatsFor("THIS_MONTH");
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[asType](#astype)|[AdViewSpace](./AdViewSpace)|Returns an AdViewSpace object, which provides access to properties specific to the type of this ad.<br />
[enable](#enable)|void|Enables the ad.<br />
[getAdGroup](#getadgroup)|[AdGroup](./AdGroup)|Returns the parent ad group of this ad.<br />
[getApprovalStatus](#getapprovalstatus)|String|Returns the approval status of the ad.
[getCampaign](#getcampaign)|[Campaign](./Campaign)|Returns the parent campaign of this ad.<br />
[getDisapprovalReasons](#getdisapprovalreasons)|String[]|Returns an array containing the reasons for which this ad was disapproved. If it is not disapproved, the array will be empty.<br />
[getDisplayUrl](#getdisplayurl)|String|Returns the display URL of this ad. This value could be null for some types of ads.<br />
[getEntityType](#getentitytype)|String|Returns the type of entity of this ad, which is “Ad”.<br />
[getHeadline](#getheadline)|String|Returns the headline (title) of this ad. This value could be null for some types of ads.<br />
[getId](#getid)|long|Returns the ID of this ad. In order to specify a unique ID for an ad, both its ad group ID and this ID must be specified.<br />
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|[Stats](./Stats)|Returns a [Stats](./Stats) object for this ad for the specified predefined date range.
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|[Stats](./Stats)|Returns a [Stats](./Stats) object for this ad for the specified date range.
[getType](#gettype)|String|Returns the type of the ad.
[isEnabled](#isenabled)|boolean|Returns true if this ad is enabled. <br />
[isMobilePreferred](#ismobilepreferred)|boolean|Returns true if this ad indicates mobile device preference or false otherwise. <br />
[isPaused](#ispaused)|boolean|Returns true if this ad is paused. <br />
[isType](#istype)|[AdTypeSpace](./AdTypeSpace)|Returns an AdTypeSpace object which provides more information on the type of this ad. <br />
[pause](#pause)|void|Pauses this ad.<br />
[remove](#remove)|void|Removes this ad.<br />
[urls](#urls)|[AdUrls](./AdUrls)|Returns an AdUrls object which provides access to the `URL` fields of this ad. <br />
&nbsp;|&nbsp;|&nbsp;

## <a name="astype"></a>asType
Returns an AdViewSpace object, which provides access to properties specific to the type of this ad.

### Returns:
|Type|Description|
|-|-
[AdViewSpace](./AdViewSpace)|An AdViewSpace.
&nbsp;|&nbsp;
## <a name="enable"></a>enable
Enables the ad.

### Returns:
|Type|Description|
|-|-
void|The ad group to which this ad belongs.
&nbsp;|&nbsp;
## <a name="getadgroup"></a>getAdGroup
Returns the parent ad group of this ad.

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|The ad group to which this ad belongs.
&nbsp;|&nbsp;
## <a name="getapprovalstatus"></a>getApprovalStatus
Returns the approval status of the ad.

Possible values:

- APPROVED
- DISAPPROVED

### Returns:
|Type|Description|
|-|-
String|The approval status of the ad.
&nbsp;|&nbsp;
## <a name="getcampaign"></a>getCampaign
Returns the parent campaign of this ad.

### Returns:
|Type|Description|
|-|-
[Campaign](./Campaign)|The campaign to which this ad belongs.
&nbsp;|&nbsp;
## <a name="getdisapprovalreasons"></a>getDisapprovalReasons
Returns an array containing the reasons for which this ad was disapproved. If it is not disapproved, the array will be empty.

### Returns:
|Type|Description|
|-|-
String[]|
&nbsp;|&nbsp;
## <a name="getdisplayurl"></a>getDisplayUrl
Returns the display URL of this ad. This value could be null for some types of ads.

### Returns:
|Type|Description|
|-|-
String|The display URL of the ad.
&nbsp;|&nbsp;
## <a name="getentitytype"></a>getEntityType
Returns the type of entity of this ad, which is “Ad”.

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "Ad".
&nbsp;|&nbsp;
## <a name="getheadline"></a>getHeadline
Returns the headline (title) of this ad. This value could be null for some types of ads.

### Returns:
|Type|Description|
|-|-
String|The headline of the ad.
&nbsp;|&nbsp;
## <a name="getid"></a>getId
Returns the ID of this ad. In order to specify a unique ID for an ad, both its ad group ID and this ID must be specified.

### Returns:
|Type|Description|
|-|-
long|The ID of the ad.
&nbsp;|&nbsp;
## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns a [Stats](./Stats) object for this ad for the specified predefined date range.

Supported date range values:

- TODAY
- YESTERDAY
- LAST_7_DAYS
- THIS_WEEK_SUN_TODAY
- LAST_14_DAYS
- LAST_30_DAYS
- LAST_WEEK_SUN_SAT
- THIS_MONTH
- LAST_MONTH
- ALL_TIME

### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range for which the stats are requested.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|The stats for the specified date range.
&nbsp;|&nbsp;
## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns a [Stats](./Stats) object for this ad for the specified date range.

You may specify the date parameters using strings or objects. To use strings, specify the date in the form, YYYYMMDD. If you use objects, create a JSON object with the following fields:

- year
- month
- day

For example, {year: 2016, month: 5, day: 13}.

### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range.
dateTo|Object|End date of the date range.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|The stats for the specified date range.
&nbsp;|&nbsp;
## <a name="gettype"></a>getType
Returns the type of the ad. 

Possible values are: 

- EXPANDED_TEXT_AD
- TEXT_AD

### Returns:
|Type|Description|
|-|-
String|The type of the ad.
&nbsp;|&nbsp;
## <a name="isenabled"></a>isEnabled
Returns true if this ad is enabled. 

### Returns:
|Type|Description|
|-|-
boolean|true if the ad is enabled.
&nbsp;|&nbsp;
## <a name="ismobilepreferred"></a>isMobilePreferred
Returns true if this ad indicates mobile device preference or false otherwise. 

### Returns:
|Type|Description|
|-|-
boolean|Whether the ad is mobile-preferred.
&nbsp;|&nbsp;
## <a name="ispaused"></a>isPaused
Returns true if this ad is paused. 

### Returns:
|Type|Description|
|-|-
boolean|true if the ad is paused.
&nbsp;|&nbsp;
## <a name="istype"></a>isType
Returns an AdTypeSpace object which provides more information on the type of this ad. 

### Returns:
|Type|Description|
|-|-
[AdTypeSpace](./AdTypeSpace)|An AdTypeSpace.
&nbsp;|&nbsp;
## <a name="pause"></a>pause
Pauses this ad.

### Returns:
|Type|Description|
|-|-
void|Access to this ad's URL fields.
&nbsp;|&nbsp;
## <a name="remove"></a>remove
Removes this ad.

### Returns:
|Type|Description|
|-|-
void|Access to this ad's URL fields.
&nbsp;|&nbsp;
## <a name="urls"></a>urls
Returns an AdUrls object which provides access to the `URL` fields of this ad. 

### Returns:
|Type|Description|
|-|-
[AdUrls](./AdUrls)|Access to this ad's URL fields.
&nbsp;|&nbsp;
