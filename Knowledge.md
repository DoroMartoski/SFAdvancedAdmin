**Salesforce knowledge lets you create and manage your company information and securely share it when and where it is needed**
* Knowledge base is built from documents of information called knowledge articles.
* Knowledge articles are published to channels => Internal APp, customer and partner communities or public websites
* User must have the "knowledge user" checkbox checked for him/her to be able to use knowledge.


### Data Categories
* SF knowledge uses data categories to classify articles.
* Data categories are organized in category group.
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

**Agents can insert site or community urls for articles into the case feed via the email, community or social publishers**
**To post Site or community urls for articles into the case feed you must have the knowledge sidebar enabled in the service console and either a force.com site or community setup**

* Article types require a template for each channel - the standard article type templates - tab and table of contents specify how the sections in the article-type layout appear in the published article.
* Custom templates are not associated with the article-type layout.
* Any articles associated with a deleted article type are automatically removed from all channels, including draft, published and archived articles.

* Use public groups and article actions to assign users to specific tasks related to articles - eg ability to do things like publish articles with a specified validation status.
* knowledge articles are templates that link a workflow action to an article type. They can be used to link article types to specific workflow article actions.

#### Data Category Mapping
* Map case fields to data categories to filter for articles assigned to those data categories. E.g cases with a field for which product they are about can be mapped to the data category of that product. This helps make suggested articles more relevant when solving cases.
* filtering articles based on case information is only supported in text and picklist fields.
* A category group can only be used once in a data category

### Article search
* Search highlights and snippets, synonyms, promoted terms, topics and keywords from cases can be enabled to improve article search.
**Search highlights and snippets are generated only from email, long text area, rich text area, and text area**
**Create synonyms and synonym groups so words or phrases are treated as equivalents in searches. Up to 10,000 synonym groups can be created for an org**
* You can add promoted search on the promoted search related list on the article.
* You can classify and search articles by assigning topics. Topics can be added from the article view and detail pages.
* Suggested topics are terms extracted from the article and hence are more concrete and precise than data category assignment.
* Topics are only supported in English and can be used to index the article.
**Articles must be in published status in order to manage their promoted terms**

### Knowledge one widget
* Lets you attach a published SF knowledge article to the case in one click
* Share an article as a URL, if it is shared on a public channel
* Email an article as a pdf if it is shared on a public channel
* Create and manage articles.
* Make adjustments based on window width.
* Case layout => custom console component => knowledge one in sidebar drop down. This will configure the knowledge one widget for consoles.

### Smart links
**You can smart link from one article to another using the Link Article dialog in the rich text editor or manually entering the URL in the rich text editor.**
