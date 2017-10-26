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

```
package:
  !com.qmatic.orchestra.provisioning.entities.Package
  UUID: '101'
  name: 'Instore Click & Collect'
  version: '1.0'
  author: 'Qmatic UK / Qmatic HQ'
  description: 'The Instore Click & Collect package addresses that specific part of the customer journey where customers come to pick up their order.'
  longDescription: '<h2>An instore click and collect solution with upsell opportunities</h2><p>Read all about it on <a href="https://m01-qmaticworld.portal.qmatic.com/en/products/software/packaged-offerings/instore-click-collect">Qmatic world</a> where you will find marketing collateral and documentation.</p><h4>Prerequisites</h4><ul><li>Clean Orchestra 6.2 Update 6 or later with licence activated</li><li>A beepsend token</li></ul><h4>Process</h4><ul><li>Click the "Download and apply" button</li><li>Enter the information asked for</li><li>Apply and wait for the process to complete</li><li>Publish the branch</li><li>Restart Orchestra to get the notification module to apply the new settings</li><li>Preview the surface and test it (Touch --> Intro17 --> ClickAndCollectSurface)</li><li>Done</li></ul><h4>Bugs or questions</h4><p>Contact support and attach the log files created by the provisioning tool together with information about the error, your Orchestra version etc</p>'
  availability: 'global'
  types: 
    - 'package'
  categories: ['retail','industry_solution']
  assets: 
    - 
      !com.qmatic.orchestra.provisioning.entities.Artifact
      name: 'Click & Collect In Store package - intro.pptx'
      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/packages/click_collect_2/ClickCollect+pricing+discussion.pptx'
      contentType: 'application/vnd.ms-powerpoint'
    - 
      !com.qmatic.orchestra.provisioning.entities.Artifact
      name: 'Click & Collect In Store package - sales leaflet.pdf'
      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/packages/click_collect_2/click-and-collect.pdf'
      contentType: 'application/pdf'
    - 
      !com.qmatic.orchestra.provisioning.entities.Artifact
      name: 'Click & Collect Configuration Manual.pdf'
      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/marketplace/packages/InstoreClickAndCollect/204_A_Click_and_Collect.pdf'
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
    #- 
    #  !com.qmatic.orchestra.provisioning.entities.Artifact
    #  name: 'alertEvernt_19A'
    #  url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/marketplace/packages/InstoreClickAndCollect/alertEvernt_19A.utt'
    #  description: 'SSSSSSS'
    #  contentType: 'application/x-zip'
    # type: 'UTT'
    - 
      !com.qmatic.orchestra.provisioning.entities.Artifact
      name: 'NotificationsCC'
      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/marketplace/packages/InstoreClickAndCollect/NotificationsCC.utt'
      description: 'Standard notification UTT but with multi notification per visit'
      contentType: 'application/x-zip'
      type: 'UTT'
    - 
      !com.qmatic.orchestra.provisioning.entities.Artifact
      name: 'Intro17_Custom'
      url: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/marketplace/packages/InstoreClickAndCollect/Intro17_Custom.utt'
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

  icon: 'https://s3-eu-west-1.amazonaws.com/cdn-qmatic-cloud/packages/click_collect_2/ClickCollect.svg'

  parameters:
    intro: 
      label: 'Please fill in the information below. Presets are for a SMS-based solution so if you want to use email later you need to configure email servers etc inside Orchestra later.'
    meta:
      label: 'Intro 17 surface settings'
      main_keyboard_lang: 
        label: 'Keyboard layout (uk, swe, fr)'
        type: 'text'
        default: 'uk'
      welcome_text: 
        label: 'Welcome text'
        type: 'text'
        default: 'Welcome to Click and Collect!'
      firstpage_text: 
        label: 'Surface intro text'
        type: 'text'
        default: 'How would you like to be notified about the progress of your order?'
      orderref_label_text: 
        label: 'Order reference label'
        type: 'text'
        default: 'Order Ref:'
      button_sms_text: 
        label: 'SMS Button Text'
        type: 'text'
        default: 'SMS:'
      #button_email_text: 
      #  label: 'Email Button Text'
      #  type: 'text'
      #  default: 'Email:'
      #orderref_input_pattern: 
      #  label: 'Order reference input regex'
      #  type: 'text'
      #  default: '^[0-9A-Z]{4,12}$'
      phone_min_digits: 
        label: 'Mobile Phone Min Length'
        type: 'text'
        default: '10'
      phone_prefix_new: 
        label: 'Mobile Phone Country Code'
        type: 'text'
        default: '44'
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
      ccUserEmail:
        label: 'Staff notification email'
        type: 'text'
        default: ''
        dataParsleyType: 'email'
      smsFromName:
        label: 'SMS Sender name'
        type: 'text'
        default: 'Qmatic'
      intro17IPAdress:
        label: 'Intro 17 IP'
        type: 'text'
        default: ''
#      mailserver_host:
#        label: 'Mailserver host'
#        type: 'text'
#        default: ''
#      mailserver_port:
#        label: 'Mailserver port'
#        type: 'text'
#        default: '587'
#      mailserver_user:
#        label: 'Mailserver user'
#        type: 'text'
#        default: ''
#      mailserver_pw:
#        label: 'Mailserver pw'
#        type: 'text'
#        default: ''
#      mailserver_ttls:
#        label: 'Mailserver ttls'
#        type: 'text'
#        default: 'true'
#      mailserver_auth:
#        label: 'Mailserver auth'
#        type: 'text'
#        default: 'true'
#      mailserver_charset:
#        label: 'Mailserver charset'
#        type: 'text'
#        default: 'UTF-8'
#      mailserver_sender:
#        label: 'Mailserver sender'
#        type: 'text'
#        default: ''
    notification_texts:
      label: 'SMS/Email Notification messages'
      visit_create_message:
        label: 'Visit create message'
        type: 'text'
        default: 'Welcome - please browse while we prepare your order'
      arrival_call_message:
        label: 'Arrival call message'
        type: 'text'
        default: 'We have just started processing your order and will notify you during the process'
      picking_call_message:
        label: 'Picking call message'
        type: 'text'
        default: 'Your order is being picked and you will be called when ready for pickup'
      collect_call_message:
        label: 'Collect call message'
        type: 'text'
        default: 'Your order is ready to pick up'
      visit_end_message:
        label: 'Visit end message'
        type: 'text'
        default: 'Thank you for using our collect service'
```



