# SIP Generator

This repository contains the SIP Generator used in the DURAARK project for creating data packages which are ingested into the long-term preservation system ExLibris ROSETTA.

Additionally the SIP Generator supports the BagIT format and allows to produce archives with this type for local storage.

The following installation and usage description is tailored for a Ubuntu 14.04 system. Other systems should work also, but are not tested.

## Prerequisites

Install Java 8 JRE with this guide:

http://tecadmin.net/install-oracle-java-8-jdk-8-ubuntu-via-ppa/

Install 'sqlite' and 'md5deep':

```shell
sudo apt-get install sqlite3 md5deep
```
## Installation

A sqlite3 database schema is necessary for passing metadata to an package. To setup the schema run the following command in folder './microservice_sip3/run':

```shell
sqlite3 < initiate_sqlitedb.sql
```

## Usage

The SIP Generator expects a defined folder structure and packages the files located within those folders. The base folder structure is already present in the '/run' folder. 

To add files to the SIP package copy them into '/run/content/streams'.

The metadata information is passed to the SIP Generator via the 'rdf' table in the SQLite database located at './microservice_sip3/run/sipdb.db'. Fill in the necessary data there. 'paketuid' is a UUID that you have to provide.

Change to the folder './microservice_sip3/run' and start the package creation with

```bash
java -jar PrototypeY2.jar <name_of_output_sip>
```
This will create a SIP which is placed in the './microservice_sip3/run/sip' folder as 'tar' archive.

