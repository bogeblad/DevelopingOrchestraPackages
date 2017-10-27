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

### Subelement types

#### Surface \(annotated with !com.qmatic.orchestra.provisioning.entities.Surface\)

Used by the surfaces element.

| Attribute | Type | Description |
| :--- | :--- | :--- |
| name | String | The name of the artifact |
| html | String | The url of the artifact \(avail. public\) |
| idSequence | Integer | Sequence number - usually 0 |
| screenHeight | Integer | Screen height |
| screenWidth | Integer | Screen width |
| timeBeforeRestart | Integer | See surface editor |
| callpageEnabled | Boolean | See surface editor |
| channelplayerEnabled | Boolean | See surface editor |
| hasVerticalMessage | Boolean | See surface editor |
| branchProfileName | String | The name of the branch profile / operation profile to tie this to. |
| surfaceType | Surface type defined by allowedDeviceName as subelement | The surface type name to categorize this surface as. |

##### Example

```
surfaces: 
  - &surface_DefaultClickAndCollectTicket
    !com.qmatic.orchestra.provisioning.entities.Surface
    name: 'ClickAndCollectArrivalSurface'
    html: "....THE HTML OF THE SURFACE..."
    idSequence: 0
    screenHeight: 1024
    screenWidth: 1280
    timeBeforeRestart: 600
    callpageEnabled: true
    channelplayerEnabled: false
    hasVerticalMessage: false
    surfaceType:
      allowedDeviceName: 'Intro17'
    branchProfileName: 'Click And Collect'
```



