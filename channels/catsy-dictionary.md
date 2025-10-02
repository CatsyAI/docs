# Catsy Dictionary

**Product:** A product is a virtual item that is never sold. A product exists in catsy to simplify content management so every variant of a product does not have to be maintained with the same exact content. Products do not exist in ERP systems, and they will never be imported nightly. Content managed at the product level gets derived down to the sellable items during the export process.

**Product Attribute:** A product attribute is any attribute that is associated to a product item. These are usually marketing attributes. These attributes will be automatically derived down to every variant under that product.

_Trigger Attribute: This is an attribute that changes the condition for another attribute._\
&#xNAN;_&#x44;ependent Attribute: This the attribute that needs to be populated when certain criteria is met by the trigger._

**Conditionally Required:** If one attribute is marked as 'Yes', then other attributes become required

Example: Hazardous material. If this is marked 'Yes', then the dependent attributes like 'Poisonous?' and 'Flammable?' become required. Not populating the dependent attributes will lower the overall completeness score since the dependents are required.&#x20;

**Conditionally Optional:** If one attribute is marked as 'Yes', then other attributes are optional.&#x20;

Example: Hazardous material. If this is marked 'Yes', then the dependent attributes like 'Poisonous?' and 'Flammable?' become visible. Not populating the dependent attributes will not lower the overall completion score since the dependents are optional.

**Conditionally Co-Dependent Required:** Let’s say there are two attributes. (a) **swatch** and (b) **swatch URL.**

If **(a)** is populated, then (b) becomes required. If **(b)** is populated then (a) becomes required. If either one's value is populated, the other becomes required. If neither is populated, they both remain optional. So either one can be a trigger attribute and the other one is a dependent attribute. If the trigger attribute is populated, but the dependent attribute is not, then the dependent will lower the overall completeness score since the dependent is required.
