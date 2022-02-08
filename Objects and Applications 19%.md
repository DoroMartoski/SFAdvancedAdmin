## Objects and Applications

#### Consideration for Relationships
* Each custom object can have up to **2 master-detail relationships**
* Each custom object **can have many lookup relationships**
* You can convert a master-detail relationship to a look-up relationship as long as no roll-up summary fields exist on the master object.
* ** when you convert a master-detail to lookup, the ord-wide default for detail side of a master-detail relationship becomes public read/write**
* You can **convert lookup relationship to master-detail relationship if the lookup field in all the records contains a value**
* **Lookup relationship can't be changed to a master-detail relationship if the org-wide default of the child object access level in the relationship is "Controlled by Parent"**

#### **Master Detail Relationships**
* Need **Customize Application user permission** to create multi-level master-detail relationships.
* When you define a master-detail relationship, the custom object on which you're working is the detail side. Its data appears as a custom related list on page layouts for the other object.
* **Reparenting**
  * By default, records can't be reparented in master-detail relationship
  * Need "**Allow reparenting**" option in the master-detail relationship definition to allow child records in master-detail relationships on custom objects to be reparented.
  * Multilevel master-detail relationships don’t support division transfers.
  * You can't create a master-detail relationship if the custom object already contains data. You can, however, create the relationship as a lookup and then convert it to master-detail if the lookup field in all records contains a value.
  * A master can roll up fields on detail records; however, it can't directly roll up fields on subdetail records
  * Custom report types created for multilevel master-detail relationships count toward the organization’s custom report type limit, and no reports generate if this limit is exceeded.
  * a custom junction object can’t become the master object in a multilevel master-detail relationship.
  * You can't delete a custom object if it is on the master side of a master-detail relationship. If you delete a custom object that is on the detail side of a master-detail relationship, the relationship is converted to a lookup relationship.
  * Deleting a detail record moves it to the Recycle Bin and leaves the master record intact; deleting a master record also deletes related detail and subdetail records. Undeleting a detail record restores it, and undeleting a master record also undeletes related detail and subdetail records. 

#### Many-to-Many Relationships
* Junction object records are deleted when either associated master record is deleted and placed in the recycle bin.
* If both master records are deleted, the junction object record is deleted permanently and can't be restored.
* Sharing access to a junction object record is determined by a user's sharing access to both associated master records and the Sharing Setting option on the relationship field.
* if the sharing setting on both parents is Read/Write, then the user must have Read/Write access to both parents in order to have Read/Write access to the junction object. If the sharing setting on both masters is Read-Only, a user with Read-Only rights on the master records would have Read access to the junction object.
* In a many-to-many relationship, a user can't delete a parent record if there are more than 200 junction object records associated with it and if the junction object has a roll-up summary field that rolls up to the other parent  
  * To delete this object, manually delete junction object records until the count is fewer than 200.

* **The first master-detail relationship you create on your junction object becomes the primary relationship. This affects the following for the junction object records:** 
  * Look and feel
  * Record ownership
  * Divisions

* Roll-up summary fields that summarize data from the junction object can be created on both master objects.
* Formula fields and validation rules on the junction object can reference fields on both master objects.
* You can define Apex triggers on both master objects and the junction object.
* A junction object can't be on the master side of another master-detail relationship.
* You can't create a many-to-many self-relationship, that is, the two master-detail relationships on the junction object can't have the same master object.

#### **Lookup Relationship**:
If the lookup field is optional, you can specify one of three behaviors to occur if the lookup record is deleted:
* Clear the value of this field - This is the default. Clearing the field is a good choice when the field doesn’t have to contain a value from the associated lookup record.
* Don’t allow deletion of the lookup record that’s part of a lookup relationship If you have dependencies built on the lookup relationship, such as a workflow rule, this option doesn’t allow the lookup record to be deleted.
* Delete this record also Available only if a custom object contains the lookup relationship, not if it’s contained by a standard object. However, the lookup object can be either standard or custom. Choose when the lookup field and its associated record are tightly coupled and you want to completely delete related data

* If the parent record in a lookup relationship is deleted, the field history tracking for the child record doesn't record the deletion. For example, if a parent account is deleted, the Account History related list for the child account doesn’t show the deletion.
* **Only lookup, external lookup, and indirect lookup relationships are available for external objects. No other relationship types are supported.**
* Relationships that involve external objects allow users to create child records from the record detail pages of parent records. However, the relationship field on each new child record isn’t automatically populated to identify the parent record.
* **A relationship field is a type of custom field. Therefore, like all custom fields on an external object, relationship fields can be overwritten when you sync the external object.**
* Cascade-delete isn’t available for external object relationships.
* Lookup search isn’t available for external lookup relationship fields. To edit an external lookup relationship field, manually enter the value of the External ID standard field for the parent record. This limitation doesn’t apply when the parent external object is associated with the cross-org adapter for Salesforce Connect.
* Lookup search isn’t available for indirect lookup relationship fields. To edit an indirect lookup relationship field, manually enter the value of the target field of the parent record. The target field is the custom field with External ID and Unique attributes that was selected when the indirect lookup relationship was created. To determine related records, Salesforce matches target field values against the values of the indirect lookup relationship field on the child object.
* Lookup filters aren’t available for external lookup relationship fields.
* Indirect lookup relationship fields can be created on external objects only.
* Only objects that have a custom field with the External ID and Unique attributes are available as parent objects in indirect lookup relationships. If you don't see the desired object when you create an indirect lookup relationship field, add a custom unique, external ID field to that object.
* If the external system uses case-sensitive values in the specified External Column Name, make sure that the parent object field is also case-sensitive. When you define the parent object’s custom field, select External ID, Unique, and Treat "ABC" and "abc" as different values (case sensitive).
