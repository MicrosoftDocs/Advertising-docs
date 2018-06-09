---
title: "Bing Ads Operation Error Codes"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Reference documentation for service operation error codes.
---
# Operation Error Codes
Bing Ads service operations may return error codes depending on the context. The list provided below includes error codes across all Bing Ads services. For information about error codes per service operation, see the reference page for each operation.

For more information about error handling and troubleshooting, see [Handling Service Errors and Exceptions](handle-service-errors-exceptions.md).

## <a name="error-codes"><a/>Error Codes
In the list below, the **Numeric Code** and **Symbolic Error Code** headers correspond to the respective *Code* and *ErrorCode* elements of the returned error data object.

The *BatchError* and *OperationError* objects for [Customer Billing](../customer-billing-service/customer-billing-service-reference.md) and [Customer Management](../customer-management-service/customer-management-service-reference.md) services do not contain the *ErrorCode* element. The corresponding **Symbolic Error Code** table entries below are noted as **Not applicable**.

Some symbolic error codes begin with the strings *BulkService* or *CampaignService*. Error codes beginning with *CampaignService* may be included in error codes for the bulk and campaign service, so you should not make assumptions about the naming convention.

> [!NOTE]
> Some numeric codes are listed twice, where the same numeric code is used for different scenarios across multiple web services.

***
## 0
***

**Numeric Code**
0

**Symbolic Error Code**
InternalError

**Description**
An unidentified error has occurred. You may obtain additional information about this error by contacting Bing Ads Support.

***

**Numeric Code**
100

**Symbolic Error Code**
NullRequest

**Description**
The request message is null.

***

**Numeric Code**
105

**Symbolic Error Code**
InvalidCredentials

**Description**
The provided user name and password could not be validated.

***

**Numeric Code**
106

**Symbolic Error Code**
UserIsNotAuthorized

**Description**
The specified user is not authorized to use the API.

***

**Numeric Code**
108

**Symbolic Error Code**
UserCompromised

**Description**
We have detected suspicious activity on your Bing Ads account. We think someone may have logged into your Bing Ads account without your permission. Please create a new password to secure your account.

***

**Numeric Code**
109

**Symbolic Error Code**
AuthenticationTokenExpired

**Description**
Authentication token expired. Please renew it or obtain a new token. For more information, see [Authentication with OAuth](authentication-oauth.md).

***

**Numeric Code**
113

**Symbolic Error Code**
InvalidDateObject

**Description**
The date specified in the request is not valid.

***

**Numeric Code**
116

**Symbolic Error Code**
RequestMissingHeaders

**Description**
One or more required header elements are missing from the request.

***

**Numeric Code**
117

**Symbolic Error Code**
CallRateExceeded

**Description**
You have exceeded the number of calls that you are allowed to make in a minute. Please reduce the number of calls that you make per minute.

***

**Numeric Code**
120

**Symbolic Error Code**
UserLoginAccessDenied

**Description**
The credentials are not valid for the person who attempted to login. Please login with the primary login credentials for this person.

The user credentials would have authenticated with versions prior to Bing Ads API Version 12. After [multi-user consolidation](customer-accounts.md#multi-user) credentials that have been merged into the primary login credentials can no longer be used to authenticate in Bing Ads. 

***

**Numeric Code**
200

**Symbolic Error Code**
Not applicable.

**Description**
The Address City property is invalid.

***

**Numeric Code**
201

**Symbolic Error Code**
ApiInputValidationError

**Description**
One or more input elements failed validation.

***

**Numeric Code**
202

**Symbolic Error Code**
ApiExecutionError

**Description**
The operation cannot be completed.

***

**Numeric Code**
203

**Symbolic Error Code**
NullParameter

**Description**
The parameter cannot be null.

***

**Numeric Code**
204

**Symbolic Error Code**
OperationNotSupported

**Description**
The operation is not supported.

***

**Numeric Code**
205

**Symbolic Error Code**
InvalidVersion

**Description**
The specified version is not valid.

***

**Numeric Code**
205

**Symbolic Error Code**
Not applicable.

**Description**
The Address Line1 property is invalid.

***

**Numeric Code**
206

**Symbolic Error Code**
NullArrayArgument

**Description**
A null array argument is not allowed.

***

**Numeric Code**
207

**Symbolic Error Code**
Not applicable.

**Description**
The Address Line3 property is invalid.

***

**Numeric Code**
208

**Symbolic Error Code**
InvalidAccount

**Description**
The account is not valid.

***

**Numeric Code**
209

**Symbolic Error Code**
TimestampNotMatch

**Description**
The time stamp does not match.

***

**Numeric Code**
209

**Symbolic Error Code**
Not applicable.

**Description**
The Address PostalCode property is invalid.

***

**Numeric Code**
210

**Symbolic Error Code**
EntityNotExistent

**Description**
The entity does not exist.

***

**Numeric Code**
211

**Symbolic Error Code**
NameTooLong

**Description**
The specified name is too long.

***

**Numeric Code**
212

**Symbolic Error Code**
CampaignServiceEntityTypeNotSupported

**Description**
The operation does not support the specified entity type.

***

**Numeric Code**
303

**Symbolic Error Code**
ApiVersionNoLongerSupported

**Description**
This version of the Bing Ads API is no longer supported. Please migrate to the latest version of the API. For more details, visit [https://go.microsoft.com/fwlink/?linkid=862106](https://go.microsoft.com/fwlink/?linkid=862106).

***

**Numeric Code**
310

**Symbolic Error Code**
Not applicable.

**Description**
You should specify a Customer object, for example when creating or updating customers.

***

**Numeric Code**
475

**Symbolic Error Code**
Not applicable.

**Description**
The insertion order name is invalid.

***

**Numeric Code**
476

**Symbolic Error Code**
Not applicable.

**Description**
The purchase order is invalid.

***

**Numeric Code**
477

**Symbolic Error Code**
Not applicable.

**Description**
The insertion order status cannot be specified when adding an insertion order.

***

**Numeric Code**
478

**Symbolic Error Code**
Not applicable.

**Description**
The customer is not allowed to add or update an insertion order.

***

**Numeric Code**
479

**Symbolic Error Code**
Not applicable.

**Description**
Only the status of an insertion order can be updated.

***

**Numeric Code**
480

**Symbolic Error Code**
Not applicable.

**Description**
The specified status is invalid.

***
## 500
***

**Numeric Code**
512

**Symbolic Error Code**
CampaignServiceFilterListOverLimit

**Description**
The associated filter list exceeds the size limit.

***

**Numeric Code**
513

**Symbolic Error Code**
CampaignServiceEntityIdsArrayExceedsLimit

**Description**
The number of entity IDs exceeds the maximum allowed.

***

**Numeric Code**
514

**Symbolic Error Code**
CampaignServiceEntityIdsArrayExceedsLimit

**Description**
Ids passed are null or empty.

***

**Numeric Code**
515

**Symbolic Error Code**
CampaignServiceIdsNotPassed

**Description**
Duplicate IDs are contained in the request.

***

**Numeric Code**
516

**Symbolic Error Code**
CampaignServiceIdsNotPassed

**Description**
The type of the entity that was specified by ID does not match provided entity filter type.

***

**Numeric Code**
517

**Symbolic Error Code**
CampaignServiceEntityIdInvalid 

**Description**
The entity identifier is invalid.

***

**Numeric Code**
532

**Symbolic Error Code**
Not applicable.

**Description**
A date or date/time is not in the range of dates that the service supports, or the end of a time range is earlier than the start.

***

**Numeric Code**
631

**Symbolic Error Code**
InvalidMaxLocations

**Description**
The maximum number of locations has been exceeded.

***

**Numeric Code**
800

**Symbolic Error Code**
CampaignEstimatorsNullOrEmpty

**Description**
You must provide a campaign estimator.

***

**Numeric Code**
801

**Symbolic Error Code**
CampaignEstimatorsLimitExceeded

**Description**
The maximum number of campaign estimators has been exceeded.

***

**Numeric Code**
802

**Symbolic Error Code**
InvalidDailyBudget

**Description**
The daily budget is invalid.

***

**Numeric Code**
803

**Symbolic Error Code**
CriteriaNullOrEmpty

**Description**
You must provide criteria.

***

**Numeric Code**
804

**Symbolic Error Code**
LocationCriterionNullOrEmpty

**Description**
You must provide a location criterion.

***

**Numeric Code**
805

**Symbolic Error Code**
NetworkCriterionNullOrEmpty

**Description**
You must provide a network criterion.

***

**Numeric Code**
806

**Symbolic Error Code**
LanguageCriterionNullOrEmpty

**Description**
You must provide a language criterion.

***

**Numeric Code**
807

**Symbolic Error Code**
DuplicateCriterion

**Description**
You cannot specify duplicate criteria.

***

**Numeric Code**
808

**Symbolic Error Code**
AdGroupEstimatorsNullOrEmpty

**Description**
You must provide one or more ad group estimators.

***

**Numeric Code**
809

**Symbolic Error Code**
InvalidAdGroupEstimatorMaxCpc

**Description**
The ad group estimator maximum Cpc is not supported.

***

**Numeric Code**
810

**Symbolic Error Code**
KeywordEstimatorsNullOrEmpty

**Description**
You must provide one or more keyword estimators.

***

**Numeric Code**
811

**Symbolic Error Code**
KeywordEstimatorKeywordNullOrEmpty

**Description**
The keyword text is required for each keyword estimator.

***

**Numeric Code**
812

**Symbolic Error Code**
InvalidKeywordEstimatorMaxCpc

**Description**
The keyword estimator maximum Cpc is not supported.

***

**Numeric Code**
813

**Symbolic Error Code**
SearchParametersNullOrEmpty

**Description**
You must provide search parameters.

***

**Numeric Code**
814

**Symbolic Error Code**
DuplicateSearchParameter

**Description**
You can only specify one of each search parameter type.

***

**Numeric Code**
815

**Symbolic Error Code**
RequiredSearchParameterMissing

**Description**
One or more of the required search parameters is missing.

***

**Numeric Code**
816

**Symbolic Error Code**
InvalidImpressionShare

**Description**
The impression share is out of range.

***

**Numeric Code**
817

**Symbolic Error Code**
InvalidSearchVolume

**Description**
The search volume is invalid.

***

**Numeric Code**
818

**Symbolic Error Code**
InvalidSuggestedBid

**Description**
The suggested bid is invalid

***

**Numeric Code**
819

**Symbolic Error Code**
InvalidIdeaTextSearchParameterMatchType

**Description**
The MatchType of IdeaTextSearchParameter is not supported.

***

**Numeric Code**
820

**Symbolic Error Code**
DateRangeSearchParameterStartDateNull

**Description**
The date range search parameter start date is missing.

***

**Numeric Code**
821

**Symbolic Error Code**
DateRangeSearchParameterEndDateNull

**Description**
The date range search parameter end date is missing.

***

**Numeric Code**
822

**Symbolic Error Code**
DateRangeSearchParameterEndDatePrecedesStartDate

**Description**
The date range search parameter end date must be later than the start date.

***
## 1000
***

**Numeric Code**
1001

**Symbolic Error Code**
Not applicable.

**Description**
The user is not authorized to perform this action.

***

**Numeric Code**
1003

**Symbolic Error Code**
CampaignServiceCannotSpecifyStatusOnAdd

**Description**
The status property must be null for an add operation.

***

**Numeric Code**
1004

**Symbolic Error Code**
CampaignServiceIdShouldBeNullOnAdd

**Description**
The identifier property must be null for an add operation.

***

**Numeric Code**
1005

**Symbolic Error Code**
CampaignServiceInvalidNegativeKeyword

**Description**
The negative keyword property is not valid.

***

**Numeric Code**
1006

**Symbolic Error Code**
CampaignServiceNegativeKeywordsTotalLengthExceeded

**Description**
The total length of the negative keywords has been exceeded.

***

**Numeric Code**
1007

**Symbolic Error Code**
CampaignServiceNegativeKeywordMatchesKeyword

**Description**
A negative keyword matches a keyword.

***

**Numeric Code**
1008

**Symbolic Error Code**
CampaignServiceInvalidAccountStatus

**Description**
The account status is not valid for the requested operation.

***

**Numeric Code**
1009

**Symbolic Error Code**
CampaignServiceAccountIdMissingInRequestHeader

**Description**
For aggregators, the customer's account ID must be supplied in the request header.

***

**Numeric Code**
1010

**Symbolic Error Code**
CampaignServiceSystemInReadOnlyMode

**Description**
The system is currently in read-only mode. Only *Get* operations are supported at this time.

***

**Numeric Code**
1011

**Symbolic Error Code**
CampaignServiceFutureFeatureCode

**Description**
An internal error has occurred.

***

**Numeric Code**
1012

**Symbolic Error Code**
CampaignServiceInvalidNegativeSiteURL

**Description**
A negative website URL is not valid.

***

**Numeric Code**
1013

**Symbolic Error Code**
CampaignServiceNegativeSiteURLExceededMaxCount

**Description**
The negative website URLs exceeded maximum allowed limit.

***

**Numeric Code**
1014

**Symbolic Error Code**
CampaignServiceTimeZoneValueInvalid

**Description**
The time zone value is not valid. See [Time Zones](time-zones.md) for list of valid time zone values.

***

**Numeric Code**
1015

**Symbolic Error Code**
CampaignServiceCurrencyValueInvalid

**Description**
The currency value is not valid. See Currency Values for list of valid values.

***

**Numeric Code**
1016

**Symbolic Error Code**
CampaignServiceInvalidEntityState

**Description**
The entity status is not valid. 

***

**Numeric Code**
1017

**Symbolic Error Code**
CampaignServiceInvalidSearchBids

**Description**
One or more of the specified search bids are not valid.

***

**Numeric Code**
1018

**Symbolic Error Code**
CampaignServiceInvalidContentBid

**Description**
The specified content bid is not valid.

***

**Numeric Code**
1029

**Symbolic Error Code**
CampaignServiceCustomerIdHasToBeSpecified

**Description**
The *CustomerId* element must be specified for this operation.

***

**Numeric Code**
1030

**Symbolic Error Code**
CampaignServiceAccountIdHasToBeSpecified

**Description**
The *CustomerAccountId* element must be specified for this operation.

***

**Numeric Code**
1031

**Symbolic Error Code**
CampaignServiceCannotPerformCurrentOperation

**Description**
The operation cannot be completed due to some customer or user information that is not valid.

***

**Numeric Code**
1032

**Symbolic Error Code**
CampaignServiceNegativeKeywordsLimitExceeded

**Description**
The number of negative keywords has exceeded the limit.

***

**Numeric Code**
1033

**Symbolic Error Code**
CampaignServiceNegativeKeywordsEntityLimitExceeded

**Description**
The number of entities with the maximum number of negative keywords has exceeded the limit.

***

**Numeric Code**
1034

**Symbolic Error Code**
CampaignServiceNegativeKeywordsNotPassed

**Description**
The array of negative keywords is null or empty.

***

**Numeric Code**
1035

**Symbolic Error Code**
CampaignServiceNegativeSiteCannotBeOwnedOrOperatedSite

**Description**
Negative site specified cannot be an owned or operated site.

***

**Numeric Code**
1036

**Symbolic Error Code**
CampaignServiceNegativeSiteURLExceedMaxSubDirectories

**Description**
Negative site specified exceeds maximum number of subdirectories.

***

**Numeric Code**
1037

**Symbolic Error Code**
CampaignServiceNegativeSiteURLExceedMaxSubDomains

**Description**
Negative site specified exceeds maximum number of subdomains.

***

**Numeric Code**
1041

**Symbolic Error Code**
DevicePreferenceNotSupported

**Description**
The Device Preference property is not supported.

***

**Numeric Code**
1042

**Symbolic Error Code**
CampaignServiceEditorialValidationError

**Description**
The specified entity did not pass editorial validation. Please see the *ReasonCode* element of this error object for details.

> [!NOTE] 
> For a list of editorial reason codes, see [Bing Ads Editorial Failure Reason Codes](editorial-failure-reason-codes.md).

***

**Numeric Code**
1043

**Symbolic Error Code**
CampaignServiceEntityAlreadyExists

**Description**
The specified entity already exists. Please see the *ReasonCode* element of this error object for details.

***

**Numeric Code**
1044

**Symbolic Error Code**
CampaignServiceEntityDoesNotExist

**Description**
The specified entity does not exist. Please see the *ReasonCode* element of this error object for details.

***

**Numeric Code**
1045

**Symbolic Error Code**
CampaignServiceEntityMaxLimitReached

**Description**
The system limit for the submitted entity type has already been reached. Please see the *ReasonCode* element of this error object for details.

***

**Numeric Code**
1046

**Symbolic Error Code**
CampaignServiceEntityIdNotPassed

**Description**
The entity ID field cannot be null or empty. Please see the *ReasonCode* element of this error object for details.

***

**Numeric Code**
1100

**Symbolic Error Code**
CampaignServiceInvalidCampaignId

**Description**
The campaign identifier is not valid.

***

**Numeric Code**
1101

**Symbolic Error Code**
CampaignServiceInvalidCampaignName

**Description**
The campaign name is not valid.

***

**Numeric Code**
1102

**Symbolic Error Code**
CampaignServiceInvalidAccountId

**Description**
The account identifier is not valid.

***

**Numeric Code**
1103

**Symbolic Error Code**
CampaignServiceNullCampaign

**Description**
The campaign object is null.

***

**Numeric Code**
1104

**Symbolic Error Code**
CampaignServiceInvalidCampaignDescription

**Description**
The campaign description is not valid.

***

**Numeric Code**
1105

**Symbolic Error Code**
CampaignServiceInvalidMonthlyBudget

**Description**
This error code is no longer in use. Monthly budgets was last used with Bing Ads API version 10.

***

**Numeric Code**
1106

**Symbolic Error Code**
CampaignServiceInvalidDailyBudget

**Description**
The campaign daily budget is not valid.

***

**Numeric Code**
1107

**Symbolic Error Code**
CampaignServiceDuplicateCampaignIds

**Description**
Duplicate identifiers are contained in the array of campaigns.

***

**Numeric Code**
1108

**Symbolic Error Code**
CampaignServiceInvalidConversionTrackingEnabled

**Description**
This error code is no longer in use. The ConversionTrackingEnabled element was last used with Bing Ads API version 9.

***

**Numeric Code**
1109

**Symbolic Error Code**
CampaignServiceTimeZoneNotEnabled

**Description**
The campaign timezone is required.

***

**Numeric Code**
1110

**Symbolic Error Code**
CampaignServiceDaylightSavingNotEnabled

**Description**
This error code is no longer in use. The daylight saving setting was last used with Bing Ads API version 10.

***

**Numeric Code**
1111

**Symbolic Error Code**
CampaignServiceInvalidConversionTrackingScriptSet

**Description**
The *Campaign.ConversionTrackingScript* element must not be set for the campaign.

***

**Numeric Code**
1113

**Symbolic Error Code**
CampaignServiceCampaignsArrayShouldNotBeNullOrEmpty

**Description**
The array of campaigns is null or empty.

***

**Numeric Code**
1114

**Symbolic Error Code**
CampaignServiceCampaignsArrayExceedsLimit

**Description**
The list of campaigns exceeds the limit.

***

**Numeric Code**
1115

**Symbolic Error Code**
CampaignServiceCannotCreateDuplicateCampaign

**Description**
An attempt was made to create a duplicate of a campaign that already exists.

***

**Numeric Code**
1117

**Symbolic Error Code**
CampaignServiceMaximumCampaignsReached

**Description**
No more campaigns can be added to the specified account.

***

**Numeric Code**
1118

**Symbolic Error Code**
CampaignServiceCampaignIdsArrayShouldNotBeNullOrEmpty

**Description**
The array of campaign identifiers is null or empty.

***

**Numeric Code**
1119

**Symbolic Error Code**
CampaignServiceCampaignIdsArrayExceedsLimit

**Description**
The list of campaign identifiers exceeds the limit.

***

**Numeric Code**
1120

**Symbolic Error Code**
CampaignServiceInvalidCampaignStatus

**Description**
The campaign status is not valid for the requested operation.

***

**Numeric Code**
1121

**Symbolic Error Code**
CampaignServiceInvalidBudgetType

**Description**
The campaign budget type is missing or is not valid.

***

**Numeric Code**
1123

**Symbolic Error Code**
CampaignServiceCampaignBudgetAmountIsLessThanSpendAmount

**Description**
The new campaign budget is less than the amount already spent for the current month.

***

**Numeric Code**
1129

**Symbolic Error Code**
CampaignServiceCampaignAlreadyExists

**Description**
The campaign already exists.

***

**Numeric Code**
1130

**Symbolic Error Code**
CampaignServiceNullCampaignNegativeKeywords

**Description**
The *NegativeKeywords* element cannot be null for the specified operation.

***

**Numeric Code**
1131

**Symbolic Error Code**
CampaignServiceCannotChangeTimezoneOrStartDateWithActiveAdGroups

**Description**
The campaign time zone cannot be updated, because some of the corresponding ad groups are not in Draft status. Once you set any of the ad group's status to Active or Paused, the parent campaign's time zone may not be updated.

***

**Numeric Code**
1132

**Symbolic Error Code**
Not applicable.

**Description**
The tracking template is too long.

***

**Numeric Code**
1133

**Symbolic Error Code**
CampaignServiceAdExtensionsArrayShouldNotBeNullOrEmpty

**Description**
The list of ad extensions cannot be null or empty.

***

**Numeric Code**
1133

**Symbolic Error Code**
Not applicable.

**Description**
Invalid tag in tracking template.

***

**Numeric Code**
1134

**Symbolic Error Code**
CampaignServiceAdExtensionIsNull

**Description**
The list of ad extensions cannot contain a null extension.

***

**Numeric Code**
1134

**Symbolic Error Code**
Not applicable.

**Description**
Invalid URL scheme in tracking template.

***

**Numeric Code**
1135

**Symbolic Error Code**
CampaignServiceAdExtensionsEntityLimitExceeded

**Description**
The list of ad extensions is too long.

***

**Numeric Code**
1135

**Symbolic Error Code**
Not applicable.

**Description**
Invalid URL in tracking template.

***

**Numeric Code**
1136

**Symbolic Error Code**
Not applicable.

**Description**
Missing tag lpurl in tracking template.

***

**Numeric Code**
1137

**Symbolic Error Code**
Not applicable.

**Description**
Invoice accounts are not allowed to add or update the TaxId.

***

**Numeric Code**
1138

**Symbolic Error Code**
Not applicable.

**Description**
Invoice accounts are not allowed to add or update the business address.

***

**Numeric Code**
1139

**Symbolic Error Code**
Not applicable.

**Description**
The business address of this account is required.

***

**Numeric Code**
1140

**Symbolic Error Code**
Not applicable.

**Description**
The business address of this account is not valid.

***

**Numeric Code**
1141

**Symbolic Error Code**
Not applicable.

**Description**
The business address country and currency of an account must match.

***

**Numeric Code**
1142

**Symbolic Error Code**
Not applicable.

**Description**
Bing Ads does not accept this currency in your business location.

***

**Numeric Code**
1143

**Symbolic Error Code**
Not applicable.

**Description**
The payment option should be set for this account.

***

**Numeric Code**
1144

**Symbolic Error Code**
Not applicable.

**Description**
TaxInformation is not applicable to the businessaddress. Check rules for each country.

***

**Numeric Code**
1145

**Symbolic Error Code**
Not applicable.

**Description**
TaxInformation has invalid or duplicate keys for the Account Business Address.

***

**Numeric Code**
1146

**Symbolic Error Code**
Not applicable.

**Description**
The GSTIN number is not valid.

***

**Numeric Code**
1147

**Symbolic Error Code**
Not applicable.

**Description**
The PAN number is not valid.

***

**Numeric Code**
1147

**Symbolic Error Code**
CampaignServiceInvalidKeywordVariantMatchEnabledValue

**Description**
The value specified for Keyword Variant Match Type is Invalid.

***

**Numeric Code**
1148

**Symbolic Error Code**
Not applicable.

**Description**
The PAN number is required.

***

**Numeric Code**
1149

**Symbolic Error Code**
CampaignServiceDuplicateSettingsInCampaign

**Description**
You may not specify duplicate settings for a campaign.

***

**Numeric Code**
1150

**Symbolic Error Code**
CampaignServiceCampaignSettingsRequired

**Description**
The required campaign settings were not specified.

***

**Numeric Code**
1151

**Symbolic Error Code**
CampaignServiceCampaignSettingsNotAllowed

**Description**
One or more settings are not supported for the campaign type.

***

**Numeric Code**
1152

**Symbolic Error Code**
CampaignServiceShoppingCampaignPriorityInvalid

**Description**
The priority of the shopping campaign is invalid.

***

**Numeric Code**
1153

**Symbolic Error Code**
CampaignServiceShoppingCampaignSalesCountryCodeInvalid

**Description**
The sales country code of the shopping campaign is invalid.

***

**Numeric Code**
1154

**Symbolic Error Code**
CampaignServiceShoppingCampaignStoreIdInvalid

**Description**
The store ID of the shopping campaign is invalid.

***

**Numeric Code**
1155

**Symbolic Error Code**
CampaignServiceCampaignTypeImmutable

**Description**
The campaign type field of a campaign cannot be updated.

***

**Numeric Code**
1156

**Symbolic Error Code**
CampaignServiceSalesCountryCodeImmutable

**Description**
The sales country code of a shopping campaign cannot be updated.

***

**Numeric Code**
1157

**Symbolic Error Code**
CampaignServiceStoreIdImmutable

**Description**
The store ID of a shopping campaign cannot be updated.

***

**Numeric Code**
1158

**Symbolic Error Code**
CampaignServiceCampaignTypeLimitExceeded

**Description**
You can specify a maximum of one campaign type for a campaign.

***

**Numeric Code**
1159

**Symbolic Error Code**
CampaignServiceCannotUpdateSharedBudget

**Description**
You cannot update shared budget through Campaign Entity, please use Budget entity to update shared budget.

***

**Numeric Code**
1200

**Symbolic Error Code**
CampaignServiceNullAdGroup

**Description**
The ad group is null or empty.

***

**Numeric Code**
1201

**Symbolic Error Code**
CampaignServiceInvalidAdGroupId

**Description**
The ad group ID is not valid.

***

**Numeric Code**
1202

**Symbolic Error Code**
CampaignServiceInvalidAdGroupName

**Description**
The ad group name is not valid.

***

**Numeric Code**
1203

**Symbolic Error Code**
CampaignServiceDuplicateInAdGroupIds

**Description**
Duplicate identifiers are contained in the array of ad groups.

***

**Numeric Code**
1204

**Symbolic Error Code**
CampaignServiceAdGroupEndDateShouldBeAfterStartDate

**Description**
The ad group end date must be later than the ad group start date.

***

**Numeric Code**
1208

**Symbolic Error Code**
CampaignServiceCampaignBudgetLessThanAdGroupBudget

**Description**
The ad group budget exceeds the campaign budget.

***

**Numeric Code**
1209

**Symbolic Error Code**
CampaignServiceAdGroupsArrayShouldNotBeNullOrEmpty

**Description**
The array of ad groups cannot be null or empty.

***

**Numeric Code**
1210

**Symbolic Error Code**
CampaignServiceAdGroupsArrayExceedsLimit

**Description**
The number of ad groups exceeds the limit.

***

**Numeric Code**
1211

**Symbolic Error Code**
CampaignServiceAdGroupUserNotAllowedContentMedium

**Description**
The ad group user cannot use the content medium.

***

**Numeric Code**
1212

**Symbolic Error Code**
CampaignServiceAdGroupStartDateLessThanCurrentDate

**Description**
The ad group start date must not be prior to today's date.

***

**Numeric Code**
1213

**Symbolic Error Code**
CampaignServiceMaximumAdGroupsReached

**Description**
No more ad groups can be added to the campaign.

***

**Numeric Code**
1214

**Symbolic Error Code**
CampaignServiceCannotCreateDuplicateAdGroup

**Description**
An attempt was made to create a duplicate of an ad group that already exists.

***

**Numeric Code**
1215

**Symbolic Error Code**
CampaignServiceCannotUpdateAdGroupInExpiredState

**Description**
An ad group that has expired cannot be updated.

***

**Numeric Code**
1216

**Symbolic Error Code**
CampaignServiceCannotUpdateAdGroupInSubmittedState

**Description**
The ad group property cannot be updated. Some ad group properties such as start date cannot be updated once the ad group has been submitted with *Active* status. 

***

**Numeric Code**
1217

**Symbolic Error Code**
CampaignServiceCannotOperateOnAdGroupInCurrentState

**Description**
The requested operation cannot be performed on an ad group in its current state.

***

**Numeric Code**
1218

**Symbolic Error Code**
CampaignServiceAdGroupIdsArrayShouldNotBeNullOrEmpty

**Description**
The array of ad group identifiers cannot be null or empty.

***

**Numeric Code**
1219

**Symbolic Error Code**
CampaignServiceAdGroupIdsArrayExceedsLimit

**Description**
The number of ad group identifiers exceeds the limit.

***

**Numeric Code**
1222

**Symbolic Error Code**
CampaignServiceAdGroupInvalidMedium

**Description**
The ad group ad distribution is not valid.

***

**Numeric Code**
1223

**Symbolic Error Code**
CampaignServiceAdGroupMediumNotAllowedForDistributionChannel

**Description**
The specified distribution channel is not enabled for your market.

***

**Numeric Code**
1224

**Symbolic Error Code**
CampaignServiceAdGroupMissingAdMedium

**Description**
The ad group ad distribution is required when a new ad group is being created.

***

**Numeric Code**
1227

**Symbolic Error Code**
CampaignServiceAdGroupStartDateCannotBeEarlierThanSubmitDate

**Description**
The ad group start date cannot be prior to the date that the ad group was submitted.

***

**Numeric Code**
1228

**Symbolic Error Code**
CampaignServiceCannotSetPricingModelOnAdGroup

**Description**
The ad group pricing model is not supported and must be null.

***

**Numeric Code**
1229

**Symbolic Error Code**
CampaignServiceCannotSetSearchBidOnAdGroup

**Description**
Search bids are not currently supported for the ad group.

***

**Numeric Code**
1230

**Symbolic Error Code**
CampaignServiceCannotSetContentBidOnAdGroup

**Description**
Content bids are not currently supported for the ad group.

***

**Numeric Code**
1231

**Symbolic Error Code**
CampaignServiceAdGroupExpired

**Description**
The operation is not valid for an ad group that is expired.

***

**Numeric Code**
1232

**Symbolic Error Code**
CampaignServiceAdGroupInvalidStartDate

**Description**
The start date specified in the ad group is not valid.

***

**Numeric Code**
1233

**Symbolic Error Code**
CampaignServiceAdGroupInvalidEndDate

**Description**
The end date specified in the ad group is not valid.

***

**Numeric Code**
1234

**Symbolic Error Code**
CampaignServiceAdGroupPricingModelCpmRequiresContentMedium

**Description**
The cost-per-thousand-impressions (CPM) pricing model is not supported.

***

**Numeric Code**
1235

**Symbolic Error Code**
CampaignServiceAdGroupInvalidMediumForCustomer

**Description**
The customer account is not allowed to create ad groups in the specified ad distribution medium.

***

**Numeric Code**
1236

**Symbolic Error Code**
CampaignServiceAdGroupPricingModelCpmIsNotEnabledForCustomer

**Description**
The customer account is not allowed to create ad groups in the specified pricing model.

***

**Numeric Code**
1237

**Symbolic Error Code**
CampaignServiceAdGroupPricingModelIsNull

**Description**
This error code is no longer in use. The pricing model is optional and will be set to Cpc by default.

***

**Numeric Code**
1240

**Symbolic Error Code**
CampaignServiceTypeCanBeSitePlacementOnlyForContentAdGroups

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
1241

**Symbolic Error Code**
CampaignServiceCannotUpdateBiddingModel

**Description**
The bidding model of an ad group cannot be changed.

***

**Numeric Code**
1242

**Symbolic Error Code**
CampaignServiceCannotUpdateAdDistributionForThisType

**Description**
The ad distribution cannot be changed for this type of ad group.

***

**Numeric Code**
1243

**Symbolic Error Code**
CampaignServiceTooManyAdGroupsInAccount

**Description**
The maximum number of ad groups for the account has been exceeded.

***

**Numeric Code**
1244

**Symbolic Error Code**
AdGroupServiceNullAdGroupNegativeKeywords

**Description**
The *NegativeKeywords* element cannot be null for the specified operation.

***

**Numeric Code**
1245

**Symbolic Error Code**
AdGroupServiceNegativeSiteUrlsNotPassed

**Description**
The *NegativeSiteUrls* element cannot be null for the specified operation.

***

**Numeric Code**
1251

**Symbolic Error Code**
AdGroupServiceNegativeSitesEntityLimitExceeded

**Description**
AdGroupNegativeSites array size exceeded the limit.

***

**Numeric Code**
1257

**Symbolic Error Code**
CampaignServiceMissingLanguage

**Description**
The language is not provided.

***

**Numeric Code**
1268

**Symbolic Error Code**
InvalidRemarketingTargetingSetting

**Description**
The Remarketing Targeting Setting value of the ad group is invalid.

***

**Numeric Code**
1300

**Symbolic Error Code**
CampaignServiceNullAd

**Description**
The ad object is null.

***

**Numeric Code**
1301

**Symbolic Error Code**
CampaignServiceInvalidAdTitle

**Description**
The title of the ad is not valid.

***

**Numeric Code**
1302

**Symbolic Error Code**
CampaignServiceInvalidAdDestinationUrl

**Description**
The ad destination URL is not valid.

***

**Numeric Code**
1303

**Symbolic Error Code**
CampaignServiceAdIdIsNull

**Description**
The ad identifier must be set.

***

**Numeric Code**
1304

**Symbolic Error Code**
CampaignServiceAdIdIsNonNull

**Description**
The ad identifier must not be set.

***

**Numeric Code**
1305

**Symbolic Error Code**
CampaignServiceAdTypeIsNonNull

**Description**
The ad type property must not be set.

***

**Numeric Code**
1306

**Symbolic Error Code**
CampaignServiceInvalidAdText

**Description**
The *Text* property of the text ad is not valid.

***

**Numeric Code**
1307

**Symbolic Error Code**
CampaignServiceInvalidAdDisplayUrl

**Description**
The display URL of the text ad is not valid.

***

**Numeric Code**
1308

**Symbolic Error Code**
CampaignServiceInvalidAdId

**Description**
The ad identifier is not valid.

***

**Numeric Code**
1309

**Symbolic Error Code**
CampaignServiceDuplicateInAdIds

**Description**
The array of ad identifiers contains one or more duplicates.

***

**Numeric Code**
1310

**Symbolic Error Code**
CampaignServiceAdsArrayShouldNotBeNullOrEmpty

**Description**
The array of ads cannot be null or empty.

***

**Numeric Code**
1311

**Symbolic Error Code**
CampaignServiceAdsArrayExceedsLimit

**Description**
The number of ads exceeds the limit.

***

**Numeric Code**
1312

**Symbolic Error Code**
CampaignServiceMaxAdsReached

**Description**
No more ads can be added to the ad group.

***

**Numeric Code**
1313

**Symbolic Error Code**
CampaignServiceDuplicateAd

**Description**
An attempt was made to create a duplicate of an ad that already exists.

***

**Numeric Code**
1314

**Symbolic Error Code**
CampaignServiceDefaultAdExists

**Description**
A default ad already exists.

***

**Numeric Code**
1315

**Symbolic Error Code**
CampaignServiceSyntaxErrorInAdTitle

**Description**
The title of the ad contains a syntax error.

***

**Numeric Code**
1316

**Symbolic Error Code**
CampaignServiceSyntaxErrorInAdText

**Description**
The *Text* property of the text ad contains a syntax error.

***

**Numeric Code**
1317

**Symbolic Error Code**
CampaignServiceSyntaxErrorInAdDisplayUrl

**Description**
The display URL of the text ad contains a syntax error.

***

**Numeric Code**
1318

**Symbolic Error Code**
CampaignServiceForbiddenTextInAdTitle

**Description**
The title of the ad contains forbidden text.

***

**Numeric Code**
1319

**Symbolic Error Code**
CampaignServiceForbiddenTextInAdText

**Description**
The *Text* property of the text ad contains forbidden text.

***

**Numeric Code**
1320

**Symbolic Error Code**
CampaignServiceForbiddenTextInAdDisplayUrl

**Description**
The display URL of the text ad contains forbidden text.

***

**Numeric Code**
1321

**Symbolic Error Code**
CampaignServiceIncorrectAdFormatInTitle

**Description**
The title of the ad is not formatted correctly.

***

**Numeric Code**
1322

**Symbolic Error Code**
CampaignServiceIncorrectAdFormatInText

**Description**
The *Text* property of the text ad is not formatted correctly.

***

**Numeric Code**
1323

**Symbolic Error Code**
CampaignServiceIncorrectAdFormatInDisplayUrl

**Description**
The display URL of the text ad is not formatted correctly.

***

**Numeric Code**
1324

**Symbolic Error Code**
CampaignServiceTooMuchAdTextInTitle

**Description**
The title of the ad exceeds the maximum length.

***

**Numeric Code**
1325

**Symbolic Error Code**
CampaignServiceTooMuchAdTextInText

**Description**
The *Text* property of the text ad exceeds the maximum length.

***

**Numeric Code**
1326

**Symbolic Error Code**
CampaignServiceTooMuchAdTextInDisplayUrl

**Description**
The display URL of the text ad exceeds the maximum length.

***

**Numeric Code**
1327

**Symbolic Error Code**
CampaignServiceTooMuchAdTextInDestinationUrl

**Description**
The destination URL of the text ad exceeds the maximum length.

***

**Numeric Code**
1328

**Symbolic Error Code**
CampaignServiceNotEnoughAdText

**Description**
The combination of the ad title and the ad text does not meet the requirement for the minimum number of words.

***

**Numeric Code**
1329

**Symbolic Error Code**
CampaignServiceExclusiveWordInAdTitle

**Description**
The title of the ad contains one or more reserved words.

***

**Numeric Code**
1330

**Symbolic Error Code**
CampaignServiceExclusiveWordInAdText

**Description**
The *Text* property of the text ad contains one or more reserved words.

***

**Numeric Code**
1331

**Symbolic Error Code**
CampaignServiceExclusiveWordInAdDisplayUrl

**Description**
The display URL of the text ad contains one or more reserved words.

***

**Numeric Code**
1332

**Symbolic Error Code**
CampaignServiceInvalidAdDisplayUrlFormat

**Description**
The display URL of the text ad is not formatted correctly.

***

**Numeric Code**
1333

**Symbolic Error Code**
CampaignServiceDefaultAdSyntaxErrorInTitle

**Description**
The title of the default ad contains a syntax error.

***

**Numeric Code**
1334

**Symbolic Error Code**
CampaignServiceDefaultAdSyntaxErrorInText

**Description**
The text of the default ad contains a syntax error.

***

**Numeric Code**
1335

**Symbolic Error Code**
CampaignServiceDefaultAdSyntaxErrorInDisplayUrl

**Description**
The display URL of the default ad contains a syntax error.

***

**Numeric Code**
1336

**Symbolic Error Code**
CampaignServiceDefaultAdForbiddenWordInTitle

**Description**
The title of the default ad contains forbidden text.

***

**Numeric Code**
1337

**Symbolic Error Code**
CampaignServiceDefaultAdForbiddenWordInText

**Description**
The text of the default ad contains forbidden text.

***

**Numeric Code**
1338

**Symbolic Error Code**
CampaignServiceDefaultAdForbiddenWordInDisplayUrl

**Description**
The display URL of the default ad contains forbidden text.

***

**Numeric Code**
1339

**Symbolic Error Code**
CampaignServiceDefaultAdIncorrectAdFormatInTitle

**Description**
The format of the title is incorrect for the default ad.

***

**Numeric Code**
1340

**Symbolic Error Code**
CampaignServiceDefaultAdIncorrectAdFormatInText

**Description**
The format of the text is incorrect for the default ad.

***

**Numeric Code**
1341

**Symbolic Error Code**
CampaignServiceDefaultAdIncorrectAdFormatInDisplayUrl

**Description**
The format of the display URL is incorrect for the default ad.

***

**Numeric Code**
1342

**Symbolic Error Code**
CampaignServiceDefaultAdTooMuchTextInTitle

**Description**
The title of the default ad exceeds the maximum limit.

***

**Numeric Code**
1343

**Symbolic Error Code**
CampaignServiceDefaultAdTooMuchTextInText

**Description**
The text of the default ad exceeds the maximum limit.

***

**Numeric Code**
1344

**Symbolic Error Code**
CampaignServiceDefaultAdTooMuchTextInDisplayUrl

**Description**
The display URL of the default ad exceeds the maximum limit.

***

**Numeric Code**
1345

**Symbolic Error Code**
CampaignServiceDefaultAdTooMuchTextInDestinationUrl

**Description**
The destination URL of the default ad exceeds the maximum limit.

***

**Numeric Code**
1346

**Symbolic Error Code**
CampaignServiceDefaultAdNotEnoughAdText

**Description**
The text of the default ad does not exceed the minimum limit.

***

**Numeric Code**
1347

**Symbolic Error Code**
CampaignServiceDefaultAdExclusiveWordInTitle

**Description**
The title of the default ad contains one or more reserved words.

***

**Numeric Code**
1348

**Symbolic Error Code**
CampaignServiceDefaultAdExclusiveWordInText

**Description**
The text of the default ad contains one or more reserved words.

***

**Numeric Code**
1349

**Symbolic Error Code**
CampaignServiceDefaultAdExclusiveWordInDisplayUrl

**Description**
The display URL of the default ad contains one or more reserved words.

***

**Numeric Code**
1350

**Symbolic Error Code**
CampaignServiceDefaultAdInvalidDisplayUrlFormat

**Description**
The format for the display URL in the default ad is not valid.

***

**Numeric Code**
1351

**Symbolic Error Code**
CampaignServiceAdIdsArrayShouldNotBeNullOrEmpty

**Description**
The array of ad identifiers cannot be null or empty.

***

**Numeric Code**
1352

**Symbolic Error Code**
CampaignServiceAdIdsArrayExceedsLimit

**Description**
The array of ad identifiers exceeds the limit.

***

**Numeric Code**
1353

**Symbolic Error Code**
CampaignServiceTooMuchTextInTitleAcrossAllAssociations

**Description**
There is too much text in the title across all keyword-ad associations.

***

**Numeric Code**
1354

**Symbolic Error Code**
CampaignServiceTooMuchTextInTextAcrossAllAssociations

**Description**
There is too much text across all keyword-ad associations.

***

**Numeric Code**
1355

**Symbolic Error Code**
CampaignServiceTooMuchTextInDisplayUrlAcrossAllAssociations

**Description**
There is too much text in the display URL across all keyword-ad associations.

***

**Numeric Code**
1356

**Symbolic Error Code**
CampaignServiceNothingToUpdateInAdRequest

**Description**
There is no information to update in the given ad request.

***

**Numeric Code**
1357

**Symbolic Error Code**
CampaignServiceCannotOperateOnAdInCurrentState

**Description**
The operation could not be performed on the specified ad in its current state.

***

**Numeric Code**
1358

**Symbolic Error Code**
CampaignServiceDefaultAdInvalidDestinationUrlFormat

**Description**
The format of the destination URL in the default ad is not valid.

***

**Numeric Code**
1359

**Symbolic Error Code**
CampaignServiceInvalidAdDestinationUrlFormat

**Description**
The format of the ad destination URL is not valid.

***

**Numeric Code**
1360

**Symbolic Error Code**
CampaignServiceAdTypeDoesNotMatch

**Description**
The ad type cannot be changed after the ad has been created.

***

**Numeric Code**
1361

**Symbolic Error Code**
CampaignServiceInvalidBusinessName

**Description**
The mobile ad business name is not valid.

***

**Numeric Code**
1362

**Symbolic Error Code**
CampaignServiceInvalidPhoneNumber

**Description**
The mobile ad phone number is not valid.

***

**Numeric Code**
1363

**Symbolic Error Code**
CampaignServiceMobileAdRequiredDataMissing

**Description**
For a mobile ad, either the phone number and business name or the URLs must be supplied.

***

**Numeric Code**
1364

**Symbolic Error Code**
CampaignServiceMobileAdSupportedForSearchOnlyAdGroups

**Description**
A mobile ad can be added only to an ad group whose ad distribution contains "Search".

***

**Numeric Code**
1365

**Symbolic Error Code**
CampaignServiceMobileAdNotSupportedForThisMarket

**Description**
Mobile ads are not supported for the specified distribution channel.

***

**Numeric Code**
1366

**Symbolic Error Code**
CampaignServiceAdTypeInvalidForCustomer

**Description**
The customer account is not enabled to create ads of the specified type.

***

**Numeric Code**
1367

**Symbolic Error Code**
CampaignServiceTooMuchAdTextInBusinessName

**Description**
The mobile ad business name exceeds the maximum length.

***

**Numeric Code**
1368

**Symbolic Error Code**
CampaignServiceTooMuchAdTextInPhoneNumber

**Description**
The mobile ad phone number exceeds the maximum length.

***

**Numeric Code**
1370

**Symbolic Error Code**
CampaignServicePhoneNumberNotAllowedForCountry

**Description**
The mobile ad phone number is not valid for the specified country/region.

***

**Numeric Code**
1371

**Symbolic Error Code**
CampaignServiceBlockedPhoneNumber

**Description**
The mobile ad contains a phone number that is blocked.

***

**Numeric Code**
1372

**Symbolic Error Code**
CampaignServicePhoneNumberNotAllowedInAdTitle

**Description**
Phone numbers are not allowed in the title of a mobile ad.

***

**Numeric Code**
1373

**Symbolic Error Code**
CampaignServicePhoneNumberNotAllowedInAdText

**Description**
Phone numbers are not allowed in the text of a mobile ad.

***

**Numeric Code**
1374

**Symbolic Error Code**
CampaignServicePhoneNumberNotAllowedInAdDisplayUrl

**Description**
Phone numbers are not allowed in the display URL of a mobile ad.

***

**Numeric Code**
1375

**Symbolic Error Code**
CampaignServicePhoneNumberNotAllowedInAdBusinessName

**Description**
Phone numbers are not allowed in the business name of a mobile ad.

***

**Numeric Code**
1376

**Symbolic Error Code**
CampaignServiceEditorialErrorInAdTitle

**Description**
The ad title failed editorial validation.

***

**Numeric Code**
1377

**Symbolic Error Code**
CampaignServiceEditorialErrorInAdText

**Description**
The ad text failed editorial validation.

***

**Numeric Code**
1378

**Symbolic Error Code**
CampaignServiceEditorialErrorInAdDisplayUrl

**Description**
The ad display URL failed editorial validation.

***

**Numeric Code**
1379

**Symbolic Error Code**
CampaignServiceEditorialErrorInAdDestinationUrl

**Description**
The ad destination URL failed editorial validation.

***

**Numeric Code**
1380

**Symbolic Error Code**
CampaignServiceEditorialErrorInAdBusinessName

**Description**
The ad business name failed editorial validation.

***

**Numeric Code**
1381

**Symbolic Error Code**
CampaignServiceEditorialErrorInAdPhoneNumber

**Description**
The ad phone number failed editorial validation.

***

**Numeric Code**
1382

**Symbolic Error Code**
CampaignServiceInvalidAdStatus

**Description**
The ad status is not valid.

***

**Numeric Code**
1383

**Symbolic Error Code**
CampaignServiceInvalidAdEditorialStatus

**Description**
The ad editorial status is read-only and cannot be modified.

***

**Numeric Code**
1385

**Symbolic Error Code**
CampaignServiceUpdateAdEmpty

**Description**
The *Ad* object is empty, so there is nothing to update.

***

**Numeric Code**
1386

**Symbolic Error Code**
CampaignServiceAdTypeDoesNotMatchExistingValue

**Description**
The ad object type does not match the existing ad type. For example a mobile ad was sent, but the ad identifier refers to a text ad.

***

**Numeric Code**
1387

**Symbolic Error Code**
CampaignServiceEditorialAdTitleBlankAcrossAllAssociations

**Description**
The ad title is empty for all keywords.

***

**Numeric Code**
1388

**Symbolic Error Code**
CampaignServiceEditorialAdTitleBlank

**Description**
A keyword would have made the ad title empty for at least one ad.

***

**Numeric Code**
1389

**Symbolic Error Code**
CampaignServiceEditorialAdTextBlankAcrossAllAssociations

**Description**
The ad text is empty for all keywords.

***

**Numeric Code**
1390

**Symbolic Error Code**
CampaignServiceEditorialAdTextBlank

**Description**
A keyword would have made the text empty for at least one ad.

***

**Numeric Code**
1391

**Symbolic Error Code**
CampaignServiceEditorialAdDisplayUrlBlankAcrossAllAssociations

**Description**
The display URL of the ad is empty for all keywords.

***

**Numeric Code**
1392

**Symbolic Error Code**
CampaignServiceEditorialAdDisplayUrlBlank

**Description**
A keyword would cause the display URL to be empty for at least one ad.

***

**Numeric Code**
1393

**Symbolic Error Code**
CampaignServiceEditorialAdDestinationUrlBlank

**Description**
A keyword would make the destination URL blank for at least one ad.

***

**Numeric Code**
1394

**Symbolic Error Code**
CampaignServiceAdDeleted

**Description**
The ad is already deleted or does not exist.

***

**Numeric Code**
1395

**Symbolic Error Code**
CampaignServiceAdInInvalidStatus

**Description**
The ad status is not valid for the requested operation.

***

**Numeric Code**
1396

**Symbolic Error Code**
CampaignServiceDefaultAdTooMuchTextInBusniessName

**Description**
The business name for the default ad is too long.

***

**Numeric Code**
1397

**Symbolic Error Code**
CampaignServiceEditorialGenericError

**Description**
The ad failed one or more checks during editorial review.

***

**Numeric Code**
1398

**Symbolic Error Code**
CampaignServiceEditorialGenericError

**Description**
The promotional text of Product Ad is too long.

***

**Numeric Code**
1399

**Symbolic Error Code**
CampaignServiceAdTypeInvalidForCampaign

**Description**
The campaign type is not enabled to create ads of this type. For example you cannot create text ads in a shopping campaign.

***

**Numeric Code**
1400

**Symbolic Error Code**
CampaignServiceNullTarget

**Description**
The target is null.

***

**Numeric Code**
1401

**Symbolic Error Code**
CampaignServiceInvalidTargetId

**Description**
The target identifier is not valid.

***

**Numeric Code**
1402

**Symbolic Error Code**
CampaignServiceNoBidsInTarget

**Description**
The target does not contain any bids.

***

**Numeric Code**
1403

**Symbolic Error Code**
CampaignServiceInvalidDayTarget

**Description**
The day target is not valid.

***

**Numeric Code**
1404

**Symbolic Error Code**
CampaignServiceInvalidHourTarget

**Description**
The hour target is not valid.

***

**Numeric Code**
1405

**Symbolic Error Code**
CampaignServiceInvalidLocationTarget

**Description**
The location target is not valid.

***

**Numeric Code**
1406

**Symbolic Error Code**
CampaignServiceInvalidGenderTarget

**Description**
The gender target is not valid.

***

**Numeric Code**
1407

**Symbolic Error Code**
CampaignServiceInvalidAgeTarget

**Description**
The age target is not valid.

***

**Numeric Code**
1408

**Symbolic Error Code**
CampaignServiceDuplicateDayTarget

**Description**
The day target is a duplicate.

***

**Numeric Code**
1409

**Symbolic Error Code**
CampaignServiceDuplicateHourTarget

**Description**
The hour target is a duplicate.

***

**Numeric Code**
1410

**Symbolic Error Code**
Not Applicable

**Description**
An invitation to manage the specified client account has already been sent.

***

**Numeric Code**
1410

**Symbolic Error Code**
CampaignServiceDuplicateMetroAreaLocationTarget

**Description**
The metro area target is a duplicate.

***

**Numeric Code**
1411

**Symbolic Error Code**
CampaignServiceDuplicateCountryLocationTarget

**Description**
The country target is a duplicate.

***

**Numeric Code**
1412

**Symbolic Error Code**
CampaignServiceDuplicateGenderTarget

**Description**
The gender target is a duplicate.

***

**Numeric Code**
1413

**Symbolic Error Code**
CampaignServiceDuplicateAgeTarget

**Description**
The age target is a duplicate.

***

**Numeric Code**
1414

**Symbolic Error Code**
CampaignServiceCountryAndMetroAreaTargetsExclusive

**Description**
The country/region and metro targets must be mutually exclusive.

***

**Numeric Code**
1415

**Symbolic Error Code**
CampaignServiceMetroTargetsFromMultipleCountries

**Description**
The metro targets specified must be from the same country/region.

***

**Numeric Code**
1417

**Symbolic Error Code**
CampaignServiceGeoTargetsInAdGroupExceedsLimit

**Description**
The ad group already has the maximum number of location targets.

***

**Numeric Code**
1418

**Symbolic Error Code**
CampaignServiceDuplicateInTargetIds

**Description**
The target array contains duplicate target IDs.

***

**Numeric Code**
1419

**Symbolic Error Code**
CampaignServiceTargetGroupAssignedEntitiesPermissionMismatch

**Description**
User does not have permission to modify all entities that this target group is assigned to.

***

**Numeric Code**
1420

**Symbolic Error Code**
CampaignServiceTargetsNotPassed

**Description**
No targets were passed to the operation.

***

**Numeric Code**
1421

**Symbolic Error Code**
CampaignServiceTargetAlreadyExists

**Description**
The target already exists.

***

**Numeric Code**
1422

**Symbolic Error Code**
CampaignServiceTargetsLimitReached

**Description**
The maximum number of targets has been reached.

***

**Numeric Code**
1423

**Symbolic Error Code**
CampaignServiceInvalidGeoLocationLevel

**Description**
Invalid geographic location level.

***

**Numeric Code**
1424

**Symbolic Error Code**
Not applicable.

**Description**
The client account is already managed by another agency.

***

**Numeric Code**
1425

**Symbolic Error Code**
CampaignServiceTargetsArrayExceedsLimit

**Description**
The number of targets exceeds the limit.

***

**Numeric Code**
1426

**Symbolic Error Code**
CampaignServiceTargetNotAssociatedWithEntity

**Description**
The target is not associated with the entity.

***

**Numeric Code**
1427

**Symbolic Error Code**
CampaignServiceTargetAlreadyAssociatedWithEntity

**Description**
A target is already associated with the entity.

***

**Numeric Code**
1428

**Symbolic Error Code**
CampaignServiceTargetHasActiveAssociations

**Description**
This target is already associated with one or more entities.

***

**Numeric Code**
1429

**Symbolic Error Code**
CampaignServiceInvalidTarget

**Description**
The target is not valid.

***

**Numeric Code**
1435

**Symbolic Error Code**
CampaignServiceNegativeBiddingNotAllowedForThisTargetType

**Description**
Negative bidding is not allowed for the specified target type.

***

**Numeric Code**
1445

**Symbolic Error Code**
CampaignServiceInvalidAddress

**Description**
The address is not valid.

***

**Numeric Code**
1449

**Symbolic Error Code**
CampaignServiceTargetsAgeBidsBatchLimitExceeded

**Description**
The maximum number of age targeting bids has been exceeded.

***

**Numeric Code**
1450

**Symbolic Error Code**
CampaignServiceTargetsDayBidsBatchLimitExceeded

**Description**
The maximum number of day targeting bids has been exceeded.

***

**Numeric Code**
1451

**Symbolic Error Code**
CampaignServiceTargetsHourBidsBatchLimitExceeded

**Description**
The maximum number of hour targeting bids has been exceeded.

***

**Numeric Code**
1452

**Symbolic Error Code**
CampaignServiceTargetsGenderBidsBatchLimitExceeded

**Description**
The maximum number of gender targeting bids has been exceeded.

***

**Numeric Code**
1453

**Symbolic Error Code**
CampaignServiceTargetsLocationBidsBatchLimitExceeded

**Description**
The maximum number of location targeting bids has been exceeded.

***

**Numeric Code**
1458

**Symbolic Error Code**
CampaignServiceInvalidLatitude

**Description**
The latitude of the radius target bid is not valid.

***

**Numeric Code**
1459

**Symbolic Error Code**
CampaignServiceInvalidLongitude

**Description**
The longitude of the radius target bid is not valid.

***

**Numeric Code**
1460

**Symbolic Error Code**
CampaignServiceDuplicateSubGeographyTarget

**Description**
The list contains duplicate state target bids.

***

**Numeric Code**
1461

**Symbolic Error Code**
CampaignServiceDuplicateCityTarget

**Description**
The list contains duplicate city target bids.

***

**Numeric Code**
1463

**Symbolic Error Code**
CampaignServiceDuplicateCustomLocationTarget

**Description**
The list contains duplicate radius target bids.

***

**Numeric Code**
1464

**Symbolic Error Code**
CampaignServiceInvalidLocationId

**Description**
The location identifier is not valid.

***

**Numeric Code**
1465

**Symbolic Error Code**
CampaignServiceGeoLocationOptionsRequired

**Description**
Not yet implemented.

***

**Numeric Code**
1466

**Symbolic Error Code**
CampaignServiceUnsupportedCombinationOfLocationIdAndOptions

**Description**
Not yet implemented.

***

**Numeric Code**
1467

**Symbolic Error Code**
CampaignServiceInvalidGeographicalLocationSearchString

**Description**
Not yet implemented.

***

**Numeric Code**
1471

**Symbolic Error Code**
Not applicable.

**Description**
Prepaid client accounts are not supported for management by agencies. The client account must be set up for post-pay billing.

***

**Numeric Code**
1472

**Symbolic Error Code**
Not applicable.

**Description**
You cannot get, delete, or update an account that is being linked or unlinked. You can determine the client link status with the [SearchClientLinks](../customer-management-service/searchclientlinks.md) operation. If the client link status is *LinkInProgress* or *UnlinkInProgress*, try waiting 5 to 30 minutes and try again. If the issue persists please reach out to [support](https://advertise.bingads.microsoft.com/bing-ads-support). 

***

**Numeric Code**
1490

**Symbolic Error Code**
CampaignServiceInvalidCustomerId

**Description**
The customer identifier is not valid.

***

**Numeric Code**
1499

**Symbolic Error Code**
CampaignServiceTargetingShouldBeExclusiveForThisTargetType

**Description**
The target type does not allow more than one target to be applied.

***
## 1500
***

**Numeric Code**
1500

**Symbolic Error Code**
CampaignServiceNullKeyword

**Description**
The keyword is null or empty.

***

**Numeric Code**
1501

**Symbolic Error Code**
CampaignServiceInvalidKeywordId

**Description**
The keyword identifier is not valid.

***

**Numeric Code**
1502

**Symbolic Error Code**
CampaignServiceDuplicateInKeywordIds

**Description**
The array of keyword identifiers contains one or more duplicates.

***

**Numeric Code**
1503

**Symbolic Error Code**
CampaignServiceInvalidKeywordText

**Description**
The keyword text is not valid.

***

**Numeric Code**
1504

**Symbolic Error Code**
CampaignServiceCannotChangeTextOnUpdate

**Description**
The keyword text cannot be updated.

***

**Numeric Code**
1505

**Symbolic Error Code**
CampaignServiceKeywordsArrayShouldNotBeNullOrEmpty

**Description**
The array of keywords cannot be null or empty.

***

**Numeric Code**
1506

**Symbolic Error Code**
CampaignServiceKeywordsArrayExceedsLimit

**Description**
The number of keywords exceeds the maximum limit.

***

**Numeric Code**
1507

**Symbolic Error Code**
CampaignServiceInvalidBidAmounts

**Description**
One or more of the keyword bid values are not valid.

***

**Numeric Code**
1508

**Symbolic Error Code**
CampaignServiceInvalidBidAmountForSearchAdGroup

**Description**
The keyword bid values are not valid for a search ad group.

***

**Numeric Code**
1509

**Symbolic Error Code**
CampaignServiceInvalidBidAmountForContentAdGroup

**Description**
The keyword bid values are not valid for a content ad group.

***

**Numeric Code**
1510

**Symbolic Error Code**
CampaignServiceInvalidBidAmountForHybridAdGroup

**Description**
The keyword bid values are not valid for a hybrid (search and content) ad group.

***

**Numeric Code**
1511

**Symbolic Error Code**
CampaignServiceInvalidParam1

**Symbolic Error Code**
The Param1 property of the keyword is not valid.

***

**Numeric Code**
1512

**Symbolic Error Code**
CampaignServiceInvalidParam2

**Symbolic Error Code**
The Param2 property of the keyword is not valid.

***

**Numeric Code**
1513

**Symbolic Error Code**
CampaignServiceInvalidParam3

**Symbolic Error Code**
The Param3 property of the keyword is not valid.

***

**Numeric Code**
1514

**Symbolic Error Code**
CampaignServiceNegativeKeywordRequiresPartialMatchBid

**Description**
Negative keywords require a partial match bid.

***

**Numeric Code**
1515

**Symbolic Error Code**
CampaignServiceBidAmountsLessThanFloorPrice

**Description**
The bid amount of a keyword, ad group, or product group is less than the minimum bid.

***

**Numeric Code**
1516

**Symbolic Error Code**
CampaignServiceBidAmountsGreaterThanCeilingPrice

**Description**
One or more of the bid values exceeds the budget that you specified for the campaign. Please verify that the bid values do not exceed the daily budget. 

***

**Numeric Code**
1517

**Symbolic Error Code**
CampaignServiceDuplicateKeyword

**Description**
An attempt was made to create a duplicate of a keyword that already exists.

***

**Numeric Code**
1518

**Symbolic Error Code**
CampaignServiceMaxKeywordsReachedForAccount

**Description**
No more keywords can be added to this account.

***

**Numeric Code**
1519

**Symbolic Error Code**
CampaignServiceMaxKeywordsReachedForAdGroup

**Description**
No more keywords can be added to this ad group.

***

**Numeric Code**
1520

**Symbolic Error Code**
CampaignServiceForbiddenWordInKeywordText

**Description**
The keyword text is invalid.

***

**Numeric Code**
1521

**Symbolic Error Code**
CampaignServiceForbiddenWordInParam1

**Symbolic Error Code**
The keyword param1 contains forbidden text.

***

**Numeric Code**
1522

**Symbolic Error Code**
CampaignServiceForbiddenWordInParam2

**Symbolic Error Code**
The keyword param2 contains forbidden text.

***

**Numeric Code**
1523

**Symbolic Error Code**
CampaignServiceForbiddenWordInParam3

**Symbolic Error Code**
The keyword param3 contains forbidden text.

***

**Numeric Code**
1524

**Symbolic Error Code**
CampaignServiceExclusiveWordInKeywordText

**Description**
The keyword text contains a reserved word.

***

**Numeric Code**
1525

**Symbolic Error Code**
CampaignServiceExclusiveWordInParam1

**Symbolic Error Code**
The keyword param1 contains a reserved word.

***

**Numeric Code**
1526

**Symbolic Error Code**
CampaignServiceExclusiveWordInParam2

**Symbolic Error Code**
The keyword param2 contains a reserved word.

***

**Numeric Code**
1527

**Symbolic Error Code**
CampaignServiceExclusiveWordInParam3

**Symbolic Error Code**
The keyword param3 contains a reserved word.

***

**Numeric Code**
1528

**Symbolic Error Code**
CampaignServiceKeywordDoesNotBelongToAdGroupId

**Description**
The specified keyword does not belong to the specified ad group.

***

**Numeric Code**
1529

**Symbolic Error Code**
CampaignServiceKeywordIdsArrayShouldNotBeNullOrEmpty

**Description**
The array of keyword identifiers cannot be empty or null.

***

**Numeric Code**
1530

**Symbolic Error Code**
CampaignServiceKeywordIdsArrayExceedsLimit

**Description**
The number of keyword identifiers exceeds the maximum limit.

***

**Numeric Code**
1531

**Symbolic Error Code**
CampaignServiceInvalidKeywordStatus

**Description**
The keyword status is not valid for the requested operation.

***

**Numeric Code**
1532

**Symbolic Error Code**
CampaignServiceInvalidKeywordEditorialStatus

**Description**
The keyword editorial status is read-only and cannot be modified.

***

**Numeric Code**
1534

**Symbolic Error Code**
CampaignServiceUpdateKeywordEmpty

**Description**
The keyword is null or empty.

***

**Numeric Code**
1535

**Symbolic Error Code**
CampaignServiceKeywordQualityScoreOperationNotEnabledForCustomer

**Description**
The user is not part of the quality score pilot program.

***

**Numeric Code**
1536

**Symbolic Error Code**
CampaignServiceDuplicateKeywordIdInRequest

**Description**
The request contains duplicate keyword identifiers.

***

**Numeric Code**
1538

**Symbolic Error Code**
CampaignServiceInvalidBidAmount

**Description**
The bid amount is invalid.

***

**Numeric Code**
1539

**Symbolic Error Code**
CampaignServiceMaxKeywordsReachedForCustomer

**Description**
You cannot add any more keywords to this customer.

***

**Numeric Code**
1541

**Symbolic Error Code**
CampaignServiceMultipleKeywordBidTypesNotAllowed

**Description**
You must set only one of the match-type bids (for example, ExactMatchBid) in the Keyword object to a non-null value. To specify multiple match-type bids for a keyword, you must create a Keyword object for each keyword and match type combination.

***

**Numeric Code**
1542

**Symbolic Error Code**
CampaignServiceKeywordAndMatchTypeCombinationAlreadyExists

**Description**
A keyword with the specified match type already exists.

***

**Numeric Code**
1543

**Symbolic Error Code**
CampaignServiceKeywordBidRequired

**Description**
The Keyword object does not contain a match-type bid. You must set one (and only one) of the match-type bids (for example, ExactMatchBid) in the Keyword object to a non-null value.

***

**Numeric Code**
1544

**Symbolic Error Code**
CampaignServiceKeywordZeroBidAmountNotAllowed

**Description**
You may not set the amount of a match-type bid to 0 (zero).

***

**Numeric Code**
1545

**Symbolic Error Code**
CampaignServiceKeywordMatchTypeChangeNotAllowedInUpdate

**Description**
You may not change the match type of a keyword when you update the Keyword object.

***

**Numeric Code**
1550

**Symbolic Error Code**
CampaignServiceTooMuchTextInKeywordDestinationUrl

**Description**
Too much text was provided for the keyword destination URL.

***

**Numeric Code**
1551

**Symbolic Error Code**
CampaignServiceKeywordTransactionalDependencyFailed

**Description**
This action failed because another dependent action failed.

***

**Numeric Code**
1604

**Symbolic Error Code**
CampaignServiceEntityNotAllowedForShoppingCampaign

**Description**
You cannot add this entity to a Shopping campaign.

***

**Numeric Code**
1605

**Symbolic Error Code**
CampaignServiceEntityNotAllowedForDynamicSearchAdsCampaign

**Description**
You cannot add this entity to a Dynamic Search Ads campaign.

***

**Numeric Code**
1606

**Symbolic Error Code**
CampaignServiceDynamicSearchAdNotAllowedForNonDynamicSearchAdsCampaign

**Description**
A Dynamic Search Ad can only be added to a Dynamic Search Ads campaign.

***

**Numeric Code**
1706

**Symbolic Error Code**
CampaignServiceInvalidEntity

**Description**
The entity ID is not valid.

***

**Numeric Code**
1707

**Symbolic Error Code**
CampaignServiceDuplicateEntity

**Description**
The list of entity IDs contains duplicates.

***

**Numeric Code**
1708

**Symbolic Error Code**
CampaignServiceJustificationTextMissingForInlineAppeal

**Description**
The justification text cannot be null or empty.

***

**Numeric Code**
1709

**Symbolic Error Code**
CampaignServiceJustificationTextTooLongForInlineAppeal

**Description**
The justification text is too long.

***

**Numeric Code**
1710

**Symbolic Error Code**
CampaignServiceAppealCreationQuotaExceeded

**Description**
The request will cause the account to exceed the maximum number of appeals that can be pending at any given point in time.

***

**Numeric Code**
1711

**Symbolic Error Code**
CampaignServiceAppealCreationQuotaExceededForLast24Hours

**Description**
The request will cause the account to exceed the maximum number of appeals allowed in a 24-hour rolling window.

***

**Numeric Code**
1712

**Symbolic Error Code**
CampaignServiceEditorialAppealEntityAlreadyAppealed

**Description**
Appeal already created for the entity.

***
## 2000
***

**Numeric Code**
2001

**Symbolic Error Code**
ReportingServiceNullReportRequest

**Description**
The report request is null.

***

**Numeric Code**
2002

**Symbolic Error Code**
ReportingServiceUnknownReportType

**Description**
The report request type is not valid.

***

**Numeric Code**
2003

**Symbolic Error Code**
ReportingServiceAccountNotAuthorized

**Description**
The specified report request contains at least one account that you do not have privileges to access.

***

**Numeric Code**
2004

**Symbolic Error Code**
ReportingServiceNoCompleteDataAvaliable

**Description**
You requested a report with complete data for all included campaigns. Currently only partial data is available in the respective time zone of one or more campaigns. Please try again later or submit a report request for partial data.

***

**Numeric Code**
2005

**Symbolic Error Code**
ReportingServiceInvalidDataAvailabilityAndTimePeriodCombination

**Description**
The report request indicates that complete data is required; however, the request contains a report time period for which complete data cannot be returned.

***

**Numeric Code**
2006

**Symbolic Error Code**
ReportingServiceInvalidReportName

**Description**
The report request contains a report name that is not valid.

***

**Numeric Code**
2007

**Symbolic Error Code**
ReportingServiceInvalidReportAggregation

**Description**
The report aggregation is not valid for the specified report time period.

***

**Numeric Code**
2008

**Symbolic Error Code**
ReportingServiceInvalidReportTimeSelection

**Description**
The report time is null or contains more than one predefined time, custom date, or custom date range start and end.

***

**Numeric Code**
2009

**Symbolic Error Code**
ReportingServiceInvalidCustomDateRangeStart

**Description**
The report time contains a custom date range start value that is not valid.

***

**Numeric Code**
2010

**Symbolic Error Code**
ReportingServiceInvalidCustomDateRangeEnd

**Description**
The report time contains a custom date range end value that is not valid.

***

**Numeric Code**
2011

**Symbolic Error Code**
ReportingServiceEndDateBeforeStartDate

**Description**
The report time contains a custom date range that is not valid; the end date cannot be earlier than the start date.

***

**Numeric Code**
2012

**Symbolic Error Code**
ReportingServiceEmptyCustomDates

**Description**
The report time contains an empty custom date array.

***

**Numeric Code**
2013

**Symbolic Error Code**
ReportingServiceCustomDatesOverlimit

**Description**
The report time contains too many custom dates.

Please refer to the *Details* element of the *OperationError* for information about the maximum number of custom dates.

***

**Numeric Code**
2014

**Symbolic Error Code**
ReportingServiceNullColumns

**Description**
The list of columns to include in the report cannot be null or empty.

***

**Numeric Code**
2015

**Symbolic Error Code**
ReportingServiceRequiredColumnsNotSelected

**Description**
The list of columns to include in the report must contain all required columns.

***

**Numeric Code**
2016

**Symbolic Error Code**
ReportingServiceDuplicateColumns

**Description**
The list of columns to include in the report contains duplicate.

Please refer to the *Details* element of the *OperationError* object for a comma-separated list of the duplicate column names.

***

**Numeric Code**
2017

**Symbolic Error Code**
ReportingServiceNoMeasureSelected

**Description**
The report request does not specify at least one measurement column.

***

**Numeric Code**
2018

**Symbolic Error Code**
ReportingServiceInvalidAccountIdInCampaignReportScope

**Description**
The campaign report scope contains an account identifier that is not valid.

Please refer to the *Details* element of the *BatchError* object for the account identifier that is not valid.

***

**Numeric Code**
2019

**Symbolic Error Code**
ReportingServiceInvalidCampaignIdInCampaignReportScope

**Description**
The campaign report scope contains a campaign identifier that is not valid.

Please refer to the *Details* element of the *BatchError* object for the campaign identifier that is not valid.

***

**Numeric Code**
2020

**Symbolic Error Code**
ReportingServiceInvalidAccountIdInAdGroupReportScope

**Description**
The ad group report scope contains an account identifier that is not valid.

Please refer to the *Details* element of the *BatchError* object for the account identifier that is not valid.

***

**Numeric Code**
2021

**Symbolic Error Code**
ReportingServiceInvalidCampaignIdInAdGroupReportScope

**Description**
The ad group report scope contains a campaign identifier that is not valid.

Please refer to the *Details* element of the *BatchError* object for the campaign identifier that is not valid.

***

**Numeric Code**
2022

**Symbolic Error Code**
ReportingServiceInvalidAdGroupIdInAdGroupReportScope

**Description**
The ad group report scope contains an ad group identifier that is not valid.

Please refer to the *Details* element of the *BatchError* object for the ad group identifier that is not valid.

***

**Numeric Code**
2023

**Symbolic Error Code**
ReportingServiceInvalidAccountIdInAccountReportScope

**Description**
The account report scope contains an account identifier that is not valid.

Please refer to the *Details* element of the *BatchError* object for the account identifier that is not valid.

***

**Numeric Code**
2024

**Symbolic Error Code**
ReportingServiceNullCampaignReportScope

**Description**
The campaign report scope is null.

***

**Numeric Code**
2025

**Symbolic Error Code**
ReportingServiceNullAdGroupReportScope

**Description**
The ad group report scope is null.

***

**Numeric Code**
2026

**Symbolic Error Code**
ReportingServiceInvalidAccountReportScope

**Description**
The account report scope does not contain account identifiers.

***

**Numeric Code**
2027

**Symbolic Error Code**
ReportingServiceInvalidAccountThruCampaignReportScope

**Description**
The account through campaign report scope contains one or more values that are not valid.

***

**Numeric Code**
2028

**Symbolic Error Code**
ReportingServiceInvalidAccountThruAdGroupReportScope

**Description**
The account through ad group report scope contains one or more values that are not valid.

***

**Numeric Code**
2029

**Symbolic Error Code**
ReportingServiceAccountsOverLimit

**Description**
The report scope contains too many accounts.

***

**Numeric Code**
2030

**Symbolic Error Code**
ReportingServiceMaximumCampaignsLimitReached

**Description**
The report scope contains too many campaigns.

***

**Numeric Code**
2031

**Symbolic Error Code**
ReportingServiceAdGroupsOverLimit

**Description**
The report scope contains too many ad groups.

***

**Numeric Code**
2032

**Symbolic Error Code**
ReportingServiceCrossSiteScriptNotAllowed

**Description**
The specified report request contains one or more strings that contain an embedded script. 

Please refer to the *Details* element of the *BatchError* object for the strings that caused this error.

***

**Numeric Code**
2033

**Symbolic Error Code**
ReportingServiceInvalidKeywordFilterValue

**Description**
The specified report request contains an invalid keyword filter.

***

**Numeric Code**
2034

**Symbolic Error Code**
ReportingServiceInvalidTimePeriodColumnForSummaryReport

**Description**
The TimePeriod column cannot be specified in a report request that has a summary aggregation.

***

**Numeric Code**
2035

**Symbolic Error Code**
ReportingServiceInvalidAccountIds

**Description**
The report request contains at least one account identifier that is not valid. 

Please refer to the *Details* element for a comma-separated list of up to 20 account identifiers that are not valid.

***

**Numeric Code**
2038

**Symbolic Error Code**
ReportingServiceSiteIdMaxArraySizeReached

**Description**
The specified report scope contains too many website identifiers. 

Please refer to the *Details* element of the *BatchError* object for the maximum number of websites.

***

**Numeric Code**
2039

**Symbolic Error Code**
ReportingServiceInvalidSiteIdValue

**Description**
The specified report request contains a website identifier filter where at least one of the values is empty or contains website identifier that is not valid.

***

**Numeric Code**
2040

**Symbolic Error Code**
ReportingServiceInvalidCustomDateRange

**Description**
The report time contains a date in the custom date range that is not valid.

***

**Numeric Code**
2041

**Symbolic Error Code**
ReportingServiceInvalidFutureStartDate

**Description**
The specified report time start date is in the future.

***

**Numeric Code**
2042

**Symbolic Error Code**
InvalidSearchQueryFilterValue

**Description**
The report request contains a search query filter where at least one of the values is null, empty, or contains a search query that is not valid.

***

**Numeric Code**
2043

**Symbolic Error Code**
SearchQueryFilterValueLengthExceeded

**Description**
The search query performance report filter contains one or more terms that are too long.

***

**Numeric Code**
2044

**Symbolic Error Code**
SearchQueryOverLimit

**Description**
The search query performance report filter contains too many search queries. 

Please refer to the *Details* element of the *BatchError* object for the maximum number of search queries allowed.

***

**Numeric Code**
2045

**Symbolic Error Code**
KeywordFilterValueLengthExceeded

**Description**
One or more of the keywords in the keyword performance report filter is too long.

***

**Numeric Code**
2046

**Symbolic Error Code**
KeywordOverLimit

**Description**
The keyword performance report filter contains too many keywords. 

Please refer to the *Details* element of the *BatchError* object for the maximum number of keywords allowed.

***

**Numeric Code**
2047

**Symbolic Error Code**
GoalIdMaxArraySizeReached

**Description**
The specified report scope contains too many Goal IDs.

The Details field contains the limit for number of goals.

***

**Numeric Code**
2048

**Symbolic Error Code**
TacticIdMaxArraySizeReached

**Description**
The specified report scope contains too many Tactic IDs.

The Details field contains the limit for number of tactic.

***

**Numeric Code**
2049

**Symbolic Error Code**
ChannelIdMaxArraySizeReached

**Description**
The specified report scope contains too many Channel IDs.

The Details field contains the limit for number of channels.

***

**Numeric Code**
2050

**Symbolic Error Code**
ThirdPartyCampaignIdMaxArraySizeReached

**Description**
The specified report scope contains too many Third Party Campaign IDs.

The Details field contains the limit for number of third party campaigns.

***

**Numeric Code**
2051

**Symbolic Error Code**
ThirdPartyAdGroupIdMaxArraySizeReached

**Description**
The specified report scope contains too many Third Party Ad Group IDs.

The Details field contains the limit for number of third party ad groups.

***

**Numeric Code**
2052

**Symbolic Error Code**
InvalidGrainForQualityScoreColumns

**Description**
The QualityScore, KeywordRelevance, LandingPageRelevance and LandingPageUserExperience columns are available only with hourly, daily, and summary report aggregation.

***

**Numeric Code**
2053

**Symbolic Error Code**
InvalidGrainForImpressionShareColumns

**Description**
The ImpressionSharePercent, ImpressionLostToBudgetPercent, ImpressionLostToRankPercent, ImpressionLostToRelevancePercent, ImpressionLostToOthersPercent, ImpressionLostToBidPercent, ImpressionLostToLandingPageRelevancePercent and ImpressionLostToKeywordRelevancePercent columns are not available for the specified ReportAggregation.

***

**Numeric Code**
2054

**Symbolic Error Code**
InvalidGrainForHistoricQualityScoreColumns

**Description**
The HistoricQualityScore, HistoricKeywordRelevance, HistoricLandingPageRelevance and HistoricLandingPageUserExperience columns are available only with daily report aggregation.

***

**Numeric Code**
2057

**Symbolic Error Code**
FilterValueBatchSizeOverLimit

**Description**
The number of values in a single filter is over limit.

***

**Numeric Code**
2058

**Symbolic Error Code**
FilterValueOverLimit

**Description**
The filter value exceeds its maximum limit.

***

**Numeric Code**
2059

**Symbolic Error Code**
UnsuportedTimeGrain

**Description**
The report type does not support the specified time grain.

***

**Numeric Code**
2060

**Symbolic Error Code**
InvalidFilterOrScopeValue

**Description**
Invalid filter or scope value.

***

**Numeric Code**
2061

**Symbolic Error Code**
InvalidSortColumn

**Description**
The sort column specified was not included in the submitted report.

***

**Numeric Code**
2100

**Symbolic Error Code**
ReportingServiceInvalidReportId

**Description**
The report identifier is not valid.

***

**Numeric Code**
2101

**Symbolic Error Code**
ReportingServiceReportNotFound

**Description**
The report was not found.

***

**Numeric Code**
2108

**Symbolic Error Code**
Not applicable.

**Description**
The account identifier is invalid.

***

**Numeric Code**
2180

**Symbolic Error Code**
Not applicable

**Description**
You must specify at least three characters in the search filter.

***

**Numeric Code**
2192

**Symbolic Error Code**
Not applicable.

**Description**
The account may not be updated given its current lifecycle status.

***

**Numeric Code**
2203

**Symbolic Error Code**
Not applicable

**Description**
Customer Threshold can only be set by users belonging to the bill to customer.

> [!NOTE] 
> This error might be returned by the *UpdateAccount* operation if you do not have permissions to update the payment method. You can remove the optional fields from the update request and try again.
 
***

**Numeric Code**
2204

**Symbolic Error Code**
Not applicable

**Description**
Billing of the balance amount in the account failed.

> [!NOTE] 
> This error could occur when attempting to delete an account. Before an account can be deleted the final billing must succeed.

***
## 2500
***

**Numeric Code**
2600

**Symbolic Error Code**
CampaignServiceNullSitePlacement

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2601

**Symbolic Error Code**
CampaignServiceInvalidSitePlacementId

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2602

**Symbolic Error Code**
CampaignServiceDuplicateInSitePlacementIds

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2603

**Symbolic Error Code**
CampaignServiceSitePlacementsArrayShouldNotBeNullOrEmpty

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2604

**Symbolic Error Code**
CampaignServiceSitePlacementsArrayExceedsLimit

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2605

**Symbolic Error Code**
CampaignServiceSitePlacementOperationNotAllowedForPilot

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2606

**Symbolic Error Code**
CampaignServiceSitePlacementIdsArrayShouldNotBeNullOrEmpty

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2607

**Symbolic Error Code**
CampaignServiceSitePlacementIdsArrayExceedsLimit

**Description**
This error code is no longer in use. Site placements were last used with Bing Ads API version 10.

***

**Numeric Code**
2608

**Symbolic Error Code**
CampaignServiceUrlsArrayShouldNotBeNullOrEmpty

**Description**
The array of URLs cannot be null or empty.

***

**Numeric Code**
2609

**Symbolic Error Code**
CampaignServiceUrlsArrayExceedsLimit

**Description**
The number of elements in the array of URLs exceeds the limit.

***

**Numeric Code**
2610

**Symbolic Error Code**
CampaignServiceNullUrl

**Description**
One or more of the URLs are null.

***

**Numeric Code**
2611

**Symbolic Error Code**
CampaignServiceInvalidUrl

**Description**
One or more of the URLs are not valid.

***

**Numeric Code**
2612

**Symbolic Error Code**
CampaignServiceInvalidPlacementId

**Description**
The placement identifier is not valid.

***

**Numeric Code**
2616

**Symbolic Error Code**
CampaignServiceCannotAddSitePlacementToSpecifiedAdGroup

**Description**
A website placement bid cannot be added to the specified ad group.

***

**Numeric Code**
2617

**Symbolic Error Code**
CampaignServiceInvalidSitePlacementStatus

**Description**
The site placement status is not valid.

***

**Numeric Code**
2802

**Symbolic Error Code**
CampaignServiceCannotChangeImageUrlOnUpdate

**Description**
The image URL cannot be updated.

***

**Numeric Code**
2803

**Symbolic Error Code**
CampaignServiceDefaultAdTooMuchTextInAltText

**Description**
The alternate text of the default ad is too long.

***

**Numeric Code**
2804

**Symbolic Error Code**
CampaignServiceTooMuchAdTextInAltText

**Description**
The Ad alternate text has too much text.

***

**Numeric Code**
2805

**Symbolic Error Code**
CampaignServiceAdTypeInvalid

**Description**
Creating or updating ads of this type is not allowed.

***

**Numeric Code**
2822

**Symbolic Error Code**
CampaignServiceConflictWithLocationExclusion

**Description**
Excluding the location would create a conflict with another location target. For example, the service will return this error if you target Washington State and also try to exclude the U.S.

***

**Numeric Code**
2902

**Symbolic Error Code**
CampaignServiceInvalidTargetName

**Description**
The target name is not valid.

***

**Numeric Code**
2904

**Symbolic Error Code**
CampaignServiceTargetInvalidForCustomer

**Description**
The customer is not allowed to use the specified target type.

***

**Numeric Code**
2909

**Symbolic Error Code**
CampaignServiceIsLibraryTargetNotNull

**Description**
This error code is no longer in use. Library targets were last used with Bing Ads API version 10.

***

**Numeric Code**
2918

**Symbolic Error Code**
CampaignServiceBusinessAndRadiusTargetsAllowedOnlyForSearchMedium

**Description**
Geographical location targeting is allowed only for search ads.

***

**Numeric Code**
2919

**Symbolic Error Code**
CampaignServiceAssociatingNonLibraryTargetNotAllowed

**Description**
Only targets that have been added to the target library are allowed to be associated with a campaign or ad group.

***

**Numeric Code**
2922

**Symbolic Error Code**
CampaignServiceInvalidDeviceTarget

**Description**
The device target specified is invalid.

***

**Numeric Code**
2923

**Symbolic Error Code**
CampaignServiceDuplicateDeviceTarget

**Description**
The customer's target library already contains the device target.

***

**Numeric Code**
2928

**Symbolic Error Code**
CampaignServiceCustomerDataBeingMigrated

**Description**
You cannot modify data for this customer at the moment, as it is under migration. 

***

**Numeric Code**
2934

**Symbolic Error Code**
CampaignServiceInvalidDeviceTargetBidAdjustment

**Description**
The value of the device target bid adjustment is not valid.

***

**Numeric Code**
2935

**Symbolic Error Code**
CampaignServiceInvalidLocationTargetBidAdjustment

**Description**
The value of location target bid adjustment is not valid.

***

**Numeric Code**
2936

**Symbolic Error Code**
CampaignServiceInvalidAgeTargetBidAdjustment

**Description**
The value of age target bid adjustment is not valid.

***

**Numeric Code**
2937

**Symbolic Error Code**
CampaignServiceInvalidGenderTargetBidAdjustment

**Description**
The value of gender target bid adjustment is not valid.

***

**Numeric Code**
2938

**Symbolic Error Code**
CampaignServiceInvalidDayTargetBidAdjustment

**Description**
The value of day target bid adjustment is not valid.

***

**Numeric Code**
2939

**Symbolic Error Code**
CampaignServiceInvalidHourTargetBidAdjustment

**Description**
The value of hour target bid adjustment is not valid.

***

**Numeric Code**
2940

**Symbolic Error Code**
CampaignServiceInvalidSegmentedTargetBidAdjustment

**Description**
The value of segmented target bid adjustment is not valid.

***

**Numeric Code**
2941

**Symbolic Error Code**
CampaignServiceBidAdjustmentNullPassedForAddTarget

**Description**
The null value for bid adjustment is not valid.

***

**Numeric Code**
2942

**Symbolic Error Code**
CampaignServiceInvalidTargetBidExclusion

**Description**


***

**Numeric Code**
2943

**Symbolic Error Code**
CampaignServiceRadiusUnitInvalid

**Description**
You must set either Miles or Kilometers as the radius unit of a radius target bid.

***

**Numeric Code**
2944

**Symbolic Error Code**
CampaignServiceDayTimeTargetInvalid

**Description**
The DayTimeTarget is not Valid.

***

**Numeric Code**
2945

**Symbolic Error Code**
CampaignServiceTargetsDayTimeBidBatchLimitExceeded

**Description**
The number of bids in the DayTimeTarget would be exceeded.

***

**Numeric Code**
2946

**Symbolic Error Code**
CampaignServiceDayTimeTargetBidIntervalInvalid

**Description**
The From or To interval of the DayTimeTargetBid is not valid.

***

**Numeric Code**
2947

**Symbolic Error Code**
CampaignServiceDayTimePilotNotEnabledForCustomer

**Description**
The customer is not in Pilot to use DayTime Targets.

***

**Numeric Code**
2948

**Symbolic Error Code**
CampaignServiceDuplicatePostalCodeTarget

**Description**
The PostalCode Target Bids contain Duplicate PostalCodes.

***

**Numeric Code**
2949

**Symbolic Error Code**
CampaignServicePostalCodePilotNotEnabledForCustomer

**Description**
The customer is not in Pilot to use PostalCode Targets.

***

**Numeric Code**
2950

**Symbolic Error Code**
CampaignServiceTargetDayTimeAndDayHourAreExclusive

**Description**
DayHour and DayTime targets are Exclusive

***

**Numeric Code**
2951

**Symbolic Error Code**
CampaignServiceDayTimeTargetBidsIntervalOverlap

**Description**
The DayTime Target intervals overlap.

***

**Numeric Code**
2952

**Symbolic Error Code**
CampaignServiceDayTimeTargetBidAdjustmentInvalid

**Description**
The DayTime Target BidAdjustment is invalid.

***

**Numeric Code**
2953

**Symbolic Error Code**
CampaignServiceOSNameIsNotSupported

**Description**
OSName is not supported.

***

**Numeric Code**
2954

**Symbolic Error Code**
CampaignServiceRelatedCriterionActionError

**Description**
The target cannot be migrated to criterion because of an error with another target subtype.

***

**Numeric Code**
2955

**Symbolic Error Code**
CampaignServiceInvalidCriterionId

**Description**
The Criterion ID is invalid.

***

**Numeric Code**
2956

**Symbolic Error Code**
CampaignServiceCriterionDoesNotMatch

**Description**
The Existing Criterion is different from the one passed for the same ID

***

**Numeric Code**
2957

**Symbolic Error Code**
CampaignServiceIncompleteDeviceCriterionSet

**Description**
The entity must either be explicitly associated with all device criterion types (Computers, Tablets, Smartphones) or should not have any device criterion.

***

**Numeric Code**
2958

**Symbolic Error Code**
InvalidGeolocationsFileVersion

**Description**
The geographical locations file version is invalid.

***

**Numeric Code**
2959

**Symbolic Error Code**
InvalidLanguageLocale

**Description**
The geographical locations file language locale is invalid.

***

**Numeric Code**
2965

**Symbolic Error Code**
CampaignServiceLocationIntentCriterionCannotBeDeleted

**Description**
Location intent criterion cannot be deleted.

***

**Numeric Code**
2966

**Symbolic Error Code**
CampaignServiceLocationIntentCriterionInvalid

**Description**
The location intent option is invalid.

***

**Numeric Code**
2967

**Symbolic Error Code**
CampaignServiceBidsMustBeEqualForDeviceType

**Description**
The bids must be equal for the same device type.

***

**Numeric Code**
2968

**Symbolic Error Code**
CampaignServiceCustomerNotEnabledForCountyTargets

**Description**
The customer is not a member of the county targets pilot program.

***
## 3000
***

**Numeric Code**
3024

**Symbolic Error Code**
Not applicable

**Description**
The batch size exceeds the limit.

***

**Numeric Code**
3030

**Symbolic Error Code**
Not applicable

**Description**
The Predicate passed in the search is invalid. For example you used an invalid predicate operator for a valid predicate field.

***

**Numeric Code**
3079

**Symbolic Error Code**
Not applicable

**Description**
At least one predicate is required to search for customers.

***

**Numeric Code**
3080

**Symbolic Error Code**
Not applicable

**Description**
Page Info must be present and have index greater than 0 (zero).

***

**Numeric Code**
3083

**Symbolic Error Code**
Not applicable

**Description**
A specified element of the client link may not be updated.

***

**Numeric Code**
3086

**Symbolic Error Code**
Not applicable

**Description**
The UserInvitation field cannot be null or empty for the SendUserInvitation operation.

***

**Numeric Code**
3087

**Symbolic Error Code**
Not applicable

**Description**
The required list of elements is null or empty.

***

**Numeric Code**
3201

**Symbolic Error Code**
CampaignServiceAccountIdsLengthExceeded

**Description**
The list of account IDs exceeds the maximum number allowed.

***

**Numeric Code**
3203

**Symbolic Error Code**
CampaignServiceCampaignsContainsMultipleAccounts

**Description**
The list of campaigns must belong to the same account.

***

**Numeric Code**
3204

**Symbolic Error Code**
CampaignServiceCampaignsContainsNullScope

**Description**
The list of campaigns cannot contain null items.

***

**Numeric Code**
3205

**Symbolic Error Code**
CampaignServiceInvalidDownloadRequestId

**Description**
The download request ID is not valid.

***

**Numeric Code**
3207

**Symbolic Error Code**
CampaignServiceAccountTooBigToDownload

**Description**
The account has more keywords than allowed per request. Please call [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) to download the account's campaigns in multiple requests. The Details field contains the campaign identifiers under the account.

> [!NOTE] 
> Calling the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation with an account that contains more than four million keywords will fail.

***

**Numeric Code**
3208

**Symbolic Error Code**
CampaignServiceLastSyncTimeCannotBeInTheFuture

**Description**
The last sync time cannot be later than now.

***

**Numeric Code**
3209

**Symbolic Error Code**
CampaignServiceLastSyncTimeTooOld

**Description**
The last sync time cannot be earlier than 1/1/1753.

***

**Numeric Code**
3210

**Symbolic Error Code**
BulkServiceMinimumRequiredEntitiesNotSpecified

**Description**
The minimum set of required entities should be specified for bulk download.

***

**Numeric Code**
3211

**Symbolic Error Code**
CampaignServiceBulkDownloadUnsupportedEntities

**Description**
One or more specified entities are not supported for bulk download.

***

**Numeric Code**
3212

**Symbolic Error Code**
BulkServiceInvalidPerformanceStatsDateRangeForDataScope

**Description**
The *PerformanceStatsDateRange* element should be specified when including performance statistics in the data scope, and otherwise should be excluded from the request.

***

**Numeric Code**
3213

**Symbolic Error Code**
BulkServiceInvalidSyncTimeForPerformanceStatsDateRange

**Description**
The *LastSyncTimeInUTC* element should be null when including performance statistics in the requested data scope.

***

**Numeric Code**
3214

**Symbolic Error Code**
BulkServiceInvalidPerformanceStatsDateRange

**Description**
The *PerformanceStatsDateRange* element should be set to a valid custom date or predefined time.

***

**Numeric Code**
3215

**Symbolic Error Code**
BulkServiceInvalidCustomDateRange

**Description**
The start and end date for performance statistics should be valid and within the supported range.

***

**Numeric Code**
3216

**Symbolic Error Code**
BulkServiceCampaignsTooBigToDownload

**Description**
The campaigns included in the download have more keywords than allowed per request. Please call [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) with fewer campaigns.

> [!NOTE] 
> Calling the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation with an account that contains more than eight million keywords will fail.

***

**Numeric Code**
3217

**Symbolic Error Code**
BulkServiceFormatVersionNotSupported

**Description**
One or more bulk download entities are not supported with the specified format version.

***

**Numeric Code**
3218

**Symbolic Error Code**
BulkServiceEntityNotSupportedForFormatVersion

**Description**
One or more bulk download entities are not supported with the specified format version.

***

**Numeric Code**
3219

**Symbolic Error Code**
BulkServiceFormatVersionRequired

**Description**
The format version is required.

***

**Numeric Code**
3220

**Symbolic Error Code**
BulkServiceInvalidBulkUploadUrl

**Description**
Invalid bulk upload URL.

***

**Numeric Code**
3221

**Symbolic Error Code**
BulkServiceNoFileFound

**Description**
No file uploaded.

***

**Numeric Code**
3222

**Symbolic Error Code**
BulkServiceMultipleFilesFound

**Description**
More than one file uploaded.

***

**Numeric Code**
3223

**Symbolic Error Code**
BulkServiceInvalidFileExtension

**Description**
The file extension is not recognized.

***

**Numeric Code**
3224

**Symbolic Error Code**
BulkServiceUrlAlreadyUsedForUpload

**Description**
The URL has already been used for file upload.

***

**Numeric Code**
3225

**Symbolic Error Code**
BulkServiceFileRowCountExceeded

**Description**
The number of rows in the file has exceeded the maximum allowed value.

***

**Numeric Code**
3226

**Symbolic Error Code**
BulkServiceUrlExpired

**Description**
The URL has expired and cannot be used for uploads.

***

**Numeric Code**
3227

**Symbolic Error Code**
BulkServiceTooManyRequests

**Description**
Too many requests.

***

**Numeric Code**
3306

**Symbolic Error Code**
CampaignServiceAccountIdsArrayShouldNotBeNullOrEmpty

**Description**
The list of account IDs cannot be null or empty.

***

**Numeric Code**
3400

**Symbolic Error Code**
CampaignServiceLanguageNotSupported

**Description**
The specified language is not supported.

***

**Numeric Code**
3412

**Symbolic Error Code**
CampaignServiceInvalidLanguage

**Description**
The language provided is invalid.

***

**Numeric Code**
3413

**Symbolic Error Code**
CampaignServiceInvalidPublisherCountryForLanguage

**Description**
The publisher country provided is invalid.

***

**Numeric Code**
3414

**Symbolic Error Code**
CampaignServiceInvalidLevel

**Description**
The location level provided is invalid.

***

**Numeric Code**
3415

**Symbolic Error Code**
CampaignServiceInvalidParentCountry

**Description**
The parent country provided is invalid.

***

**Numeric Code**
3416

**Symbolic Error Code**
CampaignServiceInvalidRollupPeriod

**Description**
The rollup period provided is invalid.

***

**Numeric Code**
3417

**Symbolic Error Code**
CampaignServiceInvalidDevice

**Description**
The device provided is invalid.

***

**Numeric Code**
3418

**Symbolic Error Code**
CampaignServiceInvalidMaxLocations

**Description**
The MaxLocations value provided is invalid.

***
## 3500
***

**Numeric Code**
3500

**Symbolic Error Code**
CampaignServiceBulkApiNotEnabledForPilot

**Description**
The customer is not a member of the bulk download pilot program.

***

**Numeric Code**
3501

**Symbolic Error Code**
CampaignServiceBulkUploadFeatureNotEnabledForCustomer

**Description**
The customer is not a member of the bulk upload program.

***

**Numeric Code**
3510

**Symbolic Error Code**
CampaignServiceKeywordVariantMatchNotEnabledForPilot

**Description**
The customer not enabled to use the Keyword Variant Match Type Feature.

***

**Numeric Code**
3602

**Symbolic Error Code**
CampaignServiceInvalidMigrationTypeFilter

**Description**
The migration type filter value is missing or invalid.

***

**Numeric Code**
3603

**Symbolic Error Code**
CampaignServiceFullSyncRequired

**Description**
The last sync time must be null.

You must set the last sync time to null if the specified account was included in a data migration, for example the URL by match type migration. After requesting a full download, you can begin requesting delta downloads again.

***

**Numeric Code**
3800

**Symbolic Error Code**
CampaignServiceInvalidAdExtensionStatus

**Description**
The ad extension status is read-only and must be null.

***

**Numeric Code**
3801

**Symbolic Error Code**
CampaignServiceInvalidAdExtensionType

**Description**
The type of ad extension is not valid.

***

**Numeric Code**
3802

**Symbolic Error Code**
CampaignServiceAdExtensionSiteLinkArrayIsNullOrEmpty

**Description**
The list of site links cannot be null or empty.

***

**Numeric Code**
3803

**Symbolic Error Code**
CampaignServiceAdExtensionSiteLinkIsNull

**Description**
The list of site links cannot contain a null site link. The Details element contains the index of the site link.

***

**Numeric Code**
3804

**Symbolic Error Code**
CampaignServiceSiteLinkDestinationUrlNullOrEmpty

**Description**
The site link's destination URL cannot be null or empty. The Details element contains the index of the site link.

***

**Numeric Code**
3805

**Symbolic Error Code**
CampaignServiceSiteLinkDisplayTextNullOrEmpty

**Description**
The site link's display text cannot be null or empty. The Details element contains the index of the site link.

***

**Numeric Code**
3806

**Symbolic Error Code**
CampaignServiceSiteLinkDestinationUrlTooLong

**Description**
The site link's destination URL is too long. The Details element contains the index of the site link.

***

**Numeric Code**
3807

**Symbolic Error Code**
CampaignServiceSiteLinkDisplayTextTooLong

**Description**
The site link's display text is too long. The Details element contains the index of the site link.

***

**Numeric Code**
3808

**Symbolic Error Code**
CampaignServiceTooManyAdExtensionsPerAccount

**Description**
Adding the ad extensions to the account will exceed the maximum number of ad extensions that you may add to the account.

***

**Numeric Code**
3809

**Symbolic Error Code**
CampaignServiceTooManySiteLinks

**Description**
The ad extension contains too many site links.

***

**Numeric Code**
3810

**Symbolic Error Code**
CampaignServiceAdExtensionIdToCampaignIdAssociationArrayShouldNotBeNullOrEmpty

**Description**
The list of ad extension to campaign associations cannot be null or empty.

***

**Numeric Code**
3811

**Symbolic Error Code**
CampaignServiceAdExtensionIdToCampaignIdAssociationArrayLimitExceeded

**Description**
The list of ad extension to campaign associations is too long.

***

**Numeric Code**
3812

**Symbolic Error Code**
CampaignServiceInvalidAdExtensionId

**Description**
The ad extension ID is not valid.

***

**Numeric Code**
3813

**Symbolic Error Code**
CampaignServiceInvalidAdExtensionIdToCampaignIdAssociation

**Description**
The extension to campaign association is not valid.

***

**Numeric Code**
3814

**Symbolic Error Code**
CampaignServiceInvalidAdExtensionTypeFilter

**Description**
The filter type is not valid.

***

**Numeric Code**
3815

**Symbolic Error Code**
CampaignServiceAdExtensionIdArrayShouldNotBeNullOrEmpty

**Description**
The list of ad extension IDs cannot be null or empty.

***

**Numeric Code**
3816

**Symbolic Error Code**
CampaignServiceAdExtensionIdsArrayExceedsLimit

**Description**
The list of ad extension IDs is too long.

***

**Numeric Code**
3817

**Symbolic Error Code**
CampaignServiceDuplicateInAdExtensionIds

**Description**
The list of ad extension IDs contains duplicates.

***

**Numeric Code**
3818

**Symbolic Error Code**
CampaignServiceCannotAssignMoreThanOneAdExtensionTypeToAnEntity

**Description**
The entity to which you are trying to associate the ad extension already has an ad extension of the same type associated with it.

***

**Numeric Code**
3819

**Symbolic Error Code**
CampaignServiceAdExtensionIdsArrayIsNullOrEmpty

**Description**
The list of ad extension IDs cannot be null or empty.

***

**Numeric Code**
3820

**Symbolic Error Code**
CampaignServiceAdExtensionIdToCampaignIdAssociationNotPassed

**Description**
The campaign to ad extension association cannot be null.

***

**Numeric Code**
3821

**Symbolic Error Code**
CampaignServiceAdExtensionIdToCampaignIdAssociationsNotPassed

**Description**
The list of campaign to ad extension associations cannot be null or empty.

***

**Numeric Code**
3822

**Symbolic Error Code**
CampaignServiceSiteLinkAdExtensionPilotNotEnabledForCustomer

**Description**
To add or get site links extensions, the customer must be a member of the SiteLink AdExtension pilot program.

***

**Numeric Code**
3823

**Symbolic Error Code**
CampaignServiceSiteLinkDestinationUrlInvalid

**Description**
The site link's destination URL contains invalid characters. The Details field contains the index of the site link element which has the error.

***

**Numeric Code**
3824

**Symbolic Error Code**
CampaignServiceTooManyCampaignIds

**Description**
The list of campaign IDs is too long.

***

**Numeric Code**
3825

**Symbolic Error Code**
CampaignServiceDuplicateInAdExtensionIdToCampaignIdAssociations

**Description**
The list of ad extension to campaign associations contains duplicates.

***

**Numeric Code**
3826

**Symbolic Error Code**
CampaignServiceAdExtensionVersionCannotBeSet

**Description**
The version field is read-only and must be null.

***

**Numeric Code**
3827

**Symbolic Error Code**
CampaignServiceDuplicateSiteLinksInAdExtension

**Description**
The list of site links contains duplicates.

***

**Numeric Code**
3828

**Symbolic Error Code**
CampaignServiceAdExtensionAddressIsNull

**Description**
The address cannot be null.

***

**Numeric Code**
3829

**Symbolic Error Code**
CampaignServiceAdExtensionStreetAddressNullOrEmpty

**Description**
The first line of the street address cannot be null or empty.

***

**Numeric Code**
3830

**Symbolic Error Code**
CampaignServiceAdExtensionStreetAddressTooLong

**Description**
The first line of the street address is too long.

***

**Numeric Code**
3831

**Symbolic Error Code**
CampaignServiceAdExtensionStreetAddressInvalid

**Description**
The first line of the street address contains content that is not valid.

***

**Numeric Code**
3832

**Symbolic Error Code**
CampaignServiceAdExtensionStreetAddress2TooLong

**Description**
The second line of the street address is too long.

***

**Numeric Code**
3833

**Symbolic Error Code**
CampaignServiceAdExtensionStreetAddress2Invalid

**Description**
The second line of the street address contains content that is not valid.

***

**Numeric Code**
3834

**Symbolic Error Code**
CampaignServiceAdExtensionCityNameNullOrEmpty

**Description**
The city name cannot be null or empty.

***

**Numeric Code**
3835

**Symbolic Error Code**
CampaignServiceAdExtensionCityNameTooLong

**Description**
The city name is too long.

***

**Numeric Code**
3836

**Symbolic Error Code**
CampaignServiceAdExtensionCityNameInvalid

**Description**
The city name contains content that is not valid.

***

**Numeric Code**
3837

**Symbolic Error Code**
CampaignServiceAdExtensionProvinceNameTooLong

**Description**
The province name is too long.

***

**Numeric Code**
3838

**Symbolic Error Code**
CampaignServiceAdExtensionProvinceNameInvalid

**Description**
The province name contains content that is not valid.

***

**Numeric Code**
3839

**Symbolic Error Code**
CampaignServiceAdExtensionPostalCodeNullOrEmpty

**Description**
The postal code cannot be null or empty.

***

**Numeric Code**
3840

**Symbolic Error Code**
CampaignServiceAdExtensionPostalCodeTooLong

**Description**
The postal code is too long.

***

**Numeric Code**
3841

**Symbolic Error Code**
CampaignServiceAdExtensionPostalCodeInvalid

**Description**
The postal code contains content that is not valid.

***

**Numeric Code**
3842

**Symbolic Error Code**
CampaignServiceAdExtensionCountryCodeNullOrEmpty

**Description**
The country code cannot be null or empty.

***

**Numeric Code**
3843

**Symbolic Error Code**
CampaignServiceAdExtensionCountryCodeWrongLength

**Description**
The country code must contain 2 characters.

***

**Numeric Code**
3844

**Symbolic Error Code**
CampaignServiceAdExtensionCountryCodeInvalid

**Description**
The country code is not valid.

The country code must be one of the supported publisher countries.

***

**Numeric Code**
3845

**Symbolic Error Code**
CampaignServiceAdExtensionGeoPointIsNotNull

**Description**
The GeoPoint field is read-only and must be null.

***

**Numeric Code**
3846

**Symbolic Error Code**
CampaignServiceAdExtensionGeoCodeStatusIsNotNull

**Description**
The GeoCodeStatus field is read-only and must be null.

***

**Numeric Code**
3847

**Symbolic Error Code**
CampaignServiceAdExtensionCompanyNameNullOrEmpty

**Description**
The company name cannot be null or empty.

***

**Numeric Code**
3848

**Symbolic Error Code**
CampaignServiceAdExtensionCompanyNameTooLong

**Description**
The company name is too long.

***

**Numeric Code**
3849

**Symbolic Error Code**
CampaignServiceAdExtensionCompanyNameInvalid

**Description**
The company name contains content that is not valid.

***

**Numeric Code**
3850

**Symbolic Error Code**
CampaignServiceAdExtensionPhoneNumberTooLong

**Description**
The phone number is too long.

***

**Numeric Code**
3851

**Symbolic Error Code**
CampaignServiceAdExtensionPhoneNumberInvalid

**Description**
The phone number contains content that is not valid.

***

**Numeric Code**
3852

**Symbolic Error Code**
CampaignServiceAdExtensionIconMediaIdInvalid

**Description**
An icon with the specified ID was not found in the account's media library.

***

**Numeric Code**
3853

**Symbolic Error Code**
CampaignServiceAdExtensionIconTooLarge

**Description**
The width and height of the icon that you are adding to the location extension is greater than the maximum allowed.

***

**Numeric Code**
3854

**Symbolic Error Code**
CampaignServiceAdExtensionImageMediaIdInvalid

**Description**
An image with the specified ID was not found in the account's media library.

***

**Numeric Code**
3855

**Symbolic Error Code**
CampaignServiceAdExtensionImageTooLarge

**Description**
The width and height of the image that you are adding to the location extension is greater than the maximum allowed.

***

**Numeric Code**
3856

**Symbolic Error Code**
CampaignServiceLocationAdExtensionPilotNotEnabledForCustomer

**Description**
To add or get location extensions, the customer must be a member of the Location Ad Extension v2 pilot program.

***

**Numeric Code**
3857

**Symbolic Error Code**
CampaignServiceCallAdExtensionPilotNotEnabledForCustomer

**Description**
To add or get call extensions, the customer must be a member of the Call Ad Extension v2 pilot program.

***

**Numeric Code**
3858

**Symbolic Error Code**
CampaignServiceAdExtensionProvinceCodeTooLong

**Description**
The province code is too long.

***

**Numeric Code**
3859

**Symbolic Error Code**
CampaignServiceAdExtensionProvinceCodeInvalid

**Description**
The province code is not valid.

***

**Numeric Code**
3860

**Symbolic Error Code**
CampaignServiceAdExtensionProvinceCodeRequiredIfProvinceNameEmpty

**Description**
The province code is required if the province name is empty.

***

**Numeric Code**
3861

**Symbolic Error Code**
CampaignServiceAdExtensionPhoneNumberNullOrEmpty

**Description**
The phone number cannot be null or empty.

***

**Numeric Code**
3862

**Symbolic Error Code**
CampaignServiceLocationAdExtensionsEntityLimitExceeded

**Description**
The number of location ad extensions in the ad extensions list exceeds the maximum allowed.

***

**Numeric Code**
3863

**Symbolic Error Code**
CampaignServiceProductAdExtensionPilotNotEnabledForCustomer

**Description**
To add or get product extensions, the customer must be a member of the Product Ad pilot program.

***

**Numeric Code**
3864

**Symbolic Error Code**
CampaignServiceProductAdExtensionTooManyProductConditionCollections

**Description**
The list of product condition collections is too long.

***

**Numeric Code**
3865

**Symbolic Error Code**
CampaignServiceProductAdExtensionTooManyConditions

**Description**
The product condition collection contains too many conditions.

***

**Numeric Code**
3866

**Symbolic Error Code**
CampaignServiceProductAdExtensionInvalidStoreId

**Description**
The Bing Merchant Center store identifier is invalid.

***

**Numeric Code**
3867

**Symbolic Error Code**
CampaignServiceProductAdExtensionProductConditionsArrayIsNullOrEmpty

**Description**
The product condition collection cannot be null or empty.

***

**Numeric Code**
3868

**Symbolic Error Code**
CampaignServiceProductAdExtensionProductConditionIsNull

**Description**
The product condition cannot be null.

***

**Numeric Code**
3869

**Symbolic Error Code**
CampaignServiceProductAdExtensionOperandIsInvalid

**Description**
The operand of one of the product conditions in the product condition collection is not valid.

***

**Numeric Code**
3870

**Symbolic Error Code**
CampaignServiceProductAdExtensionAttributeIsInvalid

**Description**
The attribute of one of the product conditions in the product condition collection is not valid.

***

**Numeric Code**
3871

**Symbolic Error Code**
CampaignServiceProductConditionAttributeTooLong

**Description**
The attribute of one of the product conditions in the product condition collection is too long.

***

**Numeric Code**
3872

**Symbolic Error Code**
CampaignServiceProductConditionDuplicateOperand

**Description**
The operand of one of the product conditions in the product condition collection is duplicated.

***

**Numeric Code**
3873

**Symbolic Error Code**
CampaignServiceProductAdExtensionStoreNameCannotBeSet

**Description**
Store Name is read-only and cannot be set.

***

**Numeric Code**
3874

**Symbolic Error Code**
CampaignServiceAdExtensionTypeMismatch

**Description**
The specified ad extension type differs from the existing ad extension type for the same identifier.

***

**Numeric Code**
3875

**Symbolic Error Code**
CallAdExtensionRequireTollFreeTrackingNumberMustBeNullWhenTrackingNotEnabled

**Description**
RequireTollFreeTrackingNumber must be null when call tracking is not enabled for the specified extension.

***

**Numeric Code**
3876

**Symbolic Error Code**
CampaignServiceCallTrackingNotEnabledForCustomer

**Description**
The customer is not a member of the Call Tracking pilot program.

***

**Numeric Code**
3877

**Symbolic Error Code**
CampaignServiceCallAdExtensionCallTrackingNotSupportedForCountry

**Description**
Call tracking is not supported for selected country.

***

**Numeric Code**
3878

**Symbolic Error Code**
CampaignServiceAdExtensionGeoPointInvalid

**Description**
The geo point coordinates are invalid.

***

**Numeric Code**
3879

**Symbolic Error Code**
CampaignServiceProductAdExtensionNameTooLong

**Description**
The name of the Product Ad Extension is too long.

***

**Numeric Code**
3880

**Symbolic Error Code**
CampaignServiceProductAdExtensionNameInvalid

**Description**
The name of the Product Ad Extension is invalid.

***

**Numeric Code**
3881

**Symbolic Error Code**
CampaignServiceDuplicateProductTarget

**Description**
The list of product targets contains duplicates.

***

**Numeric Code**
3882

**Symbolic Error Code**
CampaignServiceProductAdExtensionProductConditionCollectionIsNull

**Description**
The product condition collection cannot be null.

***

**Numeric Code**
3883

**Symbolic Error Code**
CampaignServiceInvalidAssociationType

**Description**
The specified association type is not valid.

***

**Numeric Code**
3884

**Symbolic Error Code**
CampaignServiceAdExtensionIdToAdGroupIdAssociationArrayShouldNotBeNullOrEmpty

**Description**
The list of ad extension to ad group associations cannot be null or empty.

***

**Numeric Code**
3885

**Symbolic Error Code**
CampaignServiceAdExtensionIdToAdGroupIdAssociationArrayLimitExceeded

**Description**
The list of ad extension to ad group associations is too long.

***

**Numeric Code**
3886

**Symbolic Error Code**
CampaignServiceInvalidAdExtensionIdToAdGroupIdAssociation

**Description**
The ad extension Id to ad group Id association provided is not valid.

***

**Numeric Code**
3887

**Symbolic Error Code**
CampaignServiceDuplicateInAdExtensionIdToAdGroupIdAssociations

**Description**
The list of ad extension to ad group associations contains duplicates.

***

**Numeric Code**
3888

**Symbolic Error Code**
CampaignServiceAdExtensionTypeNotAllowedForAdGroupAssociation

**Description**
The type of ad extension cannot be associated with an ad group.

***

**Numeric Code**
3889

**Symbolic Error Code**
CampaignServiceProductAdExtensionDuplicateProductFilter

**Description**
Duplicate product filter provided.

***

**Numeric Code**
3890

**Symbolic Error Code**
CampaignServiceProductAdExtensionDuplicateProductCondition

**Description**
Duplicate product condition provided.

***

**Numeric Code**
3891

**Symbolic Error Code**
CampaignServiceProductAdExtensionCannotHaveBothAllAndSpecificProducts

**Description**
Product ad extension cannot have all and specific products specified.

***

**Numeric Code**
3892

**Symbolic Error Code**
CampaignServiceMultipleProductAdExtensionCannotBeAssignedToSingleEntity

**Description**
Multiple product ad extensions cannot be assigned to a single entity.

***

**Numeric Code**
3893

**Symbolic Error Code**
CampaignServiceExtensionProductSelectionIsNull

**Description**
Product Selection is null.

***

**Numeric Code**
3894

**Symbolic Error Code**
CampaignServiceProductTargetDestinationUrlTooLong

**Description**
Product Target destination URL is too long.

***

**Numeric Code**
3895

**Symbolic Error Code**
CampaignServiceProductValueTooLong

**Description**
Product Value is too long.

***

**Numeric Code**
3896

**Symbolic Error Code**
CampaignServiceInvalidProductTargetParam1

**Symbolic Error Code**
Param1 in product target is invalid.

***

**Numeric Code**
3897

**Symbolic Error Code**
CampaignServiceInvalidProductTargetParam2

**Symbolic Error Code**
Param2 in product target is invalid.

***

**Numeric Code**
3898

**Symbolic Error Code**
CampaignServiceInvalidProductTargetParam3

**Symbolic Error Code**
Param3 in product target is invalid.

***

**Numeric Code**
3930

**Symbolic Error Code**
CampaignServiceAdExtensionSchedulingPilotNotEnabledForCustomer

**Description**
The customer is not part of the AdExtension Scheduling pilot program.

***

**Numeric Code**
3931

**Symbolic Error Code**
CampaignServiceAdExtensionScheduleInvalidStartTime

**Description**
The start date cannot be earlier than today.

***

**Numeric Code**
3932

**Symbolic Error Code**
CampaignServiceAdExtensionScheduleInvalidEndTime

**Description**
The end date cannot be earlier than today.

***

**Numeric Code**
3933

**Symbolic Error Code**
CampaignServiceInvalidScheduleDayTimeRange

**Description**
The end date cannot be earlier than the start date.

***

**Numeric Code**
3934

**Symbolic Error Code**
CampaignServiceScheduleDayTimeRangesDayBatchLimitExceeded

**Description**
The maximum number of schedule intervals per day would be exceeded.

***

**Numeric Code**
3935

**Symbolic Error Code**
CampaignServiceScheduleDayTimeRangesOverlapping

**Description**
Ad schedules must be non-overlapping.

***

**Numeric Code**
3936

**Symbolic Error Code**
CampaignServiceInvalidScheduleDayTimeRangeInterval

**Description**
The schedule interval must be greater than zero.

***

**Numeric Code**
3948

**Symbolic Error Code**
CampaignServiceSiteLinkDescriptionAllOrNoneRequired

**Description**
You must specify both sitelink description elements or do not specify either.

***

**Numeric Code**
3949

**Symbolic Error Code**
CampaignServiceEnhancedSiteLinkAdExtensionPilotNotEnabledForCustomer

**Description**
The customer is not part of the Enhanced SiteLink AdExtension pilot program.

***

**Numeric Code**
3950

**Symbolic Error Code**
CampaignServiceSiteLinkDescription1TooLong

**Description**
The site link's *Description1* text is too long.

***

**Numeric Code**
3951

**Symbolic Error Code**
CampaignServiceSiteLinkDescription2TooLong

**Description**
The site link's *Description2* text is too long.

***

**Numeric Code**
3952

**Symbolic Error Code**
CampaignServiceSiteLinkDescription1Invalid

**Description**
The site link's Description1 contains invalid characters.

***

**Numeric Code**
3953

**Symbolic Error Code**
CampaignServiceSiteLinkDescription2Invalid

**Description**
The site link's Description2 contains invalid characters.

***

**Numeric Code**
3954

**Symbolic Error Code**
CampaignServiceSiteLinkDevicePreferenceInvalid

**Description**
The site link's DevicePreference value is invalid.

***

**Numeric Code**
3955

**Symbolic Error Code**
CampaignServiceSiteLinkDisplayTextInvalid

**Description**
The site link's display text contains invalid characters.

***

**Numeric Code**
3956

**Symbolic Error Code**
CampaignServiceImageAdExtensionPilotNotEnabledForCustomer

**Description**
The customer is not part of the Image AdExtension pilot program.

***

**Numeric Code**
3957

**Symbolic Error Code**
CampaignServiceCampaignImageAdExtensionPilotNotEnabledForCustomer

**Description**
The customer is not part of the Campaign level Image Ad Extension pilot program.

***

**Numeric Code**
3960

**Symbolic Error Code**
CampaignServiceImageAdExtensionAlternativeTextNullOrEmpty

**Description**
The image ad extension's alternative text cannot be null or empty.

***

**Numeric Code**
3961

**Symbolic Error Code**
CampaignServiceImageAdExtensionAlternativeTextInvalid

**Description**
The image ad extension's alternative text contains invalid characters.

***

**Numeric Code**
3962

**Symbolic Error Code**
CampaignServiceImageAdExtensionAlternativeTextTooLong

**Description**
The image ad extension's alternative text is too long.

***

**Numeric Code**
3963

**Symbolic Error Code**
CampaignServiceImageAdExtensionDestinationUrlInvalid

**Description**
The image ad extension's destination URL contains invalid characters.

***

**Numeric Code**
3964

**Symbolic Error Code**
CampaignServiceImageAdExtensionDestinationUrlTooLong

**Description**
The image ad extension's destination URL is too long.

***

**Numeric Code**
3966

**Symbolic Error Code**
CampaignServiceImageAdExtensionMediaIdInvalid

**Description**
The image ad extension's media id is invalid.

***

**Numeric Code**
3967

**Symbolic Error Code**
CampaignServiceAdExtensionAssociationsLimitExceededPerEntityType

**Description**
The maximum number of campaigns or ad groups are already associated with ad extensions of this type. Please refer to documentation for entity association limits.

***

**Numeric Code**
3968

**Symbolic Error Code**
CampaignServiceAssociationsLimitExceededPerAdExtensionType

**Description**
The campaign or ad group cannot be associated with an additional ad extension of this type. Please refer to documentation for entity and ad extension association limits.

***

**Numeric Code**
3969

**Symbolic Error Code**
CampaignServiceAppAdExtensionPilotNotEnabledForCustomer

**Description**
The customer is not part of the App AdExtension pilot program.

***

**Numeric Code**
3970

**Symbolic Error Code**
CampaignServiceAppAdExtensionAppPlatformNullOrEmpty

**Description**
The app platform cannot be null or empty.

***

**Numeric Code**
3971

**Symbolic Error Code**
CampaignServiceAppAdExtensionInvalidAppPlatform

**Description**
The app platform is invalid.

***

**Numeric Code**
3972

**Symbolic Error Code**
CampaignServiceAppAdExtensionAppStoreIdNullOrEmpty

**Description**
The app network ad extension's app store ID cannot be null or empty.

***

**Numeric Code**
3973

**Symbolic Error Code**
CampaignServiceAppAdExtensionAppStoreIdTooLong

**Description**
The app ad extension's app store ID is too long.

***

**Numeric Code**
3974

**Symbolic Error Code**
CampaignServiceAppAdExtensionAppStoreIdInvalid

**Description**
The app ad extension's app store ID is invalid.

***

**Numeric Code**
3975

**Symbolic Error Code**
CampaignServiceAppAdExtensionDisplayTextNullOrEmpty

**Description**
The app network ad extension's display text cannot be null or empty.

***

**Numeric Code**
3976

**Symbolic Error Code**
CampaignServiceAppAdExtensionDisplayTextTooLong

**Description**
The app ad extension's display text is too long.

***

**Numeric Code**
3977

**Symbolic Error Code**
CampaignServiceAppAdExtensionDisplayTextInvalid

**Description**
The app ad extension's display text is invalid.

***

**Numeric Code**
3978

**Symbolic Error Code**
CampaignServiceAppAdExtensionDestinationUrlNullOrEmpty

**Description**
The app network ad extension's destination URL cannot be null or empty.

***

**Numeric Code**
3979

**Symbolic Error Code**
CampaignServiceAppAdExtensionDestinationUrlTooLong

**Description**
The app ad extension's URL is too long.

***

**Numeric Code**
3980

**Symbolic Error Code**
CampaignServiceAppAdExtensionDestinationUrlInvalid

**Description**
The app or measurement URL is incorrect, or doesn't correspond to the specified app ID or package name. The Details element contains the index of the app ad extension.

***

**Numeric Code**
3981

**Symbolic Error Code**
CampaignServiceAppAdExtensionDevicePreferenceInvalid

**Description**
The app ad extension device preference is invalid.

***

**Numeric Code**
3982

**Symbolic Error Code**
CampaignServiceAppInstallTrackingPilotNotEnabledForCustomer

**Description**
The customer is not part of the Application Installation Tracking pilot program.

***

**Numeric Code**
3990

**Symbolic Error Code**
CampaignServiceImageAdExtensionDescriptionInvalid

**Description**
The image ad extension's description is invalid.

***

**Numeric Code**
3991

**Symbolic Error Code**
CampaignServiceImageAdExtensionDescriptionTooLong

**Description**
The image ad extension's description is too long.

***

**Numeric Code**
3992

**Symbolic Error Code**
CampaignServiceImageAdExtensionTooManyImages

**Description**
You specified too many image media identifiers.

***

**Numeric Code**
3993

**Symbolic Error Code**
CampaignServiceImageAdExtensionImageMediaIdsNullOrEmpty

**Description**
Image media identifiers cannot be null or empty.

***
## 4000
***

**Numeric Code**
4000

**Symbolic Error Code**
CampaignServiceMediaIdInvalid

**Description**
An image or icon with the specified ID was not found in the account's media library.

***

**Numeric Code**
4001

**Symbolic Error Code**
CampaignServiceImageDataInvalid

**Description**
The image data is not valid. The data must be a base64 encoded string and cannot be null or empty.

***

**Numeric Code**
4003

**Symbolic Error Code**
CampaignServiceImageMimeTypeInvalid

**Description**
The image's MIME type is not supported.

***

**Numeric Code**
4004

**Symbolic Error Code**
CampaignServiceImageTooLarge

**Description**
The width and height of the image is greater than the maximum allowed.

***

**Numeric Code**
4005

**Symbolic Error Code**
CampaignServiceImageOverweight

**Description**
The image's binary size in megabytes is greater than the maximum allowed.

***

**Numeric Code**
4006

**Symbolic Error Code**
CampaignServiceAnimatedImageNotAllowed

**Description**
Animated images are not allowed.

***

**Numeric Code**
4007

**Symbolic Error Code**
CampaignServiceMediaTypeInvalid

**Description**
The type of media is not valid.

> [!NOTE] 
> This error may be thrown during a call to the [AddMedia](../campaign-management-service/addmedia.md) operation if either the media *Type* or *MediaType* is invalid.

***

**Numeric Code**
4008

**Symbolic Error Code**
CampaignServiceMediaIdsArrayIsNullOrEmpty

**Description**
The list of media IDs cannot be null or empty.

***

**Numeric Code**
4009

**Symbolic Error Code**
CampaignServiceMediaIdsLimitExceeded

**Description**
The list of media IDs exceeds the limit.

***

**Numeric Code**
4010

**Symbolic Error Code**
CampaignServiceDuplicateInMediaIds

**Description**
The list of media IDs contains duplicates.

***

**Numeric Code**
4011

**Symbolic Error Code**
CampaignServiceMediaEntityArrayIsNullOrEmpty

**Description**
The list of media cannot be null or empty.

***

**Numeric Code**
4012

**Symbolic Error Code**
CampaignServiceMediaEntityLimitExceeded

**Description**
The list of media exceeds the limit.

***

**Numeric Code**
4013

**Symbolic Error Code**
CampaignServiceMediaEntityIsNull

**Description**
One of the media entities is null.

***

**Numeric Code**
4014

**Symbolic Error Code**
CampaignServiceMediaEntityDataIsNull

**Description**
Data in one of the media entities is null.

***

**Numeric Code**
4015

**Symbolic Error Code**
CampaignServiceMediaDataInvalid

**Description**
Data in one or more the media is not a supported format.

***

**Numeric Code**
4016

**Symbolic Error Code**
CampaignServiceMediaEnabledEntitiesFilterInvalid

**Description**
The specified media enabled entities filter is invalid.

***

**Numeric Code**
4017

**Symbolic Error Code**
CampaignServiceMediaTypeInvalidForOperation

**Description**
The specified media is not supported by this operation.

***

**Numeric Code**
4018

**Symbolic Error Code**
CampaignServiceMediaDataEncodingInvalid

**Description**
Data in one of the media entities is not a valid format.

***

**Numeric Code**
4019

**Symbolic Error Code**
CampaignServiceMediaWidthInvalid

**Description**
Data in one or more media has invalid Width.

***

**Numeric Code**
4020

**Symbolic Error Code**
CampaignServiceMediaHeightInvalid

**Description**
Data in one or more media has invalid Height.

***

**Numeric Code**
4021

**Symbolic Error Code**
CampaignServiceMediaDataAspectRatioInvalid

**Description**
Data in one or more media has invalid aspect ratio.

***

**Numeric Code**
4022

**Symbolic Error Code**
CampaignServiceMediaFormatNotSupported

**Description**
The media you attempted to add is not represented by a supported data format. Please refer to documentation for the supported media formats.

***

**Numeric Code**
4023

**Symbolic Error Code**
CampaignServiceMediaNotFoundInAccount

**Description**
The media is not in the media library for the specified account.

***

**Numeric Code**
4024

**Symbolic Error Code**
CampaignServiceMediaIsAssociated

**Description**
The media you attempted to delete is still associated with one or more entities.

***

**Numeric Code**
4100

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIdInvalid

**Description**
The ad group criterion ID is not valid.

***

**Numeric Code**
4101

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIdArrayNullOrEmpty

**Description**
The list of ad group criterion IDs cannot be null or empty.

***

**Numeric Code**
4102

**Symbolic Error Code**
CampaignServiceDuplicateAdGroupCriterionId

**Description**
The list of ad group criterion IDs cannot contain duplicates.

***

**Numeric Code**
4103

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIdListExceedsLimit

**Description**
The list of ad group criterion IDs is too long.

***

**Numeric Code**
4104

**Symbolic Error Code**
CampaignServiceAdGroupCriterionsNullOrEmpty

**Description**
The list of ad group criterions cannot be null or empty.

***

**Numeric Code**
4105

**Symbolic Error Code**
CampaignServiceAdGroupCriterionsEntityLimitExceeded

**Description**
The list of ad group criterions is too long.

***

**Numeric Code**
4106

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIsNull

**Description**
The ad group criterion cannot be null.

***

**Numeric Code**
4107

**Symbolic Error Code**
CampaignServiceAdGroupCriterionInvalidConditionType

**Description**
The condition of Ad Group Criterion is invalid.

***

**Numeric Code**
4108

**Symbolic Error Code**
CampaignServiceAdGroupCriterionInvalidBidType

**Description**
The ad group criterion's bid type is not valid.

***

**Numeric Code**
4109

**Symbolic Error Code**
CampaignServiceAdGroupCriterionInvalidBidValue

**Description**
The ad group criterion's bid value is not valid.

***

**Numeric Code**
4110

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIdShouldBeNullOnAdd

**Description**
The ad group criterion's ID is read-only and must be null.

***

**Numeric Code**
4111

**Symbolic Error Code**
CampaignServiceInvalidAdGroupCriterionStatus

**Description**
The ad group criterion's status is not valid.

***

**Numeric Code**
4112

**Symbolic Error Code**
CampaignServiceInvalidAdGroupCriterionType

**Description**
The ad group criterion's type is not valid.

***

**Numeric Code**
4113

**Symbolic Error Code**
CampaignServiceProductAdGroupCriterionTooManyConditions

**Description**
The list of product conditions is too long.

***

**Numeric Code**
4114

**Symbolic Error Code**
CampaignServiceAdGroupCriterionProductConditionIsNull

**Description**
The product condition cannot be null.

***

**Numeric Code**
4115

**Symbolic Error Code**
CampaignServiceInvalidAdGroupCriterionCriterionTypeFilter

**Description**
The criterion's type is not valid for this operation.

***

**Numeric Code**
4116

**Symbolic Error Code**
CampaignServiceProductConditionAttributeNullOrEmpty

**Description**
The product condition's attribute cannot be null or empty.

***

**Numeric Code**
4117

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIsDeleted

**Description**
The ad group criterion is deleted.

***

**Numeric Code**
4118

**Symbolic Error Code**
CampaignServiceInvalidAdGroupCriterionEditorialStatus

**Description**
Setting Editorial Status is not allowed.

***

**Numeric Code**
4119

**Symbolic Error Code**
CampaignServiceAdGroupCriterionActionsNullOrEmpty

**Description**
The list of ad group criterion actions cannot be null or empty.

***

**Numeric Code**
4120

**Symbolic Error Code**
CampaignServiceAdGroupCriterionActionNull

**Description**
The ad group criterion action cannot be null.

***

**Numeric Code**
4121

**Symbolic Error Code**
CampaignServiceCampaignIsNotOfTypeShopping

**Description**
The Campaign must be of type Shopping for this operation.

***

**Numeric Code**
4123

**Symbolic Error Code**
CampaignServiceProductPartitionTypeInvalid

**Description**
The product partition type is invalid.

***

**Numeric Code**
4124

**Symbolic Error Code**
CampaignServiceAdGroupCriterionTypeImmutable

**Description**
The ad group criterion type cannot be updated.

***

**Numeric Code**
4125

**Symbolic Error Code**
CampaignServiceNegativeAdGroupCriterionImmutable

**Description**
The negative ad group criterion cannot be updated.

***

**Numeric Code**
4126

**Symbolic Error Code**
CampaignServiceAdGroupProductPartitionLimitExceeded

**Description**
The specified ad group cannot contain additional product partitions.

***

**Numeric Code**
4127

**Symbolic Error Code**
CampaignServiceInvalidProductPartitionHierarchy

**Description**
Adding the product partition would result in an invalid product partition hierarchy.

***

**Numeric Code**
4128

**Symbolic Error Code**
CampaignServiceRemainingProductsNodeMissingInProductPartition

**Description**
The product partition is missing a product condition that specifies the remaining products.

***

**Numeric Code**
4129

**Symbolic Error Code**
CampaignServiceDuplicatePructConditions

**Description**
Children of a product partition node cannot contain duplicate product conditions.

***

**Numeric Code**
4130

**Symbolic Error Code**
CampaignServiceProductPartitionSiblingsMustHaveSameOperand

**Description**
All children of a product partition node must have the same operand.

***

**Numeric Code**
4131

**Symbolic Error Code**
CampaignServiceProductPartitionTreeHeightLimitExceeeded

**Description**
The height of the product partition tree would have exceeded the limit.

***

**Numeric Code**
4132

**Symbolic Error Code**
CampaignServiceProductPartitionTreeRootAlreadyExists

**Description**
The ad group already has a product partition tree root node.

***

**Numeric Code**
4133

**Symbolic Error Code**
CampaignServiceCannotAddChildrenToProductPartitionUnit

**Description**
You can only add child nodes to a parent of type subdivision.

***

**Numeric Code**
4134

**Symbolic Error Code**
CampaignServiceParentAdGroupCriterionIdInvalid

**Description**
The requested parent ad group criterion does not exist in the product partition tree.

***

**Numeric Code**
4135

**Symbolic Error Code**
CampaignServiceProductPartitionCriterionImmutable

**Description**
The criterion field of a product partition cannot be updated.

***

**Numeric Code**
4136

**Symbolic Error Code**
CampaignServiceRemainingProductsNodeRequired

**Description**
You must add a replacement product partition node before it can be deleted from the subdivision.

***

**Numeric Code**
4137

**Symbolic Error Code**
CampaignServiceCriterionActionsAdGroupLimitExceeded

**Description**
Too many ad groups were specified in the list of ad group criterion actions.

***

**Numeric Code**
4139

**Symbolic Error Code**
CampaignServiceProductConditionOperandInvalid

**Description**
The product condition's operand is not valid.

***

**Numeric Code**
4140

**Symbolic Error Code**
CampaignServiceProductConditionAttributeInvalid

**Description**
The product condition's attribute is not valid.

***

**Numeric Code**
4141

**Symbolic Error Code**
CampaignServiceCriterionTypeNotAllowed

**Description**
The criterion object passed is not allowed for the operation.

***

**Numeric Code**
4142

**Symbolic Error Code**
CampaignServiceCriterionTypeMismatch

**Description**
The criterion type specified does not match the criterion object passed.

***

**Numeric Code**
4143

**Symbolic Error Code**
CampaignServiceDestinationUrlProtocolInvalid

**Description**
The destination URL protocol is invalid.

***

**Numeric Code**
4144

**Symbolic Error Code**
CampaignServiceDestinationUrlInvalid

**Description**
The destination URL is invalid.

***

**Numeric Code**
4145

**Symbolic Error Code**
CampaignServiceDestinationUrlTooLong

**Description**
The destination URL is too long.

***

**Numeric Code**
4146

**Symbolic Error Code**
CampaignServiceParam1NotSupportedForCriterionType

**Description**
Param1 is not supported for this criterion type.

***

**Numeric Code**
4147

**Symbolic Error Code**
CampaignServiceParam2NotSupportedForCriterionType

**Description**
Param2 is not supported for this criterion type.

***

**Numeric Code**
4148

**Symbolic Error Code**
CampaignServiceParam3NotSupportedForCriterionType

**Description**
Param3 is not supported for this criterion type.

***

**Numeric Code**
4149

**Symbolic Error Code**
CampaignServiceConcurrentStoreModification

**Description**
The data that you tried to modify was instead modified by another operation during the attempted processing of this service operation.

***

**Numeric Code**
4150

**Symbolic Error Code**
CampaignServiceRelatedProductPartitionActionError

**Description**
Product partition action for the same ad group has an error.

***

**Numeric Code**
4151

**Symbolic Error Code**
CampaignServiceAdGroupCriterionDoesNotExist

**Description**
The ad group criterion does not exist.

***

**Numeric Code**
4152

**Symbolic Error Code**
CampaignServiceDuplicateAdGroupCriterion

**Description**
Duplicate ad group criterions are not allowed.

***

**Numeric Code**
4153

**Symbolic Error Code**
CampaignServiceAdgroupCriterionIdIsNotNull

**Description**
The ad group criterion's Id must be null.

***

**Numeric Code**
4154

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIdIsNull

**Description**
The ad group criterion's Id cannot be null.

***

**Numeric Code**
4155

**Symbolic Error Code**
CampaignServiceAdGroupCriterionIdNotMatchCriterionType

**Description**
The ad group criterion's Id don't match criterion type.

***

**Numeric Code**
4156

**Symbolic Error Code**
CampaignServiceAdGroupCriterionBidMultiplierValueNotSet

**Description**
The BidMultiplier is not set for AdGroup Criterion.

***

**Numeric Code**
4157

**Symbolic Error Code**
CampaignServiceAdGroupCriterionCriterionIsNullOrEmpty

**Description**
The criterion of ad group criterion cannot be null.

***

**Numeric Code**
4158

**Symbolic Error Code**
RelatedTransactionError

**Description**
Reserved for internal use.

***

**Numeric Code**
4200

**Symbolic Error Code**
BulkServiceBatchOperationFailedForItems

**Description**
The upload failed due to other items in the batch.

***

**Numeric Code**
4201

**Symbolic Error Code**
BulkServiceInvalidRequestId

**Description**
The specified RequestId is not valid.

***

**Numeric Code**
4202

**Symbolic Error Code**
BulkServiceEntityNotFound

**Description**
The entity specified by the row could not be found.

***

**Numeric Code**
4203

**Symbolic Error Code**
BulkServiceUnknownTypeForRow

**Description**
The Type column of the row was not recognized and could not be inferred from the contents.

***

**Numeric Code**
4204

**Symbolic Error Code**
BulkServiceNoMoreCallsPermittedForTheTimePeriod

**Description**
No more bulk upload or download calls will be permitted for this account for the current time period. If you have reached your bulk upload limit, the bulk download operations may still be available, or vice versa. If you observe this error, you can resubmit your request after waiting up to 15 minutes. For more information see [Bulk Download and Upload](bulk-download-upload.md) and [Bulk API Throttling](services-protocol.md#throttling-bulk). 

***

**Numeric Code**
4205

**Symbolic Error Code**
BulkServiceCannotRemoveLastGoodAdExtensionItem

**Description**
You may not remove the last valid item in an ad extension. For example if you have 2 site links for an associated ad extension and only one site link is approved, you may not remove the only approved site link.

***

**Numeric Code**
4206

**Symbolic Error Code**
CampaignServiceInvalidCustomParametersText

**Description**
The text format of Custom Parameters is invalid.

***

**Numeric Code**
4207

**Symbolic Error Code**
CampaignServiceInvalidFinalUrlsText

**Description**
The text format of Final Url is invalid.

***

**Numeric Code**
4208

**Symbolic Error Code**
CampaignServiceInvalidMobileFinalUrlsText

**Description**
The text format of Mobile Final Url is invalid.

***

**Numeric Code**
4301

**Symbolic Error Code**
CampaignServiceSharedEntityNameRequired

**Description**
Shared entity Name field is a required field.

***

**Numeric Code**
4302

**Symbolic Error Code**
CampaignServiceSharedEntityLimitExceeded

**Description**
Adding the shared entity to the account will exceed the maximum number of lists that you can add to the account.

***

**Numeric Code**
4303

**Symbolic Error Code**
CampaignServiceSharedEntityInvalidType

**Description**
Shared Entity is not the correct type, currently support types are: NegativeKeywordList.

***

**Numeric Code**
4304

**Symbolic Error Code**
CampaignServiceSharedEntityAssociationsNotPassed

**Description**
Shared entity associations are required.

***

**Numeric Code**
4306

**Symbolic Error Code**
CampaignServiceMultipleSharedEntityTypesNotAllowed

**Description**
Multiple types of shared entity are not allowed in one call.

***

**Numeric Code**
4307

**Symbolic Error Code**
CampaignServiceSharedEntityAssociationsBatchLimitExceeded

**Description**
Too many shared entity associations in one batch.

***

**Numeric Code**
4308

**Symbolic Error Code**
CampaignServiceSharedEntityAssociationNull

**Description**
Shared entity associations cannot be null or empty

***

**Numeric Code**
4309

**Symbolic Error Code**
CampaignServiceSharedEntityAssociationDuplicate

**Description**
Shared entity is a duplicate of a existing association.

***

**Numeric Code**
4310

**Symbolic Error Code**
CampaignServiceSharedEntityIdsNotPassed

**Description**
Shared entity Id field cannot be null or empty.

***

**Numeric Code**
4311

**Symbolic Error Code**
CampaignServiceSharedEntityNull

**Description**
Shared Entity cannot be null or empty

***

**Numeric Code**
4312

**Symbolic Error Code**
CampaignServiceDuplicateSharedEntityId

**Description**
Duplicate shared entity Ids are not allowed

***

**Numeric Code**
4313

**Symbolic Error Code**
CampaignServiceSharedEntityTypeNotPassed

**Description**
Shared entity type is a required field.

***

**Numeric Code**
4314

**Symbolic Error Code**
CampaignServiceSharedListDeleted

**Description**
Deleted shared entity lists cannot be modified

***

**Numeric Code**
4315

**Symbolic Error Code**
CampaignServiceSharedListsNotPassed

**Description**
Shared entity lists are required.

***

**Numeric Code**
4316

**Symbolic Error Code**
CampaignServiceSharedListNotPassed

**Description**
Shared entity list is a required field.

***

**Numeric Code**
4317

**Symbolic Error Code**
CampaignServiceSharedListIdInvalid

**Description**
Shared entity list Id is not valid

***

**Numeric Code**
4318

**Symbolic Error Code**
CampaignServiceSharedListDuplicate

**Description**
Duplicate shared entity Id is not allowed

***

**Numeric Code**
4319

**Symbolic Error Code**
CampaignServiceSharedListItemsNotPassed

**Description**
Shared entity list items are a required field.

***

**Numeric Code**
4320

**Symbolic Error Code**
CampaignServiceListItemIdInvalid

**Description**
Shared entity list Id is not a valid Id

***

**Numeric Code**
4321

**Symbolic Error Code**
CampaignServiceListItemIdsLimitExceeded

**Description**
Too many shared entity list Ids in the batch

***

**Numeric Code**
4322

**Symbolic Error Code**
CampaignServiceSharedEntitiesNotPassed

**Description**
Shared entities is a required field.

***

**Numeric Code**
4323

**Symbolic Error Code**
CampaignServiceSharedEntityNameTooLong

**Description**
Shared entity name is too long.

***

**Numeric Code**
4324

**Symbolic Error Code**
CampaignServiceSharedEntityNameInvalid

**Description**
Shared entity name is invalid

***

**Numeric Code**
4325

**Symbolic Error Code**
CampaignServiceSharedListIdNotAllowed

**Description**
Shared entity list Id is not allowed

***

**Numeric Code**
4326

**Symbolic Error Code**
CampaignServiceSharedEntityIdInvalid

**Description**
Shared entity id is invalid

***

**Numeric Code**
4328

**Symbolic Error Code**
CampaignServiceMaxNegativeKeywordLimitExceededForList

**Description**
Adding the negative keyword to the list will exceed the maximum number of negative keywords that you can add to the list.

***

**Numeric Code**
4329

**Symbolic Error Code**
CampaignServiceNegativeKeywordDeleted

**Description**
Cannot modify a deleted negative keyword

***

**Numeric Code**
4330

**Symbolic Error Code**
CampaignServiceInvalidNegativeKeywordId

**Description**
Negative keyword Id is invalid

***

**Numeric Code**
4331

**Symbolic Error Code**
CampaignServiceNegativeKeywordListWithActiveAssociationsCannotBeDeleted

**Description**
A list with a active association cannot be deleted.

***

**Numeric Code**
4332

**Symbolic Error Code**
CampaignServiceNegativeKeywordInvalidType

**Description**
Negative Keyword Type field is invalid

***

**Numeric Code**
4333

**Symbolic Error Code**
CampaignServiceNegativeKeywordTextRequired

**Description**
Negative Keyword text is required

***

**Numeric Code**
4334

**Symbolic Error Code**
CampaignServiceNegativeKeywordListNameAlreadyExists

**Description**
Duplicate negative keyword list names are not allowed

***

**Numeric Code**
4335

**Symbolic Error Code**
CampaignServiceNegativeKeywordAlreadyExists

**Description**
Duplicate negative keyword already exists in this list.

***

**Numeric Code**
4336

**Symbolic Error Code**
CampaignServiceStructuredNegativeKeywordPilotNotEnabledForCustomer

**Description**
The Structured Negative Keyword Pilot is not enabled for this customer.

***

**Numeric Code**
4337

**Symbolic Error Code**
CampaignServiceNegativeKeywordTooManyParentTypes

**Description**
You cannot mix the parent types for the Negative Keywords in this calls.

***

**Numeric Code**
4338

**Symbolic Error Code**
CampaignServiceNegativeKeywordDuplicateFound

**Description**
Duplicate Negative Keywords in this call.

***

**Numeric Code**
4339

**Symbolic Error Code**
CampaignServiceNegativeKeywordNotFound

**Description**
No negative keywords were found.

***

**Numeric Code**
4340

**Symbolic Error Code**
CampaignServiceNegativeKeywordInvalidMatchType

**Description**
The match type for this keyword was invalid.

***

**Numeric Code**
4341

**Symbolic Error Code**
CampaignServiceNegativeKeywordInvalidParentType

**Description**
The parent type for this negative keyword is invalid.

***

**Numeric Code**
4342

**Symbolic Error Code**
CampaignServiceNegativeKeywordEntitiesNotPassed

**Description**
Negative Keywords entities are required for this call

***

**Numeric Code**
4343

**Symbolic Error Code**
CampaignServiceNegativeKeywordEntityNull

**Description**
Negative Keyword cannot be null

***

**Numeric Code**
4344

**Symbolic Error Code**
CampaignServiceNegativeKeywordEntityTypesMismatch

**Description**
Negative Keyword types cannot be mixed in one call.

***

**Numeric Code**
4345

**Symbolic Error Code**
CampaignServiceNegativeKeywordDuplicate

**Description**
Duplicate negative keyword are not allowed.

***

**Numeric Code**
4346

**Symbolic Error Code**
CampaignServiceSharedEntityAssociationDoesNotExist

**Description**
Shared entity association does not exisit

***

**Numeric Code**
4347

**Symbolic Error Code**
CampaignServiceCampaignIdsNotPassed

**Description**
Campaign Ids passed are null or empty.

***

**Numeric Code**
4348

**Symbolic Error Code**
CampaignServiceAdGroupIdsNotPassed

**Description**
AdGroup Ids passed are null or empty.

***

**Numeric Code**
4349

**Symbolic Error Code**
CampaignServiceSharedEntityBatchLimitExceeded

**Description**
Too many shared entities ids in one batch.

***

**Numeric Code**
4350

**Symbolic Error Code**
CampaignServiceEntityBatchLimitExceeded

**Description**
Too many entities ids in one batch.

***

**Numeric Code**
4351

**Symbolic Error Code**
CampaignServiceNegativeKeywordsAccountLimitExceeded

**Description**
Negative keyword limit at account level would be exceeded.

***

**Numeric Code**
4352

**Symbolic Error Code**
CampaignServiceSharedEntityAssociationsAccountLimitExceeded

**Description**
Shared entity association limit at account level would be exceeded.

***

**Numeric Code**
4400

**Symbolic Error Code**
AdExtensionPilotNotEnabledForCustomer

**Description**
Customer is not in pilot for this ad extension type.

***

**Numeric Code**
4401

**Symbolic Error Code**
AdExtensionCampaignAssociationPilotNotEnabledForCustomer

**Description**
Customer is not in pilot for this ad extension type campaign association.

***

**Numeric Code**
4402

**Symbolic Error Code**
AdExtensionAdGroupAssociationPilotNotEnabledForCustomer

**Description**
Customer is not in pilot for this ad extension type ad group association.

***

**Numeric Code**
4403

**Symbolic Error Code**
ValueTooShort

**Description**
Value is too short.

***

**Numeric Code**
4404

**Symbolic Error Code**
ValueTooLong

**Description**
Value is too long.

***

**Numeric Code**
4405

**Symbolic Error Code**
ValueOutOfRange

**Description**
Value is out of valid range.

***

**Numeric Code**
4406

**Symbolic Error Code**
ValueIsMissing

**Description**
Required value is missing.

***

**Numeric Code**
4407

**Symbolic Error Code**
InvalidValue

**Description**
Value is invalid.

***

**Numeric Code**
4408

**Symbolic Error Code**
CustomerNotEnableForNativeAdsPilot

**Description**
Customer is not enabled for the Native Ads pilot.

***

**Numeric Code**
4409

**Symbolic Error Code**
InvalidNativeBidAdjustmentValue

**Description**
NativeBidAdjustment value or flag is invalid.

***

**Numeric Code**
4410

**Symbolic Error Code**
InvalidHeader

**Description**
Header is invalid.

***

**Numeric Code**
4411

**Symbolic Error Code**
InvalidStructuredSnippetCharacter

**Description**
Structured Snippet values do not support commas or semicolons.

***

**Numeric Code**
4412

**Symbolic Error Code**
TooManyStructuredSnippetText

**Description**
Too many structured snippet texts.

***

**Numeric Code**
4413

**Symbolic Error Code**
TooFewStructuredSnippetText

**Description**
Too few structured snippet text.

***

**Numeric Code**
4415

**Symbolic Error Code**
ValueImmutable

**Description**
Value cannot be updated.

***
## 4500
***

**Numeric Code**
4500

**Symbolic Error Code**
ShoppingCampaignPilotNotEnabledForCustomer

**Description**
The customer is not part of the shopping campaign pilot program.

***

**Numeric Code**
4501

**Symbolic Error Code**
CampaignCriterionsNullOrEmpty

**Description**
The list of campaign criterion cannot be null or empty.

***

**Numeric Code**
4502

**Symbolic Error Code**
CampaignCriterionsLimitExceeded

**Description**
The list of campaign criterion is too long.

***

**Numeric Code**
4503

**Symbolic Error Code**
CampaignCriterionTypeInvalid

**Description**
The campaign criterion's type is not valid.

***

**Numeric Code**
4504

**Symbolic Error Code**
CampaignCriterionIsNull

**Description**
The campaign criterion cannot be null.

***

**Numeric Code**
4505

**Symbolic Error Code**
CampaignCriterionIdShouldBeNullOnAdd

**Description**
The campaign criterion's ID is read-only and must be null.

***

**Numeric Code**
4506

**Symbolic Error Code**
DuplicateCampaignCriterionId

**Description**
The list of campaign criterion IDs cannot contain duplicates.

***

**Numeric Code**
4507

**Symbolic Error Code**
CampaignCriterionIdInvalid

**Description**
The campaign criterion ID is not valid.

***

**Numeric Code**
4508

**Symbolic Error Code**
CampaignCriterionProductConditionInvalid

**Description**
The product condition of the campaign criterion is invalid.

***

**Numeric Code**
4509

**Symbolic Error Code**
CampaignTypeIsNotShoppingCampaign

**Description**
Campaign has to be of type Shopping for this operation.

***

**Numeric Code**
4510

**Symbolic Error Code**
CampaignCriterionCriterionIsNullOrEmpty

**Description**
The Criterion of campaign criterion cannot be null or empty.

***

**Numeric Code**
4511

**Symbolic Error Code**
CampaignCriterionTooManyConditions

**Description**
The list of product conditions for the campaign criterion is too long.

***

**Numeric Code**
4512

**Symbolic Error Code**
CampaignCriterionDuplicateCampaignId

**Description**
Duplicate campaign IDs were specified in the list of campaign criterion.

***

**Numeric Code**
4513

**Symbolic Error Code**
CampaignCriterionIdArrayNullOrEmpty

**Description**
The list of campaign criterion IDs cannot be null or empty.

***

**Numeric Code**
4514

**Symbolic Error Code**
CampaignCriterionIdsLimitExceeded

**Description**
The list of campaign criterion IDs is too long.

***

**Numeric Code**
4515

**Symbolic Error Code**
ProductConditionIsNull

**Description**
The product condition cannot be null.

***

**Numeric Code**
4516

**Symbolic Error Code**
CampaignCriterionDuplicateProductConditionOperand

**Description**
The product condition's operand is already in use for the campaign criterion.

***

**Numeric Code**
4517

**Symbolic Error Code**
CampaignCriterionAlreadyExists

**Description**
The campaign already has a campaign criterion. Only one campaign criterion is allowed per campaign.

***

**Numeric Code**
4518

**Symbolic Error Code**
CampaignServiceCampaignCriterionActionsNullOrEmpty

**Description**
The list of CampaignCriterionActions is NullOrEmpty. Please see the *ReasonCode* element of this error object for details.

***

**Numeric Code**
4519

**Symbolic Error Code**
CampaignServiceCampaignCriterionBidMultiplierValueNotSet

**Description**
The BidMultiplier is not set for Campaign Criterion.

***

**Numeric Code**
4570

**Symbolic Error Code**
CampaignServiceExpandedTextAdCombinedTitleTooLong

**Description**
The combined character limit for title part 1 and title part 2 would be exceeded.

***

**Numeric Code**
4571

**Symbolic Error Code**
CampaignServiceExpandedTextAdFinalUrlDomainTooLong

**Description**
The character limit for the domain portion of the final URL would be exceeded.

***

**Numeric Code**
4600

**Symbolic Error Code**
InvalidUrlScheme

**Description**
URL scheme is invalid.

***

**Numeric Code**
4601

**Symbolic Error Code**
TrackingTemplateTooLong

**Description**
Tracking URL template is too long.

***

**Numeric Code**
4602

**Symbolic Error Code**
MissingLandingPageUrlTag

**Description**
Landing page URL tag is missing.

***

**Numeric Code**
4603

**Symbolic Error Code**
CountExceedsLimit

**Description**
The list exceeds the maximum allowed limit.

***

**Numeric Code**
4604

**Symbolic Error Code**
InvalidCharactersInKey

**Description**
Key contains invalid characters.

***

**Numeric Code**
4605

**Symbolic Error Code**
InvalidCharactersInValue

**Description**
Value contains invalid characters.

***

**Numeric Code**
4606

**Symbolic Error Code**
InvalidTag

**Description**
Value contains invalid tag.

***

**Numeric Code**
4607

**Symbolic Error Code**
InvalidOsType

**Description**
OS type is invalid.

***

**Numeric Code**
4608

**Symbolic Error Code**
KeyTooLong

**Description**
Key is too long.

***

**Numeric Code**
4609

**Symbolic Error Code**
UrlTooLong

**Description**
URL is too long.

***

**Numeric Code**
4610

**Symbolic Error Code**
DuplicateOsTypeForAppUrl

**Description**
Duplicate OS type for app URL.

***

**Numeric Code**
4611

**Symbolic Error Code**
KeyNullOrEmpty

**Description**
Key is null or empty.

***

**Numeric Code**
4612

**Symbolic Error Code**
ValueNullOrEmpty

**Description**
Value is null or empty.

***

**Numeric Code**
4613

**Symbolic Error Code**
ParameterIsNull

**Description**
Parameter is null.

***

**Numeric Code**
4614

**Symbolic Error Code**
UpgradedUrlsPilotNotEnabledForCustomer

**Description**
Upgraded URLs is not enabled for this customer.

***

**Numeric Code**
4615

**Symbolic Error Code**
FinalUrlRequiredWhenUsingTrackingUrlTemplateOrUrlCustomParameter

**Description**
Final URL is required when using tracking URL template or custom parameter.

***

**Numeric Code**
4616

**Symbolic Error Code**
FinalUrlRequiredWhenUsingMobileFinalUrl

**Description**
Final URL is required when using mobile final URL.

***

**Numeric Code**
4617

**Symbolic Error Code**
MobileFinalUrlNotAllowedWithMobileDevicePreference

**Description**
Mobile final URL is not allowed with mobile device preference.

***

**Numeric Code**
4618

**Symbolic Error Code**
BothDestinationUrlAndFinalUrlNotAllowed

**Description**
Having both destination URL and final URL is not allowed.

***

**Numeric Code**
4619

**Symbolic Error Code**
BothDestinationUrlAndUrlCustomParameterNotAllowed

**Description**
Having both destination URL and URL custom parameter is not allowed.

***

**Numeric Code**
4620

**Symbolic Error Code**
DuplicatesInField

**Description**
Duplicate values in a field are not allowed.

***

**Numeric Code**
4621

**Symbolic Error Code**
BothDestinationUrlAndTrackingTemplateNotAllowed

**Description**
Having both destination url and tracking template is not allowed.

***

**Numeric Code**
4622

**Symbolic Error Code**
CampaignServiceFinalUrlAndMobileUrlNotAllowedForProductPartition

**Description**
Final Urls and Mobile Final Urls are not allowed in a product partition.

***

**Numeric Code**
4623

**Symbolic Error Code**
CampaignServiceTemplateAndParametersNotAllowedForProductPartitionSubdivision

**Description**
Tracking template and custom parameters cannot be added to a product partition subdivision.

***

**Numeric Code**
4700

**Symbolic Error Code**
BiddingSchemeNotEnabledForCustomer

**Description**
The customer is not enabled for this bidding scheme.

***

**Numeric Code**
4701

**Symbolic Error Code**
UnsupportedBiddingScheme

**Description**
The bidding scheme is not supported.

***

**Numeric Code**
4702

**Symbolic Error Code**
TargetCpaIsRequired

**Description**
TargetCpa is required for this bidding scheme.

***

**Numeric Code**
4703

**Symbolic Error Code**
MaxCpcExceedsMonthlyBudget

**Description**
This error code is no longer in use. Monthly budgets was last used with Bing Ads API version 10.

***

**Numeric Code**
4704

**Symbolic Error Code**
InheritFromParentBiddingSchemeNotAllowedForCampaign

**Description**
InheritFromParentBiddingScheme is not allowed to set to campaign and can only be applied in ad group and keyword entities.

***

**Numeric Code**
4705

**Symbolic Error Code**
AdGroupSupportOnlyManualAndInheritFromParentBiddingStrategy

**Description**
AdGroup supports only Manual and InheritFromParent bid strategy.

***

**Numeric Code**
4800

**Symbolic Error Code**
InvalidRemarketingListId

**Description**
The remarketing list ID is invalid.

***

**Numeric Code**
4801

**Symbolic Error Code**
RemarketingListIdsNotPassed

**Description**
Remarketing list IDs are required.

***

**Numeric Code**
4802

**Symbolic Error Code**
DuplicateRemarketingListId

**Description**
Duplicate remarketing list IDs are not allowed.

***

**Numeric Code**
4803

**Symbolic Error Code**
InvalidRemarketingListName

**Description**
The remarketing list name is invalid.

***

**Numeric Code**
4804

**Symbolic Error Code**
RemarketingListAssociationsArrayShouldNotBeNullOrEmpty

**Description**
Remarketing list associations are required.

***

**Numeric Code**
4805

**Symbolic Error Code**
RemarketingListAssociationInvalidBidAdjustment

**Description**
The remarketing list association's bid adjustment is invalid.

***

**Numeric Code**
4806

**Symbolic Error Code**
RemarketingListAssociationsArrayExceedsLimit

**Description**
The list of remarketing associations exceeds the limit.

***

**Numeric Code**
4807

**Symbolic Error Code**
RemarketingListAssociationDoesNotExist

**Description**
The remarketing list association does not exist.

***

**Numeric Code**
4808

**Symbolic Error Code**
CannotAssociateRemarketingListWithContentOnlyAdGroup

**Description**
Remarketing lists cannot be associated with content only ad groups.

***

**Numeric Code**
4809

**Symbolic Error Code**
DuplicateRemarketingListAssociation

**Description**
Duplicate remarketing list associations are not allowed.

***

**Numeric Code**
4810

**Symbolic Error Code**
RemarketingListAssociationIsNull

**Description**
The remarketing list association cannot be null.

***

**Numeric Code**
4811

**Symbolic Error Code**
RemarketingListAssociationIdIsNotNull

**Description**
The remarketing list association's Id must be null.

***

**Numeric Code**
4812

**Symbolic Error Code**
RemarketingListAssociationIdIsNull

**Description**
The remarketing list association's Id cannot be null.

***

**Numeric Code**
4813

**Symbolic Error Code**
InvalidRemarketingListAssociationStatus

**Description**
The remarketing list association status is invalid for the current operation.

***

**Numeric Code**
4814

**Symbolic Error Code**
InvalidRemarketingListRuleItem

**Description**
The remarketing list rule item is invalid.

***

**Numeric Code**
4815

**Symbolic Error Code**
TooManyRuleItemsError

**Description**
Too many rule items were specified in the remarketing list for the operation.

***

**Numeric Code**
4816

**Symbolic Error Code**
TooManyRuleItemGroupsError

**Description**
Too many rule item groups were specified in the remarketing list for the operation.

***

**Numeric Code**
4817

**Symbolic Error Code**
InvalidRemarketingListDescription

**Description**
Remarketing list description is invalid.

***

**Numeric Code**
4818

**Symbolic Error Code**
InvalidRemarketingListMembershipDuration

**Description**
Remarketing list membership duration is invalid.

***

**Numeric Code**
4819

**Symbolic Error Code**
RemarketingListParentIdDoesNotMatchScope

**Description**
Remarketing list parent id does not match the scope.

***

**Numeric Code**
4820

**Symbolic Error Code**
RemarketingListsArrayShouldNotBeNullOrEmpty

**Description**
Remarketing lists are required.

***

**Numeric Code**
4821

**Symbolic Error Code**
RemarketingListIsNull

**Description**
Remarketing list cannot be null.

***

**Numeric Code**
4822

**Symbolic Error Code**
RemarketingListIdIsNull

**Description**
Remarketing list id cannot be null.

***

**Numeric Code**
4823

**Symbolic Error Code**
RemarketingListIdIsNotNull

**Description**
Remarketing list id must be null.

***

**Numeric Code**
4824

**Symbolic Error Code**
InvalidRemarketingListParentId

**Description**
Remarketing list parent id is invalid or not specified.

***

**Numeric Code**
4825

**Symbolic Error Code**
InvalidRemarketingListScope

**Description**
Remarketing list scope is invalid or not specified.

***

**Numeric Code**
4826

**Symbolic Error Code**
InvalidRemarketingListTagId

**Description**
Remarketing list tag id is invalid or not specified.

***

**Numeric Code**
4827

**Symbolic Error Code**
InvalidRemarketingListRule

**Description**
Remarketing list rule is invalid or not specified.

***

**Numeric Code**
4828

**Symbolic Error Code**
RemarketingListsArrayExceedsLimit

**Description**
Remarketing lists array exceeds the limit size.

***

**Numeric Code**
4829

**Symbolic Error Code**
RemarketingListIdsArrayShouldNotBeNullOrEmpty

**Description**
Remarketing list ids array should not be null or empty.

***

**Numeric Code**
4830

**Symbolic Error Code**
RemarketingListIdsArrayExceedsLimit

**Description**
Remarketing list ids array exceeds the limit size.

***

**Numeric Code**
4831

**Symbolic Error Code**
DuplicateRemarketingListName

**Description**
Remarketing list name is duplicate.

***

**Numeric Code**
4832

**Symbolic Error Code**
RemarketingListCannotBeDeletedDueToExistingAssociation

**Description**
Remarketing list cannot be deleted due to existing association.

***

**Numeric Code**
4833

**Symbolic Error Code**
MaxRemarketingListsPerCustomerLimitReached

**Description**
Max audiences per customer limit is reached.

***

**Numeric Code**
4834

**Symbolic Error Code**
RemarketingListCanNotChangeScopeOnUpdate

**Description**
Remarketing list scope cannot be changed on update.

***

**Numeric Code**
4835

**Symbolic Error Code**
InvalidAudienceId

**Description**
The audience ID is invalid.

***

**Numeric Code**
4836

**Symbolic Error Code**
AudienceIdsNotPassed

**Description**
Audience IDs are required.

***

**Numeric Code**
4837

**Symbolic Error Code**
DuplicateAudienceId

**Description**
Duplicate audience IDs are not allowed.

***

**Numeric Code**
4838

**Symbolic Error Code**
InvalidAudienceName

**Description**
The audience name is invalid.

***

**Numeric Code**
4839

**Symbolic Error Code**
InvalidAudienceCriterionBidAdjustment

**Description**
The ad group audience criterion's bid adjustment is invalid.

***

**Numeric Code**
4840

**Symbolic Error Code**
CannotAssociateAudienceWithContentOnlyAdGroup

**Description**
Audiences cannot be associated with content only ad groups.

***

**Numeric Code**
4841

**Symbolic Error Code**
InvalidAudienceDescription

**Description**
Audience description is invalid.

***

**Numeric Code**
4842

**Symbolic Error Code**
InvalidAudienceMembershipDuration

**Description**
Audience membership duration is invalid.

***

**Numeric Code**
4843

**Symbolic Error Code**
AudienceParentIdDoesNotMatchScope

**Description**
Audience parent id does not match the scope.

***

**Numeric Code**
4844

**Symbolic Error Code**
AudiencesArrayShouldNotBeNullOrEmpty

**Description**
Audiences are required.

***

**Numeric Code**
4845

**Symbolic Error Code**
AudienceIsNull

**Description**
Audience cannot be null.

***

**Numeric Code**
4846

**Symbolic Error Code**
AudienceIdIsNull

**Description**
Audience id cannot be null.

***

**Numeric Code**
4847

**Symbolic Error Code**
AudienceIdIsNotNull

**Description**
Audience id must be null.

***

**Numeric Code**
4848

**Symbolic Error Code**
InvalidAudienceParentId

**Description**
Audience parent id is invalid or not specified.

***

**Numeric Code**
4849

**Symbolic Error Code**
InvalidAudienceScope

**Description**
Audience scope is invalid or not specified.

***

**Numeric Code**
4850

**Symbolic Error Code**
AudiencesArrayExceedsLimit

**Description**
Audiences array exceeds the limit size.

***

**Numeric Code**
4851

**Symbolic Error Code**
AudienceIdsArrayShouldNotBeNullOrEmpty

**Description**
Audience ids array should not be null or empty.

***

**Numeric Code**
4852

**Symbolic Error Code**
AudienceIdsArrayExceedsLimit

**Description**
Audience ids array exceeds the limit size.

***

**Numeric Code**
4853

**Symbolic Error Code**
DuplicateAudienceName

**Description**
Audience name is duplicate.

***

**Numeric Code**
4854

**Symbolic Error Code**
AudienceCannotBeDeletedDueToExistingAdGroupCriterion

**Description**
Audience cannot be deleted due to existing association.

***

**Numeric Code**
4855

**Symbolic Error Code**
AudienceCanNotChangeScopeOnUpdate

**Description**
Audience scope cannot be changed on update.

***

**Numeric Code**
4856

**Symbolic Error Code**
InMarketAudienceIsReadOnly

**Description**
In-market audience is read-only.

***

**Numeric Code**
4857

**Symbolic Error Code**
CustomAudienceCouldNotBeAdded

**Description**
Could not add custom audience.

***

**Numeric Code**
4858

**Symbolic Error Code**
MaxCustomAudiencesPerCustomerLimitReached

**Description**
Max custom audiences per customer limit is reached.

***

**Numeric Code**
4859

**Symbolic Error Code**
InvalidAudienceType

**Description**
Audience Type is invalid.

***

**Numeric Code**
4860

**Symbolic Error Code**
CustomAudienceAndInMarketAudienceCouldNotBeDeleted

> [!NOTE]
> In version 11 this error code is removed and you must use 4864, InMarketAudienceCouldNotBeDeleted instead. See the version 12 migration guide and error code documentation for more details.

**Description**
Could not delete custom audience and in-market audience.

***

**Numeric Code**
4861

**Symbolic Error Code**
AudienceIdDoNotMatchAudienceType

**Description**
Audience Id do not match audience type.

***

**Numeric Code**
4862

**Symbolic Error Code**
MaxAudienceCriterionsPerAccountLimitReached

**Description**
Max audience criterions per account limit is reached.

***

**Numeric Code**
4863

**Symbolic Error Code**
MaxRemarketingListAssociationsPerAccountLimitReached

**Description**
Max remarketing list associations per account limit is reached.

***

**Numeric Code**
4865

**Symbolic Error Code**
MaxAudiencesPerAccountLimitReached

**Description**
Max audiences per account limit is reached.

***

**Numeric Code**
4900

**Symbolic Error Code**
CampaignServiceBudgetPilotNotEnabledForCustomer

**Description**
Customer not in Shared Budget pilot.

***

**Numeric Code**
4901

**Symbolic Error Code**
CampaignServiceBudgetsNullOrEmpty

**Description**
The budget list should not be null or empty.

***

**Numeric Code**
4902

**Symbolic Error Code**
CampaignServiceBudgetIsNull

**Description**
The budget should not be null.

***

**Numeric Code**
4903

**Symbolic Error Code**
CampaignServiceBudgetIdShouldBeNullOnAdd

**Description**
The budget id is read-only and must be null.

***

**Numeric Code**
4904

**Symbolic Error Code**
CampaignServiceBudgetNameMissing

**Description**
The budget name should not be null or empty.

***

**Numeric Code**
4905

**Symbolic Error Code**
CampaignServiceBudgetNameTooLong

**Description**
The budget name is too long.

***

**Numeric Code**
4906

**Symbolic Error Code**
CampaignServiceBudgetNameInvalid

**Description**
The budget name has invalid characters.

***

**Numeric Code**
4907

**Symbolic Error Code**
CampaignServiceDuplicateBudgetName

**Description**
The budget name already exists.

***

**Numeric Code**
4908

**Symbolic Error Code**
CampaignServiceBudgetTypeCannotBeNullOnAdd

**Description**
The budget type must be specified.

***

**Numeric Code**
4909

**Symbolic Error Code**
CampaignServiceMonthlyBudgetNotAllowed

**Description**
This error code is no longer in use. Monthly budgets was last used with Bing Ads API version 10.

***

**Numeric Code**
4910

**Symbolic Error Code**
CampaignServiceBudgetAmountMissing

**Description**
The budget amount is not provided.

***

**Numeric Code**
4911

**Symbolic Error Code**
CampaignServiceBudgetAmountIsAboveLimit

**Description**
The budget amount is above the limit.

***

**Numeric Code**
4912

**Symbolic Error Code**
CampaignServiceBudgetAmountIsBelowLimit

**Description**
The budget amount is below the limit.

***

**Numeric Code**
4913

**Symbolic Error Code**
CampaignServiceBudgetBatchLimitExceeded

**Description**
The budget list exceeds the maximum batch size.

***

**Numeric Code**
4914

**Symbolic Error Code**
CampaignServiceBudgetEntityLimitExceeded

**Description**
The number of budgets for the account has been exceeded.

***

**Numeric Code**
4915

**Symbolic Error Code**
CampaignServiceDuplicateBudgetId

**Description**
The budget list contains duplicate budget ids.

***

**Numeric Code**
4916

**Symbolic Error Code**
CampaignServiceBudgetIdInvalid

**Description**
The budget id is invalid.

***

**Numeric Code**
4917

**Symbolic Error Code**
CampaignServiceCannotUpdateSharedDailyBudgetToUnsharedMonthlyBudget

**Description**
This error code is no longer in use. Monthly budgets was last used with Bing Ads API version 10.

***

**Numeric Code**
4918

**Symbolic Error Code**
CampaignServiceBudgetIsSharedWithCampaigns

**Description**
The budget is shared with at least one campaign, therefore it can't be deleted.

***
## 5000
***

**Numeric Code**
5000

**Symbolic Error Code**
DevicePreferenceIncompatibleWithAdType

**Description**
Device Preference cannot be set for an Ad of this type.

***

**Numeric Code**
5001

**Symbolic Error Code**
InvalidAdDevicePreference

**Description**
Device Preference passed in was invalid.

***

**Numeric Code**
5002

**Symbolic Error Code**
CampaignServiceProductAdPromotionalTextInvalid

**Description**
The promotional text of Product Ad is not valid.

***

**Numeric Code**
5005

**Symbolic Error Code**
CampaignServiceAppInstallAdAppPlatformNullOrEmpty

**Description**
The app platform cannot be null or empty.

***

**Numeric Code**
5006

**Symbolic Error Code**
CampaignServiceAppInstallAdAppPlatformInvalid

**Description**
The app platform is invalid.

***

**Numeric Code**
5007

**Symbolic Error Code**
CampaignServiceAppInstallAdAppStoreIdIsNullOrEmpty

**Description**
The app store ID cannot be null or empty.

***

**Numeric Code**
5008

**Symbolic Error Code**
CampaignServiceAppInstallAdAppStoreIdTooMuchText

**Description**
The app store ID is too long.

***

**Numeric Code**
5009

**Symbolic Error Code**
CampaignServiceAppInstallAdAppStoreIdInvalid

**Description**
The app store ID is invalid.

***

**Numeric Code**
5010

**Symbolic Error Code**
CampaignServiceAppInstallAdUpdateAppPlatformChanged

**Description**
The app platform can not be modified.

***

**Numeric Code**
5011

**Symbolic Error Code**
CampaignServiceAppInstallAdUpdateAppStoreIdChanged

**Description**
The app store ID can not be modified.

***

**Numeric Code**
5012

**Symbolic Error Code**
InvalidAdFormatPreference

**Description**
The ad format preference value is invalid.

***

**Numeric Code**
5013

**Symbolic Error Code**
CampaignServiceExpandedTextAdTitlePart1TooLong

**Description**
The title part1 is too long.

***

**Numeric Code**
5014

**Symbolic Error Code**
CampaignServiceExpandedTextAdTitlePart2TooLong

**Description**
The title part2 is too long.

***

**Numeric Code**
5015

**Symbolic Error Code**
CampaignServiceExpandedTextAdTitlePart1Invalid

**Description**
The title part1 is invalid.

***

**Numeric Code**
5016

**Symbolic Error Code**
CampaignServiceExpandedTextAdTitlePart2Invalid

**Description**
The title part2 is invalid.

***

**Numeric Code**
5017

**Symbolic Error Code**
CampaignServiceExpandedTextAdPath1TooLong

**Description**
The path1 is too long.

***

**Numeric Code**
5018

**Symbolic Error Code**
CampaignServiceExpandedTextAdPath2TooLong

**Description**
The path2 is too long.

***

**Numeric Code**
5019

**Symbolic Error Code**
CampaignServiceExpandedTextAdPath1Invalid

**Description**
The path1 is invalid.

***

**Numeric Code**
5020

**Symbolic Error Code**
CampaignServiceExpandedTextAdPath2Invalid

**Description**
The path2 is invalid.

***

**Numeric Code**
5021

**Symbolic Error Code**
ExpandedTextAdPath2SetWithoutPath1

**Description**
The path2 is set without path1. If you set path2, then path1 must also be set. 

***

**Numeric Code**
5022

**Symbolic Error Code**
CampaignServiceExpandedTextAdIsNotPilot

**Description**
The Expanded Text Ad pilot is not enabled for customer.

***

**Numeric Code**
5023

**Symbolic Error Code**
CampaignServiceExpandedTextAdCombinedTitleTooLong

**Description**
The combined Title 1 and Title 2 would exceed the limit.

***

**Numeric Code**
5024

**Symbolic Error Code**
CampaignServiceExpandedTextAdFinalUrlDomainTooLong

**Description**
The domain of the Final URL is too long.

***

**Numeric Code**
5025

**Symbolic Error Code**
CampaignServiceExpandedTextAdDisplayUrlDomainTooLong

**Description**
The domain of the Display URL is too long.
***

**Numeric Code**
5026

**Symbolic Error Code**
CampaignServiceExpandedTextAdFinalUrlDomainInvalid

**Description**
The domain of the Display URL is invalid.

***

**Numeric Code**
5027

**Symbolic Error Code**
CampaignServiceExpandedTextAdDisplayUrlMissing

**Description**
The domain of the Display URL is required.

***


**Numeric Code**
5028

**Symbolic Error Code**
CampaignServiceExpandedTextAdInvalidFunctionFormat

**Description**
The syntax of your function contains invalid formatting, likely caused by a missing }.

***

**Numeric Code**
5029

**Symbolic Error Code**
CampaignServiceExpandedTextAdUnknownFunction

**Description**
One or more functions are invalid or not supported.

***

**Numeric Code**
5030

**Symbolic Error Code**
CampaignServiceExpandedTextAdMissingDelimiterBetweenFunctions

**Description**
You need to have at least one character between any two functions.

***

**Numeric Code**
5031

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownInvalidDateTime

**Description**
Your countdown function contains an invalid date and/or time.

***

**Numeric Code**
5032

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownInvalidLanguageCode

**Description**
Your countdown function contains an invalid language code.

***

**Numeric Code**
5033

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownInvalidDaysBefore

**Description**
Your countdown function contains an invalid days-before value.

***

**Numeric Code**
5034

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownDaysBeforeOutOfRange

**Description**
The days-before value in your countdown function is out of range.

***

**Numeric Code**
5035

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownInvalidParameters

**Description**
A countdown function must have at least one parameter and no more than three.

***

**Numeric Code**
5036

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownPastDateTime

**Description**
Your countdown function contains a date and/or time in the past.

***

**Numeric Code**
5037

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownInvalidDefaultText

**Description**
Default value is not allowed in countdown function.

***

**Numeric Code**
5038

**Symbolic Error Code**
CampaignServiceExpandedTextAdCountdownInvalidDefaultText

**Description**
When using the *{Keyword}* dynamic text parameter, default text is required. For example *{Keyword:default}*.

***

**Numeric Code**
5100

**Symbolic Error Code**
CustomerNotEligibleForDynamicSearchAds

**Description**
The customer is not in pilot for Dynamic Search Ads.

***

**Numeric Code**
5101

**Symbolic Error Code**
DynamicSearchAdsCampaignSettingNotAllowedForUpdate

**Description**
The domain name and language settings of a Dynamic Search Ads campaign cannot be updated.

***

**Numeric Code**
5102

**Symbolic Error Code**
InvalidDynamicSearchAdsCampaignDomainName

**Description**
Domain name of Dynamic Search Ads campaign is invalid.

***

**Numeric Code**
5103

**Symbolic Error Code**
InvalidDynamicSearchAdsCampaignLanguage

**Description**
Language of Dynamic Search Ads campaign is invalid.

***

**Numeric Code**
5104

**Symbolic Error Code**
MaxCampaignWebpageCriterionsLimitExceededForCampaign

**Description**
The maximum campaign webpage criterion limit per campaign would be exceeded.

***

**Numeric Code**
5105

**Symbolic Error Code**
BiddableOrNegativeStatusCannotBeUpdated

**Description**
You cannot update a non-negative criterion to negative or vice versa.

***

**Numeric Code**
5106

**Symbolic Error Code**
DynamicSearchAdPath1TooLong

**Description**
Path 1 is over the character limit.

***

**Numeric Code**
5107

**Symbolic Error Code**
DynamicSearchAdPath2TooLong

**Description**
Path 2 is over the character limit.

***

**Numeric Code**
5108

**Symbolic Error Code**
DynamicSearchAdPath1Invalid

**Description**
Path 1 is not valid.

***

**Numeric Code**
5109

**Symbolic Error Code**
DynamicSearchAdPath2Invalid

**Description**
Path 2 is not valid.

***

**Numeric Code**
5110

**Symbolic Error Code**
DynamicSearchAdPath2SetWithoutPath1

**Description**
The path2 is set without path1. If you set path2, then path1 must also be set.

***

**Numeric Code**
5200

**Symbolic Error Code**
CampaignTypeIsNotDynamicSearchAdsCampaign

**Description**
The Campaign Type must correspond to a Dynamic Search Ads campaign.

***

**Numeric Code**
5201

**Symbolic Error Code**
WebpageCriterionParameterIsNull

**Description**
The Parameter of a webpage criterion is null or empty. 

***

**Numeric Code**
5202

**Symbolic Error Code**
WebpageCriterionNameInvalid

**Description**
The Criterion name of a webpage criterion is invalid.

***

**Numeric Code**
5203

**Symbolic Error Code**
WebpageCriterionConditionsContainDuplicateValues

**Description**
Conditions of a webpage criterion contain duplicate values.

***

**Numeric Code**
5204

**Symbolic Error Code**
TooManyWebpageCriterionConditions

**Description**
The number of criterion conditions would exceed the maximum limit.

***

**Numeric Code**
5205

**Symbolic Error Code**
WebpageCriterionConditionInvalid

**Description**
A Webpage criterion condition is invalid.

***

**Numeric Code**
5206

**Symbolic Error Code**
WebpageCriterionWebpageConditionOperandInvalid

**Description**
The operand of a webpage criterion condition is invalid.

***

**Numeric Code**
5207

**Symbolic Error Code**
WebpageCriterionWebpageConditionArgumentInvalid

**Description**
The argument of a webpage criterion condition is invalid.

***

**Numeric Code**
5208

**Symbolic Error Code**
NegativeWebpageCriterionConditionIsNullOrEmpty

**Description**
Negative webpage criterion condition is null or empty.

***

**Numeric Code**
5209

**Symbolic Error Code**
CannotUpdateCriterionForWebpageCriterion

**Description**
The webpage criterion condition cannot be updated.

***

**Numeric Code**
5210

**Symbolic Error Code**
BiddingSchemeMustInheritFromParentEntity

**Description**
The bidding scheme of a webpage criterion must inherit from the parent entity.

***

**Numeric Code**
5211

**Symbolic Error Code**
SubstitutionNotSupportedForDynamicSearchAd

**Description**
Dynamic Search Ads do not support dynamic keyword text substitution.

***

**Numeric Code**
5212

**Symbolic Error Code**
WebpageCriterionAlreadyExists

**Description**
Webpage criterion already exists.

***

**Numeric Code**
5213

**Symbolic Error Code**
InvalidUpgradedUrlsForWebpageCriterion

**Description**
Webpage criterion only support tracking template and customer parameters in Upgraded URLs. You cannot set Final URLs for a webpage criterion.

***

**Numeric Code**
5300

**Symbolic Error Code**
InvalidUetTagId

**Description**
The UET Tag ID is invalid.

***

**Numeric Code**
5301

**Symbolic Error Code**
DuplicateUetTagId

**Description**
Duplicate UET Tag IDs are not allowed.

***

**Numeric Code**
5302

**Symbolic Error Code**
DuplicateUetTagName

**Description**
Duplicate UET Tag names are not allowed.

***

**Numeric Code**
5303

**Symbolic Error Code**
UetTagNameAlreadyExists

**Description**
The UET Tag with the same name already exists.

***

**Numeric Code**
5304

**Symbolic Error Code**
UetTagIdsExceedsLimit

**Description**
The list of UET Tag IDs exceeds the limit.

***

**Numeric Code**
5305

**Symbolic Error Code**
UetTagNameNotPassed

**Description**
The UET Tag name is required.

***

**Numeric Code**
5306

**Symbolic Error Code**
InvalidUetTagName

**Description**
The UET Tag name is empty or exceeds the length limit.

***

**Numeric Code**
5307

**Symbolic Error Code**
InvalidUetTagDescription

**Description**
The UET Tag description is empty or exceeds the length limit.

***

**Numeric Code**
5308

**Symbolic Error Code**
UetTagsNotPassed

**Description**
The UET Tags are required.

***

**Numeric Code**
5309

**Symbolic Error Code**
UetTagArrayExceedsLimit

**Description**
The list of UET Tags exceeds the limit.

***

**Numeric Code**
5310

**Symbolic Error Code**
UetTagIsNull

**Description**
The UET Tag is required.

***

**Numeric Code**
5311

**Symbolic Error Code**
UetTagIdIsNotNull

**Description**
The UET Tag ID should be null.

***

**Numeric Code**
5312

**Symbolic Error Code**
UetTagIdIsNull

**Description**
The UET Tag ID is required.

***

**Numeric Code**
5313

**Symbolic Error Code**
TotalUetTagsExceedLimit

**Description**
The total UET Tag count would exceed the limit.

***

**Numeric Code**
5314

**Symbolic Error Code**
InvalidConversionGoalId

**Description**
The Conversion Goal ID is invalid.

***

**Numeric Code**
5315

**Symbolic Error Code**
DuplicateConversionGoalId

**Description**
Duplicate Conversion Goal IDs are not allowed.

***

**Numeric Code**
5316

**Symbolic Error Code**
DuplicateConversionGoalName

**Description**
Duplicate Conversion Goal names are not allowed.

***

**Numeric Code**
5317

**Symbolic Error Code**
ConversionGoalNameAlreadyExists

**Description**
The Conversion Goal with the same name already exists for the customer.

***

**Numeric Code**
5318

**Symbolic Error Code**
ConversionGoalIdArrayExceedsLimit

**Description**
The list of Conversion Goal IDs exceeds the limit for the current operation.

***

**Numeric Code**
5319

**Symbolic Error Code**
ConversionGoalNameNotPassed

**Description**
The Conversion Goal name is required.

***

**Numeric Code**
5320

**Symbolic Error Code**
InvalidConversionGoalName

**Description**
The Conversion Goal name is invalid or exceeds the length limit.

***

**Numeric Code**
5321

**Symbolic Error Code**
ConversionGoalsNotPassed

**Description**
The Conversion Goals are required.

***

**Numeric Code**
5322

**Symbolic Error Code**
ConversionGoalArrayExceedsLimit

**Description**
The list of Conversion Goals exceeds the limit.

***

**Numeric Code**
5323

**Symbolic Error Code**
ConversionGoalIsNull

**Description**
The Conversion Goal is required.

***

**Numeric Code**
5324

**Symbolic Error Code**
ConversionGoalIdIsNotNull

**Description**
The Conversion Goal ID must be null.

***

**Numeric Code**
5325

**Symbolic Error Code**
ConversionGoalIdIsNull

**Description**
The Conversion Goal ID is required.

***

**Numeric Code**
5326

**Symbolic Error Code**
TotalConversionGoalsExceedAccountLimit

**Description**
The total Conversion Goal count would exceed the account level limit.

***

**Numeric Code**
5327

**Symbolic Error Code**
TotalConversionGoalsExceedCustomerLimit

**Description**
The total Conversion Goal count would exceed the customer level limit.

***

**Numeric Code**
5328

**Symbolic Error Code**
InvalidConversionGoalStatus

**Description**
The Conversion Goal status is invalid.

***

**Numeric Code**
5329

**Symbolic Error Code**
ConversionGoalTypesNotPassed

**Description**
The Conversion Goal types are required.

***

**Numeric Code**
5330

**Symbolic Error Code**
UetTagIdsNotPassed

**Description**
The UET Tag IDs are required.

***

**Numeric Code**
5331

**Symbolic Error Code**
ConversionGoalTypeNotMatched

**Description**
The Conversion Goal type should be matched to the goal entity.

***

**Numeric Code**
5332

**Symbolic Error Code**
InvalidConversionGoalRevenueType

**Description**
The Conversion Goal revenue type is invalid.

***

**Numeric Code**
5333

**Symbolic Error Code**
InvalidConversionGoalRevenueValue

**Description**
The Conversion Goal revenue value is invalid.

***

**Numeric Code**
5334

**Symbolic Error Code**
UrlGoalUrlExpressionNotPassed

**Description**
The Url Expression for Url Goal is required.

***

**Numeric Code**
5335

**Symbolic Error Code**
AppInstallGoalStoreIdNotPassed

**Description**
The Store ID for App Install Goal is required.

***

**Numeric Code**
5336

**Symbolic Error Code**
EventGoalExpressionWithOperatorNotPassed

**Description**
At least one expression and operator pair is required for an Event Goal.

***

**Numeric Code**
5337

**Symbolic Error Code**
InvalidConversionGoalConversionWindow

**Description**
The Conversion Window for Conversion Goal is invalid.

***

**Numeric Code**
5338

**Symbolic Error Code**
InvalidDurationGoalDurationTime

**Description**
The Duration Time for Duration Goal is invalid.

***

**Numeric Code**
5339

**Symbolic Error Code**
InvalidMinimumPagesViewedForGoal

**Description**
The Minimum Pages Viewed is invalid for the goal.

***

**Numeric Code**
5340

**Symbolic Error Code**
InvalidAppInstallGoalAppPlatform

**Description**
The App Platform for App Install Goal is invalid.

***

**Numeric Code**
5341

**Symbolic Error Code**
InvalidUrlGoalUrlExpression

**Description**
The Url Expression for Url Goal is empty or exceeds the length limit.

***

**Numeric Code**
5342

**Symbolic Error Code**
InvalidEventGoalCategoryExpression

**Description**
The Category Expression for Event Goal is empty or exceeds the length limit.

***

**Numeric Code**
5343

**Symbolic Error Code**
InvalidEventGoalActionExpression

**Description**
The Action Expression for Event Goal is empty or exceeds the length limit.

***

**Numeric Code**
5344

**Symbolic Error Code**
InvalidEventGoalLabelExpression

**Description**
The Label Expression for Event Goal is empty or exceeds the length limit.

***

**Numeric Code**
5345

**Symbolic Error Code**
InvalidEventGoalValue

**Description**
The Value for Event Goal is invalid.

***

**Numeric Code**
5346

**Symbolic Error Code**
InvalidAppInstallGoalStoreId

**Description**
The Store ID for App Install Goal is invalid.

***

**Numeric Code**
5347

**Symbolic Error Code**
ConversionGoalTypesDoNotMatchExistingValue

**Description**
The requested conversion goal types do not match the existing conversion goal type.

***
**Numeric Code**
5348

**Symbolic Error Code**
InvalidAppInstallGoalScope

**Description**
The App Install Goal should scope to the customer.

***

**Numeric Code**
5349

**Symbolic Error Code**
InvalidAppInstallGoalCountType

**Description**
The count type for App Install Goal should be All.

***

**Numeric Code**
5350

**Symbolic Error Code**
CampaignLanguagesNotEnabledForCustomer

**Description**
The customer is not enabled for campaign languages.

***

**Numeric Code**
5351

**Symbolic Error Code**
InvalidGoalCurrencyCode

**Description**
The currency code of the goal is invalid.

***

**Numeric Code**
5352

**Symbolic Error Code**
GoalCurrencyCodeNotSupported

**Description**
The currency code is not supported for this goal type.

***

**Numeric Code**
5353

**Symbolic Error Code**
AllCampaignLanguagesCannotBeRemoved

**Description**
All campaign languages cannot be removed.

***

**Numeric Code**
5354

**Symbolic Error Code**
CampaignLanguageSpecifiedMoreThanOnce

**Description**
Campaign language specified more than once.

***

**Numeric Code**
5400

**Symbolic Error Code**
CampaignServiceLabelsListIsNullOrEmpty

**Description**
You must include one or more labels.

***

**Numeric Code**
5401

**Symbolic Error Code**
CampaignServiceLabelsEntityLimitExceeded

**Description**
You cannot add any more labels to the account.

***

**Numeric Code**
5402

**Symbolic Error Code**
CampaignServiceLabelIsNull

**Description**
The label is required.

***

**Numeric Code**
5404

**Symbolic Error Code**
CampaignServiceDuplicateLabelId

**Description**
Duplicate label identifiers cannot be included in the same request.

***

**Numeric Code**
5405

**Symbolic Error Code**
CampaignServiceLabelIdInvalid

**Description**
The label identifier is invalid.

***

**Numeric Code**
5406

**Symbolic Error Code**
CampaignServiceLabelNameInvalid

**Description**
The label name is invalid.

***

**Numeric Code**
5407

**Symbolic Error Code**
CampaignServiceLabelNameLengthExceeded

**Description**
The length of the label name is too long.

***

**Numeric Code**
5408

**Symbolic Error Code**
CampaignServiceLabelNameDuplicate

**Description**
Duplicate label names are not allowed in the same account.

***

**Numeric Code**
5409

**Symbolic Error Code**
CampaignServiceLabelDescriptionLengthExceeded

**Description**
The length of the label description is too long.

***

**Numeric Code**
5410

**Symbolic Error Code**
CampaignServiceLabelColorCodeInvalid

**Description**
The label color code is invalid.

***

**Numeric Code**
5411

**Symbolic Error Code**
CampaignServiceLabelDescriptionInvalid

**Description**
The label description is invalid.

***

**Numeric Code**
5412

**Symbolic Error Code**
CampaignServiceLabelPilotNotEnabledForCustomer

**Description**
The customer is not enabled for the labels feature.

***

**Numeric Code**
5413

**Symbolic Error Code**
CampaignServiceLabelAssociationListIsNullOrEmpty

**Description**
You must include one or more label associations.

***

**Numeric Code**
5414

**Symbolic Error Code**
CampaignServiceLabelAssociationsBatchLimitExceeded

**Description**
The maximum number of label associations per request is exceeded.

***

**Numeric Code**
5415

**Symbolic Error Code**
CampaignServiceLabelAssociationIsNull

**Description**
The label association is required.

***

**Numeric Code**
5416

**Symbolic Error Code**
CampaignServiceDuplicateLabelAssociation

**Description**
Duplicate label associations are not allowed.

***

**Numeric Code**
5417

**Symbolic Error Code**
CampaignServiceLabelAssociationsPerEntityLimitExceeded

**Description**
You cannot associate any more labels with the entity.

***

**Numeric Code**
5418

**Symbolic Error Code**
CampaignServiceLabelAssociationDoesNotExist

**Description**
The label association does not exist.

***

**Numeric Code**
5419

**Symbolic Error Code**
CampaignServiceLabelCampaignAssociationsAccountLimitExceeded

**Description**
The limit of label and campaign associations for the account would be exceeded.

***

**Numeric Code**
5420

**Symbolic Error Code**
CampaignServiceLabelAdGroupAssociationsAccountLimitExceeded

**Description**
The limit of label and ad group associations for the account would be exceeded.

***

**Numeric Code**
5421

**Symbolic Error Code**
CampaignServiceLabelAdAssociationsAccountLimitExceeded

**Description**
The limit of label and ad associations for the account would be exceeded.

***

**Numeric Code**
5422

**Symbolic Error Code**
CampaignServiceLabelKeywordAssociationsAccountLimitExceeded

**Description**
The limit of label and keyword associations for the account would be exceeded.

***

**Numeric Code**
5423

**Symbolic Error Code**
CampaignServiceLabelBatchLimitExceeded

**Description**
The maximum number of labels per request is exceeded.

***

**Numeric Code**
5424

**Symbolic Error Code**
CampaignServiceLabelAssociationEntityTypeInvalid

**Description**
Labels cannot be associated with this entity type.

***

**Numeric Code**
5425

**Symbolic Error Code**
CampaignServiceLabelAssociationEntityIdInvalid

**Description**
The label association contains an invalid entity ID.

***

**Numeric Code**
5426

**Symbolic Error Code**
CampaignServiceLabelIdsBatchLimitExceeded 

**Description**
The maximum number of label ids per request is exceeded.

***
## 5500
***

**Numeric Code**
5500

**Symbolic Error Code**
DuplicateHeaders

**Description**
Price tables rows of a price ad extension cannot contain duplicate header values.

***

**Numeric Code**
5501

**Symbolic Error Code**
TooFewPriceTableRows

**Description**
Price Ad Extension must have at least 3 price table rows.

***

**Numeric Code**
5502

**Symbolic Error Code**
NegativePrice

**Description**
Cannot set negative price amount in price table row.

***

**Numeric Code**
5503

**Symbolic Error Code**
CurrencyCodeNotSupported

**Description**
The currency is not supported.

***

**Numeric Code**
5600

**Symbolic Error Code**
OfflineConversionsNullOrEmpty

**Description**
The list of offline conversions cannot be null or empty.

***

**Numeric Code**
5601

**Symbolic Error Code**
OfflineConversionsLimitExceeded

**Description**
The list of offline conversions exceeds the limit.

***

**Numeric Code**
5602

**Symbolic Error Code**
OfflineConversionIsNull

**Description**
The offline conversion cannot be null.

***

**Numeric Code**
5603

**Symbolic Error Code**
OfflineConversionMicrosoftClickIdNullOrEmpty

**Description**
The Microsoft Click Id of offline conversion cannot be null or empty.

***

**Numeric Code**
5604

**Symbolic Error Code**
OfflineConversionMicrosoftClickIdInvalid

**Description**
The Microsoft Click Id of the offline conversion is invalid.

***

**Numeric Code**
5605

**Symbolic Error Code**
OfflineConversionNameNullOrEmpty

**Description**
The conversion name of offline conversion cannot be null or empty.

***

**Numeric Code**
5606

**Symbolic Error Code**
OfflineConversionNameInvalid

**Description**
The conversion name do not match an existing offline conversion goal.

***

**Numeric Code**
5607

**Symbolic Error Code**
OfflineConversionTimeInvalid

**Description**
The conversion time of offline conversion is invalid.

***

**Numeric Code**
5608

**Symbolic Error Code**
OfflineConversionTimeNullOrEmpty

**Description**
The conversion time of offline conversion cannot be null or empty .

***

**Numeric Code**
5609

**Symbolic Error Code**
OfflineConversionTimeOutOfWindow

**Description**
The conversion time is out of the conversion window.

***

**Numeric Code**
5610

**Symbolic Error Code**
OfflineConversionValueInvalid

**Description**
The conversion value of offline conversion is invalid.

***

**Numeric Code**
5611

**Symbolic Error Code**
OfflineConversionCurrencyCodeInvalid

**Description**
The currency code of offline conversion is invalid.

***

**Numeric Code**
5612

**Symbolic Error Code**
OfflineConversionsApplyFailed

**Description**
Failed to send offline conversions to internal server.

***

**Numeric Code**
5613

**Symbolic Error Code**
OfflineConversionPilotNotEnabledForCustomer

**Description**
The customer is not enabled for the offline conversion feature.

***

**Numeric Code**
5614

**Symbolic Error Code**
FutureConversionTimeCannotBeSet

**Description**
A future conversion time cannot be set.

***

**Numeric Code**
5615

**Symbolic Error Code**
OfflineConversionNotAcceptedForGoal

**Description**
Offline conversions cannot be accepted for the conversion goal at this time. You must wait 2 hours after the goal was created before uploading offline conversions.

***

**Numeric Code**
5616

**Symbolic Error Code**
ConversionTimeEarlierThanClickTime

**Description**
The conversion time must be later than the click time.

***

**Numeric Code**
5617

**Symbolic Error Code**
ClickIdDateTimeOutsideGoalConversionWindow

**Description**
The date and time for the click ID is outside the conversion window for this goal.

