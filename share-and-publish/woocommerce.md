---
description: 'When exporting products for Woocommerce, focus on these main topics:'
---

# WooCommerce

1. Export From Catsy
2. Manual Import into WooCommerce (Native import)
3. Scheduled Import into WooComerce (WP All Import)

***

## Export From Catsy

Before importing anything into WooCommerce, you need to properly export your product data from Catsy. Here’s the step-by-step process:

### **Step 1: Select Your Products**

* In your channel, navigate to products, and select the products you wish to add to channel
* Use filters or manual selection to choose the products you want to export.
* Only the selected products will be included in your export file.

***

### **Step 2: Map Your Attributes**

Before exporting, Catsy gives you the option to map your internal product attributes to WooCommerce's expected fields.

* For example:
  * Map `Product Title` → **Name**
  * Map `Internal SKU` → **SKU**
  * Map `Sell Price` → **Regular Price**
  * Map `Main Image` → **Images**
  * Map `Category` → **Categories**

> **Important**:\
> Mapped attributes will be exported as native WooCommerce fields and auto-mapped during import.\
> Unmapped attributes will be exported in WooCommerce’s **5-column attribute format** (so they show up as product attributes like Color, Size, Material, etc.).

***

### **Step 3: Export Your Data**

Once mapping is complete:

* Choose your export destination:
  * **Download as CSV** (for manual import)
  * **Send to FTP/SFTP** (for automated scheduled import)

***

## Manual Import into WooCommerce (Native Import)

### Step 1: Attribute Mapping (Inside Catsy)

Before exporting, you’ll have the option to **map your Catsy attributes** to WooCommerce’s standard import fields.

* If you map a field to a **native WooCommerce column** (like `SKU`, `Regular price`, `Name`, etc.), it will be exported using **that column header**.
* If a field is **not mapped** to a native WooCommerce field, it will be exported as a **product attribute** using WooCommerce’s 5-column attribute format.

#### **WooCommerce Native Fields**&#x20;

| CSV Column Name           | Maps to product property        | Example                                                           | Notes                                                                                                                                        |
| ------------------------- | ------------------------------- | ----------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `ID`                      | id                              | `100`                                                             | Defining this will overwrite data for that ID on import.                                                                                     |
| `Type`                    | type                            | `simple`, `variation, virtual`                                    | Product Type. Valid values: simple, variable, grouped, external, variation, virtual, downloadable. Multiple types can be used CSV separated. |
| `SKU`                     | sku                             | `my-sku`                                                          | Required. Auto-generated if missing.                                                                                                         |
| `Name`                    | name                            | `My Product Name`                                                 | Required.                                                                                                                                    |
| `Published`               | status                          | `1`                                                               | 1 for published, 0 for private, -1 for draft.                                                                                                |
| `Is featured?`            | featured                        | `1`                                                               | 1 or 0                                                                                                                                       |
| `Visibility in catalog`   | catalog\_visibility             | `visible`                                                         | Supported values: `visible`, `catalog`, `search`, `hidden`                                                                                   |
| `Short description`       | short\_description              | `This is a product.`                                              |                                                                                                                                              |
| `Description`             | description                     | `This is more information about a product.`                       |                                                                                                                                              |
| `Date sale price starts`  | date\_on\_sale\_from            | `2013-06-07`                                                      | Date (start of day) or leave blank.                                                                                                          |
| `Date sale price ends`    | date\_on\_sale\_to              | `2013-06-07`                                                      | Date (end of day) or leave blank.                                                                                                            |
| `Tax status`              | tax\_status                     | `taxable`                                                         | Supported values: `taxable`, `shipping`, `none`                                                                                              |
| `Tax class`               | tax\_class                      | `standard`                                                        | Can use any existing tax class.                                                                                                              |
| `In stock?`               | stock\_status                   | `1`                                                               | 1 or 0                                                                                                                                       |
| `Stock`                   | manage\_stock / stock\_quantity | `20`                                                              | Numeric stock level enables stock management. `parent` can be used for variations. Blank = no stock management.                              |
| `Low stock amount`        | low\_stock\_amount              | `3`                                                               | Empty or a number                                                                                                                            |
| `Backorders allowed?`     | backorders                      | `1`                                                               | 1, 0, or `notify`                                                                                                                            |
| `Sold individually?`      | sold\_individually              | `1`                                                               | 1 or 0                                                                                                                                       |
| `Weight (unit)`           | weight                          | `100`                                                             | Parse only numbers.                                                                                                                          |
| `Length (unit)`           | length                          | `20`                                                              | Parse only numbers.                                                                                                                          |
| `Width (unit)`            | width                           | `20`                                                              | Parse only numbers.                                                                                                                          |
| `Height (unit)`           | height                          | `20`                                                              | Parse only numbers.                                                                                                                          |
| `Allow customer reviews?` | reviews\_allowed                | `1`                                                               | 1 or 0                                                                                                                                       |
| `Purchase Note`           | purchase\_note                  | `Thanks for buying it buddy.`                                     |                                                                                                                                              |
| `Sale price`              | sale\_price                     | `20.99`                                                           | Sale price.                                                                                                                                  |
| `Regular price`           | regular\_price                  | `24.99`                                                           | Regular price.                                                                                                                               |
| `Categories`              | category\_ids                   | `Category 1, Category 1 > Category 2`                             | CSV list of categories. `>` used for hierarchy.                                                                                              |
| `Tags`                    | tag\_ids                        | `Tag 1, Tag 2`                                                    | CSV list of tags.                                                                                                                            |
| `Shipping class`          | shipping\_class\_id             | `Name`                                                            | Name of shipping class                                                                                                                       |
| `Images`                  | image\_id / gallery\_image\_ids | `http://somewhere.com/image.jpg, http://somewhere.com/image2.jpg` | First is featured image.                                                                                                                     |
| `Download limit`          | download\_limit                 | `1`                                                               | `n/a` or a limit.                                                                                                                            |
| `Download expiry days`    | download\_expiry                | `1`                                                               | `n/a` or a day limit.                                                                                                                        |
| `Parent`                  | parent\_id                      | `id:100`, `SKU-1`                                                 | Set parent ID. Used for variations. Can be just a numeric ID e.g. `id:100` or a SKU. Export will use SKU when possible.                      |
| `Grouped products`        | children                        | `id:100, id:101`, `SKU-1, SKU-2`                                  | List of IDs. Can be just a numeric ID e.g. `id:100` or a SKU. Export will use SKU when possible.                                             |
| `Upsells`                 | upsell\_ids                     | `id:100, id:101`, `SKU-1, SKU-2`                                  | List of IDs. Can be just a numeric ID e.g. `id:100` or a SKU. Export will use SKU when possible.                                             |
| `Cross-sells`             | cross\_sell\_ids                | `id:100, id:101`, `SKU-1, SKU-2`                                  | List of IDs. Can be just a numeric ID e.g. `id:100` or a SKU. Export will use SKU when possible.                                             |
| `External URL`            | product\_url                    | `https://mercantile.wordpress.org/product/wordpress-pennant/`     | Product external URL.                                                                                                                        |
| `Button text`             | button\_text                    | `Buy on the WordPress swag store!`                                | Custom product "buy" button.                                                                                                                 |
| `Position`                | menu\_order                     | `1`                                                               | Menu order, used for sorting.                                                                                                                |

### Step 2: Unmapped Fields = Custom Attributes

Any attribute that you **don’t map** will automatically be exported using WooCommerce’s 5-column attribute format:

| Column                 | Description                                          |
| ---------------------- | ---------------------------------------------------- |
| `Attribute N name`     | Name of the attribute (e.g., “Color”)                |
| `Attribute N value(s)` | Comma-separated values (e.g., “Red, Blue”)           |
| `Attribute N global`   | Set to `1` by default (makes the attribute global)   |
| `Attribute N visible`  | Set to `1` by default (makes it visible on frontend) |
| `Attribute N default`  | Optional — used only for variable products           |

### Step 3: Import into WooCommerce

In WordPress:

1. Go to **Products > All Products > Import**
2. Upload your CSV file
3. WooCommerce will auto-map standard fields and let you review the mappings
4. Click **Run the Import**

Your product data will be created with all standard fields and attributes correctly placed.

***

## Scheduled Import into Woocomerce (WP All Import)

If you'd like to automate product updates from Catsy, you will need the WP All Import plugin, which makes it simple to schedule recurring imports from your FTP or SFTP server.

### **Step 1: Start a New Import**

1. In WordPress, go to **All Import > New Import**
2. Choose **“Download a file from a URL / FTP / SFTP”**
3. Enter your FTP/SFTP info and select the file you’ll be uploading from Catsy
4. Click **“Continue to Step 2”**

***

### **Step 2: Confirm File and Post Type**

1. WP All Import will analyze your file
2. When prompted to choose post type, select **“WooCommerce Products”**
3. Click **“Continue to Step 3”**

***

### **Step 3: Drag & Drop Field Mapping**

Here’s where you map each column in your CSV to WooCommerce product fields. This only needs to be done once — your mapping will be saved.

On the right side, you’ll see the **names of your CSV columns** (like `Name`, `SKU`, `Price`, etc.)\
On the left side, WP All Import shows you **product fields** to map to (like Product Title, Description, Price, Images, etc.)

Here's exactly what to do:

| WooCommerce Field         | Drag This From CSV                                                                       |
| ------------------------- | ---------------------------------------------------------------------------------------- |
| **Product Title**         | Drag `Name`                                                                              |
| **SKU**                   | Drag `SKU`                                                                               |
| **Regular Price**         | Drag `Regular price` or `Price`                                                          |
| **Sale Price**            | Drag `Sale price` (optional)                                                             |
| **Stock Quantity**        | Drag `Stock` or `Inventory`                                                              |
| **Description**           | Drag `Description`                                                                       |
| **Short Description**     | Drag `Short description`                                                                 |
| **Categories**            | Drag `Categories`                                                                        |
| **Images**                | Drag `Images` (URLs, comma-separated)                                                    |
| **Attributes (Optional)** | Use WP All Import’s attribute builder for extra fields (add attributes, and drag values) |

Just click and drag from the right column (CSV data) into the matching field on the left.



Once all fields are mapped, click **“Continue to Step 4”**

***

### **Step 4: Schedule It**

1. Scroll to the bottom of the page
2. Check the box: **“Automatically re-run this import on a schedule”**
3. Choose how often (daily, weekly, etc.)
4. Click **“Confirm & Run Import”**

That’s it! WP All Import will now automatically fetch your updated Catsy file from FTP and import it based on your saved settings — no manual work needed after this.
