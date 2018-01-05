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


### Cross filters
* **Cross filters filter results by related objects whereas field filters limit results by the values of fields**
* **Cross filters let you filter the parent records in a report by their related child records, using WITH or WITHOUT conditions.**
**Subfilters can then be added on cross filters to further filter by fields on the child object**
* Up to 3 cross filters in a report and Up to 5 subfilters per each cross filter can be created.
* Cross filters have an AND relationship with the report type

### Bucketing:
* Can only be used with Number, picklist and text fields.
* Up to 20 buckets can be created.
