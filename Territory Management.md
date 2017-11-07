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
* Account access, case access, confine opportunity assignment, contact access, forecast manager, label, opportunity access, 


