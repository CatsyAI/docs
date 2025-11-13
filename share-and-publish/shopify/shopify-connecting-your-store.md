# Shopify: Connecting Your Store

Catsy connects to your Shopify store via a custom application that needs to be created in the Apps section of your store. Any user with admin access and app permissions is able to set up private apps and generate API credentials.&#x20;

{% hint style="warning" %}
In order to create a Shopify channel in Catsy, you will need to send us an API access token and the URL of your store. They will be used in Catsy to set up the Shopify password field and the link to the storefront.&#x20;
{% endhint %}

Here are a few short steps you can take to generate and find this API access token within your Shopify Store:

<img src="../../.gitbook/assets/1-g (2).png" alt="" data-size="line"> Login to your Shopify store and go to _Settings > Users and Permissions_ https://admin.shopify.com/store/\<store-name>/settings

<img src="../../.gitbook/assets/image (146).png" alt="" data-size="line"> Go to Apps and sales channels

<figure><img src="../../.gitbook/assets/image (89).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (90).png" alt="" data-size="line"> Click on Develop apps

<figure><img src="../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (93).png" alt="" data-size="line"> Create an app and <img src="../../.gitbook/assets/image (94).png" alt="" data-size="line"> type in 'Catsy' as the name of the new custom app

<figure><img src="../../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (1081).png" alt="" data-size="line"> Configure the new app’s API scope by clicking on the Configure Admin API scopes

<figure><img src="../../.gitbook/assets/image (1082).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (84).png" alt="" data-size="line"> Navigate to Inventory, Product listings, Products, Metaobject definitions and Metaobject entries and select 'write' and 'read' for all of them. Click 'Save'

<figure><img src="../../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (85).png" alt="" data-size="line"> Finish the app installation by clicking on 'Install app'

<figure><img src="../../.gitbook/assets/image (87).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (86).png" alt="" data-size="line"> Reveal and copy your access token.

{% hint style="danger" %}
WARNING, you’ll only be able to reveal your Admin API token once. Copy and save your Admin API access token in a secure place
{% endhint %}

<figure><img src="../../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

After you have your access token, _**save it and email it to support@catsy.com**_.
