---
title: What Google feed file attributes can I use?
description: Learn about what Google feed file attributes can be used.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What Google feed file attributes can I use?

In the tables below, all Google's attributes are listed, and under the column Used by Bing are marked with:

- **Yes**: for attributes that are accepted and used in describing product offers.
- **Not Used**: for attributes that are accepted but ignored.

Make it even easier to import your Google feed files to Microsoft Merchant Center by using the Google Merchant Center import tool. [Learn more](./hlp_BA_CONC_BMC_GMCImportIntro.md)

## Basic Product Information
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
    <th scope="col">Notes</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              id  
            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              title
            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              description
            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              google_product_category 
            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              product_type 
            </th>
    <td>Yes</td>
    <td>
              Google accepts multiple values here.  

              Bing accepts a singular value here and treats the comma-separated values as a single value.  

              This means when setting auto-targets in Microsoft Advertising, you have to exact-match the comma-separated string.
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              link
             
            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              image_link 
            </th>
    <td>Yes</td>
    <td>
              Google's minimum resolution of 250x250 is accepted by Bing
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              additional_image_link 

            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              condition  
            </th>
    <td>Yes</td>
    <td>
              Google's values are ‘new’, ‘used’, ‘refurbished’.  
              Bing accepts all these values.

            </td>
  </tr>
</table>

## Availability and Price
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
    <th scope="col">Notes</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              availability 

            </th>
    <td>Yes</td>
    <td>
              Google's values are ‘in stock’, ‘out of stock’, ‘preorder’.  
              Bing accepts all these values.  
              The English version of the valid options (in stock, out of stock, and preorder) is also accepted for other languages.
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              price 

            </th>
    <td>Yes</td>
    <td>For the United Kingdom, France, Germany, and Australia, taxes such as VAT must be included in the price.</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              sale_price 

            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              sale_price_effective_date 

            </th>
    <td>Yes</td>
    <td></td>
  </tr>
</table>

## Unique Product Identifiers
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              brand 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              gtin 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              mpn 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              identifier_exists 
            </th>
    <td>Yes</td>
  </tr>
</table>

## Apparel Products
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              gender 

            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              age_group 

            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              color 

            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              size 
            </th>
    <td>Yes</td>
  </tr>
</table>

## Product Variants
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              item_group_id 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              color 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              material 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              pattern 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
            size 
          </th>
    <td>Yes</td>
  </tr>
</table>

## Tax and Shipping (attributes ignored)
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              tax 
            </th>
    <td>Not Used</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              shipping
            </th>
    <td>Not Used</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              shipping_weight 
            </th>
    <td>Not Used</td>
  </tr>
</table>

## Tax and Shipping (attributes ignored)
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              tax 
            </th>
    <td>Not Used</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              shipping
            </th>
    <td>Not Used</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              shipping_weight 
            </th>
    <td>Not Used</td>
  </tr>
</table>

## Tax and Shipping (Germany only)
<table>
  <tr>
    <th scope="col">
              Google&nbsp;Attribute
            </th>
    <th scope="col">
              Used by Bing?
            </th>
    <th scope="col">Notes</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              shipping
            </th>
    <td>Yes</td>
    <td>Shipping field is required for Germany only.</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              shipping_weight

            </th>
    <td>Yes</td>
    <td>Shipping field is required for Germany only.</td>
  </tr>
</table>

## Merchant Defined Multipacks
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              multipack 
            </th>
    <td>Yes</td>
  </tr>
</table>

## Adult Products
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
                    adult 
                  </th>
    <td>Yes</td>
  </tr>
</table>

## Google Ads Attributes
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
    <th scope="col">Notes</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              adwords_grouping 
            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              adwords_labels 

            </th>
    <td>Yes</td>
    <td>
              Google and Bing treat this as a multi-value field composed of comma-separated values. 

              However, when setting auto-targets in Microsoft Advertising, the merchant has to exact-match the entire comma-separated string.

            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              adwords_redirect 

            </th>
    <td>Yes</td>
    <td></td>
  </tr>
</table>

## Custom label attributes for shopping campaigns
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Microsoft Shopping Campaigns?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
            custom_label_0 
          </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
            custom_label_1 
          </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
            custom_label_2 
          </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
            custom_label_4 
          </th>
    <td>Yes</td>
  </tr>
</table>

## Unit Prices (attributes ignored)
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
    <th scope="col">Notes</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              unit_pricing_measure 

            </th>
    <td>Yes</td>
    <td></td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              unit_pricing_base_measure 

            </th>
    <td>Yes</td>
    <td>This attribute is optional when you submit unit_pricing measure.</td>
  </tr>
</table>

## Energy Labels
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              energy_efficiency_class 
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              max_energy_efficiency_class
            </th>
    <td>Yes</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              min_energy_efficiency_class
            </th>
    <td>Yes</td>
  </tr>
</table>

## Loyalty Points (attributes ignored)
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              loyalty_points 
            </th>
    <td>Not Used</td>
  </tr>
</table>

## Multiple Installments (attributes ignored)
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              installment 

            </th>
    <td>Not Used</td>
  </tr>
</table>

## Additional Attributes
<table>
  <tr>
    <th scope="col">Google&nbsp;Attribute</th>
    <th scope="col">Used by Bing?</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              excluded_destination 
            </th>
    <td>Not Used</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal;border-bottom:solid 1px #ccc">
              expiration_date 
            </th>
    <td>Yes</td>
  </tr>
</table>


