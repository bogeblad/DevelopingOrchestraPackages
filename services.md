# Services

ssss

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
    ticketTemplate: *surface_DefaultTicket
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



