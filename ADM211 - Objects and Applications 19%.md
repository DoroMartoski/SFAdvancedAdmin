# Objects and Applications

#### Estimated Number of questions out of 60: 11.4 (11) questions

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
* Use favorites to boost productivity by personalizing navigation.
* Use **App Launcher** to find available apps.
* you can change which apps appear in the Lightning Experience App Launcher. You can also control the order in which the apps appear from the app menu.
* the apps that users see in their App Launcher and app menu vary depending on each app’s visibility settings and user permissions. Users see only the apps that they are authorized to see according to their profile or permission sets.

#### Search
* search results dynamically updates with matches from all searchable objects.
* **You can also sort most search results.**

#### Help Menu
* each page has a contextual Help Menu with links to resources related to the tasks on that page and resources for getting started
* **If an admin added custom resources for working in an org, users see those resources first**
 * Admins and users see different sets of resources that are appropriate to their work in Salesforce.
 * Admins can add a custom help section at the top of the Help Menu on every page in Lightning Experience. Guide users as they work in your org with links to your own URLs to websites, PDF files, videos, or Trailhead mixes. 
 * You get to name the section and pick the resources to display.

These object functions aren’t listed in the Object Manager. You can access them from elsewhere in Setup.
* Case Comment Triggers
* Feed Comment Triggers
* Feed Item Triggers
* Feed Item Layouts
* Group Layouts
* Group Triggers
* Group Member Triggers
* Group Record Triggers
* Publisher Layouts
* Topic Triggers
* Topic Assignment Triggers

**Service Setup flows offer a guided step-by-step experience to walk you through setting up various support features like email support, integrating with Twitter and Facebook, and enabling a Knowledge base**

#### Sales tools
**Opportunity Workspace**:
* you can enhance your sales users’ workflow by customizing the sales path and the activity timeline to their needs
* if your company uses a team selling approach, you can split your opportunity revenue by using opportunity splits in Lightning Experience.

#### Path
* guides users through each stage of your company's sales process
* helps users stay focused on important tasks so they can close deals or complete work quickly
* You can create a unique path for each record type for **leads, opportunities, quotes, and custom objects**.
* Provide guidance for success content, like links to Chatter posts and videos, tips, or policy reminders—anything that can help sales reps get closer to sealing the deal.
* Keep your system performance optimal by creating sales paths that have 20 or fewer stages.
* Consider labeling sales paths for regions or industries, like “Steel Industry Sales Path.”
* If you set up record types, you can have one path for each record type.

#### Activity Timeline
* tracks meetings, tasks, calls, and emails. Reps can see what they’ve done and what they still have left to do for each opportunity, lead, account, and contact.
* The configuration of page layouts and record types affects the tabs in the activity composer. Don’t see the tabs for calls, tasks, events, or emails in the activity composer? Adjust your page layouts, record types, and user permissions.
* In the activity timeline, you can customize the display and order of fields when an activity is expanded for events, tasks, and logged calls.
* The description field for events and the comments field for tasks also always appear in the timeline, although they aren’t available in the compact layout.
 
 #### Opportunity Kanban view
 * select kanban from displays menu on all list views except Recently Viewed
 * The records in the Kanban view are based on the selected list view. Reps can’t view the Kanban for Recently Viewed list views
 * Records are separated based on record type
 * A yellow triangle on an opportunity card can indicate three types of alerts: overdue tasks, no open activities, or no activity for 30 days
 * Users can click the triangle to create tasks and events right from the card.
 * Items on the board vary based on which list view is open.

#### Lead Workspace
* To convert a lead, your reps click the Converted stage in the path. Then, they either select an account or create one on the spot. Reps can also create an opportunity.

#### Accounts and Contacts
you can:
* visualizing account relationships in an account hierarchy, seeing who reports to whom in a contact hierarchy, 
* relate single contacts to multiple accounts without duplicating records. Contacts to Multiple Accounts feature lets you relate a single contact to multiple accounts so that you can easily track the relationships between people and businesses
* you can customize hierarchy columns to show the information that’s most useful to your sales reps.
* When a user transfers an account or an opportunity to a different owner, you also have the flexibility to transfer related records such as cases, just as in Salesforce Classic.

#### Service Cloud in Lightning Experience
* Split view shows a list view at the same time as workspace tabs and subtabs, letting your support agents manage multiple cases on a single screen

**Lightning knowledge**
* now a standard object
* standard record types have replaced article types
* knowledge component for lightning Service Console has replaced Knowledge one
* following actions can be done on knowledge:
 * Create an article
 * Published articles—create a draft version or archive the article
 * Draft articles—publish, edit, or delete
 * Archived articles—restore or delete
 * Bulk actions—archive, assign, publish, restore, submit for translation, and delete drafts or archived articles

**Embedded chat**: Embedded chat allows customers to get quick answers to their questions by chatting with an agent while browsing your site
* Customers fill out the brief pre-chat form, which helps agents gather basic information about the customer, like their contact information and their needs.

**Service Analytics App**: shares best practice KPIs about your service data in a single place
* the app tailors this information by role
* Using the prebuilt dashboards in the Service Analytics app, service managers can quickly view average case closing times, customer satisfaction, and trending, historical, and peer benchmarks
* They can also get insight into the team’s use of knowledge articles to resolve cases, and other data so they can quickly take appropriate actions.
* Another set of dashboards—called sidebars—are specifically for support agents. For a given case, an agent can view customer history, number of cases, and CSAT. Ensure that agents have fast access to this information by embedding these sidebars on key Salesforce pages, such as the service console.

#### Field Service
* With Field Service, your agents, dispatchers, and field technicians get the tools to manage work orders, service resources, and scheduling
* **Create service resource records that represent your field service technicians and add details about their skills, service territories, and availability.**
* **Set up multilevel service territories that represent the regions where your technicians work.**
* **Track your product inventory and service vehicle locations.**
* **Schedule one-time or recurring appointments for customers and add details about technician preference and required skills.**
* **Standardize your business’s field service tasks with maintenance plans and templates.**
* **Keep customers informed about service progress with on-site service reports.**

#### Omni-channel
* Omni-Channel helps your service center route any type of incoming work item—including cases, chats, or leads—to your most qualified, available agents - They no longer have to pick and choose work assignments from a queue, which saves everyone time, effort, and brainpower
* Use Omni-Channel to manage the priority of work items for agents and balance the distribution of assignments. You can also define which agents work on different types of assignments, such as leads or sales inquiries, and other assignments that help with support questions.
* Console users can set their presence status and accept or decline work depending on your Omni-Channel settings.

#### Social Customer Service
* Social Customer Service integrates with Twitter, Facebook, Instagram, and YouTube to deliver customer conversations directly to your agents
* Support agents get the tools to manage cases originating from social media and engage customers by responding directly in social networks.
**Inbound and outbound social posts appear as items in the case feed, making it easy to follow conversations. Attachments to posts are also viewable right in the feed. Agents can respond to posts using the Social action in the publisher and include an attachment or a Direct Message prompt. They can also like conversations, reply privately to customers, hide comments on Facebook, and delete conversations managed by your company’s social accounts.**


#### Custom Themes and Branding
* Theme and brand-based colors show up in various places in the user interface, including page backgrounds, the global header, navigation bar, tabs, and buttons. You can also use a theme’s brand image on the Lightning Experience loading page. By default, orgs use the built-in Lightning Blue theme.
* From Setup, enter Themes and Branding in the Quick Find box, then select Themes and Branding
* Upload a brand image, and choose brand colors. Custom themes modify the brand color to make it accessible.

#### The Home Page
* From the Home page, your users can manage their day, including viewing their quarterly performance summary and the most relevant tasks and updates
* You can also use the Lightning App Builder to create custom Home pages that appear for different profiles.
* Give your users access to opportunity details so that they can get the most out of the Home page.
 * **Performance Chart**: displays data based on opportunities belonging to the user or the user’s sales team. Multicurrency is supported in the performance chart.
  * Only opportunities for the current sales quarter that are closed or open with a probability over 70% are displayed
  * Closed—The sum of a user’s closed opportunities.
  * Open (>70%)—The sum of a user’s open opportunities with a probability over 70%. T
  * Goal—A user’s customizable sales goal for the quarter. This field is specific to the performance chart and has no impact on forecast quotas or any other type of goals
* **Assistant**: shows your users things they need to address, including new leads and activities related to opportunities.
 * Items in the Assistant appear in the following order:
 * Leads assigned to you today
 * Opportunities with overdue tasks
 * Opportunities with no activity in 30 days
 * Opportunities with no open activity
 * Overdue opportunitiesOpportunities are overdue if they’re still open after the Close Date. These updates stop appearing if it’s been over 8 days since the Close Date.
 * **The Assistant doesn’t show tasks due today or overdue tasks that aren’t tied to an opportunity. The Today’s Tasks component is an alternative that’s available on the Home page, and it shows a list of your tasks due today**

* **an administrator can configure an object’s Recently Viewed search layout for users**
* The search layout controls what all users see when they land on that object’s home page
* In Lightning Experience, from Setup, find the object in the Object Manager, then scroll to its Search Layout related list and edit the Search Results search layout
* You can also go directly to an object’s details page by selecting Edit Object from the Setup menu.
* **Your users can reorder the columns of the Recently Viewed Object list in Salesforce Classic, and the changes are reflected in Lightning Experience.**

**Cases are feed-first and display a Chatter tab first, rather than record details or related information**

#### Chatter in Lightning Expereince
* Can display date and time stamps on Case feed items

#### File Management and Collaboration
* Salesforce files support all file types
* Files can be viewed from the files tab as well as from files related list on a record 
* Add Files related list on object layouts.
* file preview player in Lightning Experience provides a visually and functionally rich preview experience
 *  includes controls for quickly downloading, sharing, or deleting the current file, uploading a new version of the file, editing file details, and **generating a public link to the file (you can delete the link to the file to stop public access to the file)**
* Users can access sharing options from Files home, Files related lists, the file preview player, file record detail pages, and Chatter feeds
* **you can convert attachments to files and eliminate the need for wasteful context switching. Install the  Attachments to Files tool from AppExchange and kick off bulk jobs that convert attachments to Salesforce Files**
* Salesforce CRM Content Folders and files in libraries are available from Salesforce Files in Lightning Experience
 * Library admins can create and manage libraries in Lightning Experience too. Content deliveries aren’t available in Lightning Experience, but link sharing is supported.

#### Tasks, Events and Calendars
##### Tasks
* View a list of all your open tasks, showing the opportunities, accounts, and other records they’re related to. See and edit details right there on the same page.
* **Switch to views of tasks you’ve delegated, open tasks, all overdue tasks, recently completed tasks, recently viewed tasks, recurring tasks, tasks due today, and unscheduled tasks. Quickly mark tasks complete directly from any tasks list view. Assign tasks to a queue so that you can share work more efficiently. Any member of a queue can complete a task when they have time.**

##### Calendar
* **see a list of events using the table view or find a time that works for multiple people in availability view.**
* calendar displays all events owned by a user, including events outside a user’s business hours, in the time zone selected in your Salesforce settings.
* To help you schedule meetings efficiently, you can take a peek at your coworkers’ calendars, too. What you see depends on your admin-set sharing settings and the level of sharing access that coworkers give.
* Choose a field to track on any standard or custom object. The calendar displays data in that field as calendar items.
* You can distinguish calendars by color and texture
* Calendar views display up to 150 items, including items from calendars you create. 

#### Reports & Dashboard
* Find a report or dashboard using filtered lists and folders
* Folders let you group related reports or dashboards, so they’re easy to find again later.
* Open the report feed to collaborate with others on report data
* Show or hide details like subtotals, grand totals, and record counts from your report.
* You can also lock filters 
##### Dashboards
* **For dashboards - use toolbar to add components and filters, undo or redo edits, edit chart properties, and perform administrative tasks like saving. Unique to Lightning Experience, from the chart properties menu, you can customize chart colors and dashboard theme (background color).**
* **up to nine columns and unlimited rows**
 * Dashboard components can span as many columns and rows as you like. Drag the corners and sides of a dashboard component to make it bigger or smaller
* Charts, tables, and metrics all dynamically resize
* After saving a Salesforce Classic dashboard in Lightning Experience, you can’t edit it in Salesforce Classic

###### Lightning table
* Up to 10 columns and 200 rows!
* Columns come from source reports’ report type. That means that you don’t have to add a field to the source report to show it in the table.
* Show Chatter photos and conditional highlighting.
* Lightning tables are dashboard filter compatible.
* Customize dashboard color palette and theme.

##### Interactive dashboards
* View dashboards as other people if properties are set to allow you to choose whom you view the dashboard as, click Change to see the dashboard as someone else.
* Click a chart segment or datapoint to open a filtered source report.
* Expand dashboard components to see a larger version of it

* You can view and open folders that you created in Salesforce Classic in Lightning Experience. Lightning Experience obeys sharing rules set on report and dashboard folders in Salesforce Classic.
* Joined reports are available as a beta in Lightning Experience.
* You can view and edit reports created in Lightning Experience in Salesforce Classic
* **You can’t edit dashboards created in Lightning Experience in Salesforce Classic, but you can view them. Lightning tables, a table component only available in Lightning Experience, don’t appear when you view a dashboard in Salesforce Classic.**
* Dashboards that you create in Lightning Experience that have more than three columns automatically display in Salesforce Classic with three columns (retaining all dashboard components).
