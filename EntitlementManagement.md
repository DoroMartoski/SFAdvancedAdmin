* Entitlements management defines, enforces and track service levels as part of your support management process. Tells your support team what service level each customer is entitled to based on their SLA.
* **Entitlements: helps support agents determine whether a customer is eligible for support.**
* Entitlement process: let's an admin design timelines that include all the steps that your support team must complete to resolve
 support records like cases or work orders.
 * Service contracts: lets you represent different kinds of customer support agreements like warranties, subscriptions, 
 or maintenance. **Service contracts can be restricted to cover specific products.**
 * Entitlement management is highly customizable and you have full control of which features to use and how to set them up to reflect your customer support model.
 * **Entitlement: a unit of customer support in Salesforce such as phone support or web support.**
  * Entitlements can be associated with accounts, assets, contacts and service contracts.
  * Entitlement contacts: contacts who are entitled to customer support. Contacts related list on an entitlement shows which contacts are eligible for that entitlement.
      - Contacts on an account don't automatically inherit the account's entitlements. Seperate entitlements can be created for each contact on an account.
      - Apex triggers can be created to to automatically assign an entitlement to a contact when a contact is created.
      - **Entitlement contacts do not have page layouts, search layouts, buttons, links or record types**
      - Associating a contact with an entitlement doesn't share the entitlement record with the contact or the related community user.
* Entitlement template - predefined terms of customer support that can be quickly added to products in Salesforce.
* Contract line item - specific products covered by a service contract. Can be viewed in the conline items related list on Service Contract. Contract line items can only be used if the org uses products.

* **Add milestone tracker on case feed on the case page layout to let users see a milestone countdown on cases.**
* **Add Entitlement templates related list to the product page layout.**
* **Add the Entitlement related list to the account and asset page layouts.**

