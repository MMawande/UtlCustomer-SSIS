# UtlCustomer-SSIS
ETL and None ETL tasks on MSBI
Covered Loading bulk files
Validation
Error handling
Data conversion![image](https://media.git.i.mercedes-benz.com/user/15425/files/b0754f8f-52b7-4c15-886e-e37f5322810d)
covered For Loop container, variables, parameters, debugging, quick watch & Add watch![image](https://media.git.i.mercedes-benz.com/user/15425/files/1ba617b9-a028-4a5b-889b-f14bcf86bca8)
packaging, deployment, file component and running SSIS package as a task![image](https://media.git.i.mercedes-benz.com/user/15425/files/cf9e9c30-c72c-49e7-b146-dc20c8c5f4f3)

![image](https://media.git.i.mercedes-benz.com/user/15425/files/d39785d5-4a68-4527-8270-ed58d9a9ecd2)
In Data flow we do ETL activities while in control flow we do NON-ETL activities. FOR LOOP is a NON-ETL activity and has to be done in control flow

	- For loop, Variables , parameters and debugging

There are two types of for loops (Foreach Loop Container & For loop container)

For loop container do a loop up until a fixed count 
For each container loops through a (collection) items like recordset, files in a folder and so on

Control flow pass full file name with the path to the data flow ? It is through using variables 

Variables are temporary storages where we can go and store some values
![image](https://media.git.i.mercedes-benz.com/user/15425/files/401b8144-8c68-4562-b07e-adceb9bcb353)

Dimension, measures, star schema, snow flake, shared connection managers & package tasks?

When it designing data warehouse for master data, most developers likes to choose between Normalization (OLTP) to remove redundancy/duplicate data and Star Schema/Snow flake (OLAP) for fast retrieval /reading the records

Most prefer Star Schema or Snow Flake 

	- When you are dealing  with OLTP systems, normalization design is the best way to go because data is coming into the system you want to ensure that you get Clean & proper data
	- But when we are talking about fetching, analysing that time reading the records is the most important that you want to be better in terms of performance

![image](https://media.git.i.mercedes-benz.com/user/15425/files/fda30dda-c9fc-490f-bd3c-11ef207f6c2f)

Understanding the concept of Measures & Dimensions

The whole purpose of business intelligence (MSBI) is to derive intelligent information from your data. By intelligent information meaning to do forecasting , analysis using numbers e.g (population, profit, total sales) with context e.g (country,year,product)![image](https://media.git.i.mercedes-benz.com/user/15425/files/5e7b345d-e414-47f9-8ec8-515b3c57d317)

![image](https://media.git.i.mercedes-benz.com/user/15425/files/071838d6-7275-4027-8be7-c4334214091c)

The numbers cannot do analysis , forecast and intelligence alone, they need context![image](https://media.git.i.mercedes-benz.com/user/15425/files/4d05a54b-11fa-4bfe-b60e-acb275ffbe12)

![image](https://media.git.i.mercedes-benz.com/user/15425/files/9ba63f15-33ca-4de7-b422-dcd625554843)

	That number, which the customer wants to do an analysis is termed as measures
	
	
	Star Schema : Fact is the central table with foreign key relationship with Dimension. Dimension tables are not connected as opposed to (Snowflake), with Snowflake the dimension tables are also connected
	
![image](https://media.git.i.mercedes-benz.com/user/15425/files/9bfab930-05d8-4840-8ecd-83b7f4416e1f)

	Dimension and measures
	Star schema vs snowflake
	Shared connection managers and package tasks

![image](https://media.git.i.mercedes-benz.com/user/15425/files/6d7379fb-b7ab-49cd-9662-84e21d905b78)

Create additional SSIS packages with a Master package that will execute all other packages![image](https://media.git.i.mercedes-benz.com/user/15425/files/b545dd49-f3f1-429b-8d6f-4f803fdd13c2)

![image](https://media.git.i.mercedes-benz.com/user/15425/files/4e864e96-7e52-44ac-aa48-1c2cc1dbde2b)

	Create main package that will organise the flow of packages execution
	
	Make the main package to control the flow of which packages to be executed first and second. Right clik and go to edit->packages-.click  the package name next to PackageNameFromProjectReference
	
	To make SSIS know that it has to run the main package first ,in order to run a package as a startup package, right click the main package and say Set as Startup Object
![image](https://media.git.i.mercedes-benz.com/user/15425/files/8232650c-0c69-41bb-bd5a-aa1298822ec2)

![image](https://media.git.i.mercedes-benz.com/user/15425/files/02165bd7-0dc6-4cc5-9a70-509694247858)
	Now load the CSV files to their respective tables, starting with all the Dimension tables then the Measure table. NB all the packages will be connecting to the same server, to avoid creating connection managers all over again, just create a single global connection manager.
	
Below Project.params right clik the connection managers->Click new connection manager![image](https://media.git.i.mercedes-benz.com/user/15425/files/c5ade7aa-abd5-467c-8525-1d13bef87ac3)

![image](https://media.git.i.mercedes-benz.com/user/15425/files/a668414b-c3f1-4c19-b7a2-feaf7d656efe)

	SCD (Slowly Changing Dimensions)
Merge, merge join and Look up![image](https://media.git.i.mercedes-benz.com/user/15425/files/4cfd6caf-5084-4e7b-bb3f-30c4b712ed40)
