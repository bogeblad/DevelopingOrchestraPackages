# Roles and users

SSS

```
roles:
  - &role_1
    !com.qmatic.orchestra.provisioning.entities.Role
    name: 'ClickandCollect'
    description: 'ewfwef'
    modules:
      - 'workstation'
      - 'servicePoint'
      - 'entryPoint'  
      - 'connectcounter'  
      - 'connectconcierge'  
  - &role_2
    !com.qmatic.orchestra.provisioning.entities.Role
    name: 'ClickandCollectRESTROLE'
    description: 'Only used for getting access to REST API:s'
    modules:
      - 'servicePoint'
      - 'entryPoint'
```

```
users:
  - &user_1
    !com.qmatic.orchestra.provisioning.entities.User
    userName: 'ccuser'
    pinCode: '1234'
    firstName: 'Click and Collect'
    lastName: 'User'
    language: 1
    password: 'Click123'
    status: 'ACTIVE'
    data: 
      label.phone: '{ccUserPhone}'
      label.email: '{ccUserEmail}'
    branchHierarchyRoot: 1
    roleNames:
      - 'ClickandCollect'
    branchesNames:
      - 'CNC Branch'
    branchGroupNames:
      - 'REGIONS'
  - &user_2
    !com.qmatic.orchestra.provisioning.entities.User
    userName: 'widgetrestuser'
    pinCode: '3311'
    firstName: 'Widget REST'
    lastName: 'User'
    language: 1
    password: 'widgetPass88'
    status: 'ACTIVE'
    data: 
      label.phone: '{ccUserPhone}'
      label.email: '{ccUserEmail}'
    branchHierarchyRoot: 1
    roleNames:
      - 'ClickandCollectRESTROLE'
    branchesNames:
      - 'CNC Branch'
    branchGroupNames:
      - 'REGIONS'
```



