---
description: 'Here is a list of common errors when syncing to Shopify:'
---

# Shopify: Channel Messages

<details>

<summary><mark style="color:red;">MSD-1001</mark><em><mark style="color:red;">: Empty Attribute value</mark> - Channel attribute has no value</em></summary>

Resolution:\
\
Check that the channel attribute has mapping.\
<mark style="color:red;">`[1]`</mark> If the mapping is to a constant, check that there is a valid value set as constant\
<mark style="color:red;">`[2]`</mark> If the mapping is to a main attribute, check that the main attribute has a value\
<mark style="color:red;">`[3]`</mark> If the mapping is to a formula, check that the formula is properly set and properly evaluating for the product\
\
&#xNAN;_&#x59;ou can't sync empty SKU values, so add formula to always push a SKU for every variant or standalone product. Use your main identifier as a fallback value._

\
&#xNAN;_`if (product.abc23_sku.isEmpty()) { product.number }`_&#x20;

_`else { product.abc23_sku }`_\
\
&#xNAN;_<mark style="color:green;">Please make sure the attribute keys for main identifier and SKU are adjusted.</mark>_

</details>

<details>

<summary><mark style="color:orange;">MSD-1011</mark><em><mark style="color:orange;">:</mark></em> <em><mark style="color:orange;">Empty Attribute value</mark> - Channel attribute has no value</em></summary>

Check that the channel attribute has mapping.\
\
<mark style="color:red;">`[1]`</mark> If the mapping is to a constant, check that there is a valid value set as constant\
<mark style="color:red;">`[2]`</mark> If the mapping is to a main attribute, check that the main attribute has a value\
<mark style="color:red;">`[3]`</mark> If the mapping is to a formula, check that the formula is properly set and is evaluating for the product\
\
&#xNAN;_&#x59;ou can't sync empty price values, so add formula to push 0 when there is no price._

_`if (product.abc23_price.isEmpty()) { "0" }`_&#x20;

_`else { product.abc23_price }`_

<mark style="color:green;">Please make sure the attribute key for your price mapping is adjusted.</mark>

</details>

<details>

<summary><mark style="color:orange;">MSD-1021: </mark><em><mark style="color:orange;">Missing required attribute value</mark></em><mark style="color:orange;"> -</mark> <em>Product Parent attribute has no value</em></summary>

Check that the channel attribute for the product's parent is mapped and the main attribute in Catsy has a value.\
\
<mark style="color:red;">`[1]`</mark> If the mapping is to a main attribute, check that the main attribute has a value\
<mark style="color:red;">`[2]`</mark> If the mapping is to a formula, check that the formula is properly set and is evaluating for the product

</details>

<details>

<summary><mark style="color:orange;">MSD-1022: </mark><em><mark style="color:orange;">Missing required attribute value</mark></em> - <em>Variant attribute has no value</em></summary>

Check that the channel attribute for the variant is mapped and the main attribute in Catsy has a value.\
\
<mark style="color:red;">`[1]`</mark> If the mapping is to a main attribute, check that the main attribute has a value\
<mark style="color:red;">`[2]`</mark> If the mapping is to a formula, check that the formula is properly set and is evaluating for the product

</details>

<details>

<summary><mark style="color:orange;">MSD-1025: </mark><em><mark style="color:orange;">Missing required attribute value</mark></em><mark style="color:orange;"> -</mark> <em>Metafield attribute has no value</em></summary>

Check that the channel attribute for the metafield is mapped and the main attribute _for the parent_ in Catsy has a value.\
\
<mark style="color:red;">`[1]`</mark> If the mapping is to a constant, check that there is a valid value set as constant\
<mark style="color:red;">`[2]`</mark> If the mapping is to a main attribute, check that the main attribute has a value\
<mark style="color:red;">`[3]`</mark> If the mapping is to a formula, check that the formula is properly set and is evaluating for the product

</details>

<details>

<summary><mark style="color:orange;">MSD-1031: </mark><em><mark style="color:orange;">Missing required attribute mapping</mark></em><mark style="color:orange;"> -</mark> <em>Parent attribute needs mapping</em></summary>

Check that the channel attribute for the product's parent is mapped and the main attribute in Catsy has a value.\
\
<mark style="color:red;">`[1]`</mark> If the mapping is to a main attribute, check that the main attribute has a value\
<mark style="color:red;">`[2]`</mark> If the mapping is to a formula, check that the formula is properly set and is evaluating for the product

</details>

<details>

<summary><mark style="color:orange;">MSD-1032: </mark><em><mark style="color:orange;">Missing required attribute mapping</mark></em><mark style="color:orange;"> -</mark> <em>Variant attribute needs mapping</em></summary>

Check that the channel attribute for the variant is mapped and the main attribute in Catsy has a value.\
\
<mark style="color:red;">`[1]`</mark> If the mapping is to a main attribute, check that the main attribute has a value\
<mark style="color:red;">`[2]`</mark> If the mapping is to a formula, check that the formula is properly set and is evaluating for the product

</details>

<details>

<summary><mark style="color:orange;">INV-2001: </mark><em><mark style="color:orange;">Invalid value in required attribute</mark></em><mark style="color:orange;"> -</mark> <em>Fix value for parent attribute</em></summary>

The value for the parent level attribute does not match the required format of Shopify. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The value should be a decimal, but is instead text\
<mark style="color:red;">`[2]`</mark> The value should be sent as a script with specific syntax but is not

</details>

<details>

<summary><mark style="color:orange;">INV-2002: </mark><em><mark style="color:orange;">Invalid value in required attribute</mark></em><mark style="color:orange;"> -</mark> <em>Fix value for variant attribute</em></summary>

The value for the parent level attribute does not match the required format of Shopify. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The value should be a decimal, but is instead text\
<mark style="color:red;">`[2]`</mark> The value should be sent as a script with specific syntax but is not

</details>

<details>

<summary><mark style="color:orange;">INV-2003: </mark><em><mark style="color:orange;">Invalid Product Status</mark></em><mark style="color:orange;"> -</mark> <em>Fix value for "Status" attribute</em></summary>

Check that your product's "Status" attribute is sending one of the following values only:\
\
<mark style="color:red;">`[-]`</mark> "active"\
<mark style="color:red;">`[-]`</mark> "archived"\
<mark style="color:red;">`[-]`</mark> "draft"\
\
Any other value for the "Status" attribute will lead to error in syncing the data.

</details>

<details>

<summary><mark style="color:orange;">IMG-3001: </mark><em><mark style="color:orange;">Issue with Image</mark></em><mark style="color:orange;"> -</mark> <em>Issue with Image</em></summary>

There is a problem with the image assigned to this product. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The link you are sending to Shopify is referencing a broken asset\
<mark style="color:red;">`[2]`</mark> The asset you are sending is larger than the allowed by Shopify. The requirements for images are: up to 5000 x 5000 pixels with a file size of up to 20 MB. _Shopify recommendation: for square product images, a size of 2048 x 2048 px usually looks best._\
<mark style="color:red;">`[3]`</mark> You are trying to send an image with a file extension that's not allowed by Shopify. The extensions allowed are:\
<mark style="color:red;">`[-]`</mark> png\
<mark style="color:red;">`[-]`</mark> jpeg\
<mark style="color:red;">`[-]`</mark> jpg\
<mark style="color:red;">`[-]`</mark> psd\
<mark style="color:red;">`[-]`</mark> tiff\
<mark style="color:red;">`[-]`</mark> bmp\
<mark style="color:red;">`[-]`</mark> gif\
<mark style="color:red;">`[-]`</mark> svg \
<mark style="color:red;">`[-]`</mark> heic\
<mark style="color:red;">`[-]`</mark> webp​\
\
Use this formula to make sure your assets are properly transformed prior to sending them in Shopify:\
&#xNAN;_`product.main_image.format('jpg').resize(2048, 0)`_\
Please make sure the attribute key for your image mapping is adjusted. If you need a different file format, feel free to change that as well.

</details>

<details>

<summary><mark style="color:orange;">DUP-4011: </mark><em><mark style="color:orange;">Duplicate Product number</mark></em><mark style="color:orange;"> -</mark> <em>Duplicate SKU</em></summary>

The product you are syncing has an identical SKU with one already in the store.\
\
Check your SKU attribute mapping and values. Correct to avoid the duplication.

</details>

<details>

<summary><mark style="color:orange;">DUP-4021: </mark><em><mark style="color:orange;">Duplicate Product name</mark></em><mark style="color:orange;"> -</mark> <em>Duplicate Product name</em></summary>

The product you are syncing has an identical name with one already in the store.\
\
Check your Product name attribute mapping and values. Correct to avoid the duplication.

</details>

<details>

<summary><mark style="color:orange;">VAI-5002: </mark><em><mark style="color:orange;">Issue with Variant's data</mark></em><mark style="color:orange;"> -</mark> <em>Fix value for variant attributes</em></summary>

The value for one or more of the variant level attributes does not match the required format of Shopify. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The value should be a decimal, but is instead text\
<mark style="color:red;">`[2]`</mark> The value should be sent as a script with specific syntax but is not

</details>

<details>

<summary><mark style="color:orange;">VAI-5006: </mark><em><mark style="color:orange;">Issue with variants's option value</mark></em><mark style="color:orange;"> -</mark> <em>Fix option attributes</em></summary>

Your product's option attribute values have an issue. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> There are no option attributes set for the product. If so, go to the parent details page, go to the Variants tab on the left-hand side, and assign attributes as option attributes for your variants\
<mark style="color:red;">`[2]`</mark> Check that every row of option attributes has values in it. You should not have empty option attribute values\
<mark style="color:red;">`[3]`</mark> Check that every row of option attributes is unique. The combination of values should be unique for every variant

</details>

<details>

<summary><mark style="color:orange;">VAI-5102: </mark><em><mark style="color:orange;">Issue with Variant's inventory data</mark></em><mark style="color:orange;"> -</mark> <em>Fix inventory data for a variant</em></summary>

Check the inventory mapping. Make sure that all three fields are properly mapped:\
\
<mark style="color:red;">`[1]`</mark> Inventory Management - should be set to "shopify"\
<mark style="color:red;">`[2]`</mark> Inventory Policy - should be "deny" or "continue". Shopify advises to use "deny" when customers are not allowed to place orders for the product variant if it's out of stock, and "continue" when customers are allowed to place orders for the product variant if it's out of stock\
<mark style="color:red;">`[3]`</mark> Inventory Quantity - should be populated with an integer value

</details>

<details>

<summary><mark style="color:orange;">CMF-6001: </mark><em><mark style="color:orange;">Issue with Custom field</mark></em><mark style="color:orange;"> -</mark> <em>Issue with Custom field</em></summary>

There's a problem with your custom field data. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The attribute is not mapped or is missing data even if it is mapped (empty main attribute value, empty constant mapping, erroneous formula)\
<mark style="color:red;">`[2]`</mark> The data is not properly formatted, e.g. you are sending text where decimal is required. Check mappings and data types against what is required from the store\
<mark style="color:red;">`[3]`</mark> There's an issue with an image. Check to make sure all image links are valid and all images are matching Shopify's size and dimension requirements

</details>

<details>

<summary><mark style="color:orange;">OTH-8001: </mark><em><mark style="color:orange;">other issues on Product</mark></em><mark style="color:orange;"> -</mark> <em>Issue with Product</em></summary>

There's a problem with your product data. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> One or more required attributes are not mapped or are missing data even if they are mapped (empty main attribute value, empty constant mapping, erroneous formula)\
<mark style="color:red;">`[2]`</mark> One or more attributes are sending improperly formatted data, e.g. sending text where decimal is required. Check mappings and data types\
<mark style="color:red;">`[3]`</mark> The parent's option attributes are improperly set. Check to make sure that there are option attributes and they are unique for every variant of this product\
<mark style="color:red;">`[4]`</mark> There's an issue with an image. Check to make sure all image links are valid and all images are matching Shopify's size and dimension requirements

</details>

<details>

<summary><mark style="color:orange;">OTH-8002: </mark><em><mark style="color:orange;">other issues on Variant</mark></em><mark style="color:orange;"> -</mark> <em>Issue with Variant</em></summary>

There's a problem with your variant data. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> One or more required attributes are not mapped or are missing data even if they are mapped (empty main attribute value, empty constant mapping, erroneous formula)\
<mark style="color:red;">`[2]`</mark> One or more attributes are sending improperly formatted data, e.g. sending text where decimal is required. Check mappings and data types\
<mark style="color:red;">`[3]`</mark> There's an issue with an image. Check to make sure all image links are valid and all images are matching Shopify's size and dimension requirements

</details>

<details>

<summary><mark style="color:red;">NCR-7001: </mark><em><mark style="color:red;">Miscellaneous error</mark></em><mark style="color:red;"> -</mark> <em>Issue with Product</em></summary>

There's a problem with your product data. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> One or more required attributes are not mapped or are missing data even if they are mapped (empty main attribute value, empty constant mapping, erroneous formula)\
<mark style="color:red;">`[2]`</mark> One or more attributes are sending improperly formatted data, e.g. sending text where decimal is required. Check mappings and data types\
<mark style="color:red;">`[3]`</mark> The parent's option attributes are improperly set. Check to make sure that there are option attributes and they are unique for every variant of this product\
<mark style="color:red;">`[4]`</mark> There's an issue with an image. Check to make sure all image links are valid and all images are matching Shopify's size and dimension requirements

</details>

<details>

<summary><mark style="color:red;">NCR-7002: </mark><em><mark style="color:red;">Miscellaneous error</mark></em><mark style="color:red;"> -</mark> <em>Issue with Variant</em></summary>

There's a problem with your variant data. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> One or more required attributes are not mapped or are missing data even if they are mapped (empty main attribute value, empty constant mapping, erroneous formula)\
<mark style="color:red;">`[2]`</mark> One or more attributes are sending improperly formatted data, e.g. sending text where decimal is required. Check mappings and data types\
<mark style="color:red;">`[3]`</mark> There's an issue with an image. Check to make sure all image links are valid and all images are matching Shopify's size and dimension requirements

</details>

<details>

<summary><mark style="color:red;">NCR-7003: </mark><em><mark style="color:red;">Miscellaneous error</mark></em><mark style="color:red;"> -</mark> <em>Issue with Image</em></summary>

There is a problem with the image assigned to this product. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The link you are sending to Shopify is referencing a broken asset\
<mark style="color:red;">`[2]`</mark> The asset you are sending is larger than the allowed by Shopify. The requirements for images are: up to 5000 x 5000 pixels with a file size of up to 20 MB. _Shopify recommendation: for square product images, a size of 2048 x 2048 px usually looks best._\
<mark style="color:red;">`[3]`</mark> You are trying to send an image with a file extension that's not allowed by Shopify. The extensions allowed are:\
<mark style="color:red;">`[-]`</mark> png\
<mark style="color:red;">`[-]`</mark> jpeg\
<mark style="color:red;">`[-]`</mark> jpg\
<mark style="color:red;">`[-]`</mark> psd\
<mark style="color:red;">`[-]`</mark> tiff\
<mark style="color:red;">`[-]`</mark> bmp\
<mark style="color:red;">`[-]`</mark> gif\
<mark style="color:red;">`[-]`</mark> svg \
<mark style="color:red;">`[-]`</mark> heic\
<mark style="color:red;">`[-]`</mark> webp\
\
Use this formula to make sure your assets are properly transformed prior to sending them in Shopify:\
&#xNAN;_`product.main_image.format('jpg').resize(2048, 0)`_\
Please make sure the attribute key for your image mapping is adjusted. If you need a different file format, feel free to change that as well.

</details>

<details>

<summary><mark style="color:red;">NCR-7004: </mark><em><mark style="color:red;">Miscellaneous error</mark></em><mark style="color:red;"> -</mark> <em>Issue with Custom field</em></summary>

There's a problem with your custom field data. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The attribute is not mapped or is missing data even if it is mapped (empty main attribute value, empty constant mapping, erroneous formula)\
<mark style="color:red;">`[2]`</mark> The data is not properly formatted, e.g. you are sending text where decimal is required. Check mappings and data types against what is required from the store\
<mark style="color:red;">`[3]`</mark> There's an issue with an image. Check to make sure all image links are valid and all images are matching Shopify's size and dimension requirements

</details>

<details>

<summary><mark style="color:red;">NCR-7005: </mark><em><mark style="color:red;">Miscellaneous error</mark></em><mark style="color:red;"> -</mark> <em>Issue with Metafield</em></summary>

There's a problem with your metafield data. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The attribute is not mapped or is missing data even if it is mapped (empty main attribute value, empty constant mapping, erroneous formula)\
<mark style="color:red;">`[2]`</mark> The data is not properly formatted, e.g. you are sending text where decimal is required. Check mappings and data types against what is required from the store\
<mark style="color:red;">`[3]`</mark> There's an issue with an image. Check to make sure all image links are valid and all images are matching Shopify's size and dimension requirements

</details>

<details>

<summary><mark style="color:orange;">NCR-7101: </mark><em><mark style="color:orange;">Not found in store</mark></em><mark style="color:orange;"> -</mark> <em>Product can't update in store</em></summary>

Your product cannot be updated in the store. It's possible that the structure of the data changed in some way, e.g. a product that was synced as a standalone before is now being synced with a parent/sku structure.\
\
Check for any changes to the product data structure.

</details>

<details>

<summary><mark style="color:orange;">NCR-7102: </mark><em><mark style="color:orange;">Not found in store</mark></em><mark style="color:orange;"> -</mark> <em>Variant can't update in store</em></summary>

Your product cannot be updated in the store. It's possible that the structure of the data changed in some way, e.g. a product that was synced as a standalone before is now being synced with a parent/sku structure.\
\
Check for any changes to the product data structure.

</details>

<details>

<summary><mark style="color:orange;">NCR-7103: </mark><em><mark style="color:orange;">Not found in store</mark></em><mark style="color:orange;"> -</mark> <em>Image can't update in store</em></summary>

The image you are trying to update has not been uploaded to the store yet.\
\
Please wait for the previous sync to process and try again in 1 hour.

</details>

<details>

<summary><mark style="color:orange;">NCR-7104: </mark><em><mark style="color:orange;">Not found in store</mark></em><mark style="color:orange;"> -</mark> <em>Custom field can't update in store</em></summary>

The custom field you are trying to update has not been uploaded to the store yet.\
\
Please wait for the previous sync to process and try again in 1 hour.

</details>

<details>

<summary><mark style="color:orange;">NCR-7105: </mark><em><mark style="color:orange;">Not found in store</mark></em><mark style="color:orange;"> -</mark> <em>Metafield can't update in store</em></summary>

The metafield you are trying to update has not been uploaded to the store yet.\
\
Please wait for the previous sync to process and try again in 1 hour.

</details>

<details>

<summary><mark style="color:orange;">NCR-7106: </mark><em><mark style="color:orange;">Not found in store</mark></em><mark style="color:orange;"> -</mark> <em>Option can't update in store</em></summary>

Your product cannot be updated in the store. It's possible that the structure of the data changed in some way, e.g. a product that was synced as a standalone before is now being synced with a parent/sku structure.\
\
Check for any changes to the product data structure. If there are none, retry the sync.

</details>

<details>

<summary><mark style="color:orange;">NCR-7201: </mark><em><mark style="color:orange;">Issue with external_id</mark></em><mark style="color:orange;"> -</mark> <em>Product can't update in store</em></summary>

Your product cannot be updated in the store. It's possible that the structure of the data changed in some way, e.g. a product that was synced as a standalone before is now being synced with a parent/sku structure.\
\
Check for any changes to the product data structure.

</details>

<details>

<summary><mark style="color:orange;">NCR-7202: </mark><em><mark style="color:orange;">Issue with external_id</mark></em><mark style="color:orange;"> -</mark> <em>Variant can't update in store</em></summary>

Your product cannot be updated in the store. It's possible that the structure of the data changed in some way, e.g. a product that was synced as a standalone before is now being synced with a parent/sku structure.\
\
Check for any changes to the product data structure.

</details>

<details>

<summary><mark style="color:orange;">NCR-7203: </mark><em><mark style="color:orange;">Issue with external_id</mark></em><mark style="color:orange;"> -</mark> <em>Image can't update in store</em></summary>

The image you are trying to update has not been uploaded to the store yet.\
\
Please wait for the previous sync to process and try again in 1 hour.

</details>

<details>

<summary><mark style="color:orange;">NCR-7204: </mark><em><mark style="color:orange;">Issue with external_id</mark> -</em> <em>Custom field can't update in store</em></summary>

The custom field you are trying to update has not been uploaded to the store yet. Please wait for the previous sync to process and try again in 1 hour.

</details>

<details>

<summary><mark style="color:orange;">NCR-7205: </mark><em><mark style="color:orange;">Issue with external_id</mark></em><mark style="color:orange;"> -</mark> <em>Metafield can't update in store</em></summary>

The metafield you are trying to update has not been uploaded to the store yet.\
\
Please wait for the previous sync to process and try again in 1 hour.

</details>

<details>

<summary><mark style="color:orange;">NCR-7206: </mark><em><mark style="color:orange;">Issue with external_id</mark></em><mark style="color:orange;"> -</mark> <em>Option can't update in store</em></summary>

Your product cannot be updated in the store. It's possible that the structure of the data changed in some way, e.g. a product that was synced as a standalone before is now being synced with a parent/sku structure.

</details>

<details>

<summary><mark style="color:orange;">NCR-7301: </mark><em><mark style="color:orange;">Error in api call</mark></em><mark style="color:orange;"> -</mark> <em>Issue with API call</em></summary>

An API call initiated by the integration process is failing when creating or updating the values for a parent product. Please email [success@catsy.com](mailto:success@catsy.com) to alert Catsy about this error.

</details>

<details>

<summary><mark style="color:orange;">NCR-7302: </mark><em><mark style="color:orange;">Error in api call</mark></em><mark style="color:orange;"> -</mark> <em>Issue with API call</em></summary>

An API call initiated by the integration process is failing when creating or updating the values for a variant product. Please email [success@catsy.com](mailto:success@catsy.com) to alert Catsy about this error.

</details>

<details>

<summary><mark style="color:orange;">NCR-7303: </mark><em><mark style="color:orange;">Error in api call</mark></em> - <em>Issue with Image</em></summary>

There is a problem with the image assigned to this product. Check if any of the following apply:\
\
<mark style="color:red;">`[1]`</mark> The link you are sending to Shopify is referencing a broken asset\
<mark style="color:red;">`[2]`</mark> The asset you are sending is larger than the allowed by Shopify. The requirements for images are: up to 5000 x 5000 pixels with a file size of up to 20 MB. _Shopify recommendation: for square product images, a size of 2048 x 2048 px usually looks best._\
<mark style="color:red;">`[3]`</mark> You are trying to send an image with a file extension that's not allowed by Shopify. The extensions allowed are:\
<mark style="color:red;">`[-]`</mark> png\
<mark style="color:red;">`[-]`</mark> jpeg\
<mark style="color:red;">`[-]`</mark> jpg\
<mark style="color:red;">`[-]`</mark> psd\
<mark style="color:red;">`[-]`</mark> tiff\
<mark style="color:red;">`[-]`</mark> bmp\
<mark style="color:red;">`[-]`</mark> gif\
<mark style="color:red;">`[-]`</mark> svg \
<mark style="color:red;">`[-]`</mark> heic\
<mark style="color:red;">`[-]`</mark> webp\
\
Use this formula to make sure your assets are properly transformed prior to sending them in Shopify:\
&#xNAN;_`product.main_image.format('jpg').resize(2048, 0)`_\
Please make sure the attribute key for your image mapping is adjusted. If you need a different file format, feel free to change that as well.

</details>

<details>

<summary><mark style="color:orange;">NCR-7304: </mark><em><mark style="color:orange;">Error in api call</mark></em><mark style="color:orange;"> -</mark> <em>Issue with API call</em></summary>

An API call initiated by the integration process is failing when creating or updating the values for a custom field. Please email [success@catsy.com](mailto:success@catsy.com) to alert Catsy about this error.

</details>

<details>

<summary><mark style="color:orange;">NCR-7305: </mark><em><mark style="color:orange;">Error in api call</mark></em><mark style="color:orange;"> -</mark> <em>Issue with API call</em></summary>

An API call initiated by the integration process is failing when creating or updating the values for a metafield. Please email [success@catsy.com](mailto:success@catsy.com) to alert Catsy about this error.

</details>

<details>

<summary><mark style="color:orange;">NCR-7306: </mark><em><mark style="color:orange;">Error in api call</mark></em><mark style="color:orange;"> -</mark> <em>Issue with API call</em></summary>

An API call initiated by the integration process is failing when creating or updating the values for an option attribute. Please email [success@catsy.com](mailto:success@catsy.com) to alert Catsy about this error.

</details>

