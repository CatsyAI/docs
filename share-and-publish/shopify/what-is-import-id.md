---
hidden: true
---

# What is Import ID

Shopify uses **Global IDs (GIDs)** as its internal identifiers for products and variants.\
Importing Shopify GIDs into Catsy allows Catsy to recognize and link to **existing Shopify products** during syncs.

This process is required for accurate product relinking.

### What Is a Shopify GID?

A Shopify GID is a globally unique identifier in this format:

```
gid://shopify/Product/15056253616499
```

You can find it:

* In the Shopify Admin URL when viewing a product
* After the final `/` in the product URL

### Setting Up GID Attributes in Catsy

To support multiple Shopify stores (e.g. production and dev), create **separate GID attributes** in Catsy.

#### Example Attributes

* `Prod GID` (production store)
* `Dev GID` (development store)

These attributes:

* Store the Shopify product GID
* Should live in a core or shared attribute group
* Must be mapped in every Shopify channel

### Linking GID Attributes to Shopify Channels

For each Shopify channel in Catsy:

1. Go to **Channel Settings**
2. Open **Advanced Settings**
3. Assign the correct GID attribute to the channel
   * Production channel → `Prod GID` attribute
   * Dev channel → `Dev GID` attribute

This tells Catsy to use this attribute to identify existing Shopify products in this store.

### Import GIDs

Use the Easy Import feature in Catsy to import your GIDs. Simply go to Products > Easy Import, and select the last option - Import Third Party Product IDs:&#x20;

<figure><img src="../../.gitbook/assets/image (1272).png" alt=""><figcaption></figcaption></figure>

Once a GID is stored on a Catsy product:

* Catsy knows exactly which Shopify product to target
* Syncs update the existing product instead of creating a new one
* Relinking becomes possible through the Shopify channel UI
