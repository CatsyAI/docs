---
hidden: true
---

# Custom Entities

A Custom Entity in Catsy contains relevant information in the format of a lookup table that is quickly accessed by the system to simplify the data transformation process These tables contain data for products, pricing, rates, currency, discounts, specifications, individual customers, and more, and are used in various combinations to calculate main attributes' values across the PIM.

***

## Create Custom Entity Definition <a href="#create_custom_entity_definition" id="create_custom_entity_definition"></a>

All custom entities in Catsy require a set of attributes to serve as headers for the lookup table. If you already have a Custom Entity type attribute group you can use, skip this part.

<img src="../.gitbook/assets/image (814).png" alt="" data-size="line"> Go to 'Attribute Groups'

<figure><img src="../.gitbook/assets/image (970).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (815).png" alt="" data-size="line"> Select 'Custom Entity' from the tabs on the left-hand side. Create the Attribute Group to be used by the Custom Entity by clicking on 'Add Attribute Group' button:\


<figure><img src="../.gitbook/assets/image (1012).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (816).png" alt="" data-size="line"> Fill out the Attribute Group name and click on 'Save' button.

<img src="../.gitbook/assets/image (817).png" alt="" data-size="line"> Select the above created Attribute Group, and click on the 'Add New Attributes', to add the attributes you will need in your Custom Entity table:

<figure><img src="../.gitbook/assets/image (1014).png" alt=""><figcaption></figcaption></figure>

\
For instance, we have added four Attributes, to the 'Attribute Group Demo' created above, three as Text, and one as Picklist:

<figure><img src="../.gitbook/assets/image (976).png" alt=""><figcaption></figcaption></figure>



***

## Create the Custom Entity itself <a href="#create_the_custom_entity_itself" id="create_the_custom_entity_itself"></a>

<img src="../.gitbook/assets/image (818).png" alt="" data-size="line"> Go to _Main Menu > More > Custom Entity_, and then click on 'Add Lookup Table':\


<figure><img src="../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (979).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (819).png" alt="" data-size="line"> Provide the lookup table name, and select the appropriate attribute group from the 'Select Custom Entity Attribute Group' list. Click the 'Next' button:

<figure><img src="../.gitbook/assets/image (1016).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (820).png" alt="" data-size="line"> Select the lookup attributes for your Custom Entity from the list shown. These will be used to look up the rest of the data in the Custom Entity table. Click the 'Save' button:

<figure><img src="../.gitbook/assets/image (1017).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Lookup attributes will be used as parameters to retrieve values from the custom entity (lookup table). These values will be retrieved using functions, as will be explained in Using Custom entities with formulas.
{% endhint %}

{% hint style="warning" %}
Then the Custom Entity is ready for their records to be provided, as explained in Manage Custom Entities: add, remove, import, or export records.
{% endhint %}

***

## Retrieve values from a Custom Entity <a href="#retrieve_values_from_a_custom_entity" id="retrieve_values_from_a_custom_entity"></a>

To retrieve the information from the Custom Entities, the params selected (Lookup Attributes) during their creation are used.

{% hint style="warning" %}
For a detailed explanation see the article Create Custom Entity.
{% endhint %}

The following structure must be used:

<img src="../.gitbook/assets/image (822).png" alt="" data-size="line"> The word catsy.

<img src="../.gitbook/assets/image (825).png" alt="" data-size="line"> The Custom Entity's Key. Which can be retrieved as follows:\
\- Go to _Main Menu > More > Custom Entity_, and then click on gear ('Settings') on the right of the desired custom entity:

<figure><img src="../.gitbook/assets/image (1018).png" alt=""><figcaption></figcaption></figure>

\
\- And its Key will be shown:\


<figure><img src="../.gitbook/assets/image (1019).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (824).png" alt="" data-size="line"> Then a dot, plus the word lookup, followed by in parentheses and -if there are several- comma-separated, the desired Values to match, in the same order as Lookup Attributes configured in the creation of the Custom Entity.

{% hint style="warning" %}
The attributes of the Attribute Group that are used as Lookup Attributes in the Custom Entity will be shown in green text in the Custom Entity header.
{% endhint %}

<img src="../.gitbook/assets/image (826).png" alt="" data-size="line"> To verify which attributes are:\
\- Go to _Main Menu > More > Custom Entity_, and then click on the desired Custom Entity

<figure><img src="../.gitbook/assets/image (1021).png" alt=""><figcaption></figcaption></figure>

\- In this example only 'COLOURS', but there could be several of them:

<figure><img src="../.gitbook/assets/image (988).png" alt=""><figcaption></figcaption></figure>

\- At this level, the record is retrieved, then if only an Attribute of that record is needed, it can be retrieved following the parentheses with a dot, and the desired Attribute's Key.

Recapping, following the above screenshots, this code used in a function:

`catsy.bigcommerceswatches.lookup("Brown")`

Will retrieve the second record in the image above.

While:

`catsy.bigcommerceswatches.lookup("Brown").colorhexcode1`

Will retrieve the Color value of that attribute. Which in this case is: #A76D54.



If such a function is used on a Product, and that product has an Attribute that stores the name of a color, it can be used instead of “Brown” above, and will return the corresponding value or record. For example the code:

`catsy.bigcommerceswatches.lookup(product.color)`

Would return the record that matches the color of the stored Product. Then that record can be stored in a variable, and its Attributes retrieved as needed.

***

## Select the Custom Entity to work with <a href="#select_the_custom_entity_to_work_with" id="select_the_custom_entity_to_work_with"></a>

<img src="../.gitbook/assets/image (827).png" alt="" data-size="line"> Go to _Main Menu > More > Custom Entity_\


<figure><img src="../.gitbook/assets/image (1020).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (828).png" alt="" data-size="line"> Then click on the desired Lookup Table to work with

<figure><img src="../.gitbook/assets/image (1022).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Lookup Tables are the data structures Custom Entities are stored into.
{% endhint %}

Now that the desired Lookup Table is open, we are able to add or remove, and import or export records, as explained bellow.

***

## Add records to a Custom Entity <a href="#add_records_to_a_custom_entity" id="add_records_to_a_custom_entity"></a>

<img src="../.gitbook/assets/image (829).png" alt="" data-size="line"> Select the Custom Entity as indicated above

<img src="../.gitbook/assets/image (830).png" alt="" data-size="line"> Click on the 'Add' button, in this example 'Example'

<figure><img src="../.gitbook/assets/image (1023).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (831).png" alt="" data-size="line"> Then provide the Attributes that appear in the window. These attributes will be the ones provided during the creation of the Custom Entity, and can contain several types of data (string, data, boolean, picklist, etc), being optional or required, as configured during its creation. Once at least the required ones are provided, this record will be created by clicking on the 'Create' button

<figure><img src="../.gitbook/assets/image (1024).png" alt=""><figcaption></figcaption></figure>

***

## Remove records from a Custom Entity <a href="#remove_records_from_a_custom_entity" id="remove_records_from_a_custom_entity"></a>

<img src="../.gitbook/assets/image (832).png" alt="" data-size="line"> Select the Custom Entity as indicated above

<img src="../.gitbook/assets/image (833).png" alt="" data-size="line"> Click on the checkboxes on the left of every record to be deleted, or the checkbox in the left side of the header to select all of them (previously a filter can be used to narrow the list), then click on the 'Delete' button

<figure><img src="../.gitbook/assets/image (1025).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Caution: no dialog box will appear, the deletion will occur immediately after clicking the “Delete” button, and it will not be possible to undo it.
{% endhint %}

***

## Import records into a Custom Entity <a href="#import_records_into_a_custom_entity" id="import_records_into_a_custom_entity"></a>

<img src="../.gitbook/assets/image (834).png" alt="" data-size="line"> Select the Custom Entity as indicated above

<img src="../.gitbook/assets/image (835).png" alt="" data-size="line"> It is necessary to prepare a file containing the values beforehand. As usual, the file will contain the field keys in the first row; and below them the values of one record in each subsequent row. The easiest way to obtain a template is to export a single existing record\


<figure><img src="../.gitbook/assets/image (1026).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (836).png" alt="" data-size="line"> Click on the 'Import' button\


<figure><img src="../.gitbook/assets/image (1027).png" alt=""><figcaption></figcaption></figure>

<img src="../.gitbook/assets/image (837).png" alt="" data-size="line"> Once the importation process ends, a summary is provided\


<figure><img src="../.gitbook/assets/image (1028).png" alt=""><figcaption></figcaption></figure>

***

## Export records from a Custom Entity <a href="#export_records_from_a_custom_entity" id="export_records_from_a_custom_entity"></a>

<img src="../.gitbook/assets/image (838).png" alt="" data-size="line"> Select the Custom Entity as indicated above

<img src="../.gitbook/assets/image (839).png" alt="" data-size="line"> Click the checkboxes to the left of each record you wish to delete, or click the checkbox to the left of the header to select them all (you can previously use a filter to restrict the list), and then click the 'Export' button. A dialog box will appear to save the file to your disk drive

<figure><img src="../.gitbook/assets/image (1029).png" alt=""><figcaption></figcaption></figure>
