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

#### Package

An example package section looks like this. Each element is described further down:

`package:`

`  !com.qmatic.orchestra.provisioning.entities.Package`

`  UUID: '101'`

`  name: 'Instore Click & Collect'`

`  version: '1.0'`

`  author: 'Qmatic UK / Qmatic HQ'`

`  description: 'The text that is shown in the list of packages.'`

`  longDescription: '<h2>A longer text shown on package details</h2><p>More text</p>'`

`  availability: 'global'`



  

  types: 

    - 'package'

  categories: \['retail','industry\_solution'\]

  assets: 

    - 

      !com.qmatic.orchestra.provisioning.entities.Artifact

      name: 'Click & Collect In Store package - intro.pptx'

      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/packages/click\_collect\_2/ClickCollect+pricing+discussion.pptx'

      contentType: 'application/vnd.ms-powerpoint'

    - 

      !com.qmatic.orchestra.provisioning.entities.Artifact

      name: 'Click & Collect In Store package - sales leaflet.pdf'

      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/packages/click\_collect\_2/click-and-collect.pdf'

      contentType: 'application/pdf'



  dependencies: 

    - 'Orchestra: 3.2.0.214'

    

  artifacts:

    - 

      !com.qmatic.orchestra.provisioning.entities.Artifact

      name: 'visitModifyer'

      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/marketplace/packages/InstoreClickAndCollect/visitModifyer.utt'

      description: 'SSSSSSS'

      contentType: 'application/x-zip'

      type: 'UTT'

    - 

      !com.qmatic.orchestra.provisioning.entities.Artifact

      name: 'clickandcollect'

      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/marketplace/packages/InstoreClickAndCollect/clickandcollect.wgt'

      description: 'SSSSSSS'

      contentType: 'application/x-zip'

      type: 'Widget'



  icon: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/packages/click\_collect\_2/ClickCollect.svg'



  parameters:

    intro: 

      label: 'Please fill in the information below. u want to use email later you need to configure email servers etc inside Orchestra later.'

    meta:

      label: 'Intro 17 surface settings'

      welcome\_text: 

        label: 'Welcome text'

        type: 'text'

        default: 'Welcome to Click and Collect!'

      phone\_prefix\_new: 

        label: 'Mobile Phone Country Code'

        type: 'text'

        default: '44'

      image\_main: 

        label: 'Surface logo'

        type: 'file'

        default: ''

    communication:

      label: 'Communication settings'

      beepsend\_key:

        label: 'Beepsend token'

        type: 'text'

        default: ''

    notification\_texts:

      label: 'SMS/Email Notification messages'

      visit\_create\_message:

        label: 'Visit create message'

        type: 'text'

        default: 'Welcome - please browse while we prepare your order'

      arrival\_call\_message:

        label: 'Arrival call message'

        type: 'text'

        default: 'We have just started processing your order and will notify you during the process'



