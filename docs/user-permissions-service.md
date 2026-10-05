# USER PERMISSIONS SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
```

**1. loadPermissionsInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
userPermissionsService.loadPermissionsInfo().subscribe(permissionsInfo => {
  console.log('Load Permissions Info:', permissionsInfo);
});
```

**2. hasEntityPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
userPermissionsService.hasEntityPermission(entityId, operation).subscribe(hasEntityPermission => {
  console.log('Has Entity Permission:', hasEntityPermission);
});
```

**3. getOperationsByResource**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const result = userPermissionsService.getOperationsByResource(resource);
console.log('Result:', result);
```

**4. getAllowedGroupRoleOperations**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.getAllowedGroupRoleOperations();
console.log('Result:', result);
```

**5. getAllowedResources**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.getAllowedResources();
console.log('Result:', result);
```

**6. hasReadGroupsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasReadGroupsPermission(entityType);
console.log('Result:', result);
```

**7. hasGenericReadGroupsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericReadGroupsPermission(entityType);
console.log('Result:', result);
```

**8. hasSharedReadGroupsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasSharedReadGroupsPermission(entityType);
console.log('Result:', result);
```

**9. hasReadGenericPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const result = userPermissionsService.hasReadGenericPermission(resource);
console.log('Result:', result);
```

**10. hasGenericPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericPermission(resource, operation);
console.log('Result:', result);
```

**11. isAiEnabled**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.isAiEnabled();
console.log('Result:', result);
```

**12. isResourceAllowed**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const result = userPermissionsService.isResourceAllowed(resource);
console.log('Result:', result);
```

**13. hasGenericPermissionByEntityGroupType**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const groupType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericPermissionByEntityGroupType(operation, groupType);
console.log('Result:', result);
```

**14. hasGenericEntityGroupTypePermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const groupType = {  // EntityType object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericEntityGroupTypePermission(operation, groupType);
console.log('Result:', result);
```

**15. hasGenericEntityGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroup object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericEntityGroupPermission(operation, entityGroup);
console.log('Result:', result);
```

**16. hasEntityGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.hasEntityGroupPermission(operation, entityGroup);
console.log('Result:', result);
```

**17. hasGroupEntityPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.hasGroupEntityPermission(operation, entityGroup);
console.log('Result:', result);
```

**18. isOwnedGroup**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.isOwnedGroup(entityGroup);
console.log('Result:', result);
```

**19. getUserOwnerId**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const result = userPermissionsService.getUserOwnerId();
console.log('Result:', result);
```

**20. isDirectOwner**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const ownerId = {  // EntityId object
  // ... set the fields you need
};
const result = userPermissionsService.isDirectOwner(ownerId);
console.log('Result:', result);
```

**21. hasEntityTypeOperationPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.hasEntityTypeOperationPermission(entityType, operation, entityGroup);
console.log('Result:', result);
```

**22. hasResourcesGenericPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = [];  // e.g. array of resource values
const operation = [];  // e.g. array of operation values
const result = userPermissionsService.hasResourcesGenericPermission(resource, operation);
console.log('Result:', result);
```

**23. hasGenericResourcesPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resources = [];  // e.g. array of resources values
const operation = [];  // e.g. array of operation values
const result = userPermissionsService.hasGenericResourcesPermission(resources, operation);
console.log('Result:', result);
```

**24. hasGenericOperationsPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = [];  // e.g. array of resource values
const operations = [];  // e.g. array of operations values
const result = userPermissionsService.hasGenericOperationsPermission(resource, operations);
console.log('Result:', result);
```

**25. hasGenericAllPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericAllPermission(resource, operation);
console.log('Result:', result);
```

**26. hasGenericResourcePermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const resource = {  // Resource object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.hasGenericResourcePermission(resource, operation);
console.log('Result:', result);
```

**27. checkOperation**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operations = [];  // e.g. array of operations values
const operation = {  // Operation object
  // ... set the fields you need
};
const result = userPermissionsService.checkOperation(operations, operation);
console.log('Result:', result);
```

**28. checkEntityGroupPermission**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const operation = {  // Operation object
  // ... set the fields you need
};
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const isGroup = true;
const result = userPermissionsService.checkEntityGroupPermission(operation, entityGroup, isGroup);
console.log('Result:', result);
```

**29. hasGroupPermissions**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const operation = {  // Operation object
  // ... set the fields you need
};
const isGroup = true;
const result = userPermissionsService.hasGroupPermissions(entityGroup, operation, isGroup);
console.log('Result:', result);
```

**30. isCurrentUserOwner**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const entityGroup = {  // EntityGroupInfo object
  // ... set the fields you need
};
const result = userPermissionsService.isCurrentUserOwner(entityGroup);
console.log('Result:', result);
```

**31. containsId**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const idsArray = [];  // e.g. array of ids-array values
const id = {  // EntityId object
  // ... set the fields you need
};
const result = userPermissionsService.containsId(idsArray, id);
console.log('Result:', result);
```

**32. idsEqual**

```javascript
const $injector = self.ctx.$scope.$injector;
const userPermissionsService = $injector.get(self.ctx.servicesMap.get('userPermissionsService'));
const id1 = {  // EntityId object
  // ... set the fields you need
};
const id2 = {  // EntityId object
  // ... set the fields you need
};
const result = userPermissionsService.idsEqual(id1, id2);
console.log('Result:', result);
```
