# Branches

The element "branches" is a root element in the package definition. It is a list of branches as exemplified further down.

#### Branch \(annotated with !com.qmatic.orchestra.provisioning.entities.Branch\)

#### Attributes

| Attribute | Type | Description |
| :--- | :--- | :--- |
| name | String | Internal name of the service. |
| branchPrefix | String | Internal description of the service. |
| timeZone | String | External name of the service |
| agentId | String | External description |
| enabled | Integer | See Orchestra ref manual |
| mobileEnabled | Boolean | See Orchestra ref manual |
| description | Boolean | See Orchestra ref manual |
| branchGroupName | Reference \(yaml\) | Name of the branch group it should belong to. |
| operationProfile | Reference \(yaml\) | Reference to an operation profile by ref id. |
| equipmentProfile | Reference \(yaml\) | Reference to an equipment profile by ref id. |
| branchUnitsParameters | Parameter value map | Branch unit parameters |

##### Example

```
branches:
  - &branch_2
    !com.qmatic.orchestra.provisioning.entities.Branch
    name: 'CNC Branch'
    branchPrefix: 'CNC'
    timeZone: 'Europe/London'
    agentId: 'central'
    enabled: true
    mobileEnabled: false
    description: ''
    operationProfile: *operation_profile_50
    equipmentProfile: *equipment_profile_50
    #branchParameters: 
    branchGroupName: 'REGIONS'
    branchUnitsParameters:
      - 
        name: 'NotificationsCC'
        parameters: 
          - 
            id: 'positionToNotify'
            value: 0
      - 
        name: 'WebReception'
        parameters: 
          - 
            id: 'mdNotes'
            value: 'true'
```





