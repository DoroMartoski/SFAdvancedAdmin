## Objects and Applications

#### Consideration for Relationships
* Each custom object can have up to **2 master-detail relationships**
* Each custom object **can have many lookup relationships**
* You can convert a master-detail relationship to a look-up relationship as long as no roll-up summary fields exist on the master object.
* ** when you convert a master-detail to lookup, the ord-wide default for detail side of a master-detail relationship becomes public read/write**
* You can **convert lookup relationship to master-detail relationship if the lookup field in all the records contains a value**
* **Lookup relationship can't be changed to a master-detail relationship if the org-wide default of the child object access level in the relationship is "Controlled by Parent"**
* 
