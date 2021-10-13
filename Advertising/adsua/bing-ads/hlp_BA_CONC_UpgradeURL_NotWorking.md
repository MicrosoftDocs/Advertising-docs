---
title: Why isn’t my tracking template working?
description: Learn the validation rules so that you can fix issues with your tracking template.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Why isn’t my tracking template working?

Your tracking template might not be working because your final URL, mobile URL or tracking templates don't meet the following validation rules.

- Final and Mobile URLs must start with either http:// or https://
- Tracking templates must reference a landing page URL using {lpurl} or a permutation of that tag
Tracking templates at the account, campaign, and ad group level must include a parameter that inserts your landing page URL using either the {lpurl} or other advanced parameters. Once your ad is clicked, these parameters will insert your final URL. If you don’t include a URL insertion parameter in your tracking template, your landing page URL will break.

<table>
  <tr>
    <th scope="col">
            Parameter
          </th>
    <th scope="col">
            What it returns
          </th>
  </tr>
  <tr>
    <td>
            *{lpurl}*
          </td>
    <td>
            The Final URL. It will be escaped unless you put {lpurl} at the beginning of your tracking template. If {lpurl} isn't at the beginning of your tracking template, all characters that are not letters, numbers, or the following punctuation characters will be escaped: -, _, ., !, *, (, and ).  
            <strong>Example:</strong> 
				<ul><li><strong>Final URL:</strong>  http://example.com</li><li><strong>Tracking template:</strong>  {lpurl}?matchtype={matchtype}</li><li><strong>Landing page URL:</strong>  http://example.com?matchtype={matchtype}</li></ul></td>
  </tr>
  <tr>
    <td>*{lpurl+2}*</td>
    <td>The Final URL, escaped twice. Useful when you have a chain of redirects.</td>
  </tr>
  <tr>
    <td>*{lpurl+3}*</td>
    <td>The Final URL, escaped three times. Useful when you have a chain of redirects.</td>
  </tr>
  <tr>
    <td>*{unescapedlpurl}*</td>
    <td>The Final URL, unescaped.</td>
  </tr>
  <tr>
    <td>*{escapedlpurl}*</td>
    <td>The Final URL, escaped. Escapes all characters that are not letters, numbers, or the following punctuation characters: -, _, ., !, *, (, and ).</td>
  </tr>
  <tr>
    <td>*{escapedlpurl+2}*</td>
    <td>The Final URL, escaped twice. Useful when you have a chain of redirects.</td>
  </tr>
  <tr>
    <td>*{escapedlpurl+3}*</td>
    <td>The Final URL, escaped three times. Useful when you have a chain of redirects.</td>
  </tr>
</table>

- Domain name of Display URL must match website’s landing page URL after redirect and tracking is applied.


