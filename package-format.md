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
| icon | String | URL to a package icon |
| availability | String \(global/local\) | States if the package is globally or locally available. |
| dependencies | List of strings | States all software dependencies |
| types | List of strings | States if it's a package, widget, utt etc |
| assets | List of type Artifact \(own section\) | Lists assets connected to the packagethat should be shown in detail view. Often documents or software that has to be installed manually. |
| artifacts | List of type Artifact \(own section\) | List of artifacts to deploy |
| parameters | Package configuration parameters \(own section\) | List of configurable properties on the package. Used to generate the deploy configuration form. |

##### Example

```
UUID: '101'
name: 'Instore Click & Collect'
version: '1.0'
author: 'Qmatic UK / Qmatic HQ'
description: 'The Instore Click & Collect package.'
longDescription: '<h2>Longer</h2><p>Read all about it on</p>'
availability: 'global'
icon: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/packages/click_collect_2/ClickCollect.svg'
dependencies: 
  - 'Orchestra: 3.2.0.214'
types: 
  - 'package'
assets: ...
artifacts: ...
parameters: ...
```

### Subelement types

#### Artifact \(annotated with !com.qmatic.orchestra.provisioning.entities.Artifact\)

Used by both the assets element and the artifacts element.

| Attribute | Type | Description |
| :--- | :--- | :--- |
| name | String | The name of the artifact |
| url | String | The url of the artifact \(avail. public\) |
| contentType | String | The content type of the artifact |
| description | String \(optional\) | A text desc of the artifact |
| type | String / Enum \['UTT','widget'\] \(optional\) | States if it's an Widget, UTT, Terminal etc. |

##### Example

```
artifacts:
    - 
      !com.qmatic.orchestra.provisioning.entities.Artifact
      name: 'ExampleUTT'
      url: 'https://s3-eu-west-1.amazonaws.com/example.utt'
      description: 'An example UTT'
      contentType: 'application/x-zip'
      type: 'UTT'
```



#### Parameters \(used by the "parameters" element above\)

This is a hash structure - i.e. multilevel and will be described in an example:

##### Example

```
parameters:
  meta:                                       #The section internal name
    label: 'Notification settings'            #The section headline
    main_email:                               #The field 
      label: 'Staff email'                    #The field label 
      type: 'text'                            #The field type  
      default: 'uk'                           #The field default value 
      dataParsleyType: 'email'                #The field validation type (Parsley JS Validator) 
    welcome_text: 
      label: 'Welcome text'
      type: 'text'
      default: 'Welcome to Click and Collect!'
    image_main: 
      label: 'Surface logo'
      type: 'file'        
      default: ''
  communication:
    label: 'Communication settings'
    beepsend_key:
      label: 'Beepsend token'
      type: 'text'
      default: ''
    ccUserPhone:
      label: 'Staff notification mobile number'
      type: 'text'
      default: '467010xxxxx'

```

There is a special section that is called intro: that only needs an label element. If this exists it is show first as introduction to the form.

