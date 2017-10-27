# Surface groups

The element "surfaceGroups" is a root element in the package definition. It is a list of surface groups and surfaces as examplified further down.

#### SurfaceGroup \(annotated with !com.qmatic.orchestra.provisioning.entities.SurfaceGroup\)

#### Attributes

| Attribute | Type | Description |
| :--- | :--- | :--- |
| name | String | The name of the surface group. |
| surfaces | List of type Surface \(own section below\) | A list of surfaces to include in the group. |

##### Example

```
surfaceGroups:
  - &surfaceGroup_TOUCH                                       #An id so we can reference this surfacegroup later
    !com.qmatic.orchestra.provisioning.entities.SurfaceGroup  #The class we want yaml to parse to
    name: 'TOUCH'                                             #Name of the surface group  
```

### 



