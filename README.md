# microservice_sip3
A new repo for microservice_sip -- to tidy stuff and at the sime time get nice filepaths without spaces in them

To run this you need to be on a system with command line hash-tools like md5 available. 

Java and sqlite3 are required.

Go to the folder run/

First set up the sqlite database using the initiate_sqlitedb.sql file. This can be done from the run/ folder with this one-liner:
sqlite3 < initiate_sqlitedb.sql 

Then run this from the terminal: "java -jar PrototypeY2.jar Rosetta-SIP"

This will do the SIP generation of the content placed in the "content" folder.

