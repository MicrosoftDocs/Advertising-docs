---
title: Track mobile app installs as conversions
description: Find out how to track every time someone installs your app as a conversion.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Track mobile app installs as conversions

What happens after a customer clicks on your app install ad or app extension? When you create a conversion goal to track mobile app installs you’ll discover:

- The ad campaigns that are most effective
- The keywords that lead to better conversions
- The ROI of your advertising dollars
- The audiences that have higher conversions
- How many people install your app

With mobile app install goals, you'll use the app-specific URL that is provided by a Microsoft Advertising-certified partner. Universal Event Tracking (UET) tags are not required or supported for mobile app installs. One conversion goal is required per app platform for each app, per manager account. Keep in mind that Microsoft Advertising treats both **app URL** and **measurement URL** the same way, so even if you don’t manually set up a conversion goal, your app install ad or app extension will still be tracked.

All you have to do is create an [app extension](./hlp_BA_CONC_AdExtensionAppExtension.md) or an [app install ad](./hlp_BA_CONC_AppInstallAds.md), and then create a mobile app install conversion goal.

 
## Create a measurement URL

Microsoft Advertising partners with third-party companies to help you create tracking/measurement URLs. Each partner has a template of exactly what Microsoft Advertising expects the tracking/measurement URL to look like, and the only mandatory parameter required is the **MSCLKID**.

You’ll need one measurement URL for each respective app in the app store. Visit one of the following sites to create an app-specific measurement URL to track installs from app extensions and app install ads as conversions:

- [Kochava](https://go.microsoft.com/fwlink?LinkId=526947)
- [Tune](https://go.microsoft.com/fwlink?LinkId=2161607)
- [Appsflyer](https://go.microsoft.com/fwlink?LinkId=526951)
- [Singular](https://go.microsoft.com/fwlink?LinkId=2006381)
- [Adjust](https://go.microsoft.com/fwlink?LinkId=836812)
- [Branch](https://go.microsoft.com/fwlink?LinkId=2074143)

 
## Create a conversion goal for mobile app installs

Now that you have your measurement URL and other tracking details prepared, you can create a mobile app install goal.

1. [!INCLUDE [ConversionGoals](./includes/ConversionGoals.md)]
1. Enter a name for your goal, select **Mobile app install**, and then select **Next**.
1. Select the **App platform** and then enter the **App ID**.
1. Optional: You can assign a **Revenue value** to set how much each conversion is worth to your business. Note: Variable revenue is not supported.
1. Optional: You can enter a **Conversion period** to track up to 90 days in the past.
1. [!INCLUDE [SelectSave](./includes/SelectSave.md)]

 
## How a mobile app install is tracked

- Once you enter a measurement URL from the partner, Microsoft Advertising appends a parameter called **MSCLKID** to that URL during ad delivery. When someone taps on your ad to install the app, the call goes to the partner which logs the **MSCLKID** and redirects to the app store.
- After your app is installed and opened for the first time, the partner is notified and attributes the conversion.
- The partner uploads conversion goal data back to Microsoft Advertising using the **clickID** and **appID** as the keys.
- Microsoft Advertising identifies the goals associated with the **app ID**, checks if the clicks are in the conversion window, and associates the conversion with the app extension.

 
## Remove an app install conversion goal

When you include app installs as conversions, it will create a goal for you. If you decide to not include app installs as conversions later, keep in mind the goal must be disabled through **Tools** > **Conversions** > ** Edit conversion goal**, and then uncheck **Include in Conversions**. If you decide not to report app installs, enter the app URL from the Windows Store, the Windows Phone Store, the Apple App Store, or Google Play.


