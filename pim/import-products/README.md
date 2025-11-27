---
description: >-
  Supercharge your product catalog with Catsy PIM's robust import tool—designed
  for seamless bulk uploads of new or updated data, including variants, custom
  attributes, and picklists.
---

# Import Products

**How It Works – Easy Steps:**

1. Head to _Products > Easy Import_ and select _Import Products_.
2. Upload your CSV/Excel file with a main identifier column (e.g., SKU) and attribute headers.
3. Auto-map matching headers; manually adjust others for precision.
4. Handle variants: Import parents first, then variants with parent SKUs and _Option Attributes_ (pipe-delimited keys) plus _Variation Sequence_ for ordering.
5. For assets, reference URLs or filenames; categories use hierarchical paths <mark style="color:orange;">(e.g., root > level 1).</mark>
6. Review mapping, then import—large jobs (>500 items) queue in _Import/Export Jobs_ for tracking.

Pro tips: Pre-create categories, validate data types (e.g., integers only), and download error logs post-validation. Advanced options let you skip creations, auto-build picklists, or delete empties.<br>

1. [Easy Import](./#easy-import)
2. [Advanced options](./#advanced-options)
3. [Large imports](./#large-imports)
4. [Import file formats](./#import-formats)
5. [Parents and variants](./#importing-parents-and-variants)
6. [Update existing products](./#update-existing-products)
7. [Importing Option Attributes](./#importing-option-attributes)

***

### Easy Import

<img src="../../.gitbook/assets/image (646).png" alt="" data-size="line"> Go to _Products > Easy Import_

<img src="../../.gitbook/assets/image (650).png" alt="" data-size="line"> Select 'Import Products'

<figure><img src="../../.gitbook/assets/image (898).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (654).png" alt="" data-size="line"> Upload an import file. Your import file must contain a column with your main identifier, e.g. SKU or Part Number. The rest of the columns in your import file can contain any attribute you want to populate or update. Download an example of an import file [here](https://app.catsy.com/app/dashboard/courses).

{% hint style="info" %}
Make sure your column headers are either attribute names or keys. If they are mixed, not all will be auto-mapped.
{% endhint %}

<img src="../../.gitbook/assets/image (658).png" alt="" data-size="line"> Select your main identifier from one of the column headers of your import file

<figure><img src="../../.gitbook/assets/image (684).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (661).png" alt="" data-size="line"> Complete the missing mapping if the import was not auto-mapped

<figure><img src="../../.gitbook/assets/image (685).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Any column header that **is an exact match** to your attribute names or keys will be **auto-mapped**. Any header that **differs from your attribute names or keys** you will need to **manually re-map**.
{% endhint %}

<img src="../../.gitbook/assets/image (666).png" alt="" data-size="line"> Review the evaluation screen and click 'Next' to proceed

<figure><img src="../../.gitbook/assets/image (686).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
If you are importing a large file, your evaluation screen will tell you you need to proceed to the Import/Export jobs page. Please review the [Large imports](./#large-imports) section below.
{% endhint %}

***

### Advanced options

{% hint style="info" %}
Catsy offers you various advanced options when importing products. They are available for selection during step <img src="../../.gitbook/assets/image (662).png" alt="" data-size="line">above.
{% endhint %}

<img src="../../.gitbook/assets/image (647).png" alt="" data-size="line">Click on 'Create picklist values & advanced options'

<figure><img src="../../.gitbook/assets/image (687).png" alt=""><figcaption></figcaption></figure>

You can choose from the following import advanced options:

<img src="../../.gitbook/assets/image (651).png" alt="" data-size="line"> Skip new products creation to only update existing products

<img src="../../.gitbook/assets/image (655).png" alt="" data-size="line"> Create any picklist values not present in Catsy from your current import file

<img src="../../.gitbook/assets/image (659).png" alt="" data-size="line"> Opt to delete values in Catsy corresponding to the empty cells in your import file

<img src="../../.gitbook/assets/image (663).png" alt="" data-size="line"> Create custom attributes

<figure><img src="../../.gitbook/assets/image (688).png" alt=""><figcaption></figcaption></figure>

***

### Large imports

If you are importing a file containing over 500 products or over 100 attributes, that import needs to be evaluated asynchronously and imported after evaluation.

<img src="../../.gitbook/assets/image (648).png" alt="" data-size="line"> After finishing the Easy Import process, please proceed to the Import/Export jobs page at [https://app.catsy.com/app/export-jobs](https://app.catsy.com/app/export-jobs)

<img src="../../.gitbook/assets/image (652).png" alt="" data-size="line"> In _Products > Import/Export jobs_ find the last Import Validation job you created. You can narrow down your job selection by your <img src="../../.gitbook/assets/image (656).png" alt="" data-size="line"> job type and your <img src="../../.gitbook/assets/image (660).png" alt="" data-size="line"> user name

<figure><img src="../../.gitbook/assets/image (691).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (664).png" alt="" data-size="line"> Once your Import Validation job is marked as Completed, hover over it and locate the 'Import' button. Click on it to finish the import process

<figure><img src="../../.gitbook/assets/image (692).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (665).png" alt="" data-size="line"> To review your import errors and warnings, download the error log

<figure><img src="../../.gitbook/assets/image (693).png" alt=""><figcaption></figcaption></figure>

***

### Import formats

#### Integer

<img src="../../.gitbook/assets/image (302).png" alt="" data-size="line"> Only integer values can be imported into Integer attributes. Any value containing decimal points, letters or special characters will be rejected.

<img src="../../.gitbook/assets/image (303).png" alt="" data-size="line"> The following values **will&#x20;**<mark style="color:red;">**not**</mark>**&#x20;be imported**:\
`10.12`\
`15.0`\
`7.00`\
`3lbs`

<img src="../../.gitbook/assets/image (304).png" alt="" data-size="line"> The following values **will be imported**:\
`9`\
`13`

#### Category

<img src="../../.gitbook/assets/image (302).png" alt="" data-size="line"> The import process cannot create categories automatically. All categories must be created beforehand.

<img src="../../.gitbook/assets/image (303).png" alt="" data-size="line"> Categories are structured hierarchically, like a tree, with a root category at the top and child categories branching from it.

<img src="../../.gitbook/assets/image (304).png" alt="" data-size="line"> Each category can have any number of subcategories, creating multiple levels. The root category is at level 0.

<img src="../../.gitbook/assets/image (305).png" alt="" data-size="line"> The levels are separated by “>” in the category value of the import file.

<img src="../../.gitbook/assets/image (306).png" alt="" data-size="line"> Since whitespace around the separator are ignored, the following category values are equivalent, being the separator "`>`":\
`root > level 1 > level 2`\
`root>level 1>level 2`\
`root>level 1> level 2`

#### UPC

<img src="../../.gitbook/assets/image (302).png" alt="" data-size="line"> UPC values are stored as strings, not as numbers. This means that any alphanumeric character (letters, numbers or symbols) will be stored correctly.

<img src="../../.gitbook/assets/image (303).png" alt="" data-size="line"> It is also important to note that they are not compared as integers, but character by character.

<img src="../../.gitbook/assets/image (304).png" alt="" data-size="line"> This means that:\
`000122`\
is greater than:\
`0000123`

because when comparing character by character, the first three characters are equal (`000`). Then, the fourth character of `000122` (`1`) is greater than the fourth character of `0000123` (`0`), so `000122` is considered greater.

***

### Importing parents and variants

{% hint style="warning" %}
You need to make sure you have created any parent products prior to adding variants and linking them to their Parent SKU attribute
{% endhint %}

<img src="../../.gitbook/assets/image (302).png" alt="" data-size="line"> Import parent products using the [Easy Import](./#easy-import) steps listed above

<img src="../../.gitbook/assets/image (303).png" alt="" data-size="line"> Once finished with the parents import, proceed to _Products > Easy Import_ again

<img src="../../.gitbook/assets/image (304).png" alt="" data-size="line"> Upload the variants' import file. Your import file should look like a regular import file, with a column for your main identifier, e.g. SKU or Part Number, and a column for your Parent SKU number

<img src="../../.gitbook/assets/image (305).png" alt="" data-size="line"> Follow the steps outlined in [Easy Import](./#easy-import) to upload the variants' file

<img src="../../.gitbook/assets/image (306).png" alt="" data-size="line"> When viewing the products section after import, the variants will by nested within their respective Parent Product

***

### Update existing products

<img src="../../.gitbook/assets/image (649).png" alt="" data-size="line"> Export the product data that you want to update. Instructions on the how to export product data can be found here: [Export products](../export-products.md)

<img src="../../.gitbook/assets/image (653).png" alt="" data-size="line"> Use the exported file and directly update your product data in it. Save it as a new file when finished.

<img src="../../.gitbook/assets/image (657).png" alt="" data-size="line"> Import the saved file as described in the [Easy Import](./#easy-import) section

***

### Importing Option Attributes

\
When preparing your import file in order to bulk update the option attributes at variant level\
\
Add a new column called "Option Attributes" and add the option attribute keys that you'd like to give to your variants, if you need to add more than one option attribute separate the keys  by using a pipe symbol "|" as a delimiter\
\
Then, add columns for each option attribute so that you can add the attribute values at variant level<br>

<figure><img src="../../.gitbook/assets/image (1254).png" alt=""><figcaption></figcaption></figure>

If you wish to set a specific sequencing for the attribute values, remember to add an additional column called "Variation Sequence" so that you can sort the values as needed by using numbers "1, 2, 3, 4, etc"\
<br>

<figure><img src="../../.gitbook/assets/image (1255).png" alt=""><figcaption></figcaption></figure>
