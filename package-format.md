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

#### Package \(annotated with !com.qmatic.orchestra.provisioning.entities.Package\)

#### Attributes 

| Attribute | Type | Description |
| :--- | :--- | :--- |
| UUID | String | The unique ID of the package - used for selection and navigation etc. |
| name | String | Name of the package |
| version | String | Version of the package |
| author | String | The author\(s\) of the package |
| description | String | Short description of the package |
| longDescription | String | A longer description of the package |
| availability | String \(global/local\) | States if the package is globally or locally available. |

#### Example

```
UUID: '101'
name: 'Instore Click & Collect'
version: '1.0'
author: 'Qmatic UK / Qmatic HQ'
description: 'The Instore Click & Collect package.'
longDescription: '<h2>Longer</h2><p>Read all about it on</p>'
availability: 'global'Subelements
```

### Subelements



| Attribute | Type | Description |
| :--- | :--- | :--- |
|  |  |  |



