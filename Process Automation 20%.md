### Advanced Formulas 7h
Using formulas, you can embed hyperlinks, perform arithmetic with existing fields, or use conditional logic to display 
an amount.


* formulas are case sensitive
* the standard order of applications apply when working with numbers
* Use the Power of 1 to find distinct counts of objects in a report by creating a power of 1 formular field on the object you want to get the distinct count and summarize the field in the report.
* **A Date/Time value stores a year, month, day, and a time. The time is stored as GMT, but displays in the time zone of the user viewing it.**
* If you’re subtracting two Date values, the result is a whole number. If you’re subtracting two Date/Time values, the result is a decimal value representing the number of days, hours, and minutes.
* **A Time value is like a Date/Time value without the date. However, a Time value’s precision is in milliseconds. A Date/Time value’s precision is in seconds**.
* **If you’re subtracting two Time values, the result is in milliseconds and is always positive.**
* You can convert a Date/Time to a Date by using the DATEVALUE() function, which takes a Date/Time or Text value and returns a Date
* DATETIMEVALUE() takes a Date or Text value and returns a Date/Time value, with the time set to midnight GMT
* Time fields do not include a date. So adding 25 hours to a time value is the same as adding 1 hour. The clock restarts after 24 hours.
* **Using helper formula fields is a great way to make your formulas short and easy to understand. A helper field does only part of a larger calculation and is referenced by the end formula field**


**Cross-object formula**: displays data from one object on a different object
* Members of your organization can see a formula that displays or references a cross-object field even if they do not have access to the object that the field is on
* Cross-object formulas that reference currency fields convert the value to the currency of the record that contains the formula. If the referenced currency field is from a custom setting, the field value isn’t converted to the record’s currency
* Salesforce allows a maximum of 10 unique relationships per object in cross-object formulas. The limit is cumulative across all formula fields, rules, and lookup filters. For example, if two different formulas on opportunities reference two different fields of an associated account, only one unique relationship exists (from opportunities to accounts)
* You can’t reference cross-object formulas in roll-up summary fields.
* In cross-object formulas, you can’t reference merge fields for objects related to activities. For example, merge fields for contacts and accounts aren’t available in task and event formulas.
* In cross-object formulas, you can’t reference fields from contacts through person accounts.


#### Picklists in formulas
* 3 functions take picklists as arguments in formula fields: **ISPICKVAL()**, **CASE()**, and **TEXT()**
* ISPICKVAL(picklist_field, text_value). returns boolean. ISPICKVAL() can be combined with PRIORVALUE()
* TEXT() converts a picklist value to a **text value**. Can combine **TEXT()** with Text functions such as BEGINS(), & CONTAINS().
* **TEXT() CANNOT BE USED ON MULTI-SELECT PICKLISTS**

#### Text in formulas
* Formulas that use the Text return type can concatenate Text values, convert numbers and dates to text, or display text conditionally
* **TEXT() always returns Date/Time values in GMT, not the time zone of the current user or your organization.**
* TEXT() converts a Percent, Number, Date, Date/Time, picklist, or Currency field into Text. TEXT() returns output without any formatting, commas, or currency signs. For example, TEXT(percent_value), if percent_value is set to 30%, returns 0.3

##### Display an image with CASE()
	IMAGE(
	CASE(Rating__C,
	  "Hot", "/img/samples/stars_500.gif",
	  "Warm", "/img/samples/stars_300.gif",
	  "Cold", "/img/samples/stars_100.gif",
	  "/img/samples/stars_000.gif"),
	"Unknown")


* Formula fields are restricted to 3900 characters or 4000 bytes including spaces, return characters and comments.
* Formulas cannot exceed 5000 bytes when compiled.
* Shorted formulas by:
	* Replacing longer logic by shorter version e.g. AND() with &&
	* Nexted If() with CASE()
	* Create shorter field names
* When referencing helper field, its compile size is added to the compile size of the formula's compile size. Minimize 

### Formula Return types
* Checkbox
* Currency
* Date
* Date/Time
* Number
* Percent
* Text
* Time


#### Salesforce flow
* declarative process automation
* Includes 2 tools: 
	* flow builder: build flows
	* Process builder: edit existing processes


use case                                      |  functionality
----------------------------------------------|-----------------------------------------------------------------------
create guided tutorial or wizard with screens | flow builder - has out of the box file uploads, text boxes etc.Can add custom lightning component
set up automated tasks and processes          | flow builder.
connect to external systems                   | communicate (respond and send) changes between your salesforce org and external systems  with platform events. Flow builder can also retrieve data from 3rd party systems with External Services
add automation to pages and apps              | flow builder
re-use what you build                         | In Flow Builder, break down process logic or actions into a flow that's referenced by a Subflow element. You can reuse or reference this flow in other business processes.In Process Builder, call an autolaunched flow from a process to automate complex business processes.

* Approval automation: use Approvals

**Flows:**
* when automating guided visual experience
* start a behind the scenes business process
	* onclick action
	* edited, created, deleted actions
	* when a platform event occurs
	* at a specific time and frequency
* Create chatter posts, submit records for approval & send emails
* flows can Call Apex code
* connect your flow to an external database by using core actions.
	* core actions let you make requests without going through the Salesforce server
* publish platform event messages with a create Records element
* subscribe to platform events with a Pause element. 
E.g. create a renewal opportunity when an opportunity is won

**Process Builder:**
* It is recommended by Salesforce to use Flow Builder for all behind the scenes automation needs
* A record is created, updated
* Platform event occurs
* if/then business processes
* Consists of a trigger, at least one criteria node, and at least one action.
* You can configure immediate actions or schedule actions
* **Process types**: record change, Invocable, Platform Event

**Apex:**
* When you need more complex business logic
* Recommended to build the more complex functionality as **invocable Apex methods** and then call the Apex as an Apex action in the process or as an Apex action element in the flow.

**Approval Process:**
* Automates how records are approved.
* Specify:
	* the steps necessary for a record to be approved
	* who approves the record at each step
	* the actions to take based on what happens during the approval process. e.g. update fields after a record is approved or send an email notification if the request is rejected.
* the default initial submission action after a request for approval has been sent, locks the record
	* only approvers and admins can change the record whiles it's pending approval.
* approval actions include: sending an email alert, updating a field on a record, creating a task, sending an outbound message.
* Approval steps assign approval requests to various users and define the chain of approval for a particular approval process.  


#### Apex Triggers
https://trailhead.salesforce.com/content/learn/modules/apex_triggers/apex_triggers_intro?trailmix_creator_id=strailhead&trailmix_slug=prepare-for-your-salesforce-advanced-administrator-credential

* Enables you to perform custom actions before or after events to records in Salesforce.
* You can use triggers to do anything you can do in Apex, including executing SOQL and DML or calling custom Apex methods.

```
    trigger TriggerName on ObjectName (trigger_events) {
        code_block
    }
```
* To execute a trigger before or after insert, update, delete, and undelete operations, specify multiple trigger events in a comma-separated list
	* before insert
	* before update
	* before delete
	* after insert
	* after update
	* after delete
	* after undelete

* Two types of triggers:
	* **before triggers**
	* **after triggers** 

##### Context variables:
* Use context variables to access the records that caused the trigger to fire
	* Trigger.New: contains all the records that were inserted in insert or update triggers
	* Trigger.Old: provides the old version of sObk=jects before they were updated in update triggers or list of deleted sObject in delete triggers
	* **Triggers can fire when one record is inserted, or when many records are inserted in bulk via API or Apex so the context variables such as Trigger.New can contain one or multiple records.**

**Calling a Class Method from a trigger:**
* Calling methods of other classes enables code reuse, reduces the size of your triggers, and improves maintenance of your Apex code. It also allows you to use object-oriented programming

**Adding Related Records:**
* Triggers are often used to access and manage records related to the records in the trigger context—the records that caused this trigger to fire.
* e.g.
```
trigger AddRelatedRecord on Account(after insert, after update) {
    List<Opportunity> oppList = new List<Opportunity>();
    
    // Get the related opportunities for the accounts in this trigger
    Map<Id,Account> acctsWithOpps = new Map<Id,Account>(
        [SELECT Id,(SELECT Id FROM Opportunities) FROM Account WHERE Id IN :Trigger.New]);
    
    // Add an opportunity for each account if it doesn't already have one.
    // Iterate through each account.
    for(Account a : Trigger.New) {
        System.debug('acctsWithOpps.get(a.Id).Opportunities.size()=' + acctsWithOpps.get(a.Id).Opportunities.size());
        // Check if the account already has a related opportunity.
        if (acctsWithOpps.get(a.Id).Opportunities.size() == 0) {
            // If it doesn't, add a default opportunity
            oppList.add(new Opportunity(Name=a.Name + ' Opportunity',
                                       StageName='Prospecting',
                                       CloseDate=System.today().addMonths(1),
                                       AccountId=a.Id));
        }           
    }
    if (oppList.size() > 0) {
        insert oppList;
    }
}
```

#### Trigger Exceptions
* **addError()**: call this method on the sObject to prevent saving records when certain conditions are met.
	* addError() method throws a fatal error inside a trigger
	* causes the entire set of operations to roll back, except when a bulk DML is called with partial success.
	* If a DML statement in Apex spawned the trigger, any error rolls back the entire operation. However, the runtime engine still processes every record in the operation to compile a comprehensive list of errors.
	* If a bulk DML call in the Lightning Platform API spawned the trigger, the runtime engine sets the bad records aside. The runtime engine then attempts a partial save of the records that did not generate errors.

```
trigger AccountDeletion on Account (before delete) {
   
    // Prevent the deletion of accounts if they have related opportunities.
    for (Account a : [SELECT Id FROM Account
                     WHERE Id IN (SELECT AccountId FROM Opportunity) AND
                     Id IN :Trigger.old]) {
        Trigger.oldMap.get(a.Id).addError(
            'Cannot delete account with related opportunities.');
    }
    
}
```

#### Triggers and Callouts:
* make calls to and integrate Apex code with external Web Services. Referred to as **Callouts**
* **when making a callout from a trigger, the callout must be done asynchronously so that the trigger process doesn't block you from working while waiting for the external service's response**
* the asynchrom=nous callout is made in a background process, and the response is received when the external service returns it

**Making a callout from a trigger:**
* call a class method that executes asynchronously - **future method** annotated with @future(callout=true)

```
public class CalloutClass {
    @future(callout=true)
    public static void makeCallout() {
        HttpRequest request = new HttpRequest();
        // Set the endpoint URL.
        String endpoint = 'http://yourHost/yourService';
        request.setEndPoint(endpoint);
        // Set the HTTP verb to GET.
        request.setMethod('GET');
        // Send the HTTP request and get the response.
        HttpResponse response = new HTTP().send(request);
    }
}
```
```
trigger CalloutTrigger on Account (before insert, before update) {
    CalloutClass.makeCallout();
}
```

#### Bulk trigger Design Patterns
* use bulk design patterns for processing records in triggers for better performance, use of less server resources, less likely to exceed platform limits and process large number of records.
* 
