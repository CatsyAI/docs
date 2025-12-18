---
title: Error message
---

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
