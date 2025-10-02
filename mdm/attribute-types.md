---
description: >-
  Choosing the right attribute type is essential when defining attributes in a
  Product Information Management (PIM) system. We use different types — such as
  text, integer, digital asset, URL or picklist
---

# Attribute Types

**Integer:** All characters in data must be numbers. \
\
![](<../.gitbook/assets/image (534).png>)\
\
**Measurement:** A value with an integer and an associated specified measurement\
\
![](<../.gitbook/assets/image (535).png>)\
\
**Price:** A decimal value with an associated specified currency ISO code\
\
![](<../.gitbook/assets/image (536).png>)\
\
**Boolean:** Used when you need to note that something is Active, Inactive, On Sale for example, it acts as a toggle between true/false values\
\
![](<../.gitbook/assets/image (545).png>)\
\
**Color**: By using the HEX code you can have a visual representation of the color associated with the value\
\
![](<../.gitbook/assets/image (547).png>)\
\
**Decimal:** Used when all characters are number and decimals are needed.\
\
![](<../.gitbook/assets/image (537).png>)\
\
**Single-Select or Multi-Select Picklist:** Used when you want your customer to choose between a list of predetermined options\
\
![](<../.gitbook/assets/image (538).png>)\
\
**Tag:** Create a tag field to input products tags\
\
![](<../.gitbook/assets/image (539).png>)\
\
**URL**: Use this when you need to associate a link to the product\
\
![](<../.gitbook/assets/image (548).png>)\
\
\
&#xNAN;**(Text) String:** This is the most common type due to the fact it has no format restriction. \
\
![](<../.gitbook/assets/image (533).png>)\
\
**Category:** Use this option when setting up a category or family\
\
![](<../.gitbook/assets/image (540).png>)\
\
**Digital Asset:** Use this option when setting attributes for images.\
\
<mark style="background-color:yellow;">The Digital Asset data type can also be a Multi Digital Asset</mark>\ <mark style="background-color:yellow;">This attribute gets used when users want to quickly assign multiple assets to a single attribute, without necessarily needing to designate them as a specific angle or image type (e.g. "Top Image", "Side Image", etc.). We've seen clients use them for lifestyle images pretty often, where those images just need to be associated with a product in no particular order.</mark>\
\ <mark style="background-color:yellow;">These values get stored as an array in Catsy, and are exported as such. So output typically looks like this: image\_1.jpg|image\_2.jpg|image3.jpg</mark>\
\ <mark style="background-color:yellow;">You'll get the value for each image in the array separated by a pipe character.</mark>\
\
![](<../.gitbook/assets/image (541).png>)\
\
**Product Association:** Use this option when you want to relate one product to another while keeping them as separate products.\
\
![](<../.gitbook/assets/image (542).png>)\
\
**Date:** A date attribute field with calendar popup to select dates in a YYYY/MM/DD format\
\
![](<../.gitbook/assets/image (543).png>)\
\
**Readiness**: Build your own completeness score to see a visual of where you have gaps in your data\
\
![](<../.gitbook/assets/image (544).png>)

