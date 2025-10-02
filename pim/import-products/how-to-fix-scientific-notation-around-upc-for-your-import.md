---
description: >-
  This article describes how to prevent Excel from automatically converting a
  UPC code to scientific notation and corrupting your product catalog.
---

# How to fix scientific notation around UPC for your import

<figure><img src="../../.gitbook/assets/image (1257).png" alt=""><figcaption></figcaption></figure>

\
\
By default, when you enter a number over 12 digits in an Excel spreadsheet, it auto-corrects the number to scientific notation for brevity. For example, "879860004073" is converted to "8.7986E+11". When Excel exports the value to a CSV or Text file, it will export what you see, not the actual 12-digit value. This can wreak havoc on the UPC codes in your product database.

You can use this technique for all types of unique product identifiers, known as Global Trade Item Numbers (GTINs).

**Universal Product Code (UPC)**&#x31;2 numeric digits**European Article Number (EAN)**&#x54;ypically 13 numeric digits (can also be 8 or 14 numeric digits)**Japanese Article Number (JAN)**&#x38; or 13 numeric digits**International Standard Book Number (ISBN)**&#x49;SBN-10: 10 numeric digits (last digit may be "X")ISBN-13: 13 numeric digits and usually starts with 978 or 979

&#x20;

#### Change the column format to Number and set decimal places to 0

If you already have the file open, then you can change the format of the column without closing your file and reopening it. Use any of these methods to change the column format to number and then set decimal places to none. All of these steps achieve the same thing in Excel.

**Use the Ribbon shortcuts**

1. Select the column by clicking on the column header
2. Go to Home > Number group > Change Number Format to "Number"
3. Then, use the shortcut button right below it to decrease decimal places to none

&#x20;

<figure><img src="../../.gitbook/assets/image (1258).png" alt=""><figcaption></figcaption></figure>

**Using Format Cells pop-up**

1. Right-click column header, select Format Cells
2. Choose Number and then set Decimal places to 0
3. Click Ok

![mceclip2.png](https://help.godatafeed.com/hc/article_attachments/360069535711)

&#x20;

**Use keyboard shortcuts**

1. Select column to be formatted
2. Alt > H > N > type "Number"
3. Alt > H > 9 (twice to decrease decimal places to none)

&#x20;



