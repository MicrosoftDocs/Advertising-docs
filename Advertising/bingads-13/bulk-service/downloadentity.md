---
title: DownloadEntity Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the entities that may be downloaded and uploaded in bulk.
---
# DownloadEntity Value Set - Bulk
Defines the entities that may be downloaded and uploaded in bulk.

For more information, see [Bulk File Schema](bulk-file-schema.md).

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
    <xs:enumeration value="CampaignLocationAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">11</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignCallAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">12</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="LocationAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">13</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CallAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">14</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="NegativeKeywordLists">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">15</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SharedNegativeKeywords">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeKeywordListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">17</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">18</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">19</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">20</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">21</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupAppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">22</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignAppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">23</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="PriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">24</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">25</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeDynamicSearchAdTargets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">26</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupProductPartitions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">27</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignProductScopes">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">28</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">29</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">30</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">31</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignCalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">32</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupCalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">33</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SitelinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">34</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignSitelinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">35</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupSitelinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">36</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="StructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">37</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignStructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">38</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupStructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">39</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="RemarketingLists">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">40</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">41</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Budgets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">42</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="TextAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">43</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ProductAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">44</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AppInstallAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">45</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ExpandedTextAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">46</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="DynamicSearchAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">47</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupDynamicSearchAdTargets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">48</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeDynamicSearchAdTargets">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">49</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignPriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">50</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupPriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">51</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Labels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">52</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">53</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">54</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="TextAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">55</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="KeywordLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">56</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">57</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CustomAudiences">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">58</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupCustomAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">59</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeCustomAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">60</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="InMarketAudiences">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">61</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupInMarketAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">62</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeInMarketAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">63</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Audiences">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">65</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">66</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ProductAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">67</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AppInstallAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">68</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ExpandedTextAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">69</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="DynamicSearchAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">70</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountLocationAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">71</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountImageAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">72</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountAppAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">73</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountPriceAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">74</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountReviewAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">75</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountCalloutAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">76</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountSitelinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">77</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountStructuredSnippetAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">78</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ResponsiveAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">79</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ResponsiveAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">80</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ProductAudiences">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">81</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupProductAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">82</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeProductAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">83</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SimilarRemarketingLists">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">84</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupSimilarRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">85</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeSimilarRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">86</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Experiments">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">87</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ActionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">88</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignActionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">89</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupActionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">90</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountActionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">91</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ResponsiveSearchAds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">92</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ResponsiveSearchAdLabels">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">93</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">94</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">95</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignCustomAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">96</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeCustomAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">97</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignInMarketAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">98</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeInMarketAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">99</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignProductAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">100</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeProductAudienceAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">101</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">102</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">103</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignSimilarRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">104</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeSimilarRemarketingListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">105</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Feeds">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">106</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FeedItems">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">107</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeStoreCriterions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">108</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="PromotionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">109</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountPromotionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">110</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignPromotionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">111</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupPromotionAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">112</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CombinedLists">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">113</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupCombinedListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">114</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeCombinedListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">115</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignCombinedListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">116</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeCombinedListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">117</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Images">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">118</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CustomerLists">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">119</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupCustomerListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">120</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupNegativeCustomerListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">121</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignCustomerListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">122</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignNegativeCustomerListAssociations">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">123</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FilterLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">124</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountFilterLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">125</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignFilterLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">126</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupFilterLinkAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">127</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FlyerAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">128</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AccountFlyerAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">129</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CampaignFlyerAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">130</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupFlyerAdExtensions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">131</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="PortfolioBidStrategies">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">132</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [DownloadEntity](downloadentity.md) value set has the following values: [AccountActionAdExtensions](#accountactionadextensions), [AccountAppAdExtensions](#accountappadextensions), [AccountCalloutAdExtensions](#accountcalloutadextensions), [AccountFilterLinkAdExtensions](#accountfilterlinkadextensions), [AccountFlyerAdExtensions](#accountflyeradextensions), [AccountImageAdExtensions](#accountimageadextensions), [AccountLocationAdExtensions](#accountlocationadextensions), [AccountPriceAdExtensions](#accountpriceadextensions), [AccountPromotionAdExtensions](#accountpromotionadextensions), [AccountReviewAdExtensions](#accountreviewadextensions), [AccountSitelinkAdExtensions](#accountsitelinkadextensions), [AccountStructuredSnippetAdExtensions](#accountstructuredsnippetadextensions), [ActionAdExtensions](#actionadextensions), [AdGroupActionAdExtensions](#adgroupactionadextensions), [AdGroupAppAdExtensions](#adgroupappadextensions), [AdGroupAudienceAssociations](#adgroupaudienceassociations), [AdGroupCalloutAdExtensions](#adgroupcalloutadextensions), [AdGroupCombinedListAssociations](#adgroupcombinedlistassociations), [AdGroupCustomAudienceAssociations](#adgroupcustomaudienceassociations), [AdGroupCustomerListAssociations](#adgroupcustomerlistassociations), [AdGroupDynamicSearchAdTargets](#adgroupdynamicsearchadtargets), [AdGroupFilterLinkAdExtensions](#adgroupfilterlinkadextensions), [AdGroupFlyerAdExtensions](#adgroupflyeradextensions), [AdGroupImageAdExtensions](#adgroupimageadextensions), [AdGroupInMarketAudienceAssociations](#adgroupinmarketaudienceassociations), [AdGroupLabels](#adgrouplabels), [AdGroupNegativeAudienceAssociations](#adgroupnegativeaudienceassociations), [AdGroupNegativeCombinedListAssociations](#adgroupnegativecombinedlistassociations), [AdGroupNegativeCustomAudienceAssociations](#adgroupnegativecustomaudienceassociations), [AdGroupNegativeCustomerListAssociations](#adgroupnegativecustomerlistassociations), [AdGroupNegativeDynamicSearchAdTargets](#adgroupnegativedynamicsearchadtargets), [AdGroupNegativeInMarketAudienceAssociations](#adgroupnegativeinmarketaudienceassociations), [AdGroupNegativeKeywords](#adgroupnegativekeywords), [AdGroupNegativeProductAudienceAssociations](#adgroupnegativeproductaudienceassociations), [AdGroupNegativeRemarketingListAssociations](#adgroupnegativeremarketinglistassociations), [AdGroupNegativeSimilarRemarketingListAssociations](#adgroupnegativesimilarremarketinglistassociations), [AdGroupNegativeSites](#adgroupnegativesites), [AdGroupPriceAdExtensions](#adgrouppriceadextensions), [AdGroupProductAudienceAssociations](#adgroupproductaudienceassociations), [AdGroupProductPartitions](#adgroupproductpartitions), [AdGroupPromotionAdExtensions](#adgrouppromotionadextensions), [AdGroupRemarketingListAssociations](#adgroupremarketinglistassociations), [AdGroupReviewAdExtensions](#adgroupreviewadextensions), [AdGroups](#adgroups), [AdGroupSimilarRemarketingListAssociations](#adgroupsimilarremarketinglistassociations), [AdGroupSitelinkAdExtensions](#adgroupsitelinkadextensions), [AdGroupStructuredSnippetAdExtensions](#adgroupstructuredsnippetadextensions), [AdGroupTargetCriterions](#adgrouptargetcriterions), [Ads](#ads), [AppAdExtensions](#appadextensions), [AppInstallAdLabels](#appinstalladlabels), [AppInstallAds](#appinstallads), [Audiences](#audiences), [Budgets](#budgets), [CallAdExtensions](#calladextensions), [CalloutAdExtensions](#calloutadextensions), [CampaignActionAdExtensions](#campaignactionadextensions), [CampaignAppAdExtensions](#campaignappadextensions), [CampaignAudienceAssociations](#campaignaudienceassociations), [CampaignCallAdExtensions](#campaigncalladextensions), [CampaignCalloutAdExtensions](#campaigncalloutadextensions), [CampaignCombinedListAssociations](#campaigncombinedlistassociations), [CampaignCustomAudienceAssociations](#campaigncustomaudienceassociations), [CampaignCustomerListAssociations](#campaigncustomerlistassociations), [CampaignFilterLinkAdExtensions](#campaignfilterlinkadextensions), [CampaignFlyerAdExtensions](#campaignflyeradextensions), [CampaignImageAdExtensions](#campaignimageadextensions), [CampaignInMarketAudienceAssociations](#campaigninmarketaudienceassociations), [CampaignLabels](#campaignlabels), [CampaignLocationAdExtensions](#campaignlocationadextensions), [CampaignNegativeAudienceAssociations](#campaignnegativeaudienceassociations), [CampaignNegativeCombinedListAssociations](#campaignnegativecombinedlistassociations), [CampaignNegativeCustomAudienceAssociations](#campaignnegativecustomaudienceassociations), [CampaignNegativeCustomerListAssociations](#campaignnegativecustomerlistassociations), [CampaignNegativeDynamicSearchAdTargets](#campaignnegativedynamicsearchadtargets), [CampaignNegativeInMarketAudienceAssociations](#campaignnegativeinmarketaudienceassociations), [CampaignNegativeKeywordListAssociations](#campaignnegativekeywordlistassociations), [CampaignNegativeKeywords](#campaignnegativekeywords), [CampaignNegativeProductAudienceAssociations](#campaignnegativeproductaudienceassociations), [CampaignNegativeRemarketingListAssociations](#campaignnegativeremarketinglistassociations), [CampaignNegativeSimilarRemarketingListAssociations](#campaignnegativesimilarremarketinglistassociations), [CampaignNegativeSites](#campaignnegativesites), [CampaignNegativeStoreCriterions](#campaignnegativestorecriterions), [CampaignPriceAdExtensions](#campaignpriceadextensions), [CampaignProductAudienceAssociations](#campaignproductaudienceassociations), [CampaignProductScopes](#campaignproductscopes), [CampaignPromotionAdExtensions](#campaignpromotionadextensions), [CampaignRemarketingListAssociations](#campaignremarketinglistassociations), [CampaignReviewAdExtensions](#campaignreviewadextensions), [Campaigns](#campaigns), [CampaignSimilarRemarketingListAssociations](#campaignsimilarremarketinglistassociations), [CampaignSitelinkAdExtensions](#campaignsitelinkadextensions), [CampaignStructuredSnippetAdExtensions](#campaignstructuredsnippetadextensions), [CampaignTargetCriterions](#campaigntargetcriterions), [CombinedLists](#combinedlists), [CustomAudiences](#customaudiences), [CustomerLists](#customerlists), [DynamicSearchAdLabels](#dynamicsearchadlabels), [DynamicSearchAds](#dynamicsearchads), [ExpandedTextAdLabels](#expandedtextadlabels), [ExpandedTextAds](#expandedtextads), [Experiments](#experiments), [FeedItems](#feeditems), [Feeds](#feeds), [FilterLinkAdExtensions](#filterlinkadextensions), [FlyerAdExtensions](#flyeradextensions), [ImageAdExtensions](#imageadextensions), [Images](#images), [InMarketAudiences](#inmarketaudiences), [KeywordLabels](#keywordlabels), [Keywords](#keywords), [Labels](#labels), [LocationAdExtensions](#locationadextensions), [NegativeKeywordLists](#negativekeywordlists), [PortfolioBidStrategies](#portfoliobidstrategies), [PriceAdExtensions](#priceadextensions), [ProductAdLabels](#productadlabels), [ProductAds](#productads), [ProductAudiences](#productaudiences), [PromotionAdExtensions](#promotionadextensions), [RemarketingLists](#remarketinglists), [ResponsiveAdLabels](#responsiveadlabels), [ResponsiveAds](#responsiveads), [ResponsiveSearchAdLabels](#responsivesearchadlabels), [ResponsiveSearchAds](#responsivesearchads), [ReviewAdExtensions](#reviewadextensions), [SharedNegativeKeywords](#sharednegativekeywords), [SimilarRemarketingLists](#similarremarketinglists), [SitelinkAdExtensions](#sitelinkadextensions), [StructuredSnippetAdExtensions](#structuredsnippetadextensions), [TextAdLabels](#textadlabels), [TextAds](#textads).

|Value|Description|
|-----------|---------------|
|<a name="accountactionadextensions"></a>AccountActionAdExtensions|Include [Account Action Ad Extension](account-action-ad-extension.md) records in the download that represents the association relationship between an account and an action ad extension. For [Action Ad Extension](action-ad-extension.md) records, you should include the ActionAdExtensions value in the download request.|
|<a name="accountappadextensions"></a>AccountAppAdExtensions|Include [Account App Ad Extension](account-app-ad-extension.md) records in the download that each represent the association relationship between an account and an app ad extension. For [App Ad Extension](app-ad-extension.md) records, you should include the AppAdExtensions value in the download request.|
|<a name="accountcalloutadextensions"></a>AccountCalloutAdExtensions|Include [Account Callout Ad Extension](account-callout-ad-extension.md) records in the download that represents the association relationship between an account and a callout ad extension. For [Callout Ad Extension](callout-ad-extension.md) records, you should include the CalloutAdExtensions value in the download request.|
|<a name="accountfilterlinkadextensions"></a>AccountFilterLinkAdExtensions|Include [Account Filter Link Ad Extension](account-filter-link-ad-extension.md) records in the download that represents the association relationship between an account and a filter link ad extension. For [Filter Link Ad Extension](filter-link-ad-extension.md) records, you should include the FilterLinkAdExtensions value in the download request.|
|<a name="accountflyeradextensions"></a>AccountFlyerAdExtensions|Include [Account Flyer Ad Extension](account-flyer-ad-extension.md) records in the download that represents the association relationship between an account and a flyer ad extension. For [Flyer Ad Extension](flyer-ad-extension.md) records, you should include the FlyerAdExtensions value in the download request.|
|<a name="accountimageadextensions"></a>AccountImageAdExtensions|Include [Account Image Ad Extension](account-image-ad-extension.md) records in the download that represents the association relationship between an account and an image ad extension. For [Image Ad Extension](image-ad-extension.md) records, you should include the ImageAdExtensions value in the download request.|
|<a name="accountlocationadextensions"></a>AccountLocationAdExtensions|Include [Account Location Ad Extension](account-location-ad-extension.md) records in the download that represents the association relationship between an account and a location ad extension. For [Location Ad Extension](location-ad-extension.md) records, you should include the LocationAdExtensions value in the download request.|
|<a name="accountpriceadextensions"></a>AccountPriceAdExtensions|Include [Account Price Ad Extension](account-price-ad-extension.md) records in the download that represents the association relationship between an account and a price ad extension. For [Price Ad Extension](price-ad-extension.md) records, you should include the PriceAdExtensions value in the download request.|
|<a name="accountpromotionadextensions"></a>AccountPromotionAdExtensions|Include [Account Promotion Ad Extension](account-promotion-ad-extension.md) records in the download that represents the association relationship between an account and a promotion ad extension. For [Promotion Ad Extension](promotion-ad-extension.md) records, you should include the PromotionAdExtensions value in the download request.|
|<a name="accountreviewadextensions"></a>AccountReviewAdExtensions|Include [Account Review Ad Extension](account-review-ad-extension.md) records in the download that each represent the association relationship between an account and a review ad extension. For [Review Ad Extension](review-ad-extension.md) records, you should include the ReviewAdExtensions value in the download request.|
|<a name="accountsitelinkadextensions"></a>AccountSitelinkAdExtensions|Include [Account Sitelink Ad Extension](account-sitelink-ad-extension.md) records in the download that represents the association relationship between an account and a sitelink ad extension. For [Sitelink Ad Extension](sitelink-ad-extension.md) records, you should include the SitelinkAdExtensions value in the download request.|
|<a name="accountstructuredsnippetadextensions"></a>AccountStructuredSnippetAdExtensions|Include [Account Structured Snippet Ad Extension](account-structured-snippet-ad-extension.md) records in the download that represents the association relationship between an account and a structured snippet ad extension. For [Structured Snippet Ad Extension](structured-snippet-ad-extension.md) records, you should include the StructuredSnippetAdExtensions value in the download request.|
|<a name="actionadextensions"></a>ActionAdExtensions|Include [Action Ad Extension](action-ad-extension.md) records in the download data.<br/><br/>To get all action ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the action ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="adgroupactionadextensions"></a>AdGroupActionAdExtensions|Include [Ad Group Action Ad Extension](ad-group-action-ad-extension.md) records in the download that each represent the association relationship between an ad group and an action ad extension. For [Action Ad Extension](action-ad-extension.md) records, you should include the ActionAdExtensions value in the download request.|
|<a name="adgroupappadextensions"></a>AdGroupAppAdExtensions|Include [Ad Group App Ad Extension](ad-group-app-ad-extension.md) records in the download that each represent the association relationship between an ad group and an app ad extension. For [App Ad Extension](app-ad-extension.md) records, you should include the AppAdExtensions value in the download request.|
|<a name="adgroupaudienceassociations"></a>AdGroupAudienceAssociations|Include [Ad Group Combined List Association](ad-group-combined-list-association.md), [Ad Group Custom Audience Association](ad-group-custom-audience-association.md), [Ad Group Customer List Association](ad-group-customer-list-association.md), [Ad Group In Market Audience Association](ad-group-in-market-audience-association.md), [Ad Group Product Audience Association](ad-group-product-audience-association.md), [Ad Group Remarketing List Association](ad-group-remarketing-list-association.md), and [Ad Group Similar Remarketing List Association](ad-group-similar-remarketing-list-association.md) records in the download data.<br/><br/>To get audience associations by type instead of requesting all types of audience associations, you can include one or more of the AdGroupCombinedListAssociations, AdGroupCustomAudienceAssociations, AdGroupCustomerListAssociations, AdGroupInMarketAudienceAssociations, AdGroupProductAudienceAssociations, AdGroupRemarketingListAssociations, and AdGroupSimilarRemarketingListAssociations values in the download request.|
|<a name="adgroupcalloutadextensions"></a>AdGroupCalloutAdExtensions|Include [Ad Group Callout Ad Extension](ad-group-callout-ad-extension.md) records in the download that each represent the association relationship between an ad group and a callout ad extension. For [Callout Ad Extension](callout-ad-extension.md) records, you should include the CalloutAdExtensions value in the download request.|
|<a name="adgroupcombinedlistassociations"></a>AdGroupCombinedListAssociations|Include [Ad Group Combined List Association](ad-group-combined-list-association.md) records in the download that each represent the association relationship between an ad group and a combined list. For [Combined List](combined-list.md) records, you should include the CombinedLists value in the download request.|
|<a name="adgroupcustomaudienceassociations"></a>AdGroupCustomAudienceAssociations|Include [Ad Group Custom Audience Association](ad-group-custom-audience-association.md) records in the download that each represent the association relationship between an ad group and a custom audience. For [Custom Audience](custom-audience.md) records, you should include the CustomAudiences value in the download request.|
|<a name="adgroupcustomerlistassociations"></a>AdGroupCustomerListAssociations|Include [Ad Group Customer List Association](ad-group-customer-list-association.md) records in the download that each represent the association relationship between an ad group and a customer list. For [Customer List](customer-list.md) records, you should include the CustomerLists value in the download request.|
|<a name="adgroupdynamicsearchadtargets"></a>AdGroupDynamicSearchAdTargets|Include [Ad Group Dynamic Search Ad Target](ad-group-dynamic-search-ad-target.md) records in the download data.|
|<a name="adgroupfilterlinkadextensions"></a>AdGroupFilterLinkAdExtensions|Include [Ad Group Filter Link Ad Extension](ad-group-filter-link-ad-extension.md) records in the download that each represent the association relationship between an ad group and a filter link ad extension. For [Filter Link Ad Extension](filter-link-ad-extension.md) records, you should include the FilterLinkAdExtensions value in the download request.|
|<a name="adgroupflyeradextensions"></a>AdGroupFlyerAdExtensions|Include [Ad Group Flyer Ad Extension](ad-group-flyer-ad-extension.md) records in the download that each represent the association relationship between an ad group and a flyer ad extension. For [Flyer Ad Extension](flyer-ad-extension.md) records, you should include the FlyerAdExtensions value in the download request.|
|<a name="adgroupimageadextensions"></a>AdGroupImageAdExtensions|Include [Ad Group Image Ad Extension](ad-group-image-ad-extension.md) records in the download that each represent the association relationship between an ad group and an image ad extension. For [Image Ad Extension](image-ad-extension.md) records, you should include the ImageAdExtensions value in the download request.|
|<a name="adgroupinmarketaudienceassociations"></a>AdGroupInMarketAudienceAssociations|Include [Ad Group In Market Audience Association](ad-group-in-market-audience-association.md) records in the download that each represent the association relationship between an ad group and an in-market audience. For [In Market Audience](in-market-audience.md) records, you should include the InMarketAudiences value in the download request.|
|<a name="adgrouplabels"></a>AdGroupLabels|Include [Ad Group Label](ad-group-label.md) records in the download that each represent a label applied to an ad group. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="adgroupnegativeaudienceassociations"></a>AdGroupNegativeAudienceAssociations|Include [Ad Group Negative Combined List Association](ad-group-negative-combined-list-association.md), [Ad Group Negative Custom Audience Association](ad-group-negative-custom-audience-association.md), [Ad Group Negative Customer List Association](ad-group-negative-customer-list-association.md), [Ad Group Negative In Market Audience Association](ad-group-negative-in-market-audience-association.md), [Ad Group Negative Product Audience Association](ad-group-negative-product-audience-association.md), [Ad Group Negative Remarketing List Association](ad-group-negative-remarketing-list-association.md), and [Ad Group Negative Similar Remarketing List Association](ad-group-negative-similar-remarketing-list-association.md) records in the download data.<br/><br/>To get negative audience associations by type instead of requesting all types of negative audience associations, you can include one or more of the AdGroupNegativeCombinedListAssociations, AdGroupNegativeCustomAudienceAssociations, AdGroupNegativeCustomerListAssociations, AdGroupInMarketAudienceNegativeAssociations, AdGroupNegativeProductAudienceAssociations, AdGroupNegativeRemarketingListAssociations, and AdGroupNegativeSimilarRemarketingListAssociations values in the download request.|
|<a name="adgroupnegativecombinedlistassociations"></a>AdGroupNegativeCombinedListAssociations|Include [Ad Group Negative Combined List Association](ad-group-negative-combined-list-association.md) records in the download that each represent the association relationship between an ad group and a combined list exclusion. For [Combined List](combined-list.md) records, you should include the CombinedLists value in the download request.|
|<a name="adgroupnegativecustomaudienceassociations"></a>AdGroupNegativeCustomAudienceAssociations|Include [Ad Group Negative Custom Audience Association](ad-group-negative-custom-audience-association.md) records in the download that each represent the association relationship between an ad group and a custom audience exclusion. For [Custom Audience](custom-audience.md) records, you should include the CustomAudiences value in the download request.|
|<a name="adgroupnegativecustomerlistassociations"></a>AdGroupNegativeCustomerListAssociations|Include [Ad Group Negative Customer List Association](ad-group-negative-customer-list-association.md) records in the download that each represent the association relationship between an ad group and a customer list exclusion. For [Customer List](customer-list.md) records, you should include the CustomerLists value in the download request.|
|<a name="adgroupnegativedynamicsearchadtargets"></a>AdGroupNegativeDynamicSearchAdTargets|Include [Ad Group Negative Dynamic Search Ad Target](ad-group-negative-dynamic-search-ad-target.md) records in the download data.|
|<a name="adgroupnegativeinmarketaudienceassociations"></a>AdGroupNegativeInMarketAudienceAssociations|Include [Ad Group Negative In Market Audience Association](ad-group-negative-in-market-audience-association.md) records in the download that each represent the association relationship between an ad group and an in-market audience exclusion. For [In Market Audience](in-market-audience.md) records, you should include the InMarketAudiences value in the download request.|
|<a name="adgroupnegativekeywords"></a>AdGroupNegativeKeywords|Include [Ad Group Negative Keyword](ad-group-negative-keyword.md) records in the download data.|
|<a name="adgroupnegativeproductaudienceassociations"></a>AdGroupNegativeProductAudienceAssociations|Include [Ad Group Negative Product Audience Association](ad-group-negative-product-audience-association.md) records in the download that each represent the association relationship between an ad group and a product audience exclusion. For [Product Audience](product-audience.md) records, you should include the ProductAudiences value in the download request.|
|<a name="adgroupnegativeremarketinglistassociations"></a>AdGroupNegativeRemarketingListAssociations|Include [Ad Group Negative Remarketing List Association](ad-group-negative-remarketing-list-association.md) records in the download that each represent the association relationship between an ad group and a remarketing list exclusion. For [Remarketing List](remarketing-list.md) records, you should include the RemarketingLists value in the download request.|
|<a name="adgroupnegativesimilarremarketinglistassociations"></a>AdGroupNegativeSimilarRemarketingListAssociations|Include [Ad Group Negative Similar Remarketing List Association](ad-group-negative-similar-remarketing-list-association.md) records in the download that each represent the association relationship between an ad group and a similar remarketing list exclusion. For [Similar Remarketing List](similar-remarketing-list.md) records, you should include the SimilarRemarketingLists value in the download request.|
|<a name="adgroupnegativesites"></a>AdGroupNegativeSites|Include [Ad Group Negative Site](ad-group-negative-site.md) records in the download data.|
|<a name="adgrouppriceadextensions"></a>AdGroupPriceAdExtensions|Include [Ad Group Price Ad Extension](ad-group-price-ad-extension.md) records in the download that each represent the association relationship between an ad group and a price ad extension. For [Price Ad Extension](price-ad-extension.md) records, you should include the PriceAdExtensions value in the download request.|
|<a name="adgroupproductaudienceassociations"></a>AdGroupProductAudienceAssociations|Include [Ad Group Product Audience Association](ad-group-product-audience-association.md) records in the download that each represent the association relationship between an ad group and a product audience. For [Product Audience](product-audience.md) records, you should include the ProductAudiences value in the download request.|
|<a name="adgroupproductpartitions"></a>AdGroupProductPartitions|Include [Ad Group Product Partition](ad-group-product-partition.md) records in the download data.|
|<a name="adgrouppromotionadextensions"></a>AdGroupPromotionAdExtensions|Include [Ad Group Promotion Ad Extension](ad-group-promotion-ad-extension.md) records in the download that each represent the association relationship between an ad group and a promotion ad extension. For [Promotion Ad Extension](promotion-ad-extension.md) records, you should include the PromotionAdExtensions value in the download request.|
|<a name="adgroupremarketinglistassociations"></a>AdGroupRemarketingListAssociations|Include [Ad Group Remarketing List Association](ad-group-remarketing-list-association.md) records in the download that each represent the association relationship between an ad group and a remarketing list. For [Remarketing List](remarketing-list.md) records, you should include the RemarketingLists value in the download request.|
|<a name="adgroupreviewadextensions"></a>AdGroupReviewAdExtensions|Include [Ad Group Review Ad Extension](ad-group-review-ad-extension.md) records in the download that each represent the association relationship between an ad group and a review ad extension. For [Review Ad Extension](review-ad-extension.md) records, you should include the ReviewAdExtensions value in the download request.|
|<a name="adgroups"></a>AdGroups|Include [Ad Group](ad-group.md) records in the download data.|
|<a name="adgroupsimilarremarketinglistassociations"></a>AdGroupSimilarRemarketingListAssociations|Include [Ad Group Similar Remarketing List Association](ad-group-similar-remarketing-list-association.md) records in the download that each represent the association relationship between an ad group and a similar remarketing list. For [Similar Remarketing List](similar-remarketing-list.md) records, you should include the SimilarRemarketingLists value in the download request.|
|<a name="adgroupsitelinkadextensions"></a>AdGroupSitelinkAdExtensions|Include [Ad Group Sitelink Ad Extension](ad-group-sitelink-ad-extension.md) records in the download that each represent the association relationship between an ad group and a sitelink ad extension. For [Sitelink Ad Extension](sitelink-ad-extension.md) records, you should include the SitelinkAdExtensions value in the download request.|
|<a name="adgroupstructuredsnippetadextensions"></a>AdGroupStructuredSnippetAdExtensions|Include [Ad Group Structured Snippet Ad Extension](ad-group-structured-snippet-ad-extension.md) records in the download that each represent the association relationship between an ad group and a structured snippet ad extension. For [Structured Snippet Ad Extension](structured-snippet-ad-extension.md) records, you should include the StructuredSnippetAdExtensions value in the download request.|
|<a name="adgrouptargetcriterions"></a>AdGroupTargetCriterions|Include [Ad Group Age Criterion](ad-group-age-criterion.md), [Ad Group Company Name Criterion](ad-group-company-name-criterion.md), [Ad Group DayTime Criterion](ad-group-daytime-criterion.md), [Ad Group DeviceOS Criterion](ad-group-deviceos-criterion.md), [Ad Group Gender Criterion](ad-group-gender-criterion.md), [Ad Group Industry Criterion](ad-group-industry-criterion.md), [Ad Group Job Function Criterion](ad-group-job-function-criterion.md), [Ad Group Location Criterion](ad-group-location-criterion.md), [Ad Group Location Intent Criterion](ad-group-location-intent-criterion.md), [Ad Group Negative Age Criterion](ad-group-negative-age-criterion.md), [Ad Group Negative Company Name Criterion](ad-group-negative-company-name-criterion.md), [Ad Group Negative Gender Criterion](ad-group-negative-gender-criterion.md), [Ad Group Negative Industry Criterion](ad-group-negative-industry-criterion.md), [Ad Group Negative Job Function Criterion](ad-group-negative-job-function-criterion.md), [Ad Group Negative Location Criterion](ad-group-negative-location-criterion.md), and [Ad Group Radius Criterion](ad-group-radius-criterion.md) records in the download data.|
|<a name="ads"></a>Ads|Include [App Install Ad](app-install-ad.md), [Dynamic Search Ad](dynamic-search-ad.md), [Expanded Text Ad](expanded-text-ad.md), [Product Ad](product-ad.md), [Responsive Ad](responsive-ad.md), [Responsive Search Ad](responsive-search-ad.md), and [Text Ad](text-ad.md) records in the download data.<br/><br/>To get ads by type instead of requesting all types of ads, you can include one or more of the AppInstallAds, DynamicSearchAds, ExpandedTextAds, ProductAds, ResponsiveAds, and TextAds values in the download request.|
|<a name="appadextensions"></a>AppAdExtensions|Include [App Ad Extension](app-ad-extension.md) records in the download data.<br/><br/>To get all app ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the app ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="appinstalladlabels"></a>AppInstallAdLabels|Include [App Install Ad Label](app-install-ad-label.md) records in the download that each represent a label applied to an app install ad. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="appinstallads"></a>AppInstallAds|Include [App Install Ad](app-install-ad.md) records in the download data.<br/><br/>To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="audiences"></a>Audiences|Include [Combined List](combined-list.md), [Custom Audience](custom-audience.md), [Customer List](customer-list.md), [In Market Audience](in-market-audience.md), [Product Audience](product-audience.md), [Remarketing List](remarketing-list.md), and [Similar Remarketing List](similar-remarketing-list.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of audiences for the current authenticated user. All audiences that have Scope set to Customer are included. The audiences that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if an audience is in account scope for an account that the user cannot access, then it is excluded from the download results.<br/><br/>To get audiences by type instead of requesting all types of audiences, you can include one or more of the CombinedLists, CustomAudiences, CustomerLists, InMarketAudiences, ProductAudiences, RemarketingLists, and SimilarRemarketingLists values in the download request.|
|<a name="budgets"></a>Budgets|Include [Budget](budget.md) records in the download data.|
|<a name="calladextensions"></a>CallAdExtensions|Include [Call Ad Extension](call-ad-extension.md) records in the download data.<br/><br/>To get all call ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the call ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="calloutadextensions"></a>CalloutAdExtensions|Include [Callout Ad Extension](callout-ad-extension.md) records in the download data.<br/><br/>To get all callout ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the callout ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="campaignactionadextensions"></a>CampaignActionAdExtensions|Include [Campaign Action Ad Extension](campaign-action-ad-extension.md) records in the download that represents the association relationship between a campaign and an action ad extension. For [Action Ad Extension](action-ad-extension.md) records, you should include the ActionAdExtensions value in the download request.|
|<a name="campaignappadextensions"></a>CampaignAppAdExtensions|Include [Campaign App Ad Extension](campaign-app-ad-extension.md) records in the download that each represent the association relationship between a campaign and an app ad extension. For [App Ad Extension](app-ad-extension.md) records, you should include the AppAdExtensions value in the download request.|
|<a name="campaignaudienceassociations"></a>CampaignAudienceAssociations|Include [Campaign Combined List Association](campaign-combined-list-association.md), [Campaign Custom Audience Association](campaign-custom-audience-association.md), [Campaign Customer List Association](campaign-customer-list-association.md), [Campaign In Market Audience Association](campaign-in-market-audience-association.md), [Campaign Product Audience Association](campaign-product-audience-association.md), [Campaign Remarketing List Association](campaign-remarketing-list-association.md), and [Campaign Similar Remarketing List Association](campaign-similar-remarketing-list-association.md) records in the download data.<br/><br/>To get audience associations by type instead of requesting all types of audience associations, you can include one or more of the CampaignCombinedListAssociations, CampaignCustomAudienceAssociations, CampaignCustomerListAssociations, CampaignInMarketAudienceAssociations, CampaignProductAudienceAssociations, CampaignRemarketingListAssociations, and CampaignSimilarRemarketingListAssociations values in the download request.|
|<a name="campaigncalladextensions"></a>CampaignCallAdExtensions|Include [Campaign Call Ad Extension](campaign-call-ad-extension.md) records in the download that represents the association relationship between a campaign and a call ad extension. For [Call Ad Extension](call-ad-extension.md) records, you should include the CallAdExtensions value in the download request.|
|<a name="campaigncalloutadextensions"></a>CampaignCalloutAdExtensions|Include [Campaign Callout Ad Extension](campaign-callout-ad-extension.md) records in the download that represents the association relationship between a campaign and a callout ad extension. For [Callout Ad Extension](callout-ad-extension.md) records, you should include the CalloutAdExtensions value in the download request.|
|<a name="campaigncombinedlistassociations"></a>CampaignCombinedListAssociations|Include [Campaign Combined List Association](campaign-combined-list-association.md) records in the download that each represent the association relationship between a campaign and a combined list. For [Combined List](combined-list.md) records, you should include the CombinedLists value in the download request.|
|<a name="campaigncustomaudienceassociations"></a>CampaignCustomAudienceAssociations|Include [Campaign Custom Audience Association](campaign-custom-audience-association.md) records in the download that each represent the association relationship between a campaign and a custom audience. For [Custom Audience](custom-audience.md) records, you should include the CustomAudiences value in the download request.|
|<a name="campaigncustomerlistassociations"></a>CampaignCustomerListAssociations|Include [Campaign Customer List Association](campaign-customer-list-association.md) records in the download that each represent the association relationship between a campaign and a customer list. For [Customer List](customer-list.md) records, you should include the CustomerLists value in the download request.|
|<a name="campaignfilterlinkadextensions"></a>CampaignFilterLinkAdExtensions|Include [Campaign Filter Link Ad Extension](campaign-filter-link-ad-extension.md) records in the download that represents the association relationship between a campaign and a filter link ad extension. For [Filter Link Ad Extension](filter-link-ad-extension.md) records, you should include the FilterLinkAdExtensions value in the download request.|
|<a name="campaignflyeradextensions"></a>CampaignFlyerAdExtensions|Include [Campaign Flyer Ad Extension](campaign-flyer-ad-extension.md) records in the download that represents the association relationship between a campaign and a flyer ad extension. For [Flyer Ad Extension](flyer-ad-extension.md) records, you should include the FlyerAdExtensions value in the download request.|
|<a name="campaignimageadextensions"></a>CampaignImageAdExtensions|Include [Campaign Image Ad Extension](campaign-image-ad-extension.md) records in the download that represents the association relationship between a campaign and an image ad extension. For [Image Ad Extension](image-ad-extension.md) records, you should include the ImageAdExtensions value in the download request.|
|<a name="campaigninmarketaudienceassociations"></a>CampaignInMarketAudienceAssociations|Include [Campaign In Market Audience Association](campaign-in-market-audience-association.md) records in the download that each represent the association relationship between a campaign and an in-market audience. For [In Market Audience](in-market-audience.md) records, you should include the InMarketAudiences value in the download request.|
|<a name="campaignlabels"></a>CampaignLabels|Include [Campaign Label](campaign-label.md) records in the download that each represent a label applied to a campaign. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="campaignlocationadextensions"></a>CampaignLocationAdExtensions|Include [Campaign Location Ad Extension](campaign-location-ad-extension.md) records in the download that represents the association relationship between a campaign and a location ad extension. For [Location Ad Extension](location-ad-extension.md) records, you should include the LocationAdExtensions value in the download request.|
|<a name="campaignnegativeaudienceassociations"></a>CampaignNegativeAudienceAssociations|Include [Campaign Negative Combined List Association](campaign-negative-combined-list-association.md), [Campaign Negative Custom Audience Association](campaign-negative-custom-audience-association.md), [Campaign Negative Customer List Association](campaign-negative-customer-list-association.md), [Campaign Negative In Market Audience Association](campaign-negative-in-market-audience-association.md), [Campaign Negative Product Audience Association](campaign-negative-product-audience-association.md), [Campaign Negative Remarketing List Association](campaign-negative-remarketing-list-association.md), and [Campaign Negative Similar Remarketing List Association](campaign-negative-similar-remarketing-list-association.md) records in the download data.<br/><br/>To get negative audience associations by type instead of requesting all types of negative audience associations, you can include one or more of the CampaignNegativeCombinedListAssociations, CampaignNegativeCustomAudienceAssociations, CampaignNegativeCustomerListAssociations, CampaignInMarketAudienceNegativeAssociations, CampaignNegativeProductAudienceAssociations, CampaignNegativeRemarketingListAssociations, and CampaignNegativeSimilarRemarketingListAssociations values in the download request.|
|<a name="campaignnegativecombinedlistassociations"></a>CampaignNegativeCombinedListAssociations|Include [Campaign Negative Combined List Association](campaign-negative-combined-list-association.md) records in the download that each represent the association relationship between a campaign and a combined list exclusion. For [Combined List](combined-list.md) records, you should include the CombinedLists value in the download request.|
|<a name="campaignnegativecustomaudienceassociations"></a>CampaignNegativeCustomAudienceAssociations|Include [Campaign Negative Custom Audience Association](campaign-negative-custom-audience-association.md) records in the download that each represent the association relationship between a campaign and a custom audience exclusion. For [Custom Audience](custom-audience.md) records, you should include the CustomAudiences value in the download request.|
|<a name="campaignnegativecustomerlistassociations"></a>CampaignNegativeCustomerListAssociations|Include [Campaign Negative Customer List Association](campaign-negative-customer-list-association.md) records in the download that each represent the association relationship between a campaign and a customer list exclusion. For [Customer List](customer-list.md) records, you should include the CustomerLists value in the download request.|
|<a name="campaignnegativedynamicsearchadtargets"></a>CampaignNegativeDynamicSearchAdTargets|Include [Campaign Negative Dynamic Search Ad Target](campaign-negative-dynamic-search-ad-target.md) records in the download data.|
|<a name="campaignnegativeinmarketaudienceassociations"></a>CampaignNegativeInMarketAudienceAssociations|Include [Campaign Negative In Market Audience Association](campaign-negative-in-market-audience-association.md) records in the download that each represent the association relationship between a campaign and an in-market audience exclusion. For [In Market Audience](in-market-audience.md) records, you should include the InMarketAudiences value in the download request.|
|<a name="campaignnegativekeywordlistassociations"></a>CampaignNegativeKeywordListAssociations|Include [Campaign Negative Keyword List Association](campaign-negative-keyword-list-association.md) records in the download that represents the association relationship between a campaign and a negative keyword list. For [Negative Keyword List](negative-keyword-list.md) records, you should include the NegativeKeywordLists value in the download request.|
|<a name="campaignnegativekeywords"></a>CampaignNegativeKeywords|Include [Campaign Negative Keyword](campaign-negative-keyword.md) records in the download data.|
|<a name="campaignnegativeproductaudienceassociations"></a>CampaignNegativeProductAudienceAssociations|Include [Campaign Negative Product Audience Association](campaign-negative-product-audience-association.md) records in the download that each represent the association relationship between a campaign and a product audience exclusion. For [Product Audience](product-audience.md) records, you should include the ProductAudiences value in the download request.|
|<a name="campaignnegativeremarketinglistassociations"></a>CampaignNegativeRemarketingListAssociations|Include [Campaign Negative Remarketing List Association](campaign-negative-remarketing-list-association.md) records in the download that each represent the association relationship between a campaign and a remarketing list exclusion. For [Remarketing List](remarketing-list.md) records, you should include the RemarketingLists value in the download request.|
|<a name="campaignnegativesimilarremarketinglistassociations"></a>CampaignNegativeSimilarRemarketingListAssociations|Include [Campaign Negative Similar Remarketing List Association](campaign-negative-similar-remarketing-list-association.md) records in the download that each represent the association relationship between a campaign and a similar remarketing list exclusion. For [Similar Remarketing List](similar-remarketing-list.md) records, you should include the SimilarRemarketingLists value in the download request.|
|<a name="campaignnegativesites"></a>CampaignNegativeSites|Include [Campaign Negative Site](campaign-negative-site.md) records in the download data.|
|<a name="campaignnegativestorecriterions"></a>CampaignNegativeStoreCriterions|Include [Campaign Negative Store Criterion](campaign-negative-store-criterion.md) records in the download data.|
|<a name="campaignpriceadextensions"></a>CampaignPriceAdExtensions|Include [Campaign Price Ad Extension](campaign-price-ad-extension.md) records in the download that represents the association relationship between a campaign and a price ad extension. For [Price Ad Extension](price-ad-extension.md) records, you should include the PriceAdExtensions value in the download request.|
|<a name="campaignproductaudienceassociations"></a>CampaignProductAudienceAssociations|Include [Campaign Product Audience Association](campaign-product-audience-association.md) records in the download that each represent the association relationship between a campaign and a product audience. For [Product Audience](product-audience.md) records, you should include the ProductAudiences value in the download request.|
|<a name="campaignproductscopes"></a>CampaignProductScopes|Include [Campaign Product Scope](campaign-product-scope.md) records in the download data.|
|<a name="campaignpromotionadextensions"></a>CampaignPromotionAdExtensions|Include [Campaign Promotion Ad Extension](campaign-promotion-ad-extension.md) records in the download that represents the association relationship between a campaign and a promotion ad extension. For [Promotion Ad Extension](promotion-ad-extension.md) records, you should include the PromotionAdExtensions value in the download request.|
|<a name="campaignremarketinglistassociations"></a>CampaignRemarketingListAssociations|Include [Campaign Remarketing List Association](campaign-remarketing-list-association.md) records in the download that each represent the association relationship between a campaign and a remarketing list. For [Remarketing List](remarketing-list.md) records, you should include the RemarketingLists value in the download request.|
|<a name="campaignreviewadextensions"></a>CampaignReviewAdExtensions|Include [Campaign Review Ad Extension](campaign-review-ad-extension.md) records in the download that each represent the association relationship between a campaign and a review ad extension. For [Review Ad Extension](review-ad-extension.md) records, you should include the ReviewAdExtensions value in the download request.|
|<a name="campaigns"></a>Campaigns|Include [Campaign](campaign.md) records in the download data.<br/><br/>New campaign types can be added anytime, so please be sure to leverage the [Campaign Type](campaign.md#campaigntype) and [Sub Type](campaign.md#subtype) fields to filter as needed.|
|<a name="campaignsimilarremarketinglistassociations"></a>CampaignSimilarRemarketingListAssociations|Include [Campaign Similar Remarketing List Association](campaign-similar-remarketing-list-association.md) records in the download that each represent the association relationship between a campaign and a similar remarketing list. For [Similar Remarketing List](similar-remarketing-list.md) records, you should include the SimilarRemarketingLists value in the download request.|
|<a name="campaignsitelinkadextensions"></a>CampaignSitelinkAdExtensions|Include [Campaign Sitelink Ad Extension](campaign-sitelink-ad-extension.md) records in the download that represents the association relationship between a campaign and a sitelink ad extension. For [Sitelink Ad Extension](sitelink-ad-extension.md) records, you should include the SitelinkAdExtensions value in the download request.|
|<a name="campaignstructuredsnippetadextensions"></a>CampaignStructuredSnippetAdExtensions|Include [Campaign Structured Snippet Ad Extension](campaign-structured-snippet-ad-extension.md) records in the download that represents the association relationship between a campaign and a structured snippet ad extension. For [Structured Snippet Ad Extension](structured-snippet-ad-extension.md) records, you should include the StructuredSnippetAdExtensions value in the download request.|
|<a name="campaigntargetcriterions"></a>CampaignTargetCriterions|Include [Campaign Age Criterion](campaign-age-criterion.md), [Campaign Company Name Criterion](campaign-company-name-criterion.md), [Campaign DayTime Criterion](campaign-daytime-criterion.md), [Campaign DeviceOS Criterion](campaign-deviceos-criterion.md), [Campaign Gender Criterion](campaign-gender-criterion.md), [Campaign Industry Criterion](campaign-industry-criterion.md), [Campaign Job Function Criterion](campaign-job-function-criterion.md), [Campaign Location Criterion](campaign-location-criterion.md), [Campaign Location Intent Criterion](campaign-location-intent-criterion.md), [Campaign Negative Location Criterion](campaign-negative-location-criterion.md), and [Campaign Radius Criterion](campaign-radius-criterion.md) records in the download data.|
|<a name="combinedlists"></a>CombinedLists|Include [Combined List](combined-list.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of combined lists for the current authenticated user. All combined lists that have Scope set to Customer are included. The combined lists that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a combined list is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="customaudiences"></a>CustomAudiences|Include [Custom Audience](custom-audience.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of custom audiences for the current authenticated user. All custom audiences that have Scope set to Customer are included. The custom audiences that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a custom audience is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="customerlists"></a>CustomerLists|Include [Customer List](customer-list.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of customer lists for the current authenticated user. All customer lists that have Scope set to Customer are included. The customer lists that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a customer list is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="dynamicsearchadlabels"></a>DynamicSearchAdLabels|Include [Dynamic Search Ad Label](dynamic-search-ad-label.md) records in the download that each represent a label applied to a dynamic search ad. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="dynamicsearchads"></a>DynamicSearchAds|Include [Dynamic Search Ad](dynamic-search-ad.md) records in the download data.<br/><br/>To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="expandedtextadlabels"></a>ExpandedTextAdLabels|Include [Expanded Text Ad Label](expanded-text-ad-label.md) records in the download that each represent a label applied to an expanded text ad. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="expandedtextads"></a>ExpandedTextAds|Include [Expanded Text Ad](expanded-text-ad.md) records in the download data.<br/><br/>To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="experiments"></a>Experiments|Include [Experiment](experiment.md) records in the download data.<br/><br/>To get all experiments from your account, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the experiments that use the specified base or experiment campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="feeditems"></a>FeedItems|Include [Feed Item](feed-item.md) records in the download data.<br/><br/>To get all feed items from your account, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. If you use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation, feed items will not be included in the download data.|
|<a name="feeds"></a>Feeds|Include [Feed](feed.md) records in the download data.<br/><br/>To get all feeds from your account, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. If you use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation, feeds will not be included in the download data.|
|<a name="filterlinkadextensions"></a>FilterLinkAdExtensions|Include [Filter Link Ad Extension](filter-link-ad-extension.md) records in the download data.<br/><br/>To get all filter link ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the filter link ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="flyeradextensions"></a>FlyerAdExtensions|Include [Flyer Ad Extension](flyer-ad-extension.md) records in the download data.<br/><br/>To get all flyer ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the flyer ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="imageadextensions"></a>ImageAdExtensions|Include [Image Ad Extension](image-ad-extension.md) records in the download data.<br/><br/>To get all image ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the image ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="images"></a>Images|Include [Image](image.md) records in the download data.|
|<a name="inmarketaudiences"></a>InMarketAudiences|Include [In Market Audience](in-market-audience.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of in-market audiences for the current authenticated user. All in-market audiences that have Scope set to Customer are included. The in-market audiences that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if an in-market audience is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="keywordlabels"></a>KeywordLabels|Include [Keyword Label](keyword-label.md) records in the download that each represent a label applied to a keyword. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="keywords"></a>Keywords|Include [Keyword](keyword.md) records in the download data.|
|<a name="labels"></a>Labels|Include [Label](label.md) records in the download data.<br/><br/>The [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation will ignore campaign scope and return all labels from your account's labels library. Likewise the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation will return all labels from your account's labels library.|
|<a name="locationadextensions"></a>LocationAdExtensions|Include [Location Ad Extension](location-ad-extension.md) records in the download data.<br/><br/>To get all location ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the location ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="negativekeywordlists"></a>NegativeKeywordLists|Include [Negative Keyword List](negative-keyword-list.md) records in the download data. The [Negative Keyword List](negative-keyword-list.md) records do not include negative keywords that are shared in each list. For [Shared Negative Keyword](shared-negative-keyword.md) records, you should include the SharedNegativeKeywords value in the download request.<br/><br/>The [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) will return all negative keyword lists from your account's negative keyword list library, whether or not the lists are associated with the specified campaigns .|
|<a name="portfoliobidstrategies"></a>PortfolioBidStrategies|Reserved.|
|<a name="priceadextensions"></a>PriceAdExtensions|Include [Price Ad Extension](price-ad-extension.md) records in the download data.<br/><br/>To get all price ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the price ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="productadlabels"></a>ProductAdLabels|Include [Product Ad Label](product-ad-label.md) records in the download that each represent a label applied to a product ad. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="productads"></a>ProductAds|Include [Product Ad](product-ad.md) records in the download data.<br/><br/>To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="productaudiences"></a>ProductAudiences|Include [Product Audience](product-audience.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of product audiences for the current authenticated user. All product audiences that have Scope set to Customer are included. The product audiences that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a product audience is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="promotionadextensions"></a>PromotionAdExtensions|Include [Promotion Ad Extension](promotion-ad-extension.md) records in the download data.<br/><br/>To get all promotion ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the promotion ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="remarketinglists"></a>RemarketingLists|Include [Remarketing List](remarketing-list.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of remarketing lists for the current authenticated user. All remarketing lists that have Scope set to Customer are included. The remarketing lists that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a remarketing list is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="responsiveadlabels"></a>ResponsiveAdLabels|Include [Responsive Ad Label](responsive-ad-label.md) records in the download that each represent a label applied to a responsive ad. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="responsiveads"></a>ResponsiveAds|Include [Responsive Ad](responsive-ad.md) records in the download data.<br/><br/>To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="responsivesearchadlabels"></a>ResponsiveSearchAdLabels|Include [Responsive Search Ad Label](responsive-search-ad-label.md) records in the download that each represent a label applied to a responsive search ad. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="responsivesearchads"></a>ResponsiveSearchAds|Include [Responsive Search Ad](responsive-search-ad.md) records in the download data.<br/><br/>To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|
|<a name="reviewadextensions"></a>ReviewAdExtensions|Include [Review Ad Extension](review-ad-extension.md) records in the download data.<br/><br/>To get all review ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the review ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="sharednegativekeywords"></a>SharedNegativeKeywords|Include [Shared Negative Keyword](shared-negative-keyword.md) records in the download data. Shared negative keywords belong to a negative keyword list. For [Negative Keyword List](negative-keyword-list.md) records, you should include the NegativeKeywordLists value in the download request.|
|<a name="similarremarketinglists"></a>SimilarRemarketingLists|Include [Similar Remarketing List](similar-remarketing-list.md) records in the download data.<br/><br/>The [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operations return the same set of similar remarketing lists for the current authenticated user. All similar remarketing lists that have Scope set to Customer are included. The similar remarketing lists that have Scope set to Account are also included if the user has access to view or manage those accounts. In other words, if a similar remarketing list is in account scope for an account that the user cannot access, then it is excluded from the download results.|
|<a name="sitelinkadextensions"></a>SitelinkAdExtensions|Include [Sitelink Ad Extension](sitelink-ad-extension.md) records in the download data.<br/><br/>To get all sitelink ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the sitelink ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="structuredsnippetadextensions"></a>StructuredSnippetAdExtensions|Include [Structured Snippet Ad Extension](structured-snippet-ad-extension.md) records in the download data.<br/><br/>To get all structured snippet ad extensions from your account's extension library, use the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) operation. To get only the structured snippet ad extensions that are associated with entities within the specified campaigns, use the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation.|
|<a name="textadlabels"></a>TextAdLabels|Include [Text Ad Label](text-ad-label.md) records in the download that each represent a label applied to a text ad. For [Label](label.md) records, you should include the Labels value in the download request.|
|<a name="textads"></a>TextAds|Include [Text Ad](text-ad.md) records in the download data.<br/><br/>To get all types of ads instead of requesting ads by type, you can include the Ads value in the download request.|

## Requirements
Service: [BulkService.svc v13](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
