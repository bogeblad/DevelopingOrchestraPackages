# Services

The element "services" is a root element in the package definition. It is a list of services as examplified further down.

#### Service \(annotated with !com.qmatic.orchestra.provisioning.entities.Service\)

#### Attributes

| Attribute | Type | Description |
| :--- | :--- | :--- |
| internalName | String | Internal name of the service. |
| internalDescription | String | Internal description of the service. |
| externalName | String | External name of the service |
| externalDescription | String | External description |
| targetServingTime | Integer | See Orchestra ref manual |
| mobileEnabled | Boolean | See Orchestra ref manual |
| bookingEnabled | Boolean | See Orchestra ref manual |
| ticketTemplate | Reference \(yaml\) | Reference to a ticket surface by ref id.  |

##### Example

```
services:
  - &service_1
    !com.qmatic.orchestra.provisioning.entities.Service
    internalName: 'Service A'
    internalDescription: ''
    externalName: 'Service A'
    externalDescription: ''
    targetServingTime: 0
    mobileEnabled: false
    bookingEnabled: false
    ticketTemplate: *surface_DefaultTicket #Means it will connect to an element defined as &surface_DefaultTicket
  - &service_2
    !com.qmatic.orchestra.provisioning.entities.Service
    internalName: 'Service B'
    internalDescription: ''
    externalName: 'Service B'
    externalDescription: ''
    targetServingTime: 0
    mobileEnabled: false
    bookingEnabled: false
    ticketTemplate: *surface_DefaultTicket
```



