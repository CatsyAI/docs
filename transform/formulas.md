# Formulas

All you need to know when working with formulas in Catsy is the following:

1. [Definitions](formulas.md#flow-control-less-than-stro)
2. [Main formula building blocks](formulas.md#definitions-thisc)
3. [Text operations](formulas.md#text-operations)
4. [Mathematical formulas](formulas.md#mathematical-formulas)
5. [Advanced operations](formulas.md#advanced-operations)

***

### Definitions <a href="#flow-control-less-than-stro" id="flow-control-less-than-stro"></a>

Types of attributes

* by data type
  * Text
  * Picklist
  * Decimal
  * Integer
  * Measurement
  * Category
  * Asset
  * Lists (multi-value attributes)
* by usage
  * Master Attributes
  * Channel Attributes
  * Asset Attributes&#x20;
  * Category Attributes
  * Entity Attributes

***

### Formula building blocks <a href="#definitions-thisc" id="definitions-thisc"></a>

#### Flow Control

_**if / else**_

Example: checking if a product has a value for weight and outputting a message if it doesn't.

<pre><code>if (product.weight_lbs.isEmpty()) 
    {
        product.weight_kg * 2.2 
<strong>    } 
</strong>else 
    {
        product.weight_lbs
    }
</code></pre>

#### Built-in Functions

lower, length, substring, etc.

```
product.name.lower()
```

#### Variables

def \<variable>

```
def result

result = product.price * 0.8
```

#### Operators & Expressions

arithmetic operators ( +, -, \*, /, \*\*, % )

<pre><code><strong>product.lenght_ft = product.length_in * 12
</strong></code></pre>

logical operators ( &&, ||)

<pre><code><strong>if (product.price_usd.isEmpty() &#x26;&#x26; product.price_eur.isEmpty()) 
</strong><strong>    {
</strong><strong>        product.missing_price == 'YES'
</strong><strong>    }
</strong></code></pre>

relational operators (>,<,>=,<=,==,!=)

<pre><code><strong>if (product.sale_price &#x3C; product.regular_price) 
</strong><strong>    {
</strong><strong>        product.on_sale = TRUE
</strong><strong>    }
</strong></code></pre>

***

### **Examples for some of the main formula applications**

#### Text operations

<table data-full-width="false"><thead><tr><th>Function</th><th>Example</th></tr></thead><tbody><tr><td><strong>Concatenate</strong><br><em><code>product.key1 + product.key2</code></em><br>Combines multiple values together. The values can be an attribute or a constant that you choose. This formula can handle as many values as you need.</td><td><p>DATA VALUE: <br>category_id = '41123'<br>name = '12345'</p><p><br>USAGE : <br><code>product.</code><em><code>category_id + '-' + product.name</code></em><br><br>RESULT: 41123-12345</p></td></tr><tr><td><strong>Concatenate</strong><br><em><code>product.key.concat('text')</code></em><br>Combines multiple values together. The values can be an attribute or a constant that you choose.</td><td><p>DATA VALUE:<br>category_id = '41123'<br></p><p>USAGE : <br><code>product.category_id.concat("-GRNR")</code> <br><br>RESULT: 41123-GRNR</p></td></tr><tr><td><strong>Concatenate non-string attribute values</strong><br><strong>'</strong><em><code>${product.key1} ${product.key2}</code></em><strong>'</strong><br>Converts non string values to strings and combines them together. Any text can be added between/around the values.</td><td><p>DATA VALUE: </p><p>height_in = <strong>'</strong>56<strong>'</strong></p><p>width_in = <strong>'</strong>23<strong>'</strong></p><p></p><p>USAGE:<br> <strong>'</strong><em><code>The shipment dimensions are ${product.height_in} x ${product.width_in}</code></em><strong>'</strong><br></p><p>RESULT: The shipment dimensions are 56 x 23</p></td></tr><tr><td><p><strong>Extract a substring</strong></p><p><code>product.key.substring(0,50)</code><br>Limits a text length to 50 characters</p></td><td><p>DATA VALUE: long_description = <strong>'</strong>This is an sample description that is longer than 50 characters<strong>'</strong></p><p><br>USAGE: product.long_description.substring(0,50)</p><p><br>RESULT: This is an sample description that is longer than</p></td></tr><tr><td><p><strong>Extract a substring based on a specific character within it</strong></p><p><code>product.key.substring((product.key.indexOf(</code><strong>'</strong> <code>-</code> <strong>'</strong><code>)+3),300)</code><br>Only returns the part of the string after an unique <strong>'</strong> - <strong>'</strong> in the value</p></td><td><p>DATA VALUE:</p><p>title = <strong>'</strong>Super Awesome Widget - Green and Black Spring<strong>'</strong></p><p><br>USAGE: product.title.substring((product.title.indexOf(<strong>'</strong> - <strong>'</strong>)+2),300);</p><p><br>RESULT: Green and Black Spring</p></td></tr><tr><td><p><strong>Replace</strong></p><p><code>product.key.replace(</code><strong>'</strong><code>value1</code><strong>'</strong><code>,</code> <strong>'</strong><code>value2</code><strong>'</strong><code>)</code><br>Replaces a value1 with a value 2 in an attribute value</p></td><td><p>DATA VALUE: height = 12 inches</p><p><br>USAGE: product.height.replace(<strong>'</strong> inches<strong>'</strong>, <strong>''</strong>)</p><p></p><p>RESULT: 12"</p></td></tr><tr><td><p><strong>Replace multiple text values</strong></p><p><code>replaceAll(product.key,'SubstitueThis','WithThis','OldValue','NewValue')</code><br>Substitutes multiple values in an attribute with one formula</p></td><td><p>DATA VALUE:</p><p>description = <strong>'</strong>This is a longer text field with some more text<strong>'</strong></p><p><br>USAGE: replaceAll(product.description,<strong>'</strong>longer<strong>'</strong>,<strong>'</strong>different<strong>'</strong>,<strong>'</strong>text<strong>'</strong>,<strong>'</strong>data<strong>'</strong>)</p><p><br>RESULT:</p><p><strong>'</strong>This is a different data field with some more data<strong>'</strong></p></td></tr><tr><td><p><strong>Remove non-alphanumeric characters from text</strong></p><p><code>product.key.replaceAll('[^a-zA-Z0-9]', '')</code><br>Removes all non-alphanumeric characters from a string</p></td><td><p>DATA VALUE:</p><p>sku = '12+H&#x26;E<strong>'</strong></p><p><br>USAGE: product.sku.replaceAll('[^a-zA-Z0-9]', '')</p><p><br>RESULT: '12HE'</p></td></tr><tr><td><p><strong>Capitalize</strong></p><p><code>product.key.upper</code><br>Converts a text value to all caps.</p></td><td><p>DATA VALUE:</p><p>short_description = This is a product</p><p><br>USAGE: product.short_description.upper</p><p><br>RESULT: THIS IS A PRODUCT</p></td></tr><tr><td><p><strong>Convert to integer</strong></p><p><code>product.key.integerValue()</code><br>Converts a string to an integer.</p><p><mark style="color:orange;">IMPORTANT: make sure that the string contains only numbers before applying the conversion formula.</mark></p></td><td><p>DATA VALUE:</p><p>width_depth_inches = '8x4'</p><p><br>USAGE:</p><p><code>def first = product.width_depth_inches.substring(0,product.key.indexOf('x')).integerValue() def second = product.width_depth_inches.replace(first,'').replace('x','').integerValue() def result = first * second</code></p><p><code>result</code></p><p><br>RESULT: 32</p></td></tr><tr><td><p><strong>Remove trailing spaces</strong></p><p><code>product.key.trim()</code><br>Removes empty spaces from the end of a text field.</p></td><td><p>DATA VALUE:</p><p>name = "Classic Rosette "</p><p><br>USAGE: product.name.trim()</p><p><br>RESULT: "Classic Rosette"</p></td></tr><tr><td><p><strong>Convert text to lowercase letters</strong></p><p><code>product.key.lower()</code><br>Converts all the letters from a value to lowercase.</p></td><td><p>DATA VALUE:</p><p>name = "3DR 2 inch Wall"</p><p><br>USAGE: product.name.lower()</p><p><br>RESULT: "3dr 2 inch wall"</p></td></tr><tr><td><p><strong>Convert text to uppercase letters</strong></p><p><code>product.key.upper()</code><br>Converts all the letters from a value to uppercase.</p></td><td><p>DATA VALUE:</p><p>name = "3DR 2 inch Wall"</p><p><br>USAGE: product.name.upper()</p><p><br>RESULT: "3DR 2 INCH WALL"</p></td></tr><tr><td><p><strong>Return the number of characters contained in a text</strong></p><p><code>product.key.length()</code></p><p>Returns the exact number of characters in a text.</p></td><td><p>DATA VALUE:</p><p>name = "3DR 2 inch Wall"</p><p><br>USAGE: product.name.length()</p><p><br>RESULT: "15"</p></td></tr><tr><td><p><strong>Checks where within a text a specific phrase starts</strong></p><p><code>product.key.find("text")</code></p><p>Returns the index of the character of the first occurrence of the phrase</p></td><td><p>DATA VALUE:</p><p>name = "3DR 2 inch Wall"</p><p><br>USAGE:</p><p>product.name.find("2 inch")</p><p><br>RESULT:</p><p>"4"</p></td></tr><tr><td><p><strong>Remove a specific phrase from a text</strong></p><p><code>product.key.remove("text")</code></p><p>Removes a specific phrase from a text.</p></td><td><p>DATA VALUE:</p><p>name = "3DR 2 inch Wall"</p><p><br>USAGE: product.name.remove("2 inch ")</p><p><br>RESULT: "3DR Wall"</p></td></tr><tr><td><p><strong>Concatenate text with new line dividers</strong></p><p><code>def result = ''</code></p><p><code>if (!product.key.isEmpty()) { result += " - " + product.key } else { result += '' }</code></p><p><code>if (!product.key2.isEmpty()) {</code></p><p><code>result += "\n" + "- " + product.key2</code></p><p><code>} else {</code></p><p><code>result += ''</code></p><p><code>}</code></p><p><code>result</code></p><p>Changes the style of a text with a bulleted dash</p></td><td><p></p><p>DATA VALUE:</p><p>featuresbenefits_1 = "text 1"</p><p>featuresbenefits_2 = "text 2"</p><p><br>USAGE:</p><p>def result = ''</p><p>if (!product.featuresbenefits_1.isEmpty()) { result += " - " + product.featuresbenefits_1 } else { result += '' }</p><p>if (!product.featuresbenefits_2.isEmpty()) {</p><p>result += "\n" + "- " + product.featuresbenefits_2</p><p>} else {</p><p>result += ''</p><p>}</p><p>result</p><p><br>RESULT:</p><ul><li>text 1</li><li>text 2</li></ul></td></tr><tr><td><p><strong>Loop through a list of tags or a multi-select picklist;</strong></p><p><strong>Create new tags in channels via a formula</strong></p><p><code>def result = []</code></p><p><code>product.tags.forEach(s -> result += ("text " + s))</code></p><p><code>result += "predominant colour: " + product.predominant_colour.toString()</code></p><p><code>result += "secondary colour(s): " + product.secondary_colour.toString().replace("|","; ")</code></p><p><code>result</code></p></td><td></td></tr><tr><td><p><strong>Concatenate Category IDs</strong></p><p><code>def catArray = [product.category_id,product.category_id_2]</code></p><p><code>catArray.join(", ")</code></p><p>Combines two category IDs with a delimiter, where a separate attribute with data type Integer has already been created to be used based on the Subcategory ID</p></td><td><p>DATA VALUE:</p><p>category_id_1 = "123456"</p><p>category_id_2 = "1234567"<br></p><p>USAGE:</p><p><code>def catArray = [product.category_id_1,product.category_id_2]</code></p><p><code>catArray.join(", ")</code><br></p><p>RESULT:</p><p>123456, 1234567</p></td></tr></tbody></table>

#### Mathematical formulas

<table data-full-width="false"><thead><tr><th>Function</th><th>Example</th></tr></thead><tbody><tr><td><p><strong>Basic mathematical operations</strong></p><p><code>product.key + number</code></p><p><code>product.key / number</code></p><p><code>(product.key1 - product.key2) * number</code></p><p></p><p><mark style="color:orange;">MATHEMATICAL FORMULAS ONLY WORK ON ATTRIBUTES WITH DATA TYPES:</mark></p><p><mark style="color:orange;">Integers, Decimals, Price, Measurement</mark></p></td><td><p>DATA VALUE:<br>price1 = 100</p><p>price 2 = 50<br></p><p>USAGE: product.price1 + 20 <br>RESULT: 120<br></p><p>USAGE: product.price1 / 4 <br>RESULT: 25<br></p><p>USAGE: (product.price1 - product.price2) * 1.5 RESULT: 75</p></td></tr><tr><td><p><strong>Mathematical operations using methods</strong></p><p><code>product.key.div(number)</code></p><p><code>product.key.multiply(number)</code></p><p><code>product.key.minus(number)</code></p><p><code>product.key.plus(number)</code></p><p><mark style="color:orange;">MATHEMATICAL METHODS ONLY WORK ON ATTRIBUTES WITH DATA TYPES:</mark></p><p><mark style="color:orange;">Integers Decimals Price Measurement</mark></p></td><td><p>DATA VALUE:</p><p>max_amount = 100</p><p><br>USAGE: product.max_amount.div(10) <br>RESULT: 10</p><p><br>USAGE: product.max_amount.multiply(3) <br>RESULT: 300</p><p><br>USAGE: product.max_amount.minus(12) RESULT: 88</p><p><br>USAGE: product.max_amount.plus(15) RESULT: 115</p></td></tr><tr><td><p><strong>Round decimals UP</strong></p><p><code>product.key.round(2)</code></p><p>Rounds a number attribute to two decimal places</p><p><mark style="color:orange;">MATHEMATICAL FORMULAS ONLY WORK ON ATTRIBUTES WITH DATA TYPES:</mark></p><p><mark style="color:orange;">Integers Decimals Price Measurement</mark></p></td><td><p>DATA VALUE:</p><p>price = 10.2468</p><p><br>USAGE: product.price.round(2)</p><p></p><p>RESULT: 10.25</p></td></tr><tr><td><p><strong>Round decimals DOWN</strong></p><p><code>product.key.roundDown(2)</code></p><p>Rounds a number attribute to two decimal places</p><p><mark style="color:orange;">MATHEMATICAL FORMULAS ONLY WORK ON ATTRIBUTES WITH DATA TYPES:</mark></p><p><mark style="color:orange;">Integers Decimals Price Measurement</mark></p></td><td><p>DATA VALUE:</p><p>price = 10.2468</p><p><br>USAGE: product.price.roundDown(2)</p><p><br>RESULT: 10.24</p></td></tr><tr><td><p><strong>Format decimals</strong></p><p><code>product.key.format('###.##')</code></p><p>Formats a number's decimal points</p><p><mark style="color:orange;">MATHEMATICAL FORMULAS ONLY WORK ON ATTRIBUTES WITH DATA TYPES:</mark></p><p><mark style="color:orange;">Integers Decimals Price Measurement</mark></p></td><td><p>DATA VALUE:</p><p>price = 150</p><p><br>USAGE: product.price.format('#,##0.00')</p><p><br>RESULT: 1,500.00</p></td></tr><tr><td><p><strong>Get a negative value</strong></p><p><code>product.key.negative()</code></p><p>Returns a negative value of an integer or a decimal</p><p><mark style="color:orange;">MATHEMATICAL FORMULAS ONLY WORK ON ATTRIBUTES WITH DATA TYPES:</mark></p><p><mark style="color:orange;">Integers Decimals Price Measurement</mark></p></td><td><p>DATA VALUE:</p><p>x_coordinate = 3.5</p><p><br>USAGE: product.x_coordinate.negative()</p><p><br>RESULT: -3.5</p></td></tr></tbody></table>

#### Advanced operations

<table data-full-width="false"><thead><tr><th>Function</th><th>Example</th></tr></thead><tbody><tr><td><p><strong>Check if a value is empty and assigning a value based on the result</strong></p><p><code>product.key1.isEmpty() ? product.key2 : product.key1</code></p><p>If an attribute is missing values, substitute a different attribute instead, but if it is not empty use the original attribute</p></td><td><p>DATA VALUE:<br>product.revised_title = NULL<br>product.name = TEST<br></p><p>USAGE : <br><code>product.revised_title.isEmpty() ? product.name : product.revised_title</code><br><br>RESULT: TEST</p></td></tr><tr><td><p><strong>Program attributes with conditional statements</strong> <br><code>def result = ''</code></p><p><code>if (product.key1 == 'mm') {</code></p><p><code>result = product.key1_mm</code></p><p><code>}</code></p><p><code>if (product.key1 == 'inch'){</code></p><p><code>result = product.key1_inch</code></p><p><code>}</code></p><p><code>if (product.key1 == 'n/a'){</code></p><p><code>result = product.key1_decimal</code></p><p><code>}</code></p><p><code>result</code></p><p>If a value of an attribute equals "mm", then use an attribute found at key1_mm</p><p>If a value of an attribute equals "inch", then use an attribute found at key1_inch</p><p>If a value of an attributes equals "n/a", then use an attribute found at key1_decimal</p></td><td><p>DATA VALUE:</p><p>unit_inchmm = inch<br>ls_shank_length_inch = 12" product.ls_shank_length_mm = 100mm</p><p><br>USAGE:</p><p><code>def result = ''</code></p><p><code>if (product.unit_inchmm == 'mm') {</code></p><p><code>result = product.ls_shank_length_mm</code></p><p><code>}</code></p><p><code>if (product.unit_inchmm == 'inch'){</code></p><p><code>result = product.ls_shank_length_inch</code></p><p><code>}</code></p><p><code>if (product.unit_inchmm == 'n/a'){</code></p><p><code>result = product.ls_shank_length_decimal_inch</code></p><p><code>}</code></p><p><code>result</code></p><p><br>RESULT: 12"</p></td></tr><tr><td><p><strong>Concatenate attribute values using conditional statements</strong></p><p><code>def result = ''</code></p><p><code>if (!product.key1.trim().isEmpty()) {</code></p><p><code>result += product.key1 + "x"</code></p><p><code>}</code></p><p><code>if (!product.key2.trim().isEmpty()) {</code></p><p><code>result += product.key2 + "x"</code></p><p><code>}</code></p><p><code>if (!product.key3.trim().isEmpty()) {</code></p><p><code>result += product.key3</code></p><p><code>}</code></p><p><code>result</code></p><p>Combine individual attributes into one field separated by an "x"</p></td><td><p>DATA VALUE:</p><p>product.depth = 12</p><p>product.width = 10</p><p>product.height = 8</p><p><br>USAGE:</p><p><code>def result = ''</code></p><p><code>if (!product.depth.trim().isEmpty()) {</code></p><p><code>result += product.depth + "x"</code></p><p><code>}</code></p><p><code>if (!product.width.trim().isEmpty()) {</code></p><p><code>result += product.width + "x"</code></p><p><code>}</code></p><p><code>if (!product.height.trim().isEmpty()) {</code></p><p><code>result += product.height</code></p><p><code>}</code></p><p><code>result</code></p><p><br>RESULT: 12x10x8</p></td></tr><tr><td><p><strong>Pull information from a picklist value's properties</strong></p><p><code>product.picklist_value.asset</code></p><p>Returns the image associated with a picklist value</p></td><td><p>DATA VALUE:</p><p><em>product.color</em> contains picklist values "blue", "green" and "yellow" with corresponding images: <img src="https://cforce.atlassian.net/wiki/download/thumbnails/4030467/blue.jpg?version=1&#x26;modificationDate=1643027755708&#x26;cacheVersion=1&#x26;api=v2&#x26;width=50&#x26;height=50" alt="" data-size="line"> <img src="https://cforce.atlassian.net/wiki/download/thumbnails/4030467/green.jpg?version=1&#x26;modificationDate=1643027775003&#x26;cacheVersion=1&#x26;api=v2&#x26;width=50&#x26;height=50" alt="" data-size="line"> <img src="https://cforce.atlassian.net/wiki/download/thumbnails/4030467/yellow.jpg?version=1&#x26;modificationDate=1643027802406&#x26;cacheVersion=1&#x26;api=v2&#x26;width=50&#x26;height=49" alt="" data-size="line"></p><p><br>USAGE:</p><p>product.picklist_value = green</p><p>product.picklist_value.asset = https://s3-us-west-2.amazonaws.com/catsy....green.jpg</p></td></tr><tr><td><p><strong>Format attribute values as JSON strings</strong></p><p><code>"{ "unit": "in", "value": " + product.dimension + " }"</code></p><p>Returns a formatted JSON string ready for Shopify metafields</p></td><td><p>DATA VALUE:</p><p>product.width = 7.4</p><p><br>USAGE:</p><p><code>"{ "unit": "in", "value": " + product.width + " }"</code></p><p><br>RESULT: { "unit": "in", "value": 7.4 }</p></td></tr><tr><td><p><strong>Concatenate non-empty values</strong></p><p><code>def values = [product.key_1.toString(),product.key_2.toString(),product.key_3.toString()]</code></p><p><code>values.join("x")</code></p><p>Adds values of an attribute to a list, and returns the non-null list values separated by an "x"</p></td><td><p>DATA VALUE:</p><p>product.attribute_1 = "4"</p><p>product.attribute_2 = (null)</p><p>product.attribute_3 = "Apple"</p><p><br>USAGE:</p><p><code>def values = [product.attribute_1.toString(),product.attribute_2.toString(),product.attribute_3.toString()]</code></p><p><code>values.join("x")</code></p><p><br>RESULT:</p><p>4xApple</p></td></tr><tr><td><p><strong>Pull a variant's parent information</strong></p><p><code>product.parent.key</code></p><p>Gets the value of the variants's parent attribute</p></td><td><p>DATA VALUE:</p><p>Variant's product.familyname = "NULL" Parent's product.familyname = "Tucson"</p><p><br>USAGE:</p><p>At Variant Product Level</p><p>product.parent.familyname</p><p><br>RESULT:</p><p>"Tucson"</p></td></tr><tr><td><p><strong>Returns the picklist value in the same list index as a different picklist attribute</strong><br><code>catsy.attributes.attribute2.picklistValues[catsy.attributes.attribute1.indexOf(product.attribute1.toString())]</code></p><p></p></td><td><p>Attribute 1 Picklist Values:</p><p>Value 1</p><p>Value 2</p><p>Value 3</p><p>Attribute 2 Picklist Values:</p><p>Value 4</p><p>Value 5</p><p>Value 6</p><p>When Attribute 1 = "Value 1", Attribute 2 = "Value 4"</p><p>When Attribute 1 = "Value 3", Attribute 2 = "Value 6"</p></td></tr><tr><td><p><strong>Pull category information</strong></p><p><code>product.category[1].name</code></p><p>Returns the name of the first sub-category of a Category type attribute. Change the index in the square brackets to get the second subcategory [2] or the root category [0] instead.</p><p>References to additional metadata may be made by changing the metadata key to the appropriate field. (e.g. reference a category's description by using <code>product.category[1].description</code> instead of <code>product.category[1].name</code>).</p></td><td><p>DATA VALUE:</p><p>category = "Gifts > For Him > Apparel"</p><p><br>USAGE:</p><p>product.category[0].name</p><p>product.category[1].name</p><p>product.category[2].name</p><p><br>RESULT:</p><p>"Gifts"</p><p>"For Him"</p><p>"Apparel"</p></td></tr><tr><td><p><strong>Substitute a variant's image for its parent's</strong></p><p><code>product.parent.main_image</code></p><p>Uses a parent's main image as a variant's secondary image</p></td><td></td></tr><tr><td><p><strong>Pull elements from price attributes</strong></p><p><code>product.price.getAmount() product.price.getCurrency()</code></p><p>Returns the value or currency of a price attribute</p></td><td></td></tr><tr><td><p><strong>Get a product's create or update date</strong></p><p><code>product.create_date.toString().substring(0,10)</code></p></td><td></td></tr><tr><td><p><strong>Get a list of the attribute keys contained in an attribute group</strong></p><p><code>catsy.attributeGroup('core').attributes</code></p><p><code>catsy.attributeGroup('core').attributes[0]</code></p></td><td></td></tr><tr><td><p><strong>Get a list of a parent's variant's attribute values (a "list of lists")</strong></p><p><code>product.variants.collect { variant -> variant.attribute-key[0] }</code></p></td><td><p>DATA VALUE:</p><p>product.variants.colors:</p><p>sku-101A: Red | Orange sku-101B: Blue | Green</p><p><br>USAGE:</p><p>product.variants.collect { variant -> variant.color_list[0] }</p><p><br>RESULT:</p><p>"Red | Orange | Blue | Green"</p></td></tr><tr><td><p><strong>Get a list of a parent's variant's attribute values (a "list of lists") without duplications</strong></p><p><code>product.variants.collect { variant -> variant.attribute-key }.flatten().unique()</code></p></td><td><p>DATA VALUE:</p><p>product.variants.colors:</p><p>sku-101A: Red | Orange sku-101B: Blue | Red</p><p><br>USAGE:</p><p>product.variants.collect { variant -> variant.color_list[ }.flatten().unique()</p><p><br>RESULT:</p><p>"Red | Orange | Blue"</p></td></tr></tbody></table>

**In your Shopify channel you can map to a rich text format field and sync that to Shopify but you need to use a conversion formula**\
\
USAGE:

```
def Att = product.features_tab_2

if(!Att.isEmpty()){
if(Att.contains('<')){
def result = '{"type": "root","children" : ['

result +=Att.replaceAll('"','\\\\'+'"').replaceAll(/<p.*?>/,'{"type": "paragraph","children": [{"type": "text","value": "').replace('</p>','"}]}').replaceAll(/<h.*?>/,'{"type": "paragraph","children": [{"type": "heading","children": [{"type": "text", "value": "').replaceAll('</h.*?>','"}], "level": 3}]}').replace('<ul>','{"listType": "unordered","type": "list","children": [').replace('<ol>','{"listType": "ordered","type": "list","children": [').replace('<li>',' {"type": "list-item","children": [{"type": "text","value": "').replace('</li>','"}]},').replace('</ul>',']}').replace('</ol>',']}').replace('<strong>','').replace('<i>','').replace('</strong>','","bold":true,"},{"type":"text","value": "').replace('</i>','","italic":true,"},{"type":"text","value": "').replace(',}','}').replace(',,',',').replace('true,"}','true}').replace(',","',',"').replace('},]','}]').replace('}{','},{').replace('}"}','}').replace('},"','').replaceAll('&nbsp;','')

result += ']}'

result}

else
{
def result = '{"type": "root","children": [{"type": "paragraph","children": [{"type": "text","value": "'+Att+'"}]}]}'

result
}
}
else{
def result = ''
result
}
```
