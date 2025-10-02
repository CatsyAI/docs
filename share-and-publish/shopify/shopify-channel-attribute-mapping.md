# Shopify Channel Attribute Mapping

**Every Shopify channel in Catsy has to be mapped before any data is synced to the online platform.**

1. [Required mappings](shopify-channel-attribute-mapping.md#required-mappings)
2. [Optional but important mappings](shopify-channel-attribute-mapping.md#optional-but-important-mappings)
3. [Additional optional mappin](shopify-channel-attribute-mapping.md#additional-optional-mappings)

***

### Required mappings

{% hint style="info" %}
Required mappings should always have an output value, meaning even if they are mapped to an attribute with a missing value, a formula should be put in place to ensure that the field is always populated.
{% endhint %}

**Title:** usually mapped to Product Name or Shopify Title.&#x20;

**SKU**: mapped to Product Number, SKU or Shopify SKU.

**Weight**: mapped to the variant's weight attribute. Use a formula to ensure an output every time, e.g.:

`if (product.weight_lbs.isEmpty()) { "0" } else { product.weight_lbs }`

**Price**: mapped to the variant's price attribute. If mapping to a price attribute, use a formula to output the value of the price without the currency code:

`if (product.price.isEmpty()) { "0" } else { product.price.getAmount() }`

***

### Optional but important mappings

**Handle**: mapping a handle is optional, if you have a handle attribute in Catsy. If not, Shopify will convert the name of your product into a handle by default

**Body HTML**: mapped to the product's Description or Shopify Description. This field supports Rich Text Formatting so you can map to a Rich Text field in Catsy. The formatting will carry over to Shopify

**Default Image**: _mapped to the parent product's image_. Please use an image transformation to ensure the image size is compatible with Shopify's requirements:

`product.main_image.getTransformedAsset('_xl')`

**Variant Image**: _mapped to the variant's image_. Again, use image transformation to ensure the image size is compatible with Shopify's requirements.

***

### Additional optional mappings

**Images**: mapped to the parent's secondary images. Please use an image transformation to ensure the image size is compatible with Shopify's requirements.

**Collections**: mapped to the product's Category attribute.

**Tags**: mapped to the product's Tags attribute.

**Variant Data**: mapped to the variant's attributes, e.g.:

<figure><img src="../../.gitbook/assets/image (1256).png" alt=""><figcaption></figcaption></figure>

**Syncing a rich text field:** in your Shopify channel you can map to a rich text format field and sync that to Shopify but you need to use a conversion formula. The formula is available [here](../../transform/formulas.md), in Catsy’s list of formulas\
\
**Syncing files or metaobjects**: In order to sync any information to Shopify referencing files or metaobjects, you need to store their GIDs in Catsy in a [custom entity table](../../mdm/entities.md). Once this is done, you can sync to Catsy using a formula similar to this one:

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
