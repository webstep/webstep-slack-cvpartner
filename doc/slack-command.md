# Command query syntax 

/cv with \<skill\> location \<city or region\> for \<customer\>  sector \<industry sector\> last \<n years\>

In this example the 'with' clause is mandatory, all other clauses are optional.

## Examples 

/cv with aws location Bergen for Ambita sector offentlig last 1 

/cv with neo4j  

/cv with "Data Warehouse" sector telecom 


## command metadata 

/cv catalog \<skill\>|\<location\>|\<customer\>|\<sector\>

Lists available items in each metadata category 

## metadata examples 

/cv catalog location 

returns a list of all available locations, such as Norge, Sverige, Oslo, Bergen, Trondheim etc.  Default is Norge 
