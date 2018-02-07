---
title: DownloadEntity Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the entities that may be downloaded in bulk.
---
# DownloadEntity Value Set - Bulk
Defines the entities that may be downloaded in bulk.

For more information, see [Bulk File Schema](../bulk-service/bulk-file-schema.md).

## Syntax
```xml
<xs:simpleType name="DownloadEntity" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Campaigns">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroups">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Ads">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Keywords">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeKeywords">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">5</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeKeywords">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">6</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignTargetCriterions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">7</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupTargetCriterions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">8</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeSites">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">9</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeSites">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">10</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignSiteLinksAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">11</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignLocationAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">12</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignCallAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">13</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupSiteLinksAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">14</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="LocationAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">15</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CallAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SiteLinksAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">17</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="NegativeKeywordLists">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">18</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SharedNegativeKeywords">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">19</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeKeywordListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">20</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">21</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">22</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">23</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">24</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupAppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">25</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignAppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">26</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="PriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">27</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">28</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeDynamicSearchAdTargets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">29</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupProductPartitions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">30</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignProductScopes">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">31</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">32</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">33</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">34</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignCalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">35</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupCalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">36</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Sitelink2AdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">37</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignSitelink2AdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">38</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupSitelink2AdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">39</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ActionLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">40</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignActionLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">41</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupActionLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">42</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="StructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">43</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignStructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">44</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupStructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">45</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="RemarketingLists">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">46</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">47</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Budgets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">48</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="TextAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">49</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ProductAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">50</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AppInstallAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">51</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ExpandedTextAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">52</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="DynamicSearchAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">53</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupDynamicSearchAdTargets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">54</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeDynamicSearchAdTargets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">55</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignPriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">56</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupPriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">57</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Labels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">58</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">59</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">60</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="TextAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">61</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="KeywordLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">62</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">63</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CustomAudiences">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupCustomAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">65</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeCustomAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">66</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="InMarketAudiences">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">67</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupInMarketAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">68</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeInMarketAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">69</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Audiences">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">70</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">71</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">72</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ProductAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">73</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AppInstallAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">74</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ExpandedTextAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">75</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="DynamicSearchAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">76</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountLocationAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">77</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">78</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountAppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">79</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountPriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">80</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">81</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountCalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">82</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountSitelink2AdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">83</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountActionLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">84</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountStructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">85</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="accountactionlinkadextensions"></a>AccountActionLinkAdExtensions|Reserved for future use.|
|<a name="accountappadextensions"></a>AccountAppAdExtensions|Include [Account App Ad Extension](../bulk-service/account-app-ad-extension.md) records in the download that each represent the association relationship between an account and an app ad extension. For [App Ad Extension](../bulk-service/app-ad-extension.md) records, you should include the AppAdExtensions value in the download request.|
|<a name="accountcalloutadextensions"></a>AccountCalloutAdExtensions|Include [Account Callout Ad Extension](../bulk-service/account-callout-ad-extension.md) records in the download that represents the association relationship between an account and a callout ad extension. For [Callout Ad Extension](../bulk-service/callout-ad-extension.md) records, you should include the CalloutAdExtensions value in the download request.|
|<a name="accountimageadextensions"></a>AccountImageAdExtensions|Include [Account Image Ad Extension](../bulk-service/account-image-ad-extension.md) records in the download that represents the association relationship between an account and an image ad extension. For [Image Ad Extension](../bulk-service/image-ad-extension.md) records, you should include the ImageAdExtensions value in the download request.|
|<a name="accountlocationadextensions"></a>AccountLocationAdExtensions|Include [Account Location Ad Extension](../bulk-service/account-location-ad-extension.md) records in the download that represents the association relationship between an account and a location ad extension. For [Location Ad Extension](../bulk-service/location-ad-extension.md) records, you should include the LocationAdExtensions value in the download request.|
|<a name="accountpriceadextensions"></a>AccountPriceAdExtensions|Include [Account Price Ad Extension](../bulk-service/account-price-ad-extension.md) records in the download that represents the association relationship between an account and a price ad extension. For [Price Ad Extension](../bulk-service/price-ad-extension.md) records, you should include the PriceAdExtensions value in the download request.|
|<a name="accountreviewadextensions"></a>AccountReviewAdExtensions|Include [Account Review Ad Extension](../bulk-service/account-review-ad-extension.md) records in the download that each represent the association relationship between an account and a review ad extension. For [Review Ad Extension](../bulk-service/review-ad-extension.md) records, you should include the ReviewAdExtensions value in the download request.|
|<a name="accountsitelink2adextensions"></a>AccountSitelink2AdExtensions|Include [Account Sitelink2 Ad Extension](../bulk-service/account-sitelink2-ad-extension.md) records in the download that represents the association relationship between an account and a sitelink2 ad extension. For [Sitelink2 Ad Extension](../bulk-service/sitelink2-ad-extension.md) records, you should include the Sitelink2AdExtensions value in the download request.|
|<a name="accountstructuredsnippetadextensions"></a>AccountStructuredSnippetAdExtensions|Include [Account Structured Snippet Ad Extension](../bulk-service/account-structured-snippet-ad-extension.md) records in the download that represents the association relationship between an account and a structured snippet ad extension. For [Structured Snippet Ad Extension](../bulk-service/structured-snippet-ad-extension.md) records, you should include the StructuredSnippetAdExtensions value in the download request.|
|<a name="actionlinkadextensions"></a>ActionLinkAdExtensions|Reserved for future use.|
|<a name="adgroupactionlinkadextensions"></a>AdGroupActionLinkAdExtensions|Reserved for future use.|
|<a name="adgroupappadextensions"></a>AdGroupAppAdExtensions|Include [Ad Group App Ad Extension](../bulk-service/ad-group-app-ad-extension.md) records in the download that each represent the association relationship between an ad group and an app ad extension. For [App Ad Extension](../bulk-service/app-ad-extension.md) records, you should include the AppAdExtensions value in the download request.|
|<a name="adgroupaudienceassociations"></a>AdGroupAudienceAssociations|Include [Ad Group Custom Audience Association](../bulk-service/ad-group-custom-audience-association.md), [Ad Group In Market Audience Association](../bulk-service/ad-group-in-market-audience-association.md), and [Ad Group Remarketing List Association](../bulk-service/ad-group-remarketing-list-association.md) records in the download data.<br/><br/> To get audience associations by type instead of requesting all types of audience associations, you can include one or more of the AdGroupCustomAudienceAssociations, AdGroupInMarketAudienceAssociations, and AdGroupRemarketingListAssociations values in the download request.|
|<a name="adgroupcalloutadextensions"></a>AdGroupCalloutAdExtensions|Include [Ad Group Callout Ad Extension](../bulk-service/ad-group-callout-ad-extension.md) records in the download that each represent the association relationship between an ad group and a callout ad extension. For [Callout Ad Extension](../bulk-service/callout-ad-extension.md) records, you should include the CalloutAdExtensions value in the download request.|
|<a name="adgroupcustomaudienceassociations"></a>AdGroupCustomAudienceAssociations|Include [Ad Group Custom Audience Association](../bulk-service/ad-group-custom-audience-association.md) records in the download that each represent the association relationship between an ad group and a custom audience. For [Custom Audience](../bulk-service/custom-audience.md) records, you should include the CustomAudiences value in the download request.|
|<a name="adgroupdynamicsearchadtargets"></a>AdGroupDynamicSearchAdTargets|Include [Ad Group Dynamic Search Ad Target](../bulk-service/ad-group-dynamic-search-ad-target.md) records in the download data.|
|<a name="adgroupimageadextensions"></a>AdGroupImageAdExtensions|Include [Ad Group Image Ad Extension](../bulk-service/ad-group-image-ad-extension.md) records in the download that each represent the association relationship between an ad group and an image ad extension. For [Image Ad Extension](../bulk-service/callout-ad-extension.md) records, you should include the ImageAdExtensions value in the download request.|
|<a name="adgroupinmarketaudienceassociations"></a>AdGroupInMarketAudienceAssociations|Include [Ad Group In Market Audience Association](../bulk-service/ad-group-in-market-audience-association.md) records in the download that each represent the association relationship between an ad group and an in-market audience. For [In Market Audience](../bulk-service/in-market-audience.md) records, you should include the InMarketAudiences value in the download request.|
|<a name="adgrouplabels"></a>AdGroupLabels|Include [Ad Group Label](../bulk-service/ad-group-label.md) records in the download that each represent a label applied to an ad group. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="adgroupnegativeaudienceassociations"></a>AdGroupNegativeAudienceAssociations|Include [Ad Group Negative Custom Audience Association](../bulk-service/ad-group-negative-custom-audience-association.md), [Ad Group Negative In Market Audience Association](../bulk-service/ad-group-negative-in-market-audience-association.md), and [Ad Group Negative Remarketing List Association](../bulk-service/ad-group-negative-remarketing-list-association.md) records in the download data.<br/><br/> To get negative audience associations by type instead of requesting all types of negative audience associations, you can include one or more of the AdGroupNegativeCustomAudienceAssociations, AdGroupInMarketAudienceNegativeAssociations, and AdGroupNegativeRemarketingListAssociations values in the download request.|
|<a name="adgroupnegativecustomaudienceassociations"></a>AdGroupNegativeCustomAudienceAssociations|Include [Ad Group Negative Custom Audience Association](../bulk-service/ad-group-negative-custom-audience-association.md) records in the download that each represent the association relationship between an ad group and a custom audience exclusion. For [Custom Audience](../bulk-service/custom-audience.md) records, you should include the CustomAudiences value in the download request.|
|<a name="adgroupnegativedynamicsearchadtargets"></a>AdGroupNegativeDynamicSearchAdTargets|Include [Ad Group Negative Dynamic Search Ad Target](../bulk-service/ad-group-negative-dynamic-search-ad-target.md) records in the download data.|
|<a name="adgroupnegativeinmarketaudienceassociations"></a>AdGroupNegativeInMarketAudienceAssociations|Include [Ad Group Negative In Market Audience Association](../bulk-service/ad-group-negative-in-market-audience-association.md) records in the download that each represent the association relationship between an ad group and an in-market audience exclusion. For [In Market Audience](../bulk-service/in-market-audience.md) records, you should include the InMarketAudiences value in the download request.|
|<a name="adgroupnegativekeywords"></a>AdGroupNegativeKeywords|Include [Ad Group Negative Keyword](../bulk-service/ad-group-negative-keyword.md) records in the download data.|
|<a name="adgroupnegativeremarketinglistassociations"></a>AdGroupNegativeRemarketingListAssociations|Include [Ad Group Negative Remarketing List Association](../bulk-service/ad-group-negative-remarketing-list-association.md) records in the download that each represent the association relationship between an ad group and a remarketing list exclusion. For [Remarketing List](../bulk-service/remarketing-list.md) records, you should include the RemarketingLists value in the download request.|
|<a name="adgroupnegativesites"></a>AdGroupNegativeSites|Include [Ad Group Negative Site](../bulk-service/ad-group-negative-site.md) records in the download data.|
|<a name="adgrouppriceadextensions"></a>AdGroupPriceAdExtensions|Include [Ad Group Price Ad Extension](../bulk-service/ad-group-price-ad-extension.md) records in the download that each represent the association relationship between an ad group and a price ad extension. For [Price Ad Extension](../bulk-service/price-ad-extension.md) records, you should include the PriceAdExtensions value in the download request.|
|<a name="adgroupproductpartitions"></a>AdGroupProductPartitions|Include [Ad Group Product Partition](../bulk-service/ad-group-product-partition.md) records in the download data.|
|<a name="adgroupremarketinglistassociations"></a>AdGroupRemarketingListAssociations|Include [Ad Group Remarketing List Association](../bulk-service/ad-group-remarketing-list-association.md) records in the download that each represent the association relationship between an ad group and a remarketing list. For [Remarketing List](../bulk-service/remarketing-list.md) records, you should include the RemarketingLists value in the download request.|
|<a name="adgroupreviewadextensions"></a>AdGroupReviewAdExtensions|Include [Ad Group Review Ad Extension](../bulk-service/ad-group-review-ad-extension.md) records in the download that each represent the association relationship between an ad group and a review ad extension. For [Review Ad Extension](../bulk-service/review-ad-extension.md) records, you should include the ReviewAdExtensions value in the download request.|
|<a name="adgroups"></a>AdGroups|Include [Ad Group](../bulk-service/ad-group.md) records in the download data.|
|<a name="adgroupsitelink2adextensions"></a>AdGroupSitelink2AdExtensions|Include [Ad Group Sitelink2 Ad Extension](../bulk-service/ad-group-sitelink2-ad-extension.md) records in the download that each represent the association relationship between an ad group and a sitelink2 ad extension. For [Sitelink2 Ad Extension](../bulk-service/sitelink2-ad-extension.md) records, you should include the Sitelink2AdExtensions value in the download request.|
|<a name="adgroupsitelinksadextensions"></a>AdGroupSiteLinksAdExtensions|This value is deprecated in favor of AdGroupSitelink2AdExtensions.|
|<a name="adgroupstructuredsnippetadextensions"></a>AdGroupStructuredSnippetAdExtensions|Include [Ad Group Structured Snippet Ad Extension](../bulk-service/ad-group-structured-snippet-ad-extension.md) records in the download that each represent the association relationship between an ad group and a structured snippet ad extension. For [Structured Snippet Ad Extension](../bulk-service/structured-snippet-ad-extension.md) records, you should include the StructuredSnippetAdExtensions value in the download request.|
|<a name="adgrouptargetcriterions"></a>AdGroupTargetCriterions|Include [Ad Group Age Criterion](../bulk-service/ad-group-age-criterion.md), [Ad Group DayTime Criterion](../bulk-service/ad-group-daytime-criterion.md), [Ad Group DeviceOS Criterion](../bulk-service/ad-group-deviceos-criterion.md), [Ad Group Gender Criterion](../bulk-service/ad-group-gender-criterion.md), [Ad Group Location Criterion](../bulk-service/ad-group-location-criterion.md), [Ad Group Location Intent Criterion](../bulk-service/ad-group-location-intent-criterion.md), [Ad Group Negative Location Criterion](../bulk-service/ad-group-negative-location-criterion.md), and [Ad Group Radius Criterion](../bulk-service/ad-group-radius-criterion.md) records in the download data.|
|<a name="ads"></a>Ads|Include [App Install Ad](../bulk-service/app-install-ad.md), [Dynamic Search Ad](../bulk-service/dynamic-search-ad.md), [Expanded Text Ad](../bulk-service/expanded-text-ad.md), [Product Ad](../bulk-service/product-ad.md), and [Text Ad](../bulk-service/text-ad.md) records in the download data.<br/><br/> To get ads by type instead of requesting all types of ads, you can include one or more of the AppInstallAds, DynamicSearchAds, ExpandedTextAds, ProductAds, and TextAds values in the download request.|
|<a name="appadextensions"></a>AppAdExtensions|Include [App Ad Extension](../bulk-service/app-ad-extension.md) records in the download data.<br/><br/> To get all app ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the app ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="appinstalladlabels"></a>AppInstallAdLabels|Include [App Install Ad Label](../bulk-service/app-install-ad-label.md) records in the download that each represent a label applied to an app install ad. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="appinstallads"></a>AppInstallAds|Include [App Install Ad](../bulk-service/app-install-ad.md) records in the download data.<br/><br/> To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="audiences"></a>Audiences|Include [Custom Audience](../bulk-service/custom-audience.md), [In Market Audience](../bulk-service/in-market-audience.md), and [Remarketing List](../bulk-service/remarketing-list.md) records in the download data.<br/><br/> The [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operations return the same set of audiences for the current authenticated user. All audiences that have Scope set to Customer are included. The audiences that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if an audience is in account scope for an account that the user cannot access, then it is excluded from the download results.<br/><br/> To get audiences by type instead of requesting all types of audiences, you can include one or more of the CustomAudiences, InMarketAudiences, and RemarketingLists values in the download request.|
|<a name="budgets"></a>Budgets|Include [Budget](../bulk-service/budget.md) records in the download data.|
|<a name="calladextensions"></a>CallAdExtensions|Include [Call Ad Extension](../bulk-service/call-ad-extension.md) records in the download data.<br/><br/> To get all call ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the call ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="calloutadextensions"></a>CalloutAdExtensions|Include [Callout Ad Extension](../bulk-service/callout-ad-extension.md) records in the download data.<br/><br/> To get all callout ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the callout ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="campaignactionlinkadextensions"></a>CampaignActionLinkAdExtensions|Reserved for future use.|
|<a name="campaignappadextensions"></a>CampaignAppAdExtensions|Include [Campaign App Ad Extension](../bulk-service/campaign-app-ad-extension.md) records in the download that each represent the association relationship between a campaign and an app ad extension. For [App Ad Extension](../bulk-service/app-ad-extension.md) records, you should include the AppAdExtensions value in the download request.|
|<a name="campaigncalladextensions"></a>CampaignCallAdExtensions|Include [Campaign Call Ad Extension](../bulk-service/campaign-call-ad-extension.md) records in the download that represents the association relationship between a campaign and a call ad extension. For [Call Ad Extension](../bulk-service/call-ad-extension.md) records, you should include the CallAdExtensions value in the download request.|
|<a name="campaigncalloutadextensions"></a>CampaignCalloutAdExtensions|Include [Campaign Callout Ad Extension](../bulk-service/campaign-callout-ad-extension.md) records in the download that represents the association relationship between a campaign and a callout ad extension. For [Callout Ad Extension](../bulk-service/callout-ad-extension.md) records, you should include the CalloutAdExtensions value in the download request.|
|<a name="campaignimageadextensions"></a>CampaignImageAdExtensions|Include [Campaign Image Ad Extension](../bulk-service/campaign-image-ad-extension.md) records in the download that represents the association relationship between a campaign and an image ad extension. For [Image Ad Extension](../bulk-service/image-ad-extension.md) records, you should include the ImageAdExtensions value in the download request.|
|<a name="campaignlabels"></a>CampaignLabels|Include [Campaign Label](../bulk-service/campaign-label.md) records in the download that each represent a label applied to a campaign. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="campaignlocationadextensions"></a>CampaignLocationAdExtensions|Include [Campaign Location Ad Extension](../bulk-service/campaign-location-ad-extension.md) records in the download that represents the association relationship between a campaign and a location ad extension. For [Location Ad Extension](../bulk-service/location-ad-extension.md) records, you should include the LocationAdExtensions value in the download request.|
|<a name="campaignnegativedynamicsearchadtargets"></a>CampaignNegativeDynamicSearchAdTargets|Include [Campaign Negative Dynamic Search Ad Target](../bulk-service/campaign-negative-dynamic-search-ad-target.md) records in the download data.|
|<a name="campaignnegativekeywordlistassociations"></a>CampaignNegativeKeywordListAssociations|Include [Campaign Negative Keyword List Association](../bulk-service/campaign-negative-keyword-list-association.md) records in the download that represents the association relationship between a campaign and a negative keyword list. For [Negative Keyword List](../bulk-service/negative-keyword-list.md) records, you should include the NegativeKeywordLists value in the download request.|
|<a name="campaignnegativekeywords"></a>CampaignNegativeKeywords|Include [Campaign Negative Keyword](../bulk-service/campaign-negative-keyword.md) records in the download data.|
|<a name="campaignnegativesites"></a>CampaignNegativeSites|Include [Campaign Negative Site](../bulk-service/campaign-negative-site.md) records in the download data.|
|<a name="campaignpriceadextensions"></a>CampaignPriceAdExtensions|Include [Campaign Price Ad Extension](../bulk-service/campaign-price-ad-extension.md) records in the download that represents the association relationship between a campaign and a price ad extension. For [Price Ad Extension](../bulk-service/price-ad-extension.md) records, you should include the PriceAdExtensions value in the download request.|
|<a name="campaignproductscopes"></a>CampaignProductScopes|Include [Campaign Product Scope](../bulk-service/campaign-product-scope.md) records in the download data.|
|<a name="campaignreviewadextensions"></a>CampaignReviewAdExtensions|Include [Campaign Review Ad Extension](../bulk-service/campaign-review-ad-extension.md) records in the download that each represent the association relationship between a campaign and a review ad extension. For [Review Ad Extension](../bulk-service/review-ad-extension.md) records, you should include the ReviewAdExtensions value in the download request.|
|<a name="campaigns"></a>Campaigns|Include [Campaign](../bulk-service/campaign.md) records in the download data.|
|<a name="campaignsitelink2adextensions"></a>CampaignSitelink2AdExtensions|Include [Campaign Sitelink2 Ad Extension](../bulk-service/campaign-sitelink2-ad-extension.md) records in the download that represents the association relationship between a campaign and a sitelink2 ad extension. For [Sitelink2 Ad Extension](../bulk-service/sitelink2-ad-extension.md) records, you should include the Sitelink2AdExtensions value in the download request.|
|<a name="campaignsitelinksadextensions"></a>CampaignSiteLinksAdExtensions|This value is deprecated in favor of CampaignSitelink2AdExtensions.|
|<a name="campaignstructuredsnippetadextensions"></a>CampaignStructuredSnippetAdExtensions|Include [Campaign Structured Snippet Ad Extension](../bulk-service/campaign-structured-snippet-ad-extension.md) records in the download that represents the association relationship between a campaign and a structured snippet ad extension. For [Structured Snippet Ad Extension](../bulk-service/structured-snippet-ad-extension.md) records, you should include the StructuredSnippetAdExtensions value in the download request.|
|<a name="campaigntargetcriterions"></a>CampaignTargetCriterions|Include [Campaign Age Criterion](../bulk-service/campaign-age-criterion.md), [Campaign DayTime Criterion](../bulk-service/campaign-daytime-criterion.md), [Campaign DeviceOS Criterion](../bulk-service/campaign-deviceos-criterion.md), [Campaign Gender Criterion](../bulk-service/campaign-gender-criterion.md), [Campaign Location Criterion](../bulk-service/campaign-location-criterion.md), [Campaign Location Intent Criterion](../bulk-service/campaign-location-intent-criterion.md), [Campaign Negative Location Criterion](../bulk-service/campaign-negative-location-criterion.md), and [Campaign Radius Criterion](../bulk-service/campaign-radius-criterion.md) records in the download data.|
|<a name="customaudiences"></a>CustomAudiences|Include [Custom Audience](../bulk-service/custom-audience.md) records in the download data.<br/><br/> The [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operations return the same set of custom audiences for the current authenticated user. All custom audiences that have Scope set to Customer are included. The custom audiences that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a custom audience is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="dynamicsearchadlabels"></a>DynamicSearchAdLabels|Include [Dynamic Search Ad Label](../bulk-service/dynamic-search-ad-label.md) records in the download that each represent a label applied to a dynamic search ad. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="dynamicsearchads"></a>DynamicSearchAds|Include [Dynamic Search Ad](../bulk-service/dynamic-search-ad.md) records in the download data.<br/><br/> To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="expandedtextadlabels"></a>ExpandedTextAdLabels|Include [Expanded Text Ad Label](../bulk-service/expanded-text-ad-label.md) records in the download that each represent a label applied to an expanded text ad. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="expandedtextads"></a>ExpandedTextAds|Include [Expanded Text Ad](../bulk-service/expanded-text-ad.md) records in the download data.<br/><br/> To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="imageadextensions"></a>ImageAdExtensions|Include [Image Ad Extension](../bulk-service/image-ad-extension.md) records in the download data.<br/><br/> To get all image ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the image ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="inmarketaudiences"></a>InMarketAudiences|Include [In Market Audience](../bulk-service/in-market-audience.md) records in the download data.<br/><br/> The [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operations return the same set of in-market audiences for the current authenticated user. All in-market audiences that have Scope set to Customer are included. The in-market audiences that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if an in-market audience is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="keywordlabels"></a>KeywordLabels|Include [Keyword Label](../bulk-service/keyword-label.md) records in the download that each represent a label applied to a keyword. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="keywords"></a>Keywords|Include [Keyword](../bulk-service/keyword.md) records in the download data.|
|<a name="labels"></a>Labels|Include [Label](../bulk-service/label.md) records in the download data.<br/><br/> The [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation will ignore campaign scope and return all labels from your account's labels library. Likewise the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation will return all labels from your account's labels library.|
|<a name="locationadextensions"></a>LocationAdExtensions|Include [Location Ad Extension](../bulk-service/location-ad-extension.md) records in the download data.<br/><br/> To get all location ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the location ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="negativekeywordlists"></a>NegativeKeywordLists|Include [Negative Keyword List](../bulk-service/negative-keyword-list.md) records in the download data. The [Negative Keyword List](../bulk-service/negative-keyword-list.md) records do not include negative keywords that are shared in each list. For [Shared Negative Keyword](../bulk-service/shared-negative-keyword.md) records, you should include the SharedNegativeKeywords value in the download request.<br/><br/> The [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) will return all negative keyword lists from your account's negative keyword list library, whether or not the lists are associated with the specified campaigns .|
|<a name="priceadextensions"></a>PriceAdExtensions|Include [Price Ad Extension](../bulk-service/price-ad-extension.md) records in the download data.<br/><br/> To get all price ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the price ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="productadlabels"></a>ProductAdLabels|Include [Product Ad Label](../bulk-service/product-ad-label.md) records in the download that each represent a label applied to a product ad. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="productads"></a>ProductAds|Include [Product Ad](../bulk-service/product-ad.md) records in the download data.<br/><br/> To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="remarketinglists"></a>RemarketingLists|Include [Remarketing List](../bulk-service/remarketing-list.md) records in the download data.<br/><br/> The [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operations return the same set of remarketing lists for the current authenticated user. All remarketing lists that have Scope set to Customer are included. The remarketing lists that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a remarketing list is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="reviewadextensions"></a>ReviewAdExtensions|Include [Review Ad Extension](../bulk-service/review-ad-extension.md) records in the download data.<br/><br/> To get all review ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the review ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="sharednegativekeywords"></a>SharedNegativeKeywords|Include [Shared Negative Keyword](../bulk-service/shared-negative-keyword.md) records in the download data. Shared negative keywords belong to a negative keyword list. For [Negative Keyword List](../bulk-service/negative-keyword-list.md) records, you should include the NegativeKeywordLists value in the download request.|
|<a name="sitelink2adextensions"></a>Sitelink2AdExtensions|Include [Sitelink2 Ad Extension](../bulk-service/sitelink2-ad-extension.md) records in the download data.<br/><br/> To get all sitelink2 ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the sitelink2 ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="sitelinksadextensions"></a>SiteLinksAdExtensions|This value is deprecated in favor of Sitelink2AdExtensions.|
|<a name="structuredsnippetadextensions"></a>StructuredSnippetAdExtensions|Include [Structured Snippet Ad Extension](../bulk-service/structured-snippet-ad-extension.md) records in the download data.<br/><br/> To get all structured snippet ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) operation. To get only the structured snippet ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operation.|
|<a name="textadlabels"></a>TextAdLabels|Include [Text Ad Label](../bulk-service/text-ad-label.md) records in the download that each represent a label applied to a text ad. For [Label](../bulk-service/label.md) records, you should include the Labels value in the download request.|
|<a name="textads"></a>TextAds|Include [Text Ad](../bulk-service/text-ad.md) records in the download data.<br/><br/> To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
