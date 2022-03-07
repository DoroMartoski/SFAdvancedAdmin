
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

#### API Specification
* Salesforce uses the **OpenApI specification** for the description format (standardized format to describe the structure of the API)
* The APi spec contains a **schema definition** that describes what types of inputs and outputs can be included in the calls or requests made to the external web service
* **The APi spec also contains the endpoint information and authentication parameters for the REST-based API web services being accessed**
* The endpoint exposes the web services resources that External Services interacts with.

##### Schema validation requirements & External Services schema requirements:
https://help.salesforce.com/articleView?id=enhanced_external_services_considerations.htm&type=5

If you use the open-source framework OpenAPI, you can use the Swagger Editor tool to validate that your schema complies with the OpenAPI specification

Summary:
* External web service provider makes its REST-based API specification available
* BASED on the OPENAPI specification, the web service provider, a developer e.t.c. creates a JSON based API spec that describes the API

##### Registering External Service
In addition to a valid and supported schema, we need a simple way to secure our external web service and our Salesforce org
* Use **Named Credentials** to authenticate our callouts
 * URL of a callout endpoint and its required authentication parameters
* Use the External Services Wizard to Register Your Web Service
 * after registering, the operations in your API spec have now become invocable actions in Salesforce 

1. An external services provider, such as a bank, shares their REST-based API spec: We got this information from our fictional bank.
2. Based on the OpenAPI specification, the web service provider, a developer (or maybe you) creates a JSON-based schema definition that describes the bank's API: While we didn’t create this API spec ourselves, we reviewed the elements of the schema and the requirements for a supported one. When you work with external services, you or your developer can define the schema you need for your use case.
3. A Salesforce administrator declaratively creates a Named Credential to authenticate to the service endpoint using the URL provided by the external service provider: We defined our named credential, https://th-external-services.herokuapp.com.
4. A Salesforce administrator declaratively registers the service and uses both the API spec and Named Credential during the registration process: We just registered our first external service and looked at the actions in the wizard.


#### Import and Export with Data Management Tools
* Data Import Wizard - provides a unified interface through which you can import data for accounts and contacts, leads, solutions, and custom objects.
* Dataloader.io - bulk import or export data. insert, update, delete, export or upsert Salesforce records for both standard & custom objects.
 * The free edition of Dataloader.io allows for up to 10,000 records per month and file size limits of 10MB


#### Big Objects
* Big objects allow you to store and manage a massive amount of data on the Salesforce platform
* Big objects provide consistent performance for a billion records or more, and are accessible with a standard set of APIs to your org or external system
* Big objects support only object and field permissions.
* Big objects support custom Salesforce Lightning and Visualforce components rather than standard UI elements (home pages, detail pages, list views, and so on)
* Big objects don’t support transactions that include big objects, standard objects, and custom objects.
* To support the scale of data in a big object, you can’t use triggers, flows, processes, and the Salesforce app.
* 2 types of big objects:
 * Standard big objects - FieldHistoryArchive, FieldHistoryArchive
 * Custom big objects - You can create a custom big object in Setup, where you set its definition, fields, and index. The fields defined in a big object’s index determine the big object’s identity and its ability to be queried

Examples of use cases for custom big objects:
* 360° View of the Customer
* Auditing and Tracking
* Historical Archive

You can query Big Objects using 
* **SOQL** - Use SOQL if you know that your query will return a small amount of data, don’t want to wait for the results, or need the results returned immediately for use in Apex
* **Async SOQL** - a way to run SOQL queries in situations where you can’t wait for the results in real time due to the sheer size of the data being queried. It is a highly scalable solution that uses a subset of SOQL commands, making it easy to use for anyone already familiar with SOQL. Async SOQL schedules and runs queries asynchronously in the background, so it can run queries that normally time out with regular SOQL.
 * With Async SOQL, you can run multiple queries in the background while monitoring their completion status.
 * Async SOQL is implemented via the Chatter REST API.

**Supported field types:**
* Lookup Relationship
* Date/Time
* Email
* Number
* Phone
* Text
* Text Area (Long)
* URL

* Big Object Index: index defines the composite primary key for a big object
 * The fields defined in a big object’s index determine the big object’s identity and ability to be queried
 * If you’re using SOQL to query your big object, you can query only on the fields that make up your index, in the order you defined them in
 * You can also use only specific comparison operators, depending on the field’s position in your query

##### Populating Big Object
There are two main ways of populating a big object. 
* You can use a .csv file with Data Loader or the API,
* entirely through Apex - use the insertImmediate method

##### Querying Big Objects
2 ways to use Async SOQL for querying Big Object
* Filtering
* Coarse aggregations - AVG(field), COUNT(field), COUNT_DISTINCT(field), SUM(field), MIN(field), MAX(field)

##### Error Handling
2 types of errors can occur during execution of an Async SOQL query
* error in the query execution
* one or more errors writing the results into the target big object
* **Because of the volume of data involved, capturing every error is inefficient. Instead, subsets of the errors generated are captured in the BackgroundOperationResult object and retained for seven days. You can query this object with the Async SOQL query jobId to filter the errors for the specific Async SOQL query. Async SOQL job info is retained for a year.**


