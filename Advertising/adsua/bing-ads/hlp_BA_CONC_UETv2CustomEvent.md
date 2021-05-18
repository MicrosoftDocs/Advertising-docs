---
title: How to track custom events with UET
description: Learn how to create custom events that allow you to track more than one type of conversion for a single webpage.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How to track custom events with UET

Microsoft Advertising allows you to track custom events on your website, such as when people subscribe to a newsletter or download a white paper, as conversions.     To learn more, see [Why track custom events](./hlp_BA_PROC_UETv2TrackCustomEvent.md).

## Requirements

Before you start setting up custom events, make sure you have:

- **A JavaScript UET tag** : [Create a Microsoft Advertising UET tag](./hlp_BA_PROC_UETv2CreateTag.md) and [add the UET tag tracking code to every page of your website](./hlp_BA_PROC_UETv2AddTag.md).
   - JavaScript is required to ensure you have access to the full functionalities of conversion tracking and remarketing.  If you are using a non-JavaScript tag, please switch over to a JavaScript tag.

- **The ability to edit website code** : Make sure that either you or your webmaster can edit your website code.

## How to set up custom events

## Step 1: Add the UET tag tracking code to your website
> [!NOTE]
> Do you use Google Tag Manager? Check out [Set up UET tags using Google Tag Manager](./hlp_BA_PROC_UET_TMS_GTM.md).
> Do you use a different tag manager? Take a look at the "Add the UET tag tracking code using a tag manager" section of [this article](./hlp_BA_PROC_UETv2AddTag.md).
> Do you use a website-hosting service? Take a look at the "Add the UET tag tracking code using your website platform" section of [this article](./hlp_BA_PROC_UETv2AddTag.md).

1. In the left navigation pane of Microsoft Advertising, click **Conversion Tracking** and then **UET tags** (or from the global menu at the top of the page, click **Tools** and then **UET tags**).
1. Find the tag you want to use and, in the **Action** column, click **View tag**.
1. Click **Copy**.
1. In your website's code, paste the tag in one of the following locations:
```
```<head>```Your page title  
// Option 1: Insert your UET tag here, between the "```head```" tags.

 ```</head>```  ```<body>```  					   
// Option 2: Insert your UET tag here, right after beginning of the "```body```" tag.

    ... ```<button>```Download now```</button>```    ... ```</body>```
```

## Step 2: Create a conversion goal or remarketing list
- Creating a conversion goal for a custom event:
   1. In the left navigation pane of Microsoft Advertising, click **Conversion Tracking** and then **Conversion goals** (or from the global menu at the top of the page, click **Tools** and then **Conversion goals**).
   1. Click **Create conversion goal**.
   1. Give your conversion goal a name, select **Event** for **Type**, and then click **Next**.
   1. Choose the parameters to report when logging custom events by assigning each one you want to use a text string or numeric value. The possible parameters are:
      - **Category** : The category of the event you want to track. Let's say you want to track downloads of a document on a page of your site. For this example, the category could be "```downloads```".
      - **Action** : The type of user interaction you want to track. For our example, "```downloadbuttonclick```".
      - **Label** : The name of the element that caused the action. For our example, "```document05```".
      - **Value** : A numerical value associated with that event. For our example, the number of pages in the document: "4".  						  The event value can be any value from 0 to 9999999 to 3 decimal places.

> [!NOTE]
> You'll customize your UET tag tracking code to match the values defined here (this is discussed in Step 3). This will allow Microsoft Advertising to match these values with the custom events being logged via UET to count them as conversions.

   1. Select the **Revenue value**, **Count**, and **Conversion window** for this custom event goal.
   1. For **UET tag**, select the UET tag that you added to your website in Step 1.
   1. Click **Save**.

> [!NOTE]
> Every action that we detect that matches your conversion goal will be counted as one conversion.

- Creating a remarketing list for a custom event:
   1. In the left navigation pane of Microsoft Advertising, click **Shared Library** and then **Audiences** (or from the global menu at the top of the page, click **Tools** and then **Audiences**).
   1. Click **Create audience**.
   1. Name your remarketing list, select **Remarketing list**, and then click **Next**.
   1. For **Whom to add to your audience**, select **Custom events**.
   1. Choose the parameters to report when logging custom events by assigning each one you want to use a text string or numeric value. The possible parameters are:
      - **Category** : The category of the event you want to track. Let's say you want to track downloads of a document on a page of your site. For this example, the category could be "```downloads```".
      - **Action** : The type of user interaction you want to track. For our example, "```downloadbuttonclick```".
      - **Label** : The name of the element that caused the action. For our example, "```document05```".
      - **Value** : A numerical value associated with that event. For our example, the number of pages in the document: "4".  						  The event value can be any value from 0 to 9999999 to 3 decimal places.

> [!IMPORTANT]
> You'll customize your UET tag tracking code to match the values defined here (this is discussed in Step 3). This will allow Microsoft Advertising to match these values with the custom events being logged via UET to count them as conversions.

   1. Set the **Membership duration** to tell Microsoft Advertising how far back in time to look for actions that match your remarketing list definition in order to add people to your list.
   1. For **Tag name**, select the UET tag that you added to your website in Step 1.
   1. Click **Save**.
   1. [Associate this remarketing list with an ad group](./hlp_BA_CONC_Audiences_AssociateAdGroup.md)

## Step 3: Modify the UET tag tracking code in your website
Following on our example in Step 2, let's say that the custom event you want to track on your webpage is **people clicking the "Download now" button**  (this would be an **Action** event, as discussed above).
1. Add the following custom event JavaScript below the UET tag that you added to your webpage's code in Step 1:
```
```<head>```Your page title  ```</head>```	  					```<body>``` 
 // Let's say this is where you pasted the UET tag in Step 1.

 ```<script>```Your UET tag is here.```</script>```   
 // Here is where to paste the following JavaScript:   	```<script>   								   window.uetq = window.uetq || [];      window.uetq.push ('event', 'Replace_with_Event_Action', {'event_category': 'Replace_with_Event_Category', 'event_label': 'Replace_with_Event_Label', 'event_value': 'Replace_with_Event_Value'});   </script>```

      ... ```<button>```Download now```</button>```      ... ```</body>```
```

1. Give this code snippet a function name. The function name can be anything, as long as it hasn't already been used in your website. In this example, we're naming it "```GetCustomEvent()```":
```
```<head>```Your page title  ```</head>```	  					```<body>``` ```<script>```Your UET tag is here.```</script> ```  						```<script>		```
   ```function GetCustomEvent() {```

```   window.uetq = window.uetq || [];      window.uetq.push ('event', 'Replace_with_Event_Action', {'event_category': 'Replace_with_Event_Category', 'event_label': 'Replace_with_Event_Label', 'event_value': 'Replace_with_Event_Value'});  ```
   ```}```

```</script>```       ... ```<button>```Download now```</button>```							     ...							 ```</body>```
```

1. You now need to customize your webpage's code to call this function when the appropriate action occurs. In our example, the custom event is a click of the "Download now" button, so we'd need to add a call in the button's code:
```
```<head>```Your page title  ```</head>```	  					```<body>``` ```<script>```Your UET tag is here.```</script> ```  ```</script> ```  							```<script>		```   													   ```function GetCustomEvent() {```  							```   window.uetq = window.uetq || [];      window.uetq.push ('event', 'Replace_with_Event_Action', {'event_category': 'Replace_with_Event_Category', 'event_label': 'Replace_with_Event_Label', 'event_value': 'Replace_with_Event_Value'});  ```  							   ```}```  							```</script>``` 							     ...							 ```<button
<c_data><![CDATA[<font color="ff0027" size="2">OnClick="GetCustomEvent()"</font>]]></c_data>
>```Download now```</button>```							     ...							 ```</body>```
```

1. Note the four different parameters in the custom event JavaScript: ```'event'```, ```'event_category'```, ```'event_label'```, and ```'event_value'```. These correspond to the parameters you had the option to define for your custom event conversion goal in Step 2. In the JavaScript you added, the parameters have placeholder values assigned to them:
```
```<head>```Your page title  ```</head>```	  					```<body>``` ```<script>```Your UET tag is here.```</script> ```  ```</script> ```  							```<script>		```   													   ```function GetCustomEvent() {```  							```   window.uetq = window.uetq || [];      window.uetq.push ('event', '
<c_data><![CDATA[<font color="ff0027" size="2">Replace_with_Event_Action</font>]]></c_data>
', {'event_category': '
<c_data><![CDATA[<font color="ff0027" size="2">Replace_with_Event_Category</font>]]></c_data>
', 'event_label': '
<c_data><![CDATA[<font color="ff0027" size="2">Replace_with_Event_Label</font>]]></c_data>
', 'event_value': '
<c_data><![CDATA[<font color="ff0027" size="2">Replace_with_Event_Value</font>]]></c_data>
'});  ```  							   ```}```  							```</script>``` 							     ...						 ```<button OnClick="GetCustomEvent()>```Download now```</button>```							     ...							 ```</body>```
```

1. The JavaScript you added needs to return a value to Microsoft Advertising when the custom event occurs, and that value needs to match what you entered in Step 2. In our example, we are tracking button clicks, which are **Action** events as shown in Step 2 (and are represented by ```'event'``` in the JavaScript). So we would need to modify the placeholder value of the ```'event'``` parameter (and we can remove the other three parameters):
```
```<head>```Your page title  								```</head>```	  													```<body>```								 								```<script>```Your UET tag is here.```</script> ```  															```<script>		```  																					   ```function GetCustomEvent() {```  															```   window.uetq = window.uetq || [];   								   window.uetq.push ('event', '
<c_data><![CDATA[<font color="ff0027" size="2">downloadbuttonclick</font>]]></c_data>
', {});  ```  															   ```}```  															```</script>```															  								   ... 															 								```<button OnClick="GetCustomEvent()>```Download now```</button>```															  								   ...															 								```</body>```
```

1. Save and deploy your edited website code.

## Tips for working with custom events
- uetq is a JavaScript object instantiated by the UET tracking code when the page is loaded.
- The code inside the &lt;script&gt;&lt;/script&gt; tag should be instantiated when the user action (for example, a button click) is complete.  It could be wired up directly to an onclick event or wrapped inside a JavaScript function that is wired to the onclick event.
- The command 'event' is always required, even if you're not reporting any Event action. If that's the case, you can set Event action either as:
   - Empty. For example:  
```
<script>   window.uetq = window.uetq || [];    window.uetq.push('event', '', {'event_category': 'Replace_with_Event_Category', 'event_label': 'Replace_with_Event_Label', 'event_value': 'Replace_with_Event_Value'});  </script>
```

   - One of the following actions that might help you identify the event action in the future: 				add_payment_info, add_to_cart, add_to_wishlist, begin_checkout, checkout_progress, exception, generate_lead, login, page_view, purchase, refund, remove_from_cart, screen_view, search, select_content, set_checkout_option, share, sign_up, timing_complete, view_item, view_item_list, view_promotion, view_search_results  				For example:  
```
<script>   window.uetq = window.uetq || [];    window.uetq.push('event', 'add_payment_info', {'event_category': 'Replace_with_Event_Category', 'event_label': 'Replace_with_Event_Label', 'event_value': 'Replace_with_Event_Value'});  </script>
```

- If you're only tracking Event action, you can remove the other parameters from the code. For example:  
```
<script>   window.uetq = window.uetq || [];    window.uetq.push('event', 'Event action', {});  </script>
```

- You can use any string value for Replace_with_Event_Category, Event action, and Replace_with_Event_Label.
- You can send the event value without quotes given that it's a numerical value. For example, &lt;button onclick="window.uetq = window.uetq || []; window.uetq.push({ ```'event_category':'Video', 'event':'Play', 'event_label':'Product Demo', 'event_value':5 });"&gt;Play&lt;/button&gt;```. Event value 5 is passed without quotes.
- You can also pass variable revenue with the custom events. To learn more, see [How to report variable revenue with UET](./hlp_BA_CONC_UETv2RevenueVariables.md).

> [!NOTE]
> You can validate that your custom events are working using the [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md).
> To see an example of a custom event UET tag tracking code installed in the body of a webpage, visit [this webpage](https://go.microsoft.com/fwlink?LinkId=2010575 ) (English only), right-click in the webpage, and then click **View source** or **View page source** depending on your browser. On this page, you'll also see some buttons. Clicking each button will trigger a custom event. If you use a third-party monitoring tool like Fiddler, you can see the HTTP request generated to bat.bing.com to report each custom event.
> As your webpage loads, it triggers the UET tag, resulting in a number of HTTP requests. The most important request is to "bat.bing" (the one that looks like "http://bat.bing.com/action/0?ti=..."). This request tells Microsoft Advertising  about the user visits to your webpage. You can use third-party tools such as Fiddler to monitor all the requests that your browser is making when your webpage loads.
> For custom events, an additional HTTP request is triggered to report the same to Microsoft Advertising. The request is similar to the bat.bing but it has different parameters to report custom event (as opposed to just page visit).


