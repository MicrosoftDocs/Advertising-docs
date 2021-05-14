---
title: Signing in with a work account
description: If you want to restrict access to only authenticated individuals at your company, you can require users to sign in with a work account.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Signing in with a work account

> [!IMPORTANT]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.

Most users sign in to Microsoft Advertising with a Microsoft account, which is a single user name and password that connects a user to various Microsoft products and services. Each Microsoft account is assigned for personal use, even if the user only manages advertising accounts for work. However, your IT department may restrict access to company assets, including data that's stored in third-party tools such as Microsoft Advertising.

To help those corporate users enforce their IT policies, Microsoft Advertising now offers the ability to restrict sign-in to only work accounts that are authenticated by Azure Active Directory.

## Azure Active Directory in a nutshell

Azure Active Directory is Microsoft's cloud-based identity and access management service. It's used by IT departments to administer user names and corporate access at a global scale.

## Benefits to requiring access with a work account

There are several benefits to requiring a work account to access Microsoft Advertising.

- Users can use their existing work credentials to sign in, thereby eliminating the need to have another set of user names for Microsoft Advertising.
- Get seamless access with single sign-on (SSO), if it's enabled by your IT department.
- Easier access management: For example, if an employee leaves your company, then that person loses access to Microsoft Advertising when their work account is deactivated.
- Help keep your Microsoft Advertising account in compliance with your company's IT standards.

> [!NOTE]
> Enabling this feature is optional. It's geared towards companies that use Azure Active Directory to authenticate users on their network. As you assess whether this feature is right for you, here are a few things to consider:
> 
> - Third-party tool providers don't yet support Azure Active Directory authentication for Microsoft Advertising. If you implement this feature before your tool provider is ready, you may lose access to your third-party software. Check with your tool provider on when they'll support this feature.
> - If you're a small business that uses a personal account (such as Gmail, Outlook, or Yahoo) for a business address, you can ignore this feature and continue signing in with that personal account.
> - To enable this feature, you must use Azure Active Directory.

## Implementation: How to require access with a work account

## Switching your user type to a work account
If you're a Super Admin who wants to enable this feature, you'll first need to switch your user type to a work account before you require all other users to sign in with a work account. Once the feature is enabled, all other users will be prompted to switch to a work account as follows.

1. [!INCLUDE [PreferencesMySettings](./includes/PreferencesMySettings.md)]
1. Next to **User type**, select **Switch to a work account**, and follow the instructions on the screen.

## Reverting your user type to a personal account
If you need to revert your user type from work account to a personal account, please [contact support](https://go.microsoft.com/fwlink?LinkId=398371).

## Enabling sign-in with a work account
To enable this feature, you must be a Super Admin who already signs in with a work account. If you haven't done so, you'll first need to switch your user type to a work account.

1. Select **Tools** from the global menu, and then select **Account access** to go to **User management**.
1. Next to **Require sign-in with a work account**, slide the switch to the right to turn on this feature.

Once you enable this feature, your users will be prompted to confirm their work account the next time they sign in. If a user provides an email address that's not authenticated by Azure Active Directory, then that user will be blocked. See the following section on how to manage users once this feature is enabled.

## Disabling sign-in with a work account
To disable this feature, you must be a Super Admin.

1. Select **Tools** from the global menu, and then select **Account access** to go to **User management**.
1. Next to **Require sign-in with a work account**, slide the switch to the left to turn off this feature.

## Managing access with a work account

You'll need to keep a few things in mind to make sure that users don't lose access to Microsoft Advertising when you require signing in with a work account.

## How can I tell who has been blocked from accessing Microsoft Advertising?
You'll see a label that reads **Blocked** within the user's tile in **Users**.

## One of my users is blocked. What do I do next?
You'll need to provide a work account to your user if they don't have one. If they do have one, then they'll be prompted at sign-in to choose whether they want to continue signing in with their work account or with their personal account. Be sure that they choose the option to sign in with a work account.

## How can I tell what a user signs in with?
In **Users**, you'll see **Signs in with** for each user. There, it notes whether a user is signing in with a personal account or a work account.

## A work account that's authenticated by Azure Active Directory is classified as a personal account. Can that be fixed?
Yes. Users will be prompted to sign in with their work account once they click **Switch now**. Note: some users may have to sign in first with their personal accounts before they can provide a new work account when switching credentials.


