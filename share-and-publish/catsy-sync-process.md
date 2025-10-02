---
description: >-
  Managing product data between Catsy and platforms like Shopify or BigCommerce
  requires understanding how sync and delta generation differ. Both keep your
  store updated, but they operate differently.
---

# Catsy Sync Process

**The process is broken down into two phases:**

* **Delta Generation**
* **Sync Changes to Store**

### Key Differences: Delta vs Sync

<table><thead><tr><th width="212"></th><th>Delta Generation</th><th>Sync Process</th></tr></thead><tbody><tr><td>Reason to perform</td><td>Identifies changes in product data</td><td>Publishes the changes to the live store</td></tr><tr><td>Detected product-related actions</td><td>Create, Update, Delete</td><td>Executes create/update; deletes only under safe conditions</td></tr><tr><td>Thresholds</td><td>Protects from bulk changes (e.g., too many updates, unintentional deletes)</td><td>Relies on delta results, adheres to thresholds</td></tr><tr><td>Cadence</td><td>Manual or scheduled</td><td>Manual, selective or scheduled</td></tr><tr><td><strong>Goal</strong></td><td><strong>"What needs to happen?"</strong></td><td><strong>"Make it happen in the store."</strong></td></tr></tbody></table>

### What is Delta Generation?

Delta generation is how Catsy spots what’s new, changed, or needs to be removed in your product data.

* _**Create**_: The delta process identifies any new products or variants that you have prepared to be added to your store.
* _**Update**_: The delta generation takes notice of product changes—like its price, description, or photos—so we can update just those parts.
* _**Delete**_: If you've removed a product from your Catsy channel, the delta generation marks it as a product that should be removed from your store.
* _**Scheduled or Interactive:**_ You can run delta generation yourself or let it run automatically on a schedule.&#x20;
* _**Thresholds:**_ If it ever looks like too many products might be updated or deleted at once, the system will pause and double-check with you so nothing important is lost by accident.

### How the Catsy Sync Operates

#### Syncing is the process that updates your store’s product data. There are a few ways sync can be run:

* _**Manual Identify Delta**_: The system looks for any products that are new, changed, or removed, so you can update your store with just those items.
* _**Retry Sync**_: If a product didn’t update correctly, you can use this to try refreshing its information and its options.
* _**Sync Selected**_: Lets you choose specific products to update, instead of updating everything at once.
* _**Automated Scheduled Delta Sync**_: The system regularly checks for any changes to your products and updates your store. It’s set up to carefully manage deletions so you don’t accidentally remove products.

#### Product Structure Overview

* Standalone products in Catsy sync directly as standalone items in your store.
* Parent products and their variants are mapped as families, maintaining consistency across platforms.

### In Short

Deltas protect your store from accidental large-scale changes. Syncs ensure only the right changes are applied, whether that’s a single product retry or an automated update across thousands of SKUs.

Together, they give you both control and safety in managing product data. Both are part of Catsy’s safeguard system to keep your store accurate, up-to-date, and protected from errors.

