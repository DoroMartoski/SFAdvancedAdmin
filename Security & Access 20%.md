Security & Access topics:
* Picklist Administration
* Enhanced Transaction Security
* Sessions based permission set & security
* Company wide org settings
* Administer Account teams
* What is MFA and how does it work
* Configure Enterprise Territory Management permissions and Access


## Picklist Administration
Picklists help to simplify data entry and standardize values. Picklists are not ideal for long entries or 
unique values. 
2 parts of Picklists:
1. The field: defines the type of picklist. 
2. The value set: defines the choices a user sees, their order and the default value amongst other things.

**3 Types of picklists:**
    * Standard
    * Custom
    * Custom Multi-select
    
**Picklist values can be:**
* Restricted
* Dependent or Controlling

**Picklist values can be defined in 3 ways:**
* Set individual values when you create the picklist. SPecific to a single picklist field
* Use the built-in set of values for the standard picklist fields that come with your org.
* Create a global value set. A global values set is a custom set of values you create to share with 
more than one picklist field.

### Standard picklists:
* these may share a standard value set so any change made on the value set will appear on all objects using that value set.

### Custom Picklists
You have the option to create a picklist or multi-select picklist. 
Selected values on a Multi-select picklist appear separated by semicolon

**Notes**:
* Global picklist value set are always restricted picklists; preserves data integrity.
* For custom picklists fields that use global picklist value set, you can change from a single-select to 
multi-select picklist & vice-versa. But can't chsnge the picklist to a different field type such a checkbox or text
* You can't undo a custom picklist field's association with a global value set. 
* Reports referencing multi-select picklists should use contains or includes to collect all results that contain 
more than one value.
* In report results, or dashboards, multi-select picklist selections are grouped independently. For example: One record has a, b, and c values. Another record has b and c values. And another record has only c selected. You’ll get three different groupings: one for a;b;c, one for b;c and another for c.
* Only specific functions can reference multi-select picklists in formulas.
* **Standard picklist cannot be a dependent picklist, be restricted, multi-select or use a formula for a default value.**

### Restricted Picklists
Keeps users from adding new values.

**Dependent Picklists**
Guide users, save UI space, and further improve data integrity with a dependent picklist
* Filters values for one picklist based on a selection from another picklist or a checkbox
