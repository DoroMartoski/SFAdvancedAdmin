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





