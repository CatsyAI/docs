# How to switch from Parent Product model to Leading Product model

Making the switch from Parent Product model to Leading Product model.

<img src="../../.gitbook/assets/image (1071).png" alt="" data-size="line"> Take a sample product, and review the attribute Parent SKU

<img src="../../.gitbook/assets/image (1072).png" alt="" data-size="line"> If parentsku = sku, then it becomes the Leading Product Schema. (Meaning the product points to itself)

<img src="../../.gitbook/assets/image (1073).png" alt="" data-size="line"> If parentsku = blank, then you have Parent Product Schema

<img src="../../.gitbook/assets/image (1074).png" alt="" data-size="line"> Export attributes from the parent record marketing copy

<img src="../../.gitbook/assets/image (1075).png" alt="" data-size="line"> In the exported file, make sure parent\_sku=sku and for remaining children, parent\_sku=parent's sku\


<figure><img src="../../.gitbook/assets/image (1069).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1070).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (1076).png" alt="" data-size="line"> Import the file

<img src="../../.gitbook/assets/image (1077).png" alt="" data-size="line"> Delete the empty parents (by this step all parent items will have no children)

<img src="../../.gitbook/assets/image (1078).png" alt="" data-size="line"> Now, apply the filter on "Parentage" and you will see all the options.\
\


<figure><img src="../../.gitbook/assets/image (1079).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1080).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Please test the above with a sample product before applying to all products.
{% endhint %}
