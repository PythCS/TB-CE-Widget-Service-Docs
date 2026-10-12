# USER PERMISSIONS SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
```

**1. loadPermissionsInfo**

```javascript
userPermissionsService.loadPermissionsInfo().subscribe(loadPermissionsInfo => {
  console.log('Load Permissions Info:', loadPermissionsInfo);
});
```

**2. hasEntityPermission**

```javascript
userPermissionsService.hasEntityPermission('your-entity-id', 'your-operation-value').subscribe(hasEntityPermission => {
  console.log('Has Entity Permission:', hasEntityPermission);
});
```

**3. getOperationsByResource**

```javascript
userPermissionsService.getOperationsByResource('your-resource-value').subscribe(operationsByResource => {
  console.log('Get Operations By Resource:', operationsByResource);
});
```

**4. getAllowedGroupRoleOperations**

```javascript
userPermissionsService.getAllowedGroupRoleOperations().subscribe(allowedGroupRoleOperations => {
  console.log('Get Allowed Group Role Operations:', allowedGroupRoleOperations);
});
```

**5. getAllowedResources**

```javascript
userPermissionsService.getAllowedResources().subscribe(allowedResources => {
  console.log('Get Allowed Resources:', allowedResources);
});
```

**6. hasReadGroupsPermission**

```javascript
userPermissionsService.hasReadGroupsPermission('your-entitytype-value').subscribe(hasReadGroupsPermission => {
  console.log('Has Read Groups Permission:', hasReadGroupsPermission);
});
```

**7. hasGenericReadGroupsPermission**

```javascript
userPermissionsService.hasGenericReadGroupsPermission('your-entitytype-value').subscribe(hasGenericReadGroupsPermission => {
  console.log('Has Generic Read Groups Permission:', hasGenericReadGroupsPermission);
});
```

**8. hasSharedReadGroupsPermission**

```javascript
userPermissionsService.hasSharedReadGroupsPermission('your-entitytype-value').subscribe(hasSharedReadGroupsPermission => {
  console.log('Has Shared Read Groups Permission:', hasSharedReadGroupsPermission);
});
```

**9. hasReadGenericPermission**

```javascript
userPermissionsService.hasReadGenericPermission('your-resource-value').subscribe(hasReadGenericPermission => {
  console.log('Has Read Generic Permission:', hasReadGenericPermission);
});
```

**10. hasGenericPermission**

```javascript
userPermissionsService.hasGenericPermission('your-resource-value', 'your-operation-value').subscribe(hasGenericPermission => {
  console.log('Has Generic Permission:', hasGenericPermission);
});
```

**11. isAiEnabled**

```javascript
userPermissionsService.isAiEnabled().subscribe(isAiEnabled => {
  console.log('Is Ai Enabled:', isAiEnabled);
});
```

**12. isResourceAllowed**

```javascript
userPermissionsService.isResourceAllowed('your-resource-value').subscribe(isResourceAllowed => {
  console.log('Is Resource Allowed:', isResourceAllowed);
});
```

**13. hasGenericPermissionByEntityGroupType**

```javascript
userPermissionsService.hasGenericPermissionByEntityGroupType('your-operation-value', 'your-grouptype-value').subscribe(hasGenericPermissionByEntityGroupType => {
  console.log('Has Generic Permission By Entity Group Type:', hasGenericPermissionByEntityGroupType);
});
```

**14. hasGenericEntityGroupTypePermission**

```javascript
userPermissionsService.hasGenericEntityGroupTypePermission('your-operation-value', 'your-grouptype-value').subscribe(hasGenericEntityGroupTypePermission => {
  console.log('Has Generic Entity Group Type Permission:', hasGenericEntityGroupTypePermission);
});
```

**15. hasGenericEntityGroupPermission**

```javascript
userPermissionsService.hasGenericEntityGroupPermission('your-operation-value', 'your-entitygroup-value').subscribe(hasGenericEntityGroupPermission => {
  console.log('Has Generic Entity Group Permission:', hasGenericEntityGroupPermission);
});
```

**16. hasEntityGroupPermission**

```javascript
userPermissionsService.hasEntityGroupPermission('your-operation-value', 'your-entitygroup-value').subscribe(hasEntityGroupPermission => {
  console.log('Has Entity Group Permission:', hasEntityGroupPermission);
});
```

**17. hasGroupEntityPermission**

```javascript
userPermissionsService.hasGroupEntityPermission('your-operation-value', 'your-entitygroup-value').subscribe(hasGroupEntityPermission => {
  console.log('Has Group Entity Permission:', hasGroupEntityPermission);
});
```

**18. isOwnedGroup**

```javascript
userPermissionsService.isOwnedGroup('your-entitygroup-value').subscribe(isOwnedGroup => {
  console.log('Is Owned Group:', isOwnedGroup);
});
```

**19. getUserOwnerId**

```javascript
userPermissionsService.getUserOwnerId().subscribe(userOwnerId => {
  console.log('Get User Owner Id:', userOwnerId);
});
```

**20. isDirectOwner**

```javascript
userPermissionsService.isDirectOwner('your-owner-id').subscribe(isDirectOwner => {
  console.log('Is Direct Owner:', isDirectOwner);
});
```

**21. hasEntityTypeOperationPermission**

```javascript
userPermissionsService.hasEntityTypeOperationPermission('your-entitytype-value', 'your-operation-value', 'your-entitygroup-value').subscribe(hasEntityTypeOperationPermission => {
  console.log('Has Entity Type Operation Permission:', hasEntityTypeOperationPermission);
});
```

**22. hasResourcesGenericPermission**

```javascript
userPermissionsService.hasResourcesGenericPermission('your-resource-value', 'your-operation-value').subscribe(hasResourcesGenericPermission => {
  console.log('Has Resources Generic Permission:', hasResourcesGenericPermission);
});
```

**23. hasGenericResourcesPermission**

```javascript
userPermissionsService.hasGenericResourcesPermission('your-resources-value', 'your-operation-value').subscribe(hasGenericResourcesPermission => {
  console.log('Has Generic Resources Permission:', hasGenericResourcesPermission);
});
```

**24. hasGenericOperationsPermission**

```javascript
userPermissionsService.hasGenericOperationsPermission('your-resource-value', 'your-operations-value').subscribe(hasGenericOperationsPermission => {
  console.log('Has Generic Operations Permission:', hasGenericOperationsPermission);
});
```

**25. hasGenericAllPermission**

```javascript
userPermissionsService.hasGenericAllPermission('your-resource-value', 'your-operation-value').subscribe(hasGenericAllPermission => {
  console.log('Has Generic All Permission:', hasGenericAllPermission);
});
```

**26. hasGenericResourcePermission**

```javascript
userPermissionsService.hasGenericResourcePermission('your-resource-value', 'your-operation-value').subscribe(hasGenericResourcePermission => {
  console.log('Has Generic Resource Permission:', hasGenericResourcePermission);
});
```

**27. checkOperation**

```javascript
userPermissionsService.checkOperation('your-operations-value', 'your-operation-value').subscribe(operation => {
  console.log('Check Operation:', operation);
});
```

**28. checkEntityGroupPermission**

```javascript
userPermissionsService.checkEntityGroupPermission('your-operation-value', 'your-entitygroup-value', true).subscribe(entityGroupPermission => {
  console.log('Check Entity Group Permission:', entityGroupPermission);
});
```

**29. hasGroupPermissions**

```javascript
userPermissionsService.hasGroupPermissions('your-entitygroup-value', 'your-operation-value', true).subscribe(hasGroupPermissions => {
  console.log('Has Group Permissions:', hasGroupPermissions);
});
```

**30. isCurrentUserOwner**

```javascript
userPermissionsService.isCurrentUserOwner('your-entitygroup-value').subscribe(isCurrentUserOwner => {
  console.log('Is Current User Owner:', isCurrentUserOwner);
});
```

**31. containsId**

```javascript
userPermissionsService.containsId('your-idsarray-value', 'your--id').subscribe(containsId => {
  console.log('Contains Id:', containsId);
});
```

**32. idsEqual**

```javascript
userPermissionsService.idsEqual('your-id1-value', 'your-id2-value').subscribe(idsEqual => {
  console.log('Ids Equal:', idsEqual);
});
```
