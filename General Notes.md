App - a set of fields, objects, permissions and functions to support a business process.

**Lightning apps let you brand your apps with a custom color and logo and include a utility bar and lightning page tabs**

**A lightning app can contain:**
* Most standard objects
* Custom objects
* Visualforce tabs
* Lightning component tabs
* Canvas apps via Visualforce tabs
* Web tabs

**Use the App Manager to create and manage your tools**

**In lightning, a page's layout can be customized or it's contents customized. This is done using separate tools.**
**Lightning pages are a collection of lightning components arranged in regions on the page.**

### Compact Layouts
* Controls which fields users see in the highlights panel at the top of a record.
* Also controls the fields that appear in the expanded lookup card when one hovers over a link in record details.


Identify processes that involves manual processing, emaail driven, teams using spreadsheets to function and documents shared on local machines as some of the processes to move into SF.
Summary reports are similar to tabular reports, but also allows users to group rows of data, view subtotals 
and create charts.
Matrix reports should be used when looking for an at a glance overview of data, especially for something 
like totals of revenue or quantity of products sold.
Joined reports lets you create different views of data from multiple report types. You can add up to 
5 report blocks.

### Dashboard component type:
Chart (pie,bar) - use this when you want to show data graphically.
Gauge - use this when you have a single value that you want to show within a range of custom values.
Metric - use this when you have one key value to display. Enter metric label directly on components
by clicking the empty text field next to the grand total. Metric components place directly above and 
below each other in a dashboard column are displayed together as a single component.
Table - use this to show a set of report data in column form.
Visualforce page - use this when you want to create a custom component or show information not
available in another componenttype.

**Dynamic dashboards - each user sees the data they have access to without needing to create a 
separate dashboards for each user.**

**Embedded charts - allows you to add up to 2 charts on a single page layout.Source report should
be in a folder that's shared with the users who should view the chart.Source report format is summary 
or matrix and should have a chart.**

**Sharing and Notifications:**
Folder sharing allows you to restrict access to reports and dashboards through users, roles, roles and 
their subs, public and private groups.
Report subscription notification types: send a salesforce1 in-app notification, post to chatter, send an 
email notification or execute a custom apex action such as creating tasks or escalating cases.

**Importing data in salesforce:**
* Data import wizard - lets you import data in common standard objects as well as custom objects.
Import up to 50,000 records at a time.

* Data loader - can import up to 5 million records at a time, of any data type either from files or database
connection. Can be done through user interface or the command line.This makes it possible to automate 
the import process, using API calls.
Data export - export now or schedule export.
Data export wizard allows you to export data manually once every six days for weekly export or 28 days 
for monthly export.

### Object relationships:
* Look-up relationship - links one object to another object and allows you to navigate from records in one 
object to the related records in another object. Used to create one to one and one to many relationships.

* Master-Detail - creates a parent-child or master-detail relationship between two objects. Tightly linked the master record controls certain behaviors of the detail and sub-detail record. Ownership and sharing
of detail records are determined by the master record - when you delete the master record, all of its detail
records are automatically deleted along with it. **Master-detail relationship fields are always required
on the detail records.
* Master object in master-detail relationship can also contain roll-up summary fields. These fields store 
values aggregated from the child records in the relationship.

* You can't create a detail record without a master record. The detail record inherits sharing rules
from the master. The number of master-detail relationship you can set are limited depending on your 
edition or license. You can't set profile permissions for a detail record.
* You can convert a master-detail relationship to a lookup relationship as long as no roll-up summary
fields exist on the master object.
* You can convert a lookup relationship to a master-detail relationship only if the lookup fields on 
the records contains a value.
* The master object controls the access to the detail's data.
* When creating master-detail relationship, always create the relationship field on the detail object.

**Hierarchical relationship: available only on the user object for creating management chains between users**

**Schema builder: lets you visualize and edit your data model**

### Forecasting
Forecast is an expression of expected sales revenue based on the gross rollup of a set of opportunities.
* The forecast amounts shown on the forecast tab are totals and subtotals of the opportunities in the 4 forecast categories => Pipeline,
Best case, commit and closed.
Forecasts amounts in the rollup table are organized by forecast rollup, time period and optionally product family.
Forecasts can include adjustments made by forecast managers to their immediate subordinates' forecasts as well as adjustments made forecast 
users to their own forecast amounts.
Admins can enable up to 4 different types of forecast at the same time.
* Users can view forecast amounts and their related opportunities by forecast rollup for an individual or for everyone below them in 
the forecast hierarchy.
Collaborative Forecasts => Predict sales revenue and quantities from your opportunity pipeline and incorporate product families, opportunity
splits, and custom opportunity currency fields if needed.
Predict and plan the sales cycle from pipeline to closed sales and manage sales expectations throughout the organization with 
Collaborative forecast.

**Use collaborative forecast to perform tasks such as:**
* See forecast summaries for each product family.
* See split percentages and split amounts that contribute to each forecast.
* View and use the list of opportunities related to each forecast amount you select. Access opportunity details directly from this list.
* Make adjustments and view adjustment details such as the original adjustment details and who made the adjustments. Each forecast type
maintains its own separate adjustments.
* If you are a forecast manager, move up and down the hierarchy easily.
* View revenue or quantity based forecasts.
* View forecasts in multiple currencies. 
* View quota information on each user's forecast page. If multiple forecasts are enabled each forecast type maintains its own separate 
quota information.
** Include the opportunities of your partner portal users in your forecasts.
 
**When migrating from Customizable forecasting to collaborative, note**:
* Forecast history, overides, reports and sharing data from customizable forecasting are purged so consider exporting those data prior
to migration.
* Default Collaborative forecast period is monthly - you can however change the setting to quarterly. If you use custom fiscal year then 
your fiscal period is the default.
* The forecast hierarchy is retained.

## Salesforce CRM Content
**Instead of file folders that are harder to search, CRM content stores files in fully searchable file repos called libraries.**
* Multiple libraries can be created based on classifications such as dept name, job function etc.
* User permissions can be created within the libraries to manage security.
* Authors can add descriptive labels or tags to help classify and organize content across libraries. Tags can be used as search filters
* Private libraries which allow users to reduce their desktop clutters can also be created.
* Benefit of CRM Content/ content management is document search and version control.
* CRM Content searches the entire body of the document as well as content properties such as title, description, author name and tags.

Library => Contribute => choose file to upload => Add title, description, tags and choose library to publish to => 
Record type if needed => publish
### Searching
* Scans the entire body of the document as well as the content properties such as title, description, tags etc.
* Content searches can be filtered based on file format, author, tags, libraries, and custom fields
* Search can also be filtered by chatter files.

### Subscribing
* Files can be subscribed to for alerts on changes.
* User can also subscribe to an author, tags, and libraries.

### Previewing
* MS PPt, excel, or Adobe PDF files can be entirely previewed in the browser without downloading
* Copy protected files cannot be previewed

* Simply upload a new version of the file and SF CRM maintains a version list accessible from the content details page.
* Featuring a piece of content increases its visibility in search results
* You can see who has subscribed to a file, link, or doc and how many times files have been downloaded.
* * If content delivery is enabled, you can send content to colleagues, leads, and contacts and track how often the content has been downloaded.
* If content is enabled on an object, the CRM content uses the fields on the object detail page to search for files that may be relevant to that object record.
* Salesforce CRM Content user license must be given to a user for them to access contents. This is a checkbox on the user page
* There are 3 tagging rules: restricted (doesn't allow the author to create new tags), guided tagging, and open tagging.

**Users can vote thumps up or down on files or links or google doc**

### Content delivery
* Allows you to easily convert docs into optimized web-based versions for easy online viewing.
* Creates encrypted URL to any recipient such as leads, customers, partners.
* this can then be tracked to know how often the content is viewed or downloaded.(available only in classic- lightning email is its equivalent in lightning).
* you can create a new delivery for a content or view all the deliveries associated with it.
* you can allow users to publish, edit and search for content in any of the 20 salesforce supported languages.
* If a user does not choose a language when publishing content, the content is asssociated with the user's personal language by default.
* if the user's personal language is different from the organization's language, content published by the user is associated with the user's language, not the organization's language.
* Enable content delivery by choosing the Enable Creation of Content Deliveries for Salesforce files under the Content Deliveries section in Setup.
* Best practice to require password protection on content delivery if your users will be sending confidential documents through content delivery. **3 password options through Org-wide default** => Password protection is optional and defaults to off, Password protection is optional and defaults to ON and lastly Password protection is required (with this option, Password is generated each time a content delivery is created - users cannot opt out of the password requirement.

### Content packs
* This is a collection of related documents or files that are stored as a group in Salesforce CRM Content.
* Total number of content delivery views allowed in 24 hour period is 20k.
* Total number of bandwidth allocated to content deliveries is limited to 20gb with a 24 hour period - after this users receive a rate limit has been exceeded notification.
* content delivery can be created with any file type - if the file type is not supported for online viewing, your recipient can only download the document in its original format. Important to preview your documents before before sending the URL to recipients.
* Customer portal and partner portal users cannot create content deliveries.
* Only the creator of a content delivery can delete the delivery record or edit details such as the expiration date.

### Enabling Google Docs
* Enable the Add Google Docs to Salesforce service. This allows users to use the Add Google Doc drop-down list on the libraries tab to add Google docs, spreadsheets and presentations to their CRM Content Libraries.
* You must have a Google App account and configure that accounts domain settings

### Restricting Record types in Library
* My libraries => Record types => restrict the record types available in the library checkbox => select either one or both of 
  * Allow content with any record type to be linked to this library
  * Do not apply record type restrictions to existing content
 
* For each record type you want to allow in the library, move it from the Available Record types list to the Selected Record type list. and then save.
* If the library already contains published content, selecting the Restrict the record types available in the library option automatically moves all the record types used by the published content to the selected Record types list.
* Deselecting the Restrict the Record types available in the library option automatically moves any record types in the Selected Record types list to the available record types list
* When changing a file's managing library, the record type of the file must be permitted in the new managing library.
* When sharing a file with a library, the file's record type must be permitted in the shared library unless the **Allow content with any record type to be linked to this library** option is selected for the shared library.
* when the default record type for a user's profile differs from the default record type for a library, the user profile default takes priority when a user with that profile shares a file with the library.
* When there are no record types in commong between a user profile and a library, the default record type for a library is available to users with that user profile who are sharing files with the library.

**Create folders in lightning experience to organize files already in libraries. Upload files to a library by selecting the library and then clicking add files.**
**Switch to classic to create libraries.**

### Tagging
* Tags are descriptive labels to help classify & organize content.
* Assign tagging rules to a library by => My libraries => select library => click tagging rules => choose type of tagging rule.
* Open tagging: Contributors are free to enter any tags when publishing or editing content. This is the default tagging rule.
* Guided tagging: this rule also enables contributors to enter any tag when publishing or editing content but contributors are also offered a list of suggested tags.
* Restricted tagging: this rule requires contributors to choose from the list of suggested tags.

* Portal users without a Salesforce CRM Content feature license can download, rate, comment on, and subscribe to content if they
have the “View Content on Portals” user permission. They cannot view potentially sensitive data such as usernames, download
history, and version history. The content delivery feature is not available to portal users.
* Portal users with a Salesforce CRM Content feature license can access all Salesforce CRM Content features granted by their library
permission(s), including contributing content, moving and sharing content among libraries, and deleting content. They can also
view Salesforce CRM Content reports. The content delivery feature is not available to portal users.
