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

### Subelement types

#### WidgetSettings \(annotated with !com.qmatic.orchestra.provisioning.entities.WidgetSetting\)

As widgets are referenced in the html of a surface we only need to supply the settings for it.

| Attribute | Type | Description |
| :--- | :--- | :--- |
| identifier | String | The identifier of the widget |
| title | String \(optional\) | The widget title |
| description | String \(optional\) | The widget description |
| icon | String \(optional\) | A text desc of the artifact |
| standalone | String \(optional\) | See widget docs |
| widgetId | String | The id of the widget as referenced in the html-attribute.  |
| parameters | List of key/value | The widget settings - see example |

##### Example

```
widgetSettings: 
  -
    !com.qmatic.orchestra.provisioning.entities.WidgetSetting
    identifier: 'http://qmatic.com/widgets/simpleexamplewidget'
    title: 'Click and Collect'
    description: 'Simple example Widget'
    icon: 'http://127.0.0.1:8080/wookie/wservices/qmatic.com/widgets/simpleexamplewidget/img/x.png'
    standalone: 'true'
    widgetId: 'widget_1'
    parameters:
      -
        key: "font.color"
        value: "blue"
      -
        key: "font.size"
        value: "24px"

```

#### 



