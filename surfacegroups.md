# Surface groups

The element "globalUnits" is a root element in the package definition. It is a list of global units as examplified further down.

#### GlobalUnit \(annotated with !com.qmatic.orchestra.provisioning.entities.GlobalUnit\)

#### Attributes

| Attribute | Type | Description |
| :--- | :--- | :--- |
| name | String | The name of the unit. |
| description | String | Description of the unit |
| unitTemplateName | String | Which unit template it is based on |

##### Example

```
globalUnits:
  - &globalUnit_A                                           #An yaml ID so we can reference this unit from other elements
    !com.qmatic.orchestra.provisioning.entities.GlobalUnit  #States the type so yaml can parse
    name: 'UnitA'                                           #Name of unit
    description: 'An intro 17 unit'                         #Description
    unitTemplateName: 'Intro17'                             #Which unit template it is based on
  - &globalUnit_B
    !com.qmatic.orchestra.provisioning.entities.GlobalUnit
    name: 'SpecialCardReaderExample'
    description: 'A custom unit'
    unitTemplateName: 'SpecialCardReaderExample'
```

### 



