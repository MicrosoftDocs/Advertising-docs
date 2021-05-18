---
title: Customer match: Use your own data to find customers
description: Learn how to upload your own customer match lists to Microsoft Advertising and then target this audience.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Customer match: Use your own data to find customers

With customer match, use the email addresses your customers have shared with you to reengage with them across the Microsoft Search Network and Microsoft Audience Network.

- **Boosted performance** . Use your complete user understanding, including offline data, to retarget customers who are more likely to convert.
- **Full control and flexibility over the customer data that’s uploaded** . You decide how to use your own first-party data – build and modify any number of lists to help you reach your business goals.
- **Streamlined management** . Use your existing segmentation and Customer match lists by uploading them to your Microsoft Advertising account.

Use your customer match lists to grow brand awareness, increase conversions by reengaging with them, or tailor messaging to upsell or cross-sell other products and services. You can also use your lists as exclusions to ensure you’re only engaging with potential new customers. Some example Customer match list use cases include:

- Loyalty programs
- Credit card holders
- Rewards club members
- Newsletter subscribers
- Greatest lifetime value
- Recent purchasers
- Highest spend potential

Customer match is not allowed for sensitive content categories, products, or services. Additional information about our remarketing policy can be found on the [remarketing policy page](https://go.microsoft.com/fwlink?LinkId=852540).

Third-party user data cannot be used for customer match. If you are currently working with a DMP and would like to use that data in your Microsoft Advertising campaigns, check out [custom audiences](./hlp_BA_CONC_Audiences_CustomAudience.md). If your DMP is not supported, you can export the data and then upload it as a customer match list.

## Preparing customer match lists

To get started with customer match, you must first prepare your customer list. A customer list is contact information that you have compiled to enable customer match. The requirements for the list are:

- Files must be in a .csv format. A template file is available during customer match list setup.
- Each email address per user must be contained within its own cell (row and column)
- Set the column header (first line in the file) to "Email," and then provide email addresses in the lines below.
- The list should have at least 300 active email users if being used for targeting across both the Microsoft Search Network and Microsoft Audience Network.
- Each customer list file can containt up to 1 million entries per upload. To apply 10 million email addresses to one customer match list, you must upload 10 files separately. If the active user match rate is 30%, the final audience size shown in Microsoft Advertising would be 3 million.

For the privacy of your customers, the personal customer data in your file (email addresses) must be encrypted i.e., hashed. We recommend that you hash your data before you submit the file in Microsoft Advertising. If you choose to upload your list in plain text, the personal customer data in your file (email addresses) will be encrypted on your computer before it is sent to Microsoft Advertising.

## Using customer match lists

Once you have your customer list in a file, you can create a new audience for targeting.

1. From the global menu at the top of the page, choose **Tools** and then **Audiences** under the Shared library menu.
1. Select **Create audience**.
1. Give this audience a unique name.
1. For **Type**, select **Customer list**.
1. Select **Next**.
1. Choose **Plain text** or **Hashed file**.
1. Select the checkbox confirming that you will comply with the listed policies and terms.
1. Choose the membership duration and description (optional), and then select **Next**.
1. Preview the changes and then select **Apply changes** to start the upload.

Customer match lists are ready to be associated with campaigns and ad groups 48 hours after upload.
## Associate the audience with campaigns and ad groups

Customer lists are just one of our [audience targeting options](./hlp_BA_CONC_Audiences_Options.md). Once you have created or selected an audience, you need to associate it with an ad group or campaign, or with multiple ad groups or campaigns. The association can increase bids for, target, or exclude the people included in your audience.

[Learn more about associating audiences with ad groups or campaigns](./hlp_BA_CONC_Audiences_AssociateAdGroup.md).


