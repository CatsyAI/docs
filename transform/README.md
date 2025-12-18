---
description: >-
  In Catsy transforming content falls into two broad categories: Data
  transformation and Image transformation.
icon: transporter-1
---

# Transform Content

**Four methods for importing digital assets into Catsy:**

1. Image Transformation
2. Data generation with Formulas
3. Data generation with Rules

Key differences between Formulas and Rules

Formulas in Catsy are supported with the primary intention of creating new content based on combining, substracting or running an evaluation on data that is already in Catsy. So, the output of a  formula in Catsy is data that is displayed in the interface, (results screen or product details page), exported or used in content syndicated to an external system. **Data from a formula is transient in nature and is not stored in the database.**

A rule in Catsy is data that is generated and saved into a master attribute when the record is created or updated. **A rule leads to durable and persistent data.** The syntax of rules is identical to the syntax of formulas. And a rule can be executed with a Create or an Update event.

**When to use Formulas vs Rules**

<table><thead><tr><th width="530">Usecase</th><th width="119">Formula</th><th>Rule</th></tr></thead><tbody><tr><td>Generate a description for a channel</td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td><td></td></tr><tr><td>Calculate Sale Price</td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td><td></td></tr><tr><td>Generate a description, and include in completeness calculation</td><td></td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td></tr><tr><td>Run a filter on an attribute that is a generated value</td><td></td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td></tr><tr><td>Channel Level </td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td><td></td></tr><tr><td>Master Data Level</td><td></td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td></tr><tr><td>Include in search</td><td></td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td></tr><tr><td>Display in Digital Catalog</td><td></td><td><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" data-size="line"></td></tr></tbody></table>
