# ROLE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
```

**1. getRoles**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // RoleType object
  // ... set the fields you need
};
roleService.getRoles(pageLink, type).subscribe(roles => {
  console.log('List of Roles:', roles);
});
```

**2. getRolesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const roleIds = ['your-role-i-1', 'your-role-i-2'];
roleService.getRolesByIds(roleIds).subscribe(rolesBys => {
  console.log('List of Roles By Ids:', rolesBys);
});
```

**3. getRole**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const roleId = 'your-role-id';
roleService.getRole(roleId).subscribe(role => {
  console.log('Get Role:', role);
});
```

**4. saveRole**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const role = {  // Role object
  // ... set the fields you need
};
roleService.saveRole(role).subscribe(savedRole => {
  console.log('Saved Role:', savedRole);
});
```

**5. saveGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermission = {  // GroupPermission object
  // ... set the fields you need
};
roleService.saveGroupPermission(groupPermission).subscribe(savedGroupPermission => {
  console.log('Saved Group Permission:', savedGroupPermission);
});
```

**6. deleteGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissionIds = ['your-group-permission-i-1', 'your-group-permission-i-2'];
roleService.deleteGroupPermissions(groupPermissionIds).subscribe(result => {
  console.log('Delete Group Permissions result:', result);
});
```

**7. deleteGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissionId = 'your-group-permission-id';
roleService.deleteGroupPermission(groupPermissionId).subscribe(result => {
  console.log('Delete Group Permission result:', result);
});
```

**8. getUserGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const userGroupId = 'your-user-group-id';
roleService.getUserGroupPermissions(userGroupId).subscribe(userGroupPermissions => {
  console.log('List of User Group Permissions:', userGroupPermissions);
});
```

**9. getEntityGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const entityGroupId = 'your-entity-group-id';
roleService.getEntityGroupPermissions(entityGroupId).subscribe(entityGroupPermissions => {
  console.log('List of Entity Group Permissions:', entityGroupPermissions);
});
```

**10. getGroupPermissionInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissionId = 'your-group-permission-id';
const isUserGroup = true;
roleService.getGroupPermissionInfo(groupPermissionId, isUserGroup).subscribe(groupPermissionInfo => {
  console.log('Get Group Permission Info:', groupPermissionInfo);
});
```

**11. loadUserGroupPermissionInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const roleService = $injector.get(self.ctx.servicesMap.get('roleService'));
const groupPermissions = [];  // e.g. array of group-permissions values
roleService.loadUserGroupPermissionInfos(groupPermissions).subscribe(userGroupPermissionInfos => {
  console.log('List of User Group Permission Infos:', userGroupPermissionInfos);
});
```
