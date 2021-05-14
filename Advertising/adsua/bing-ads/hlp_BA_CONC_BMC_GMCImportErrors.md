---
title: Google Merchant Center import errors
description: Troubleshoot Google Merchant Center import errors.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Google Merchant Center import errors

Now that you’ve imported your Google Merchant Center offers, are you seeing that there are some errors or offers that got skipped? When there is an import error, you can see the error details in the **Choose import options** step of the import process.

Take a look at the different types of errors or skipped offers you may encounter with your Google Merchant Center import below:

<table>
  <tr>
    <th scope="col">Error/Skipped Offers</th>
    <th scope="col">Description</th>
    <th scope="col">Solution</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc">No matching products in Google Merchant Center</th>
    <td>
        Matching offers couldn’t be found in Google Merchant Center because they did match some or all of the following:
        <ul><li>Market. There were no offers for the user-specified markets.</li><li>No approved offers.</li><li>No online offers.</li><li>Product destination was not set to Shopping.</li></ul></td>
    <td>
        Check the offers in Google Merchant Center to ensure they are approved shopping offers and also check the import options in Microsoft Merchant Center to ensure that the markets associated with the approved shopping Google Merchant Center offers are specified. Try to import again. If you still encounter issues, please [contact support](https://go.microsoft.com/fwlink?LinkId=398371).
      </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc">Internal error</th>
    <td>An internal import error occurred.</td>
    <td>
        Please [contact support](https://go.microsoft.com/fwlink?LinkId=398371)
      </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc">Import size limit</th>
    <td>Offers are skipped if the maximum 10 million offers per market limit is exceeded.</td>
    <td>
        Please [contact support](https://go.microsoft.com/fwlink?LinkId=398371)
      </td>
  </tr>
</table>


