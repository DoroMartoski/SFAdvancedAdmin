Security & Access topics:
* Picklist Administration
* Enhanced Transaction Security
* Sessions based permission set & security
* Company wide org settings
* Administer Account teams
* What is MFA and how does it work
* Configure Enterprise Territory Management permissions and Access


## Picklist Administration
Picklists help to simplify data entry and standardize values. Picklists are not ideal for long entries or 
unique values. 
2 parts of Picklists:
1. The field: defines the type of picklist. 
2. The value set: defines the choices a user sees, their order and the default value amongst other things.

**3 Types of picklists:**
    * Standard
    * Custom
    * Custom Multi-select
    
**Picklist values can be:**
* Restricted
* Dependent or Controlling

**Picklist values can be defined in 3 ways:**
* Set individual values when you create the picklist. SPecific to a single picklist field
* Use the built-in set of values for the standard picklist fields that come with your org.
* Create a global value set. A global values set is a custom set of values you create to share with 
more than one picklist field.

### Standard picklists:
* these may share a standard value set so any change made on the value set will appear on all objects using that value set.

### Custom Picklists
You have the option to create a picklist or multi-select picklist. 
Selected values on a Multi-select picklist appear separated by semicolon

**Notes**:
* Global picklist value set are always restricted picklists; preserves data integrity.
* For custom picklists fields that use global picklist value set, you can change from a single-select to 
multi-select picklist & vice-versa. But can't chsnge the picklist to a different field type such a checkbox or text
* You can't undo a custom picklist field's association with a global value set. 
* Reports referencing multi-select picklists should use contains or includes to collect all results that contain 
more than one value.
* In report results, or dashboards, multi-select picklist selections are grouped independently. For example: One record has a, b, and c values. Another record has b and c values. And another record has only c selected. You’ll get three different groupings: one for a;b;c, one for b;c and another for c.
* Only specific functions can reference multi-select picklists in formulas.
* **Standard picklist cannot be a dependent picklist, be restricted, multi-select or use a formula for a default value.**

### Restricted Picklists
Keeps users from adding new values.

**Dependent Picklists**
Guide users, save UI space, and further improve data integrity with a dependent picklist
* Filters values for one picklist based on a selection from another picklist or a checkbox

**Note**
* If you replace a picklist value with blank, existing records will not display any value anymore.
* Custom picklist fields can be either controlling or dependent fields
* Standard picklist field can be controlling fields but not dependent fields.
* Multi-select picklists fields can be dependent but not controlling fields.
* You can set default values for controlling fields but not for dependent pickists

**Use formulas for Default Picklist Values**
**When you change a multi-select picklist to a picklist that doesn’t allow multi-selection, Salesforce clears the values for that field on existing records. This makes sense, right? Because the field now only allows one value.**

### Share Values with Global Value Sets
Global value sets:
* lets you share the same picklist values with more than one picklist field.
* They are always restricted and can not be converted to unrestricted.
* You can define a default value for a Global value set
* **Individual fields that use the global value set can have their own default values, independent of the global value set’s default. This extends to formula default values, too.**
* **If you find that a particular set of values for one field makes a good set for another field, you can promote the existing value set to a global value set.** 


### Enhanced Transaction Security
* A salesforce feature that monitors Salesforce events in real time to spot potential troubles based on rules you create.
* Create policies that consists of events, notifications, and actions

* **Event**: any action in Salesforce including user clicks, record state changes and measuring values. Immutable and timestamped
* Pick a transaction or event to monitor and then choose actions that are triggered when the event occurs.
* The rules & actions you create for a Transaction Security is referred to as policies.
* Transaction security policies can be extended with Apex for customized protection.
* **To use Transaction Security, you have to first purchase a Salesforce Shield or Salesforce Shield Event Monitoring add-on subscription.**

Examples of available event types for Transaction Security policies
* API Event for monitoring and protecting all API queries. Prevents unauthroized data exports
* List View Event for access to list views. Tracks user's access to list views from both UI and API queries.
* Login Event monitoring. Blocks logins from untrusted locations, unsupported browsers and specific device types.
* Report Event for Report views and exports. Blocks or requires multi-factor authentication for access to sensitive info
 or notifies when reports are run or exported.
 
 **Available Actions for a policy**:
 * Block the operation
 * Require a higher level of assurance using multi-factor authentication
 * Do nothing (can be useful for testing)
 * Opt-in for policy notifications sent via Email, In-app notification to the Salesforce app or Both email and n-app notifications.

### Creating transaction Security Policy through Condition Builder

### Create a Transaction Security Policy Using Apex

________________________________________________________________________________________________________________________
*************************************************************************************************************************

### Session-based Permission Sets
* Limit functional access for select permissions in a permission set to an activated session.
* Select **Session Activation Required checkbox** when creating permission set.

**Activating Session-based Permissions Sets**
* Session based permission sets can be activated declaratively or programmatically.
* **The PermissionSet object in the Soap API contains a field called HasActivationRequired**, 
* a boolean that indicates whether the permission set requires an associated active session (true) or not (false). 
* Insert a record into the SessionPermSetActivation object with the combination of session ID and permission set to achieve the activation

**Activating Session-based Permissions Sets Without Code**
* Use a flow to activate Session-based Permission sets

#### Create Easy Access to the Activation Flow
* Couple of options
      1. Create a simple Visualforce markup and a custom tab to run your flow
      2. Use a Lightning app page
            * From Setup, enter Builder in the Quick Find box, then select Lightning App Builder.
            * Click New and select App Page then click Next.
            * Name your page Activate Temp Access Flow and click Next.
            * Select One Region and click Finish.
            * Drag the Flow component onto your canvas, and for Flow, select Activate Contracts Access. (It may already be                   selected.)
            * Click Save and select Activate.
            * On the Activation window, select Lightning Experience and for Lightning Apps add Sales.
            * Save your work and click Back to exit Lightning App Builder.

******************************************************************************************************************************************************************************************************************************************************
#### Regional Settings
* Company settings are the collection of information about your Salesforce org. Snapshot of your company's identity.

**Locale Settings**: determine the display formats for date and time, user names, addresses, commas and periods in numbers.
* The admin sets the default locale but users can set a personal locale if based in a different location.

**Currencies**
* As the admin for your organization, you set that “corporate currency,” which reflects the currency of your corporate HQ.
* You also maintain the list of active currencies and their conversion rates relative to the corporate currency.
* once a multicurrency setup is enabled, it can’t be disabled
* standard conversion rate control is straightforward but it impacts current and closed deals.
* For accurate historical record keeping, it’s best to avoid impacting the value of completed business. 
* Advanced Currency Management for currency fields on opportunities and opportunity products lets you manage exchange rate start dates.
* When advanced currency management is enabled, Visualforce <apex:inputField> and <apex:outputField> components cannot display currency fields.
* personal currency is used as the default currency in quotas, forecasts (depending on which forecasting version they use—see  the  resources  section  for  more help), opportunities, quotes, and reports.

___________________________________________________________________________________________________________________________
***********************************************************************************************************************
#### Account Teams:
* Enable account teams so that your reps can create and maintain teams for their accounts.
* Every account team member has a role on an account, such as account manager or sales rep. To track the roles that team members fill in your company, customize account team roles
* Use the **Mass Reassign Account Teams** from Setup to Add, remove, or replace multiple account team members at a time. Update member roles and access.
* When editing team members, users see custom fields, even if you don’t add the fields to the Add Account Team Members multiline page layout
* If you delete a custom field, filters based on the custom field are also deleted. The results of assignment or escalation rules that rely on the custom field’s data can change.
* If you include a default value for a custom field, the field appears blank to Lightning Experience users while they’re adding account team members. If users don’t enter a value, the default value appears on the record after they save.
* Mass Reassign Account Teams doesn’t support custom picklists.
* You can’t create a lookup from an object, such as an account, to an account team member
* The Account Team related list is sorted by Team Member Name. The sort order can’t be customized, even if you specify the sort order in the Account Team Member page layout. A user can sort the related list by any other column, but when the page is refreshed, sorting reverts to the Team Member Name column.
* If you set the org-wide default for contacts to Controlled by Parent, users can’t see or edit the Contact Access field.
* A deleted account team member record is not moved to the Recycle Bin, and it can’t be undeleted unless the record was cascade-deleted when deleting a related account.
* **Validation rules, flows, and Apex triggers are applied when Lightning Experience users** add their default team to an account using the Add action on the related list. However, they’re not applied when Lightning Experience users select the personal settings option to add their default team to accounts automatically.
* Validation rules and Apex triggers are bypassed when **Salesforce Classic users** add default account teams via any method.
* When an account team member is removed during an account ownership change, Apex triggers are bypassed
* A team member’s level of access to an account. The access level can be Read/Write or Read Only, but it can’t be less than the default account sharing access.
* The Contact Access field is unavailable when the organization-wide default for contacts is set to Controlled by Parent.

_____________________________________________________________________________________________________________________________
*****************************************************************************************************************************
#### Salesforce Multi-Factor Authentication
* Effective way to increase protection for user accounts against threats such as phishing, credential stuffing and account takeovers
* MFA requires two or more factors, providing options for many combinations of authentication mechanisms. 2FA, on the other hand, is a subset of MFA that requires two factors only.
* Beginning February 1, 2022, Salesforce will require customers to use MFA in order to access Salesforce products.
* MFA requirement applies to all users who access a Salesforce product’s user interface, whether by logging in directly or via SSO
* MFA is not required for your company's Experience Cloud sites, employee communities, help portals, or e-commerce sites/storefronts
* All Salesforce mobile and desktop apps that are accessed via user interface logins are included in the MFA requirement
* Risk-based authentication, also known as adaptive authentication or Continuous Adaptive Risk and Trust Assessment (CARTA), is an authentication system that continually analyzes the risk associated with a user by monitoring multiple signals coming from the user, the user’s device, and how and when the user accesses services. If the level of risk in a given situation warrants, the identity provider or authentication service automatically requires the user to satisfy additional security challenges.
* MFA requires users to supply a strong verification method every time they log in. Email and SMS text messages aren't allowed for MFA logins because of their inherent susceptibility to attack by bad actors, so these options aren't allowed for MFA logins.
* If a user loses or forgets their mobile device or security key, Salesforce admins can generate a temporary verification code that allows the user to log in to their account. The code can be used multiple times until it expires
* There's only one scenario where an admin needs to coordinate with a user to have them respond to an MFA challenge: when the user's profile requires a High Assurance session at login, but the admin is logged in with a standard security session level. To avoid this situation, admins should always log in using MFA, which automatically results in a High Assurance session.

**Verification methods for MFA**
* Salesforce Authenticator mobile app (available on the App Store® or Google Play™)
* Time-based one-time passcode (TOTP) authenticator apps, like Google Authenticator™, Microsoft Authenticator™, or Authy™
* Security keys that support WebAuthn or U2F, such as Yubico’s YubiKey™ or Google’s Titan™ Security Key
* Built-in authenticators, such as Touch ID®, Face ID®, or Windows Hello™

**Non-accepted verification methods:
* Email messages
* Text messages
* Phone calls
* Security questions: users can satisfy the MFA login requirement by using physical security keys
* Used on their own, trusted devices, trusted networks, or VPN aren't adequate verification methods for the MFA requirement.
**

______________________________________________________________________________________________________________________________
******************************************************************************************************************************
#### Configure Enterprise Territory Management Permissions and Access for Salesforce Admins and Users
**Profiles** 
* define how users access objects and data, and what they can do within the application. When you create users, you assign a profile to each one.
* View and Edit Tab Settings in Permission Sets and Profiles: Tab settings specify whether a tab appears in the All Tabs page or is visible in a tab set
* View and Edit Assigned Apps in Profiles: Assigned app settings specify the apps that users can select in the Lightning Platform app menu
* Enable Custom Permissions in Profiles: Custom permissions give you a way to provide access to custom processes or apps
* Edit Session Settings in Profiles: You can control session settings on a user profile basis. If you don’t configure the profile session settings, the org’s session settings apply to users of the profile. When set, the profile settings override the org-wide settings.
* View and Edit Password Policies in Profiles: To ensure that the appropriate level of password security is used for your organization, specify password requirements with Password Policies settings for users assigned to a profile.

**Permission Sets**
* A permission set is a collection of settings and permissions that give users access to various tools and functions. Permission sets extend users’ functional access without changing their profiles.
* Create permission sets to grant access among logical groupings of users, regardless of their primary job function.
