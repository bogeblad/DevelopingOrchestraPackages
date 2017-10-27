# Surface groups

The element "surfaceGroups" is a root element in the package definition. It is a list of surface groups and surfaces as examplified further down.

#### SurfaceGroup \(annotated with !com.qmatic.orchestra.provisioning.entities.SurfaceGroup\)

#### Attributes

| Attribute | Type | Description |
| :--- | :--- | :--- |
| name | String | The name of the unit. |
| surfaces | List of Surfaces \( | Description of the unit |

##### Example

```
surfaceGroups:
  - &surfaceGroup_TOUCH
    !com.qmatic.orchestra.provisioning.entities.SurfaceGroup
    name: 'TOUCH'
```

### 



