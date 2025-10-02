---
hidden: true
---

# Attribute Mapping

The attribute mapping page is where you match the channel's attributes to your master attributes.&#x20;

<figure><img src="https://cforce.atlassian.net/wiki/download/thumbnails/5373953/image2023-3-29_16-25-58.png?version=1&#x26;modificationDate=1680096360606&#x26;cacheVersion=1&#x26;api=v2&#x26;width=1280&#x26;height=557" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (1190).png" alt="" data-size="line"> These are the attributes unique to the channel (green tag). They contain validation and restrictions that are required by the channel.&#x20;

<img src="../.gitbook/assets/image (1191).png" alt="" data-size="line"> Mapping - This column shows how the channel attribute is mapped.

<img src="../.gitbook/assets/image (1192).png" alt="" data-size="line"> Data source - This tells you where the values are coming from such as the master attribute (black tag).

<img src="../.gitbook/assets/image (1193).png" alt="" data-size="line"> Completeness - This score shows you the percentage of items for a specific attribute that have validated data.&#x20;

**There are multiple attribute types of attributes to map channel attributes:**

* [(Text) String Mapping](attribute-mapping.md#text-string-mapping)
* [Asset Mapping](attribute-mapping.md#asset-mapping)
* [Picklist Mapping](attribute-mapping.md#picklist-mapping)
* [Constant Mapping](attribute-mapping.md#constant-mapping)

***

### (Text) String Mapping

Mapping a channel attribute that is a (text) string to a master attribute.&#x20;

<img src="../.gitbook/assets/image (1195).png" alt="" data-size="line"> To map a (text) string attribute inside a channel either hoover over the area highlighted in yellow or click the attribute name to bring up the selection window.\


<figure><img src="https://cforce.atlassian.net/wiki/download/thumbnails/6881327/image2022-3-8_13-7-18.png?version=1&#x26;modificationDate=1646737638794&#x26;cacheVersion=1&#x26;api=v2&#x26;width=1779&#x26;height=557" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (1196).png" alt="" data-size="line"> This popup will allow you to select the master attribute you want to populate the channel attribute with. You can use the 'Attributes search..' or scroll through the list.

<img src="../.gitbook/assets/image (1197).png" alt="" data-size="line"> Make your selection and then click Save.\


<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6881327/image2023-2-1_15-45-41.png?version=1&#x26;modificationDate=1675259143601&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (1198).png" alt="" data-size="line"> A successful mapping

1. Master data
2. Data populated into channel attribute. The green checkmark means it's validated against the channel's requirements such as character length.

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6881327/image2023-2-1_15-46-0.png?version=1&#x26;modificationDate=1675259162733&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

***

### &#x20;Asset Mapping

Mapping a channel attribute that is an asset to a master attribute.\
\
<img src="../.gitbook/assets/image (1199).png" alt="" data-size="line"> To map an asset attribute inside a channel either hoover over the area highlighted in yellow or click the attribute name to bring up the selection window.

<figure><img src="https://cforce.atlassian.net/wiki/download/thumbnails/6914062/image2022-3-8_15-33-49.png?version=1&#x26;modificationDate=1646746429248&#x26;cacheVersion=1&#x26;api=v2&#x26;width=1678&#x26;height=149" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (1200).png" alt="" data-size="line"> This popup will allow you to select the master attribute you want to populate the channel attribute with. You can filter attributes by data type or scroll through the list.

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6914062/image2023-2-1_15-46-42.png?version=1&#x26;modificationDate=1675259205086&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (1202).png" alt="" data-size="line"> Make your selection and then click Save.

\
You can then also use the Asset Transformation option to help you Build a formula that resizes, renames, or transforms an asset. You can use this option if you have specific channel guidelines you need to follow.

* Rename Asset - If you need to Base the name on the Item Number -from the drop down choose 'Attribute'  and select 'Item ID', then click 'Save' for example:

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6914062/image2023-2-1_15-47-8.png?version=1&#x26;modificationDate=1675259231621&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6914062/image2023-2-1_15-47-36.png?version=1&#x26;modificationDate=1675259258904&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

* Transform Asset - If you need to choose a specific format or size for all assets

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6914062/image2023-2-1_15-48-7.png?version=1&#x26;modificationDate=1675259289903&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

To check the result of the transformation, click on the mapped attribute and open the URL in your browser:

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6914062/image2023-2-1_15-48-25.png?version=1&#x26;modificationDate=1675259308375&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

***

### Picklist Mapping

\
You can also choose a picklist value as a Constant. Click on the arrow to expand the drop-down, choose your value, and click '**Save'**.

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/7077951/image2023-2-1_15-54-31.png?version=1&#x26;modificationDate=1675259673456&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

You can go back to the Picklist Channel Attribute and check the populated value.

<figure><img src="https://cforce.atlassian.net/wiki/download/thumbnails/7077951/image2022-3-15_13-31-34.png?version=1&#x26;modificationDate=1647349971878&#x26;cacheVersion=1&#x26;api=v2&#x26;width=1637&#x26;height=880" alt=""><figcaption></figcaption></figure>

***

### Constant Mapping

The constant attribute mapping option is used when you have to use specific wording, company name to add to all your products for example 'B**rand Name'**, '**Warranty Company'**, etc.

\
In this case type, the Warranty Company name in the field '**Enter a constant value'** and click '**Save'**:

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6848547/image2023-2-1_15-55-5.png?version=1&#x26;modificationDate=1675259707494&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

Once you do this go back to the Channel Attribute and check if the name has populated for all products.

<figure><img src="https://cforce.atlassian.net/wiki/download/attachments/6848547/image2023-2-1_15-55-20.png?version=1&#x26;modificationDate=1675259723128&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

