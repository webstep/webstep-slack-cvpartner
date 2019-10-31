# Command query syntax 

/cv skill \<skill\> experience \<skill\> location \<city or region\> for \<customer\>  sector \<industry sector\> years \<n years\>

All clauses are optional, but at least one must be specified.  

* skill - _technology, practice, system, knowledge_
* experience _skill learned in project deployment_
* location _office affiliation of consultant_
* customer _customer where skill was aquired_ 
* sector _Industry sector of customer_
* years _number of years with skill experience_

skill and experience cannot be combined. Choose one.

location cannot be specified on its own, it acts as a filter 

years cannot be specified on its own, it acts as a filter 

## Examples 

/cv skill aws location Bergen for Ambita sector offentlig experience 5 

/cv experience neo4j  

/cv skill "Data Warehouse" sector Telecom 

## command metadata 

/cv catalog skill|location|customer|sector \<filter\>

Lists available items in each metadata category, optionally filter results 

## metadata examples 

/cv catalog location 

returns a list of all available locations, such as Norge, Sverige, Oslo, Bergen, Trondheim etc.  Default is Norge 

/cv catalog customer Hydro

returns a list of all available customers containing the string Hydro in the customer name.
