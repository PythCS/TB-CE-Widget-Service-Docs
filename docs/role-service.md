# ROLE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
```

**1. getRoles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
roleService.getRoles(pageLink, 'your-type-value').subscribe(roles => {
  console.log('Get Roles:', roles);
});
```

**2. getRolesByIds**

```javascript
roleService.getRolesByIds('your-roleids-value').subscribe(rolesByIds => {
  console.log('Get Roles By Ids:', rolesByIds);
});
```

**3. getRole**

```javascript
roleService.getRole('your-role-id').subscribe(role => {
  console.log('Get Role:', role);
});
```

**4. saveRole**

```javascript
roleService.saveRole('your-role-value').subscribe(role => {
  console.log('Save Role:', role);
});
```

**5. saveGroupPermission**

```javascript
roleService.saveGroupPermission('your-grouppermission-value').subscribe(groupPermission => {
  console.log('Save Group Permission:', groupPermission);
});
```

**6. deleteGroupPermissions**

```javascript
roleService.deleteGroupPermissions('your-grouppermissionids-value').subscribe(groupPermissions => {
  console.log('Delete Group Permissions:', groupPermissions);
});
```

**7. deleteGroupPermission**

```javascript
roleService.deleteGroupPermission('your-grouppermission-id').subscribe(groupPermission => {
  console.log('Delete Group Permission:', groupPermission);
});
```

**8. getUserGroupPermissions**

```javascript
roleService.getUserGroupPermissions('your-usergroup-id').subscribe(userGroupPermissions => {
  console.log('Get User Group Permissions:', userGroupPermissions);
});
```

**9. getEntityGroupPermissions**

```javascript
roleService.getEntityGroupPermissions('your-entitygroup-id').subscribe(entityGroupPermissions => {
  console.log('Get Entity Group Permissions:', entityGroupPermissions);
});
```

**10. getGroupPermissionInfo**

```javascript
roleService.getGroupPermissionInfo('your-grouppermission-id', true).subscribe(groupPermissionInfo => {
  console.log('Get Group Permission Info:', groupPermissionInfo);
});
```

**11. loadUserGroupPermissionInfos**

```javascript
roleService.loadUserGroupPermissionInfos('your-grouppermissions-value').subscribe(loadUserGroupPermissionInfos => {
  console.log('Load User Group Permission Infos:', loadUserGroupPermissionInfos);
});
```
