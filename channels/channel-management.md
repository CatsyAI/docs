# Channel Management

Channels give the ability to configure exports for channel partners to meet their import requirements. These can be a .CSV format, .XLS format, or a .JSON format. Once the channel has been created and configured, exports are a simple process to get them in the desired format.

There are two ways to create a channel, one from an already existing template, and another by creating a new template from Attributes contained within Catsy.

<figure><img src="../.gitbook/assets/image (1205).png" alt=""><figcaption></figcaption></figure>

***

### Channels Menu Navigation

<figure><img src="../.gitbook/assets/image (1206).png" alt=""><figcaption></figcaption></figure>

The Channels menu navigation includes an option along the top to add a new Channel, along the side are filters by channel type.

***

### New Channel from Template

To create a Channel from an already existing spreadsheet, complete the following steps:

1. Navigate to '**Channel'**, located in the top navigation bar
2. Click '**Install Channel'**
3.  On the next step, select which format the template should be exported in.<br>

    <figure><img src="../.gitbook/assets/image (1207).png" alt=""><figcaption></figcaption></figure>
4. On Step 1, select '**Click here if you have a template that you want the data in'**&#x20;
5. On the next step, choose the template file
6.  On step 3, enter the desired name for the channel being created<br>

    <figure><img src="../.gitbook/assets/image (1208).png" alt=""><figcaption></figcaption></figure>

(Sample Excel Template)

\
On step 4, select worksheets where the data should be populated

1. For any tab that should be ignored, select '**Ignore this tab'**
2. For any tab that should be completed, choose '**Populate this tab'** and complete the following steps under '**Select Template Row'**
3. **N/A** - select when row should be ignored
4. **Attribute Name Row** - select which row should contain Attribute names
5. **Attribute Key Row** - select which row should contain Attribute keys
6. **Validation Level Row** - select which row should contain validation level
7.  **First Body Row** - select which row data population should begin on<br>

    <figure><img src="../.gitbook/assets/image (1209).png" alt=""><figcaption></figcaption></figure>
8. On Step 5, review the Scanned Attributes Report. Address and missing attributes, and click '**Continue'**
9.  On Step 6, paste a list of product SKUs (separated by comma) to be included in the channel, or use the product browser by clicking on '**click here'**<br>

    <figure><img src="../.gitbook/assets/image (1210).png" alt=""><figcaption></figcaption></figure>

Once done, click '**Finish'**

{% hint style="info" %}
Note: Remember that when you are installing an Excel type channel with a prepared template, if your template has a Validation Row, then the values that Catsy will detect are only "Required" or "Optional". If the Validation Level is indicated by using "Y" , "N", "Yes" or "No" then the validation level won't be detected properly and the validation level won't be noted correctly on the Channel's Attribute Mapping page\
\
![](<../.gitbook/assets/image (1259).png>)  ![](<../.gitbook/assets/image (1260).png>)
{% endhint %}



***

### New Channel from Attributes

To create a Channel from Attributes within Catsy, complete the following steps:

1. Navigate to '**Channels'**, located in the top navigation bar
2. Select '**Install Channel'**
3. On the next step, select which format the data should be exported in
4. On Step 1, select '**Click here if you do not have a template and want to create the export by selecting attributes'**
5.  On Step 2, select which Attributes should be included as part of the channel<br>

    <figure><img src="../.gitbook/assets/image (1217).png" alt=""><figcaption></figcaption></figure>
6. On the next step, enter the Channel name
7. On the final step, enter a list of SKUs, separated by commas. The product browser can also be used by clicking '**Click Here'**
8. When done, click '**Finish'**

***

### Navigation Inside a Channel

When a channel has been selected, there are several navigation options available in both the top and left-hand navigation bar. \
The top navigation includes the following options: <br>

<figure><img src="../.gitbook/assets/image (1218).png" alt=""><figcaption></figcaption></figure>

* **Export** - completes Export of channel in configured format
* **Search** - allows for search by SKU
* **Group Variants** - groups or ungroups products with variants
* **Filter** - filter products in Channel based on Attribute
* **Add Products** - add products to Channel
* **Attributes Selection** - changes which Attributes are displayed in the channel view of products
* **Remove Products** - removes selected product(s) from Channel
* **Sort** - allows for sorting products by any Attribute in Channel

<div align="left"><figure><img src="../.gitbook/assets/image (1219).png" alt="" width="260"><figcaption></figcaption></figure></div>

The side navigation includes the following options:

* **Products** - shows products contained within channel
* **Attribute Mapping** - click to change Attribute mapping
* **Settings**
  * **Overview** - shows basic Channel details
  * **Asset Scaling** - set default dimensions and format for asset exports
  * **Format and Scheduling** - schedule Channel exports
  * **Publishing History** - view export history
  * **Template Details** - change Channel template, along with viewing errors in template parameters
  * **Advanced** - change Advanced details of Channel

***

### Exporting a Channel

To Export a channel, complete the following steps:

1. Navigate to '**Channels'**
2. Select Channel to be exported
3. Click '**Export'**
4. On the first step, enter where the Export should be emailed to, along with one of the following options:
   * **Browse & Select Products** - allows for products to be selected for the export via Product Browser or a list of SKUs
   * **Updates Only** - select a date range, and only products updated within that date range will be exported
   * **Added to Channel** - select a date range, and only products added within that date range will be exported
   * **Deleted from Channel** - select a date range, and only products deleted from the channel within that date range will be exported
   * **Selected Products** - only products selected prior to pressing **“Export”** will be included in the export
   *   **All Products** - all products within the channel will be exported<br>

       <figure><img src="../.gitbook/assets/image (1220).png" alt=""><figcaption></figcaption></figure>
5. On the next step, select from the following options:
   1. **All Data** - Export all data
   2. **Completed Products** - Export products with required attributes populated
   3. \*Advanced may be selected if export format should be changed
6. When '**Export'** is clicked, the data will be exported and emailed to the email address listed.
