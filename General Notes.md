App - a set of fields, objects, permissions and functions to support a business process.
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

Dynamic dashboards - each user sees the data they have access to without needing to create a 
separate dashboards for each user.

Embedded charts - allows you to add up to 2 charts on a single page layout.Source report should
be in a folder that's shared with the users who should view the chart.Source report format is summary 
or matrix and should have a chart.

Sharing and Notifications:
Folder sharing allows you to restrict access to reports and dashboards through users, roles, roles and 
their subs, public and private groups.
Report subscription notification types: send a salesforce1 in-app notification, post to chatter, send an 
email notification or execute a custom apex action such as creating tasks or escalating cases.

Importing data in salesforce:
Data import wizard - lets you import data in common standard objects as well as custom objects.
Import up to 50,000 records at a time.

Data loader - can import up to 5 million records at a time, of any data type either from files or database
connection. Can be done through user interface or the command line.This makes it possible to automate 
the import process, using API calls.
Data export - export now or schedule export.
Data export wizard allows you to export data manually once every six days for weekly export or 28 days 
for monthly export.

### Object relationships:
Look-up relationship - links one object to another object and allows you to navigate from records in one 
object to the related records in another object. Used to create one to one and one to many relationships.

Master-Detail - creates a parent-child or master-detail relationship between two objects. Tightly linked
- the master record controls certain behaviors of the detail and sub-detail record. Ownership and sharing
of detail records are determined by the master record - when you delete the master record, all of its detail
records are automatically deleted along with it. **Master-detail relationship fields are always required
on the detail records.
**Master object in master-detail relationshipcan also contain roll-up summary fields. These fields store 
values aggregated from the child records in the relationship.

** You can't create a detail record without a master record. The detail record inherits sharing rules
from the master. The number of master-detail relationship you can set are limited depending on your 
edition or license. You can't set profile permissions for a detail record.**
** You can convert a master-detail relationship to a lookup relationship as long as no roll-up summary
fields exist on the master object.**
** You can convert a lookup relationship to a master-detail relationship only if the lookup fields on 
the records contains a value.

### Forecasting
Forecast is an expression of expected sales revenue based on the gross rollup of a set of opportunities.
**The forecast amounts shown on the forecast tab are totals and subtotals of the opportunities in the 4 forecast categories => Pipeline,
Best case, commit and closed.
Forecasts amounts in the rollup table are organized by forecast rollup, time period and optionally product family.
Forecasts can include adjustments made by forecast managers to their immediate subordinates' forecasts as well as adjustments made forecast 
users to their own forecast amounts.
Admins can enable up to 4 different types of forecast at the same time.
**Users can view forecast amounts and their related opportunities by forecast rollup for an individual or for everyone below them in 
the forecast hierarchy.
Collaborative Forecasts => Predict sales revenue and quantities from your opportunity pipeline and incorporate product families, opportunity
splits, and custom opportunity currency fields if needed.
Predict and plan the sales cycle from pipeline to closed sales and manage sales expectations throughout the organization with 
Collaborative forecast.

Use collaborative forecast to perform tasks such as:
** See forecast summaries for each product family.
** See split percentages and split amounts that contribute to each forecast.
** View and use the list of opportunities related to each forecast amount you select. Access opportunity details directly from this list.
** Make adjustments and view adjustment details such as the original adjustment details and who made the adjustments. Each forecast type
maintains its own separate adjustments.
** If you are a forecast manager, move up and down the hierarchy easily.
** View revenue or quantity based forecasts.
** View forecasts in multiple currencies. 
** View quota information on each user's forecast page. If multiple forecasts are enabled each forecast type maintains its own separate 
quota information.
** Include the opportunities of your partner portal users in your forecasts.
 
**When migrating from Customizable forecasting to collaborative, note**:
*Forecast history, overides, reports and sharing data from customizable forecasting are purged so consider exporting those data prior
to migration.
*Default Collaborative forecast period is monthly - you can however change the setting to quarterly. If you use custom fiscal year then 
your fiscal period is the default.
*The forecast hierarchy is retained.
