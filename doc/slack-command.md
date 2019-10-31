# Command query syntax 

/cv skill \<skill\> experience \<skill\> location \<city or region\> for \<customer\>  sector \<industry sector\> last \<n years\>

All clauses are optional, but at least one must be specified.  Location is used as a filter, and must be specified in conjuction with another clause. 

## Examples 

/cv skill aws location Bergen for Ambita sector offentlig last 1 

/cv skill neo4j  

/cv skill "Data Warehouse" sector Telecom 

## command metadata 

/cv catalog skill|location|customer|sector \<filter\>

Lists available items in each metadata category, optionally filter results 

## metadata examples 

/cv catalog location 

returns a list of all available locations, such as Norge, Sverige, Oslo, Bergen, Trondheim etc.  Default is Norge 

/cv catalog customer Hydro

returns a list of all available customers containing the string Hydro in the customer name.
