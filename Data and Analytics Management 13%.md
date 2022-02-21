### Data and Analytics Management

#### Formulas & Validations.
* Formulas are case sensitive
* When working with numbers, the standard order of operations applies
* Find Distinct Objects Using the Power of One
  *  Summarize and then Sum.


#### Roll-up Summary
*  roll-up summary fields calculate values from a set of related records, such as those in a related list
*  display a value on a master record based on the values of records in a detail record
*  detail records must be directly related to the master through a master-detail relationship
*  Summary types include:
  * COUNT
  * SUM
  * MIN
  * MAX 

#### Validation Rules:
* You can create validation rules for objects, fields, campaign members, or case milestones

#### Duplicate Management
* Manage duplicates for:
  * Business accounts
  * Person Accounts
  * Contacts
  * Leads
  * Custom objects

**Identifying Duplicate Records**:
* Matching Rules:
  * matching criteria to identify duplicate records
  * Salesforce comes with three standard matching rules: one for business accounts; one for contacts and leads, and another for person accounts.
* Duplicate Rule: determines actions to take as it encounters duplicates
  * Alert
  * Hard block
  * Add Potential duplicate component on Layout
* Use **Bypass sharing rules** Prevent user from creating duplicates even if the user has no access to the existing record. The alert won't provide information on the existing record the user doesn't have permission to view.
* Create report types for Duplicate reporting.  

#### External Services
* declaratively (no coding!) integrate with externally hosted services that perform a variety of business actions or computations for use in your Salesforce org
* External Services—
  * **Salesforce integration product that encompasses registering an external web service that you submit as an OpenAPI-compliant specification defining the web service**, and 
  * **bringing the operations of your external web service into the Salesforce platform (see invocable actions) for use with point-and-click tools like Flow Builder.**
* external web service - **Any type of function, action or process that’s developed and hosted outside of the Salesforce platform. For an external web service to be consumable by External Services, it must be a REST-based API that typically uses the HTTP(s) protocol to navigate the web.**
* API specification - **a file that contains the descriptive schema that defines what an API can do. External Services adheres to a JSON-based, OpenAPI specification format. An API spec is readable by both humans and machines. It defines the basics for the naming, order, and contents of objects, and ensures clear interactions with a REST API.**
* invocable actions (in the context of External Services): **Represent the declarative building blocks available from a growing number of Salesforce platform tools like Flow Builder or Einstein Bots. Invocable actions assist admins and developers by providing a way to implement and use any type of action in a consistent manner. In the External Services ecosystem, once you register your external web service's operations with External Services, you can access the resulting invocable actions from, for example, the Flow Builder tool.**
* **key point to note**: all about **actions**. Concept is to be able to invoke an action in Salesforce based on the external service API.
