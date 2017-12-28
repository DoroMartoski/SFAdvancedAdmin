### Salesforce Security

**There are several ways security can be maintained in Salesforce**
* Two-factor authentication
* Restrict IP addresses
* Data encryption


### Field Tracking
* Up to 20 fields can be tracked.
* Field history related list can be added to the layout of an object that has the field history enabled.
* On long text field only the user and date information are tracked but on other fields the previous value and new values are also tracked along with the user who made the change and the date/time.
* 


### Debugging
* Use debug logs to track events that occur in your SF org.
* Debug logs are generated when you have active user-based trace flags, when you run apex tests and when executed code or API requests include debugging parameters or headers.

**Debug logs can contain informationn on:**
* Database changes
* HTTP callouts
* Apex errors
* Resources used by Apex
* Automated workflow processes such as workflow rules, assignment rules, approval processes and validation rules.

**The system generates a debug log every time a transaction that is included in the defined filter criteria is executed such transactions can include:**
* Salesforce user interface
* API
* executeanonymous calls
* Web services
* Email services

**The filter criteria set for the user, developer consoles or the API header determine what is included in the debug log.**
**Use the debug log to:**
* As a developer Validate an application's behavior
* As an admin to troubleshoot when a user reports difficulty by setting up a trace flag on the user and asking the user to step through the problematic transactions and then use the debug log to view the system details.

* Debug logs must be 2 MB or smaller.
* Debug logs are retained for 7 days
* If Debug logs of more than 250MB are generated within a 15 minute window, your trace flags are disabled and SF sends an email to the users who last modified the trace flags informing them that they can re-enable the trace flags in 15 minutes.
