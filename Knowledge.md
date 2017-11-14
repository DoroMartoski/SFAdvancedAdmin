**Salesforce knowledge lets you create and manage your company information and securely share it when and where it is needed**
* Knowledge base is built from documents of information called knowledge articles.
* Knowledge articles are published to channels => Internal APp, customer and partner communities or public websites
* User must have the "knowledge user" checkbox checked for him/her to be able to use knowledge.


### Data Categories
* SF knowledge uses data categories to classify articles.
* Data categories are organized under category group.
* Authors can assign up to 8 different data categories from one category group.
* Create data categories and sub categories and activate the data category for use in knowledge.
* Choose default category visibility.
* By default all category groups created are assigned to Salesforce knowledge but only the active category appear when creating an article.

### Knowledge Article types
* Knowledge article type are similar to record types in the way they function.
* Each knowledge article type has its own page layout and can have new fields created on it and added to its layout - this provide the format and structure to control how an article is displayed for each audience, known as channel.
* You can create workflow rules and approval processes to help your organization track and manage article creation and publication.
* knowledge actions are templates that link a workflow action to an article type
* You can add validation rule on article type to ensure article content is compliant with the company standards.
* You can track history of certain fields or set tracking for the article type and track the full history of an article and its versions. **Article events are tracked for up to 18 months**

**You can import articles into salesforce via the article import wizard.**

* **Define which case fields map to which data category groups and set a default data category for cases that have no value for the mapped fields. For example, you can map a products custom case field with a products data category group to filter the articles for the customer's products.**
**Use file field type or rich text field if you would like to add attachments to a knowledge article. Maximum of 5 file fields per article type (file field cannot be converted into any other field type).**
**Maximum of 25MB of attachment/file**
**Maximum of 50,000 articles and 100 article types**
**Maximum of 5 data category groups with 3 active at a time and maximum of 5 levels in a data category group hierarchy**
**100 categories in a data category group.**

**Filter articles by defining which case **

**You can enable knowledge one with a permission set or on profiles => this replaces the articles tab with a knowledge tab.**
**You can use an apex class for pre-populating fields on draft articles when support agents are able to create Salesforce knowledge articles while closing a case.**

**Field level security lets admins restrict access to specific fields on detail and edit pages.**
**If using both article type page layout and field level security to define field visibility, the most restrictive field access setting always applies**
**You can assign a page layout based on a profile.**

### Send articles content in email.

**With knowledge one, users can send an article's content through an email rather than sending the URL.**
* Case Page layout => Feed View => check "Enable attaching articles inline" and then save.
* Then under knowledge article type => communication channel mapping => select emails from list of available channels => select the available fields => save.
**10 mb attachment limit on case feed attachment**
**If rich text is not enabled on your case feed layout for the article type, only article text is embedded into the email and the action changes to Email article text only**

**Agents can insert site or community urls for articles into the case feed via the email, community or social publishers*
**To post Site or community urls for articles into the case feed you must have the knowledge sidebar enabled in the service console and either a force.com site or community setup**


