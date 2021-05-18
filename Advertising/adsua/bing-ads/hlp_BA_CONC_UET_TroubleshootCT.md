---
title: Why am I not recording conversions or tracked revenue?
description: Not seeing conversions after setting up conversion tracking? Troubleshoot issues here.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Why am I not recording conversions or tracked revenue?

If you have [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md) set up, but you aren't finding conversions or tracked revenue in Microsoft Advertising, follow this troubleshooter.

## Before anything else, check these two things

- **Has it been more than 24 hours since you set up this UET tag or this conversion goal?**   			It can take up to 24 hours for Microsoft Advertising to receive data from a new UET tag or conversion goal. Wait until 24 hours have passed and check again.
- **What is your conversion goal's tracking status?**   			From the global menu at the top of the page, click **Tools**&nbsp;&gt;&nbsp;**Conversion goals** and check the **Tracking status** column for this conversion goal.
   - Tracking status is **"Unverified"** or **"Tag inactive"**: Follow the steps in next section of this article.
   - Tracking status is **"No recent conversions"**: Follow the steps in [this section](#NoRecentConvs) of the article.

## Tracking status is "Unverified" or "Tag inactive"

<table>
  <tr>
    <th colspan="2">Have you added the UET tag to your website's code?</th>
  </tr>
  <tr>
    <td><strong>No</strong> </td>
    <td>Your UET tag must be inserted into the code of each page of your website for conversion tracking to work. For instructions, refer to the "Add the tag to your website" section of [this article](./hlp_BA_CONC_UET_Setup_Master.md).</td>
  </tr>
  <tr>
    <td><strong>Yes</strong> </td>
    <td>There are three likely scenarios:
					<ul><li>You didn't add the UET tag to every page of your website.</li><li>You didn't add the UET tag correctly.</li><li>You added the wrong UET tag.</li></ul><para>To investigate, use the UET Tag Helper browser extension:
						<ol><li>Install the browser extension following the instructions in [this article](./hlp_BA_CONC_UET_TagHelper.md).</li><li>In Microsoft Edge or Google Chrome, go to a webpage that features a conversion event for your goal, and then click the UET Tag Helper icon.</li><li>In UET Tag Helper, flip the switch to <strong>On</strong>, refresh the browser page, and then click the UET Tag Helper icon again.</li><li>Review the UET Tag Helper icon status. The number shows how many times there was a UET tag request from the webpage and the number's surrounding color shows the status.
								
									
										<table><tr><td style="min-width:120px; text-align:center">![UET Tag Helper icon showing no tags on webpage](../images/BA_ScreenCap_UEtTagManagerNoTags.png)</td><td style="vertical-align:middle">If no number appears, either there is no UET tag in the webpage's code or there is an incorrectly installed UET tag. Review your webpage's code and make sure your UET tag is installed properly.</td></tr><tr><td style="min-width:120px; text-align:center">![UET Tag Helper icon showing number of valid tags](../images/BA_ScreenCap_UETTagManagerGoodTags.png)</td><td style="vertical-align:middle">If you see a green number, there is a functioning UET tag on the page, but it may be the wrong UET tag. Click the browser extension and check the <strong>Tag ID</strong>. If it doesn't match the UET tag ID you're expecting, update the ID in either your conversion goal or the UET tag in your website's code. </td></tr><tr><td style="min-width:120px; text-align:center">
												![UET Tag Helper icon showing number of tags with issues](../images/BA_ScreenCap_UETTagHelperYellowTag.png)
												![UET Tag Helper icon showing number of tags that are not valid](../images/BA_ScreenCap_UETTagHelperRedTag.png) 												
												</td><td style="vertical-align:middle">If you see a yellow or red number, there are issues with the UET tag. Click the browser extension, verify that the <strong>Tag ID</strong> matches the UET tag ID you're expecting to be used, and then follow the instructions in the helper. </td></tr></table></li></ol></para></td>
  </tr>
</table>

<anchor id="NoRecentConvs" />

## Tracking status is "No recent conversions"

<table>
  <tr>
    <th>First, check your conversion goal settings</th>
  </tr>
  <tr>
    <td>
      <para>
        <expando_list multiple="true">
          <expando expanded="false">
            <expando_head>
					Where to find conversion goal settings
				  </expando_head>
            <expando_content>
              <ol>
                <li>In Microsoft Advertising, click <strong>Campaigns</strong> at the top of the page, and then, in the left pane, click <strong>Conversion Tracking</strong> and then <strong>Conversion goals</strong> (or from the global menu at the top of the page, click <strong>Tools</strong> and then <strong>Conversion goals</strong>).</li>
                <li>Select the conversion goal you want to check.</li>
                <li>Click <strong>Edit</strong>&nbsp;&gt;&nbsp;<strong>Edit goal</strong>.</li>
                <li>Click <strong>Next</strong> to get to the <strong>Goal details</strong> page.</li>
              </ol>
            </expando_content>
          </expando>
        </expando_list>
        <ul>
          <li><strong>Is the goal scoped to the correct account?</strong>  
				For <strong>Scope</strong>, verify that this conversion goal is scoped to the account in which you're expecting to see conversions.</li>
          <li><strong>Is the goal's conversion window constraining you?</strong>  
				For <strong>Conversion window</strong>, verify that your window is wide enough to reasonably expect conversions. (Keep your conversion window setting in mind as you go on to the next step.)</li>
          <li><strong>Is your conversion goal enabled?</strong>   
				From the global menu at the top of the page, click <strong>Tools</strong>&nbsp;&gt;&nbsp;<strong>Conversion goals</strong> and check the <strong>Status</strong> column for this conversion goal. If its status is <strong>Removed</strong>, change it to <strong>Enabled</strong>.</li>
        </ul>
      </para>
    </td>
  </tr>
  <tr>
    <th>Second, verify you're getting enough clicks</th>
  </tr>
  <tr>
    <td>
      <para>
        <ol>
          <li>Click <strong>All campaigns</strong> (or <strong>Back to campaigns</strong>) and then <strong>Overview</strong>. </li>
          <li>In the <strong>Performance</strong> tile, check how many clicks you've received in your goal's conversion window. </li>
          <li>Consider: Are you getting enough clicks to reasonably expect conversions?
					<ol><li>If you're not, try improving your ads, building up your keyword lists, or widening your targeting. Learn more about [creating effective ads](./hlp_BA_CONC_AboutWritingEffectiveAds.md) and [improving keyword lists](./hlp_BA_CONC_NewAd_BuildCampaign_Keywords.md). </li><li>If you are, continue to the next step.</li></ol></li>
        </ol>
      </para>
    </td>
  </tr>
  <tr>
    <th>Third, test your conversion goal with UET Tag Helper</th>
  </tr>
  <tr>
    <td>UET Tag Helper can now test your conversion goals. Show it which conversion you want to test and then navigate your website, and it will tell you what conversion events it records and what problems it encounters.
		<para><ol><li>Make sure you have UET Tag Helper installed. If not, follow the instructions in [this article](./hlp_BA_CONC_UET_TagHelper.md).</li><li>From the global menu at the top of the page in Microsoft Advertising, click <strong>Tools</strong>&nbsp;&gt;&nbsp;<strong>Conversion goals</strong>.</li><li>Hover over the <strong>Tracking status</strong> for this conversion goal and click <strong>Test this conversion goal</strong>. </li><li>Click the UET Tag Helper icon in your browser's extension menu.</li><li>Enter your landing page URL in the helper and click <strong>Start test</strong>.</li><li>Navigate through your website and attempt to trigger your conversion goal event.</li><li>When you see either <strong>Conversion found</strong> or <strong>Problem encountered</strong>, click <strong>View report</strong> for a summary of what was passed back to Microsoft Advertising.</li><li>For the <strong>Problems encountered</strong>, follow the instructions in the report to fix the issues.</li><li>Wait at least 24 hours and then check to see if you're recording conversions and variable revenue accurately.</li></ol></para></td>
  </tr>
</table>


