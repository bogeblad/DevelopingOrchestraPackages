# Package format

We have selected to use the popular configuration format YAML \(.yml\). It's readable and has support for comments, internal references between nodes and other things which for example JSON does not.

The file is text only and can be named anything as it is the registry who points it out. We recommend you to name it **configuration.yml** or package.yml.

## Configuration structure

The current format has the following main areas / root elements :

* **package** - contains package meta data and all binary asset references. Full details below. 
* **globalUnits** - Orchestra configuration for global units - more details below
* **surfaceGroups **- Orchestra configuration for surfaces / widgets - more details below
* **services **- Orchestra configuration for services - more details below
* **operationProfiles **- Orchestra configuration for operation profiles, equipment profiles etc- more details below
* **branches **- Orchestra configuration for branches - more details below
* **roles **- Orchestra configuration for roles - more details below
* **users **- Orchestra configuration for users - more details below
* **globalVariables **- Orchestra configuration for global variables - more details below

The next chapters will describe each of these in detail.



