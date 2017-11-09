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





