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

**Note**
* If you replace a picklist value with blank, existing records will not display any value anymore.
* Custom picklist fields can be either controlling or dependent fields
* Standard picklist field can be controlling fields but not dependent fields.
* Multi-select picklists fields can be dependent but not controlling fields.
* You can set default values for controlling fields but not for dependent pickists

**Use formulas for Default Picklist Values**
**When you change a multi-select picklist to a picklist that doesn’t allow multi-selection, Salesforce clears the values for that field on existing records. This makes sense, right? Because the field now only allows one value.**

### Share Values with Global Value Sets
Global value sets:
* lets you share the same picklist values with more than one picklist field.
* They are always restricted and can not be converted to unrestricted.
* You can define a default value for a Global value set
* **Individual fields that use the global value set can have their own default values, independent of the global value set’s default. This extends to formula default values, too.**
* **If you find that a particular set of values for one field makes a good set for another field, you can promote the existing value set to a global value set.** 


### Enhanced Transaction Security
* A salesforce feature that monitors Salesforce events in real time to spot potential troubles based on rules you create.
* Create policies that consists of events, notifications, and actions

* **Event**: any action in Salesforce including user clicks, record state changes and measuring values. Immutable and timestamped
* Pick a transaction or event to monitor and then choose actions that are triggered when the event occurs.
* The rules & actions you create for a Transaction Security is referred to as policies.
* Transaction security policies can be extended with Apex for customized protection.
* **To use Transaction Security, you have to first purchase a Salesforce Shield or Salesforce Shield Event Monitoring add-on subscription.**

Examples of available event types for Transaction Security policies
* API Event for monitoring and protecting all API queries. Prevents unauthroized data exports
* List View Event for access to list views. Tracks user's access to list views from both UI and API queries.
* Login Event monitoring. Blocks logins from untrusted locations, unsupported browsers and specific device types.
* Report Event for Report views and exports. Blocks or requires multi-factor authentication for access to sensitive info
 or notifies when reports are run or exported.
 
 **Available Actions for a policy**:
 * Block the operation
 * Require a higher level of assurance using multi-factor authentication
 * Do nothing (can be useful for testing)
 * Opt-in for policy notifications sent via Email, In-app notification to the Salesforce app or Both email and n-app notifications.


 





