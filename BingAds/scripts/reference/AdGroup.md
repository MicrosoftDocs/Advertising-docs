# AdGroup
Represents an ad group in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
[ads]('#ads')|[AdSelector](./AdSelector)|Returns a selector of all the ads under this ad group.<br />
[devices]('#devices')|[AdGroupDevices](./AdGroupDevices)|Returns an AdGroupDevices object associated with this ad group.<br />
[enable]('#enable')|void|Enables this ad group.<br />
[getCampaign]('#getCampaign')|[Campaign](./Campaign)|Returns the parent campaign of this ad group.<br />
[getEntityType]('#getEntityType')|String|Returns the entity type of this ad group, which is “Ad Group”.<br />
[getId]('#getId')|long|Returns the ID of this ad group.<br />
[getName]('#getName')|String|Returns the name of this ad group.<br />
[getStatsFor(String dateRange)]('#getStatsFor-String-dateRange)')|String|Returns stats for this ad group for the given date range. Supported values include:<br /> <br /> `TODAY`,<br /> `YESTERDAY`,<br /> `LAST_7_DAYS`,<br /> `THIS_WEEK_SUN_TODAY`,<br /> `LAST_14_DAYS`,<br /> `LAST_30_DAYS`,<br /> `LAST_WEEK_SUN_SAT`,<br /> `THIS_MONTH`,<br /> `LAST_MONTH`,<br /> `ALL_TIME`<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)]('#getStatsFor-Object-dateFrom_ Object dateTo)')|String|Returns stats for this ad group for the given custom date range. Both parameters can be either a string in `YYYYMMDD` format or an object with year, month and day properties. In either case, a full date must be specified <br />
[isEnabled]('#isEnabled')|boolean|Returns true if this ad group is enabled. <br />
[isPaused]('#isPaused')|boolean|Returns true if this ad group is paused. <br />
[isRemoved]('#isRemoved')|boolean|Returns true if this ad group is removed. <br />
[keywords]('#keywords')|[KeywordSelector](./KeywordSelector)|Returns a selector of all the keywords under this ad group.<br />
[newAd]('#newAd')|[AdBuilderSpace](./AdBuilderSpace)|Returns a new ad builder space associated with this ad group, which can be used to construct the new ad.<br />
[newKeywordBuilder]('#newKeywordBuilder')|[KeywordBuilder](./KeywordBuilder)|Returns a new keyword builder associated with this ad group, which can be used to construct the new keyword.<br />
[pause]('#pause')|void|Pauses this ad group.<br />
[setName(String name)]('#setName-String-name)')|void|Sets the name of this ad group.<br />
[urls]('#urls')|[AdGroupUrls](./AdGroupUrls)|Returns an AdGroupUrls object which provides access to the URL fields of this ad group.<br />

<a name="ads"></a>
## ads
Returns a selector of all the ads under this ad group.


<a name="devices"></a>
## devices
Returns an AdGroupDevices object associated with this ad group.


<a name="enable"></a>
## enable
Enables this ad group.


<a name="getCampaign"></a>
## getCampaign
Returns the parent campaign of this ad group.


<a name="getEntityType"></a>
## getEntityType
Returns the entity type of this ad group, which is “Ad Group”.


<a name="getId"></a>
## getId
Returns the ID of this ad group.


<a name="getName"></a>
## getName
Returns the name of this ad group.


<a name="getStatsFor-String-dateRange)"></a>
## getStatsFor(String dateRange)
Returns stats for this ad group for the given date range. Supported values include:<br /> <br /> `TODAY`,<br /> `YESTERDAY`,<br /> `LAST_7_DAYS`,<br /> `THIS_WEEK_SUN_TODAY`,<br /> `LAST_14_DAYS`,<br /> `LAST_30_DAYS`,<br /> `LAST_WEEK_SUN_SAT`,<br /> `THIS_MONTH`,<br /> `LAST_MONTH`,<br /> `ALL_TIME`<br />


<a name="getStatsFor-Object-dateFrom_ Object dateTo)"></a>
## getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this ad group for the given custom date range. Both parameters can be either a string in `YYYYMMDD` format or an object with year, month and day properties. In either case, a full date must be specified 


<a name="isEnabled"></a>
## isEnabled
Returns true if this ad group is enabled. 


<a name="isPaused"></a>
## isPaused
Returns true if this ad group is paused. 


<a name="isRemoved"></a>
## isRemoved
Returns true if this ad group is removed. 


<a name="keywords"></a>
## keywords
Returns a selector of all the keywords under this ad group.


<a name="newAd"></a>
## newAd
Returns a new ad builder space associated with this ad group, which can be used to construct the new ad.


<a name="newKeywordBuilder"></a>
## newKeywordBuilder
Returns a new keyword builder associated with this ad group, which can be used to construct the new keyword.


<a name="pause"></a>
## pause
Pauses this ad group.


<a name="setName-String-name)"></a>
## setName(String name)
Sets the name of this ad group.


<a name="urls"></a>
## urls
Returns an AdGroupUrls object which provides access to the URL fields of this ad group.


