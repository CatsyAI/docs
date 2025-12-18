---
hidden: true
---

# What is Re-Link

**Re-linking products in Catsy** allows you to connect an existing product in Shopify to an existing product in Catsy, instead of creating a new product during a sync.

### When to Use Product Re-linking

Use re-linking when:

* A product was manually created in Shopify
* Products were previously synced from another system
* You want to attach Catsy data (images, descriptions, metafields) to an existing Shopify product
* You are working with a dev or production store that already has products live

### How Relinking Works in Catsy

Relinking is done through the **Shopify channel** in Catsy and uses Shopify’s internal product identifiers (GIDs) to match records.

#### <img src="../../.gitbook/assets/image.png" alt="" data-size="line"> Enable Grouped Variant View

In the Shopify channel product view:

* Toggle **Group Variants** ON
* Select one or multiple products
* This exposes Shopify-specific actions, including relinking

Once enabled, you will see a 'Re-link IDs of selected products button' under the three dot menu at the top:

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### <img src="../../.gitbook/assets/image (3).png" alt="" data-size="line"> Generate Re-link and Sync

* Click on the 'Re-link IDs of selected products button'
* Head over to Settings > Relink Ids in the left menu to check the progress of your re-link:

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### <img src="../../.gitbook/assets/image (4).png" alt="" data-size="line"> Why Re-linking is important

Relinking ensures the following remain intact:

* Shopify product and variant IDs
* Product URLs and SEO value
* Existing collections
* Metafields
* Inventory and fulfillment connections
* App integrations tied to product IDs

{% hint style="success" %}
This makes re-linking **safe for both dev and production Shopify stores**.
{% endhint %}
