---
title: Using the JavaScript UET tag tracking code
description: After you create a UET tag, the next step is to add the UET tag tracking code to your website.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Using the JavaScript UET tag tracking code

Before you can track conversions or target audiences using a remarketing list, you need to create a UET tag in Microsoft Advertising and then add the UET tag tracking code to every page of your website. We strongly recommend that you use JavaScript to ensure accurate conversion tracking.

## What are the advantages of using JavaScript?

- The tag updates automatically when we receive any changes to the UET tag tracking code.
- JavaScript allows Microsoft Advertising to collect richer activity data to ensure accurate conversion tracking as well as improve remarketing in paid search.

## What does the JavaScript tag look like?

A JavaScript tracking code allows Microsoft Advertising to collect richer activity data that improves conversion tracking and remarketing in paid search. The only time you shouldn't use this is if your website has rules that prohibit JavaScript from being installed on it.

Here is an example of the JavaScript UET tag tracking code:

&lt;script&gt;           (function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[]          ,f=function(){var o={ti:"TAG_ID_HERE"};          o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")}          ,n=d.createElement(t),n.src=r,n.async=1,n.onload=n          .onreadystatechange=function()          {var s=this.readyState;s          &amp;&amp;s!=="loaded"&amp;&amp;          s!=="complete"||(f(),n.onload=n.          onreadystatechange=null)},i=          d.getElementsByTagName(t)[0],i.          parentNode.insertBefore(n,i)})(window,document,"script","          //bat.bing.com/bat.js","uetq");           &lt;/script&gt;   

## Single-page application (SPA) websites

If your website is built as single-page application (SPA), additional changes are required to ensure UET is working on pages where the content is loaded dynamically without a traditional full-page load. Please refer to [this site](https://go.microsoft.com/fwlink?LinkId=2007421) for detailed instructions and to view code samples in action.

 
> [!NOTE]
> Don't know what UET is? See [What is UET and how can it help me?](./hlp_BA_CONC_UETv2WhatIsTag.md)


