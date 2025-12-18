---
description: >-
  This guide explains how to successfully sync product data from Catsy PIM to
  Shopify, combining Catsy’s official Shopify documentation with internal best
  practices.
hidden: true
coverY: 0
---

# Shopify User Guide

1. Introduction: Products in Catsy and Shopify
2. Preparing Your Product Data
3. Shopify Channel Setup in Catsy
4. Syncing Product Metafields
5. Sync Process
6. Channel Sync Messages
7. Common Mistakes to Avoid

### <img src="../../.gitbook/assets/image (1) (1).png" alt="" data-size="line"> Products in Catsy and Shopify

Understanding how Catsy product structures translate into Shopify is critical before syncing.

**Key rule:** A product should be **either** a standalone **or** a parent with variants — never both.

| Catsy               | Shopify            |
| ------------------- | ------------------ |
| Standalone Product  | Standalone Product |
| Parent Product      | Shopify Product    |
| Variant of a Parent | Shopify Variant    |

{% hint style="danger" %}
Badly setup structure in Catsy leads directly to issues in Shopify such as:

* Duplicate product pages
* Broken size or color selectors
* Inconsistent swatches and filters
{% endhint %}

### <img src="../../.gitbook/assets/image (2) (1).png" alt="" data-size="line"> Preparing Your Product Data

_**Standardize Product Structure**_

In Catsy:

* Parent products hold shared data: title, description, brand, specifications
* Variants only store what is unique: size, color, material differences
* Each variant must reference exactly one parent

In Shopify:

* All variants appear under a single product page
* Differences are displayed as **options** (Color, Size, etc.)

_**Think About Identifiers**_

Two fields control product identity in Shopify:

* **SKU** – internal identifier (must remain stable)
* **Handle** – Shopify’s public identifier (URL)

{% hint style="success" %}
_**Best practice:**_ generate your handles in Catsy, and sync the products with them. Never manually edit the handles in Shopify.
{% endhint %}

{% hint style="danger" %}
If a SKU or handle changes unexpectedly, Shopify treats the product as new, causing:

* Duplicates
* Lost inventory links
* Broken metafields and collections


{% endhint %}

### <img src="../../.gitbook/assets/image (3) (1).png" alt="" data-size="line"> Shopify Channel Setup in Catsy

When configuring your Shopify channel in Catsy, you define:

* Which products are eligible to sync
* How attributes map to Shopify fields
* How variants, images, options, and metafields behave

{% hint style="success" %}
_**Best practice**_: avoid pushing all attributes into the product description. Use metafields for structured data.
{% endhint %}

Every Shopify channel in Catsy has to be mapped before any data is synced to the online platform.

**Required mappings**

{% hint style="info" %}
Required mappings should always have an output value, meaning even if they are mapped to an attribute with a missing value, a formula should be put in place to ensure that the field is always populated.
{% endhint %}

Titl&#x65;**:** usually mapped to Product Name or Shopify Title.&#x20;

SKU: mapped to Product Number, SKU or Shopify SKU.

Weight: mapped to the variant's weight attribute. Use a formula to ensure an output every time, e.g.:

`if (product.weight_lbs.isEmpty()) { "0" } else { product.weight_lbs }`

Price: mapped to the variant's price attribute. If mapping to a price attribute, use a formula to output the value of the price without the currency code:

`if (product.price.isEmpty()) { "0" } else { product.price.getAmount() }`

_**Optional but important mappings**_

Handle: mapping a handle is optional, if you have a handle attribute in Catsy. If not, Shopify will convert the name of your product into a handle by default

Body HTML: mapped to the product's Description or Shopify Description. This field supports Rich Text Formatting so you can map to a Rich Text field in Catsy. The formatting will carry over to Shopify

Default Image: _mapped to the parent product's image_. Please use an image transformation to ensure the image size is compatible with Shopify's requirements:

`product.main_image.getTransformedAsset('_xl')`

Variant Image: _mapped to the variant's image_. Again, use image transformation to ensure the image size is compatible with Shopify's requirements.

**Additional optional mappings**

Images: mapped to the parent's secondary images. Please use an image transformation to ensure the image size is compatible with Shopify's requirements.

Collections: mapped to the product's Category attribute.

Tags: mapped to the product's Tags attribute.

Variant Data: mapped to the variant's attributes, e.g.:

<figure><img src="../../.gitbook/assets/image (1256).png" alt=""><figcaption></figcaption></figure>

Syncing a rich text field: in your Shopify channel you can map to a rich text format field and sync that to Shopify but you need to use a conversion formula. The formula is available [here](../../transform/formulas.md), in Catsy’s list of formulas\
\
Syncing files or metaobjects: In order to sync any information to Shopify referencing files or metaobjects, you need to store their GIDs in Catsy in a [custom entity table](../../mdm/entities.md). Once this is done, you can sync to Catsy using a formula similar to this one:

```
def result = []
product.web_technology_callout.forEach(s -> {
    def gid = catsy.technology_callout_gids.lookup(s).shopify_metaobject_gid
    if (gid) {
        result += "gid://shopify/Metaobject/" + gid
    }
})
product.web_sustainability_callout.forEach(s -> {
    def gid = catsy.sustainability_callout_gids.lookup(s).shopify_metaobject_gid
    if (gid) {
        result += "gid://shopify/Metaobject/" + gid
    }
})
result
```

### <img src="../../.gitbook/assets/image (8).png" alt="" data-size="line"> Syncing Product Metafields

_**Start off in Shopify**_&#x20;

If you have no metafields already created in Shopify, go to Settings > Custom Data > Products > Add definition. Here, create a new metafield definition with namespace called 'custom'.&#x20;

<figure><img src="../../.gitbook/assets/image (1011).png" alt=""><figcaption></figcaption></figure>

This will create your namespace in Shopify&#x20;

_**Continue in Catsy**_

Go to Attributes and select one or more of your attributes that you'd like to send to Shopify as metafields. Click on the three dots menu, and select 'Create Metafield Defs in Shopify:

<figure><img src="../../.gitbook/assets/image (922).png" alt=""><figcaption></figcaption></figure>

Select the custom namespace you created. This way your metafield will be sent to Shopify with your next sync.

<figure><img src="../../.gitbook/assets/image (924).png" alt=""><figcaption></figcaption></figure>

Add values for these attributes to existing products:

<figure><img src="../../.gitbook/assets/image (925).png" alt=""><figcaption></figcaption></figure>

Sync and see the data in metafields in Shopify:

<figure><img src="../../.gitbook/assets/image (926).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (927).png" alt=""><figcaption></figcaption></figure>

### <img src="../../.gitbook/assets/image (5) (1).png" alt="" data-size="line"> Sync Process

Catsy uses **delta-based syncing**, meaning only detected changes are sent to Shopify. Here are the sync actions that make up the sync process:

**Generate Delta (Manual or Scheduled)**

* Scans for Create, Update, and Delete actions

**Retry Sync (Manual)**

* Re-syncs selected products and their variants
* Includes full attribute, media, option, and metafield sync

**Sync Selected**

* Pushes only explicitly selected products or variants

Catsy has sync thresholds to protect your Shopify store from unintended large-scale changes. For each delta run, Catsy calculates:

* **Create %** – new parents and variants
* **Update %** – products with changed values
* **Delete %** – products marked for deletion

The percentage is calculated relative to the total product count in the Shopify store. If a threshold is exceeded, the channel status becomes:

{% hint style="danger" %}
**SUSPENDED\_SYNC**
{% endhint %}

This prevents accidental mass updates or deletions.

_**Delete Threshold (Most Important)**_

* Protects against large accidental deletions
* Variant deletions caused by parent restructuring still respect thresholds

### <img src="../../.gitbook/assets/image (6).png" alt="" data-size="line"> Channel Sync Messages

Here is a list of common errors when syncing to Shopify: [https://catsyhq.gitbook.io/docs/share-and-publish/shopify/shopify-channel-messages](https://catsyhq.gitbook.io/docs/share-and-publish/shopify/shopify-channel-messages)

### <img src="../../.gitbook/assets/image (9).png" alt="" data-size="line"> Common Mistakes to Avoid

{% hint style="danger" %}
#### Pushing Technical Specs into Descriptions

* Makes pages hard to read
* Breaks layouts
{% endhint %}

{% hint style="success" %}
**Fix:** Use metafields for technical data
{% endhint %}

{% hint style="danger" %}
#### Mismatched Metafield Data Types

If Catsy and Shopify metafield data types differ:

* Data may be rejected
* Filters may fail
* Layouts may break
{% endhint %}

{% hint style="success" %}
**Fix:** Align metafield definitions before syncing
{% endhint %}

{% hint style="danger" %}
#### Overcomplicated Mapping Formulas

Complex formulas are:

* Hard to maintain
* Fragile
* Error-prone
{% endhint %}

{% hint style="success" %}
**Fix:**

* Normalize data in Catsy
* Keep mappings simple
{% endhint %}
