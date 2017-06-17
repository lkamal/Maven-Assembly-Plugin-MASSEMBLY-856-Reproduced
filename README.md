# Maven-Assembly-Plugin-MASSEMBLY-856-Reproduced
Maven Assembly plugin is not currently overwriting files. This sample project is used to demonstrate that.

Details of this is recorded at [MASSEMBLY-856](https://issues.apache.org/jira/browse/MASSEMBLY-856).

## Content
This project has three modules. 
1. module1 - has two files; conf.propeties & MODULE1_README
2. module2 - has two files; conf.propeties & MODULE2_README
3. release - builds a zip file with above 4 files.

Both module1 & module2 has a filenamed conf.properties. When the release zip file is generated, it can contain only one conf.properties file. Expectation is to retain the file from module2 by replacing the one coming from module1; but it is not happening. Always the file from module1 bundles into the zip file.

## How to reproduce the problem
Build the project using below command.

`mvn clean install`

Extract generated zip file at assemblypluginoverwrite/release/target/assemblyplugin-overwrite-release-1.0-SNAPSHOT.zip.

It contains conf.properties file from module1, not from module2.
