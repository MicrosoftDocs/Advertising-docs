Universal Event Tracking (UET) is a useful way to track what happens after someone has clicked on your ad. Here, find some common user questions, tips, and best practices when getting started with UET:

## What is UET and how does it related to Conversion Tracking and Remarketing features?
Universal Event Tracking (UET) is a mechanism for advertisers to report user activity on their websites to Microsoft Advertising by installing one site-wide tag.         UET is a prerequisite for advertisers to track conversions and/or do remarketing. Once the UET tag is installed by the advertiser across their website,         the tag reports user activity on the advertiser website to Microsoft Advertising. Advertisers can then create conversion goals to specify which subset of user actions on the website qualify         to be counted as conversions. If Microsoft Advertising finds a match between a conversion goal and the user activity logged by the UET tag installed on their website, it counts a conversion.         Similarly, advertisers can create remarketing lists based on user activity on website and Microsoft Advertising matches the list definitions with UET logged user activity to put users into those lists.

[Learn more about conversion tracking](../hlp_BA_CONC_UETv2HowCTWorks.md)

[Learn more about remarketing](../hlp_BA_CONC_Remarketing_FAQ.md)

## Which tag management systems can I use when working with UET?
UET will work with all industry ready tag management systems. Here is the current list of (and links to instructions for) tested and supported tag managers:

- [Google Tag Manager](../hlp_BA_PROC_UET_TMS_GTM.md)
- [Qubit Opentag](../hlp_BA_PROC_UET_TMS_Qubit.md)
- [Tealium](../hlp_BA_PROC_UET_TMS_Tealium.md)
- [Ensighten](../hlp_BA_PROC_UET_TMS_Ensighten.md)
- [Signal](../hlp_BA_PROC_UET_TMS_Signal.md)
- [Adobe Dynamic Tag Manager](../hlp_BA_PROC_UET_TMS_AdobeDTM.md)
- [Adobe Launch](../hlp_BA_PROC_UET_TMS_AdobeLaunch.md)

## Which website platforms can I use when working with UET?
UET is designed to work with all major website platforms. Here is the current list of (and links to instructions for) tested and supported platforms that allow you to install UET tags:

- [BigCommerce](../hlp_BA_PROC_UET_WebPlatform_BigCommerce.md)
- [Shopify](../hlp_BA_PROC_UET_WebPlatform_Shopify.md)
- [WordPress.com](../hlp_BA_PROC_UET_WebPlatform_WordPress.md)
- [Wix](../hlp_BA_PROC_UET_WebPlatform_Wix.md)

## How do I validate if my UET tag is set up properly?
See [this troubleshooter](../hlp_BA_CONC_UET_TroubleshootCT.md) to find out how to validate if your UET tag is set up properly.

## Should I update my existing UET tags to the new syntax?
We recommend doing so to take advantage of the new syntax's benefits. [Learn more about the new syntax.](../hlp_BA_CONC_UETv2SyntaxUpdate.md)

## When should I be creating more than one UET tag?
See [Reasons for creating more than one UET tag](../hlp_BA_CONC_UETv2MutliTags.md) to find if you should create more than one UET tag.

## Are the tags SSL compliant? If so, how does it work?
Yes, the tags are SSL compliant. The way it works is that it reads the protocol of whatever page it's placed on (http or https) and matches the protocol.

## What data does UET collect once I install it on my website?
UET collects the following data and Microsoft Advertising retains it for 390 days. UET will also collect the IP address and the Microsoft cookie (with an expiration date of 13 months). This cookie contains a GUID assigned to the user’s browser, and/or an ID assigned to a user as long as it authenticated through their Microsoft account. In general, the cookie in the relevant domain and IP address are always passed with every http request and not just via UET. Microsoft Advertising doesn't resell this data to third parties or share it with other advertisers.

<table>
  <tr>
    <th scope="col">Parameter</th>
    <th scope="col">Value Passed</th>
    <th scope="col">Purpose</th>
  </tr>
  <tr>
    <th scope="row">ea</th>
    <td>Event action (custom value passed by advertiser)</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">ec</th>
    <td>Event category (custom value passed by advertiser)</td>
    <td>These are needed if advertiser chooses to use custom events for conversion tracking or remarketing.</td>
  </tr>
  <tr>
    <th scope="row">el</th>
    <td>Event label (custom value passed by advertiser)</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">ev</th>
    <td>Event value (custom value passed by advertiser)</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">evt</th>
    <td>Event type (page load or custom)</td>
    <td>Distinguishes page load event from custom events.</td>
  </tr>
  <tr>
    <th scope="row">gc</th>
    <td>Variable revenue currency (custom value passed by advertiser)</td>
    <td>Needed if advertiser chooses to track variable revenue.</td>
  </tr>
  <tr>
    <th scope="row">gv</th>
    <td>Variable revenue (custom value passed by advertiser)</td>
    <td>Needed if advertiser chooses to track variable revenue.</td>
  </tr>
  <tr>
    <th scope="row">ifm</th>
    <td>1</td>
    <td>A value of 1 indicates that the tag is being fired from within an iFrame.</td>
  </tr>
  <tr>
    <th scope="row">kw</th>
    <td>Keyword</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">lg</th>
    <td>Browser language setting</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">lt</th>
    <td>Page load time</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">mid</th>
    <td>GUID generated by UET tag</td>
    <td>Used to relate page load and any custom events passed with each other.</td>
  </tr>
  <tr>
    <th scope="row">msclkid</th>
    <td>
      <para>Ad select information, generated at ad select time and appended to the landing page URL when auto-tagging of Microsoft Click ID is enabled.</para>
      <para>Format: GUID followed by extra byte indicating whether the current value is a new one (unique to that session), as in "cdd4afcccb1c9a4cad9544dd7e5006d5-1". Note:
				<ul><li>This value will be "N" if cookies are blocked by the browser or no ad select information exists in cookie, and the msclkid parameter <strong>isn't</strong> in the landing page URL.</li><li>The Microsoft Click ID will have "1N" added to the end if cookies are blocked by the browser and the msclkid parameter <strong>is</strong> in the landing page URL.</li></ul></para>
      <para>Cookie name: _uetmsclkid</para>
      <para>Cookie expiration date: 90 days</para>
    </td>
    <td>Microsoft Click ID, which is used to improve the accuracy of conversion tracking. Note: UET sets a first-party cookie on your site’s domain for this parameter. 
			</td>
  </tr>
  <tr>
    <th scope="row">p</th>
    <td>URL of the page </td>
    <td>Identifies webpage.</td>
  </tr>
  <tr>
    <th scope="row">pi</th>
    <td>Digital signature - one way hash of tl, lt, lg, sc, sh, sw.</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">r</th>
    <td>Referrer URL</td>
    <td>Identifies referrer URL.</td>
  </tr>
  <tr>
    <th scope="row">rn</th>
    <td>Random number</td>
    <td>Handles browser cache.</td>
  </tr>
  <tr>
    <th scope="row">sc</th>
    <td>Screen color depth</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">sh</th>
    <td>Screen height</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">sid</th>
    <td>Session ID</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">sv</th>
    <td>Subversion</td>
    <td>Identifies the version of UET.</td>
  </tr>
  <tr>
    <th scope="row">sw</th>
    <td>Screen width</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row">ti</th>
    <td>UET tag ID</td>
    <td>Identifies tag.</td>
  </tr>
  <tr>
    <th scope="row">tl</th>
    <td>Page title</td>
    <td>Used to construct digital signature so that we can detect fraud. </td>
  </tr>
  <tr>
    <th scope="row">uid</th>
    <td>User ID</td>
    <td>A unique, non-personally identifiable ID representing a signed-in user. Advertisers may choose to store the user ID in a first-party cookie named "_uetuid". It'll be automatically read when UET events fire.</td>
  </tr>
  <tr>
    <th scope="row">ver</th>
    <td>Version</td>
    <td>Identifies the version of UET.</td>
  </tr>
  <tr>
    <th scope="row">vid</th>
    <td>Visitor ID</td>
    <td>A unique, anonymized visitor ID, assigned by UET, representing a unique visitor. UET stores this data in a first-party cookie named "_uetvid".</td>
  </tr>
</table>

If you do not want the UET tag to set any first-party cookies, you can opt-out by including the following parameter in your UET tracking code: **storeConvTrackCookies:false**

**Example:**

Here is what this opt-out code looks like within your UET tracking code:

&lt;script&gt;(function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"TAG_ID_HERE", **storeConvTrackCookies:false**};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&amp;&amp;s!=="loaded"&amp;&amp;s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");&lt;/script&gt;

> [!NOTE]
> For additional details about Microsoft privacy policies for usage of data, please refer to [Microsoft Privacy Statement](https://go.microsoft.com/fwlink?LinkId=517636). Also note that we will not be reselling the data we collect via UET to third parties and/or share it with other advertisers using Microsoft Advertising.

## What cookies does UET use?
The following table lists the cookies that UET stores or accesses in your browser. Microsoft Advertising doesn't resell this data to third parties or share it with other advertisers.

|Cookie ID|Cookie Description|
|---|---|
|MUID|This is a Microsoft cookie that contains a GUID assigned to your browser. It gets set when you interact with a Microsoft property, including a UET beacon call or a visit to a Microsoft property through the browser.|
|_uetmsclkid|This is the Microsoft Click ID, which is used to improve the accuracy of conversion tracking.		   		  **Note:**  UET sets a first-party cookie on your site’s domain for this parameter. When auto-tagging of the Microsoft Click ID is enabled, the ad click information is generated at ad click time and appended to the landing page URL.|
|_uetsid|This contains the session ID for a unique session on the site.|
|_uetvid|UET assigns this unique, anonymized visitor ID, representing a unique visitor. UET stores this data in a first-party cookie.|

## How can I mark first-party cookies set by UET as secure?
If your website enforces the https protocol for all pages, you can modify your UET tag to mark first-party cookies as secure. Just add the highlighted code to the base UET tag on each page of your website:

&lt;script&gt;(function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"TAG_ID_HERE", **cookieFlags: "SameSite=None;Secure"**};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&amp;&amp;s!=="loaded"&amp;&amp;s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");&lt;/script&gt;

> [!IMPORTANT]
> This change will break UET functionality if any part of your site is not using the https protocol.

## How can I stop UET events from being fired for users who request to restrict data sharing?
Set the cookie named "_uetmsdns" with a value of 1. Advertisers are responsible for setting this cookie, and it must be set in a first-party context (for example, in the advertiser's domain, such as contoso.com). This cookie is read by the client-side UET JavaScript during runtime, and if the value is set to 1, no UET events will fire.

## Does the tag use browser caching and does it have an expiration date?
Yes, it leverages browser caching with an expiration time of 30 minutes.

## I received the following warning message in Google Chrome: "A cookie associated with a cross-site resource at http://bat.bing.com/ was set without the 'SameSite' attribute." What does this mean?
This is a temporary warning, and clearing your browser's cookies should resolve it. It has no impact on your website or conversion tracking functionality for your website.


