### Leads & Opportunities

**Leads**: people and companies identifies as potential customers
Advantages of Leads:
* better tracking and reporting on and target marketing campaigns to prospective customers

Leads entry: 
* direct entry into Salesforce including through file import
* Web-to-Lead form that collects leads from your business website.

Use Leads workspace to track interactions with leads, check campaign history and plan future activities.

After qualifying a lead, you can convert the lead into an opportunity.
* When you convert a lead, Salesforce uses the information stored in the lead record to create a business account, a contact, and an opportunity.
* If you’ve enabled person accounts and the lead record didn’t include a company name, the lead is converted into a person account and an opportunity.

**Opportunities**: deals in progress.
opportunities can be created for existing accounts or by converting a qualified lead.
Progress opportunities through stages such as: Prospecting, Proposal/Price Quote, Negotiation/Review, Closed/Won, Closed/Lost.
Each opportunity stage is associated with a Probability of winning the deal.
You can set up separate sales processes for each **type of sale** that reps make.

**Contact Roles on Opportunities**:
* tells you which contacts you’re dealing with and how each contact is related to the opportunity. 
* You can also use contact roles to link contacts from other accounts to the opportunity.

**Opportunity Splits**:
* whereas account team members can be expected to form a long-term relationship with a customer, an opportunity team is a temporary group.
* Opportunity team members have special visibility into an opportunity, such as related Chatter posts
* If you’re the opportunity owner or above the owner in the role hierarchy, you can add and adjust splits on an opportunity.
* There are two kinds of splits. 
  * **Revenue splits**: **for crediting team members who are directly responsible for the revenue on an opportunity**. Revenue splits always total 100% of the opportunity amount.
  * **Overlay Split**: An overlay split gives you a way to credit supporting team members. It can total any percentage of the opportunity amount, including a percentage over 100%, and it doesn’t count toward the revenue split on the same opportunity.
* **Team members working on an opportunity can roll their individual sales credits into forecasts and into quota and pipeline reports for the entire team.** 
* To generate reports, use one of the following report types.
  * Split Opportunities
  * Split Opportunities with Products
  * Split Opportunities with Products and Schedules

**Path**: Path shows you at a glance where the record is in your sales process.
* Key Fields highlight the information you need the most when you open a record, so you don’t have to switch tabs or scroll around to find critical data.
* Guidance for Success (provided at each step on a Path) can help you come up to speed quickly and make sure you don’t miss any critical activities.
* Use the Path to update the record’s status by clicking Mark Status as Complete to move the record to the next step on the path

* Kanban view: By default, the Kanban view for opportunities organizes your records into columns by Stage, and shows a summary of the deals in each column based on the sum of the Amounts of each column’s opportunities.
  * you can change both what columns records are organized into, and what number is used in the summary.
  * you can view the Kanban view on almost any list view.
  * You can delete a record or change the opportunity’s owner.
  * click the down arrow on a Kanban card, and select Edit
  * Click Show charts (1) and you see a chart or graph that summarizes the data in your list view in different ways
  * Filter the Kanban View
  
  
 Quotes: 
 * After customer accepts a specific quote, sync the quote so that its line items appear as the opportunity’s products. This removes risk of having discrepancies between the line items in the quote and the products in the opportunity. 

Quote template: use Create PDF on quote to generate a PDF copy of the quote.

**Customer Contracts**:
* Use field level security and Field Accessibility to provide access to users profiles that needs access to Contracts.

### Territory Management:
* This is an account sharing system that grants access to accounts based on the characteristics of the accounts.
* Allows a company to structure SF data and users the same way you would structure your sales territories.
* Original Territory Management is available only with **Customizable Forecasts** but not with **colaborative forecast** where as **Enterprise Territory Management** can be enabled even with **Collaborative Forecasts** but the two are not currently integrated to work together in Salesforce.
* For orgs with private sharing models, territory management can be used to grant account and user access based on criteria such as postal code, a custom field or any other relevant field.
* Account sharing and ownership rules remain valid even with territory management.

### Benefits of territory management
* Ability to use account criteria to expand the private sharing model.
* Support for complex and frequently changed sales organization models.
* Support for transferring users between terriotories with the option of retaining opportunities
* Multiple forecasts per user based on territory membership.
* Territory based reports.
**Territory Management only affect accounts and the standard objects that have a master-detail relationship with accounts. E.g opportunities but leads are not affected by territory management**

**Territory is a flexible collection of accounts and users where the users have at least a read only access to the account regardless of who owns the accounts(s)**
* Configuring territory settings can give users read, read/write and ownership access to the accounts in that territory.
* Accounts and users can exist in multiple territories. Accounts can be manually added or through account assignment rules.
* Territory management can also be used to control user access to opportunities and cases associated with account in a particular territory regardless of who owns the account recors.

**Territories exist in hierarchies which can be nested to as many levels as needed. E.g NA => Canada and USA => Eastern, Western, Northern, SOuthern etc**
* Territory hierarchies do not have to be geography based - they can be defined however suits the organization.

### Territory management and forecasting
* The territory hierarchy becomes the forecast hierarchy.
* The forecast data is derived from the opportunities that are associated with the accounts in the territory.
* Users have a different forecast for the opportunities they have for each account territory they are assigned to.
* Field security and page layout determine which territory fields are visible and editable.

### Territory fields:
* Account acces(view only, view and edit, view, edit, transfer and delete), case access(no access, view only, view and edit), confine opportunity assignment **(prevents the opportunities in current territory from being moved from that territory and its child territories)** , contact access(no access, view only, view only and edit), forecast manager **(the user to whom the forecasts from child and lower-level territories roll-up to)** - modifiable by clicking change on Territory detail, label, opportunity access(no access, view only, view only and edit), Parent Territory, sharing group (read only and displays only on the territory detail page). **For every territory, 2 sharing groups are created - one for the territory and another for the territory and its children**. 
**Customizable forecasting must be enabled before territory management can be turned on**
* Your forecast hierarchy is automatically derived from your role hierarchy when customizable forecast is enabled.
* set default account, opportunity, contact and case access. ALso set if forecast managers can administer territories below them in the hierarchy.
### Territory related settings
* Add territory and Exclude from Territory Assignment rules fields to account page layout.
* Add Territory field to the opportunity page layout
* Give users the **Manage territories** permission to be able to administer territory hierarchies. **Users that had the “Customize Application” permission before you enabled territory management are automatically given the “Manage Territories” permission.**
**Territories can have unlimited number of users and users can be in unlimited number of territories.**
*  If “Allow Forecasting” is disabled for a user who is deactivated, the user is removed from any territories he or she is assigned to
**Rollup amounts are kept current for deactivated Salesforce users**
**A deactivated salesforce user can continue to own opportunities and belong to territories**
**For deactivated salesforce users their opportunity forecast overrides, adjusted  total overrides and manager's choice overrides are frozen**
* Users with Active in Territory checked on the territory detail page have open opportunities, closed opportunities, or no
opportunities at all in that territory. Users with Active in Territory deselected have been transferred out of or removed
from the territory, but retain ownership of opportunities in the old territory.
* To view the territories to which you belong, view the Territories related list on your personal information page

**A territory can have only one forecast manager to whom the forecasts from child and lower level territories roll up to.**
**If a territory has no forecast manager, then there is no forecast for that territory.**
**You can enable forecast managers to act as delegated administrator for the territories below them.**

### FAQS
* Accounts, opportunities and users have territory fields. Accounts and user can have multiple territories but an opportunity can only be assigned to one territory.
* Territory hierarchy determines forecasts and affects account and opportunity reports.
* Manually assigned accounts to territories are not evaluated when running account assignment rules. They remain in the territory until they are manually removed.

### Account Assignment rules evaluation
* Account is created using the Salesforce user interface, API 20.0 or through a client
* Account is imported through an import wizard.
* An account is created by the conversion of a lead.
* An account is editted and saved if the *select by default* checkbox is selected for the "Evaluate this account against territory rules on save" checkbox under the layout properties.
* An account is edited and saved via the force.com API
* Run rules is clicked on the territory detail page as long as the "Exclude from territory assignment rules" checkbox on the account is deselected.
* Save and run rules is clicked on the manage account assignment rules page for a territory.
* Duplicate accounts are merged.

### Opportunity territory assignment
* Creating a new opportunity
* Running account assignment rules

### Opportunity not assigned to territories when
* An account is removed from a territory and not reassigned to a new one in the same operation => accounts' opportunities no longer belong to any territories.
* An account is reassigned to multiple territories in one operation => the account's opportunities from the original territory no longer belong to any territories, unless the "confine opportunity assignment" checkbox is checked.

### when are opportunity territories unchanged
**Manually assigning the opportunity's account to a territory**
**Changing which account is associated with the opportunity**
**Changing the account's territory as a result of account assignment rules if the opportunity and its account are in different territories**
**Transferring the opportunity to a new owner**

**If an opportunity owner does not belong to the opportunity territory, the owner gets automatically assigned to the opportunity territory with "Active in Territory" unchecked in the Assigned Users list of the territory**







**Enterprise Territorry Management**:
* Territory: organize groups of accounts and the sales reps who work with them.
* Territory Type: Helps you group territories according to a common denominator such as core reps versus overlay, or named accounts versus geographic territories. Every territory you create has a territory type.
* Territory type priority: Helps you choose the appropriate territory type for territories you create or edit
* Territory model: Represents a complete territory management system for your company.
* Territory hierarchy: Shows a model’s territory structure and serves as its main interaction point. You start from the hierarchy to create, edit, and delete territories; run assignment rules for territories, and navigate to territory detail pages for more information.
* Territory model state: Indicates whether a territory is in the planning stage, in active use, or archived. You can have only one active territory model at a time, but you can create and maintain multiple models in planning or archived state to use for additional modeling or reference. Territory forecasts are based on your active territory model.











