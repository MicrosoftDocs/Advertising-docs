# ExpandedTextAd
Represents an expanded text ad in Bing Ads. For information, see [Ad Extensions](/bingads/guides/entity-hierarchy-limits#adextensions).

# Methods
|Method Name|Return Type|Description|
|-|-|-
[asType](#astype)|[AdViewSpace](./AdViewSpace)|Returns properties specific to the type of this ad.
[enable](#enable)|void|Enables the ad.
[getAdGroup](#getadgroup)|[AdGroup](./AdGroup)|Returns the ad group this ad belongs to.
[getApprovalStatus](#getapprovalstatus)|String|Returns the ad's approval status.
[getCampaign](#getcampaign)|[Campaign](./Campaign)|Returns the campaign this ad belongs to.
[getDescription](#getdescription)|String|Returns the description of this ad.
[getDisapprovalReasons](#getdisapprovalreasons)|String[]|Returns an array containing the reasons for which this ad was disapproved. If it is not disapproved, the array is empty.
[getEntityType](#getentitytype)|String|Returns the entity type.
[getHeadlinePart1](#getheadlinepart1)|String|Returns the first part of the ad's headline (title).
[getHeadlinePart2](#getheadlinepart2)|String|Returns the second part of the ad's headline (title).
[getId](#getid)|long|Returns the ID of this ad.
[getPath1](#getpath1)|String|Returns the first path that appears with this ad's display URL.
[getPath2](#getpath2)|String|Returns the second path that appears with this ad's display URL.
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|[Stats](./Stats)|Returns an object which provides statistics for the specified date range.
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|[Stats](./Stats)|Returns an object which provides statistics for the specified predefined date range.
[getType](#gettype)|String|Returns the type of this ad.
[isEnabled](#isenabled)|Boolean|Returns a Boolean value that indicates if this ad is enabled.
[isPaused](#ispaused)|Boolean|Returns a Boolean value that indicates if this ad is paused.
[isType](#istype)|[AdTypeSpace](./AdTypeSpace)|Returns an object which provides more information about the type of this ad.
[pause](#pause)|void|Pauses this ad.
[remove](#remove)|void|Removes this ad.
[urls](#urls)|[AdUrls](./AdUrls)|Returns the ad's URLs.

## <a name="astype"></a>asType
Returns properties specific to the type of this ad.

### Returns:
|Type|Description|
|-|-
[AdViewSpace](./AdViewSpace)|Properties specific to the type of this ad.

## <a name="enable"></a>enable
Enables the ad.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getadgroup"></a>getAdGroup
Returns the ad group this ad belongs to.

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|Ad group this ad belongs to.

## <a name="getapprovalstatus"></a>getApprovalStatus
Returns the ad's approval status. Possible values:

- APPROVED
- DISAPPROVED

### Returns:
|Type|Description|
|-|-
String|Ad's approval status.

## <a name="getcampaign"></a>getCampaign
Returns the campaign this ad belongs to.

### Returns:
|Type|Description|
|-|-
[Campaign](./Campaign)|Campaign this ad belongs to.

## <a name="getdescription"></a>getDescription
Returns the description of this ad.

### Returns:
|Type|Description|
|-|-
String|Description of the ad.

## <a name="getdisapprovalreasons"></a>getDisapprovalReasons
Returns an array containing the reasons for which this ad was disapproved. If it is not disapproved, the array is empty.

### Returns:
|Type|Description|
|-|-
String[]|

## <a name="getentitytype"></a>getEntityType
Returns the entity type.

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "ExpandedTextAd".

## <a name="getheadlinepart1"></a>getHeadlinePart1
Returns the first part of the ad's headline (title).

### Returns:
|Type|Description|
|-|-
String|First part of the ad's headline (title).

## <a name="getheadlinepart2"></a>getHeadlinePart2
Returns the second part of the ad's headline (title).

### Returns:
|Type|Description|
|-|-
String|Second part of the ad's headline.

## <a name="getid"></a>getId
Returns the ID of this ad.

### Returns:
|Type|Description|
|-|-
long|ID of this ad.

## <a name="getpath1"></a>getPath1
Returns the first path that appears with this ad's display URL.

### Returns:
|Type|Description|
|-|-
String|First path that appears with the ad's displayed URL.

## <a name="getpath2"></a>getPath2
Returns the second path that appears with this ad's display URL.

### Returns:
|Type|Description|
|-|-
String|Second path that appears with the ad's displayed URL.

## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns an object which provides statistics for the specified date range. [!INCLUDE[date-range-objects](../includes/date-range-objects.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range.
dateTo|Object|End date of the date range.
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|Stats for the specified date range.

## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns an object which provides statistics for the specified predefined date range. [!INCLUDE[date-range-constants](../includes/date-range-constants.md)]


### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range for which the stats are requested.
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|Stats for the specified date range.

## <a name="gettype"></a>getType
Returns the type of this ad. Possible values are:

- EXPANDED_TEXT_AD
- TEXT_AD


### Returns:
|Type|Description|
|-|-
String|Type of the ad.

## <a name="isenabled"></a>isEnabled
Returns a Boolean value that indicates if this ad is enabled.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this ad is enabled.

## <a name="ispaused"></a>isPaused
Returns a Boolean value that indicates if this ad is paused.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this ad is paused.

## <a name="istype"></a>isType
Returns an object which provides more information about the type of this ad.

### Returns:
|Type|Description|
|-|-
[AdTypeSpace](./AdTypeSpace)|Object that provides more information about the type of this ad.

## <a name="pause"></a>pause
Pauses this ad.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="remove"></a>remove
Removes this ad.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="urls"></a>urls
Returns the ad's URLs.

### Returns:
|Type|Description|
|-|-
[AdUrls](./AdUrls)|Ad's URLs.

