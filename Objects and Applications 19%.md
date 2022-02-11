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

### Prepare for the Lightning Experience Module
#### Lightning Experience Transition
* The Transition Assistant guides you through each phase, stage and activity in your transition.
* Use the Enablement Pack full of rollout resources and customizable templates to prepare for and complete a successful transition.

**Phases**: Discover ---> Rollout ---> Optimize
* **Discovery Phase:** evaluate your production org's readiness for the new interface.
 * plan your rollout and change management strategies and aling with stakeholder on your transition goals.
 * Calculate the ROI from transitioning to Lightning Experience
 * Review your current Business processes - consider ways to improve them in the transition.
 * Use the **Lightning Experience Readiness Check** to help you identify where your org stands through a personalized report that shows how to adjust your implementation.
 * **Access the Impact of Feature Gaps**: Part of your evaluation is to identify how important upcoming features are to your business needs. Work with affected teams and users to identify gaps that are relevant for your org and the severity of each gap. You can use several methodologies when assessing impact, including assigning a numeric value to each gap, or plotting the gaps on a simple chart.
 * Get Hands-on with Lightning Experience
* **Plan your Lightning Experience Rollout**
 * Pick a rollout strategy: 
  * Gradual rollout: decide the Users and Scope of Work for Each Group in Your Rollout 
  * Big bang
 * Develop a Change Management Plan
  * Start with a change impact assessment to learn how users feel about your current Salesforce implementation and what their impressions are of Lightning Experience.
  * identify the processes and activities that change in the new interface, and work with affected stakeholders and users to assess the impact.
  * Lightning Experience Transition Change Management Hub for help developing and implementing a change management plan. The Hub guides you through all the recommended steps and best practices for managing change throughout your org’s transition. 
 * Define Measures for Success
 * Pick launch date

**Rollout**
* My Domain: Create a subdomain to help manage login and authentication
* To use Lightning Experience, users must have the Lightning Experience User permission. This permission is automatically enabled in all standard Salesforce profiles. But custom profiles don’t usually include this permission by default.
* Use the **Lightning Experience Converter** to recreate Actions and Buttons,  VF pages.
* Use **Magic Mover** for Notes and Attachments conversion to enahnce notes and Salesforce Files.
* Use **Lightning Knowledge Migration tool** to move Classic knowledge base to Lightning Knowledge.
* Use the Switch Users tool in the Lightning Experience Transition Assistant to assign the new interface as a user’s default experience, on a user-by-user basis.

**Optimize**
* Keep an eye on adoption rates: use the Lightning Usage App for insights on active Lightning Expereince Users, the number of users switching back to Salesforce Classic, most visited pages in Lightning Experience.
* **Collect and evaluate feedback**: Poll(informal chatter poll to gather quick insights), SUrvey, Focus Groups
* Engage with your champions
* Monitor Your Success Metrics
 * Reporting snapshots are a way to analyze trends over time
* Deliver an Executive Summary
 * Keep it to 1-2 pages maximum
 * Showcase metrics and results
 * Highlight any noteworthy anecdotes
 * Share lessons learned
 * Note any next steps still planned
* Motivate Users to Work in Lightning Experience
* Iterate on Your Rollout Plan
* **Improve Your Implementation with Salesforce Optimizer**
 * Run it in sandbox or production environments to get a personalized report with recommendations for improving features, cleaning up customizations, reducing complexity, and driving feature adoption.
 * Some of the features that Optimizer evaluates include Apex triggers, fields, profiles, record types, and validation rules.
 * **Turn Off Salesforce Classic for Your Org**
  * You do this by removing the Switcher for all users in your org.
 
### Lightning Experience Features
#### Navigate Lightning Experience and Setup
* In Lightning Experience you can even include Lightning page tabs and a utility bar that allows instant access to productivity tools, like integrated voice, in the footer of Lightning Experience
* users can create records and access recent records and lists directly from the navigation bar for items like Opportunities.

**Lightning app navigation bar** can contain:
* Most standard objects, including Home, the main Chatter feed, Groups, and People
* Your org’s custom objects
* Visualforce tabs
* Lightning component tabs
* Canvas apps via Visualforce tabs
* Web tabs
* Lightning page tabs and utilities like Lightning Voice - you can enable a utility bar in your app that allows instant access to productivity tools, like integrated voice, in the Lightning Experience footer

**Personalizing the navigation bar** using the enhanced editor:
* Reorder the items already in your navigation bar.
* Rename items you’ve added.
* Add items to the navigation bar

Notes:
* Users can’t personalize the navigation bar of Classic apps in Lightning Experience.
* can’t personalize the navigation bar when it contains more than 50 items
* Items that you add to an app’s navigation bar are added to the end of users’ personalized navigation bars in the order that you added them.
* When you remove an item from an app, that item remains in your users’ personalized navigation bars, and users can then delete it.
* If you don’t want your users to personalize the navigation bar for a specific app, disable personalization.
* If you don’t want your users to personalize the navigation bar for any app, disable personalization.
* Control if temporary tabs are created when users access items outside of the app.
* New action doesn’t appear if The New action isn’t part of the search layout for the object’s list view
