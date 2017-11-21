### Process Automation

* Process Builder has all the functionalities of a workflow except send outbound messages without code. This limitation can be mitigated by calling Apex code from a process. It also supports multiple if/then statements.
* If a process is too complicated for the Process Builder or requires more advanced functionality, create a flow by using visual workflow.
* Visual workflow can be used for complex branching logic such as checking whether a case is escalated and then check the account's region and route the case accordingly.
* Visual workflow can also be used to sort through, iterate over and operate on several records - e.g after an opportunity is closed and won, calculate the opportunity's discount. then apply that discount to all the related opportunity products.
* Visual workflow can also be used to build a wizard to collect information from a rep, walk the rep through a call script, and create a case that's assigned to the right person.

* Create approval processes to automate your organizations processes fro approving records.

**Workflow and approval process can update only the record or its parent but process builder can update any related record whereas visual workflow can update any record**
**Except Approval processes all the other process automation support time based actions**
**Only visual workflow supports user interaction**
**Visual workflow and process builder can create any object record whereas workflow and approval process can create only task records.**
**Process builder can invoke processes.**
**Only visual workflow can delete records**
**Process builder and visual workflow can post to chatter**
**Visual workflow can send emails but process builder, approval processes and workflows can send email alerts only.**
