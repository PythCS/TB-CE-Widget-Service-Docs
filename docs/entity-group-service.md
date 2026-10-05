# ENTITY GROUP SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityGroupService = $injector.get(self.ctx.servicesMap.get('entityGroupService'));

// Alternative: Direct context access
const entityGroupService = self.ctx.entityGroupService;
```

**1. getOwners**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityGroupService.getOwners(pageLink).subscribe(owners => {
  console.log('List of Owners:', owners);
});
```

**2. getOwnerInfos**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityGroupService.getOwnerInfos(pageLink).subscribe(ownerInfos => {
  console.log('List of Owner Infos:', ownerInfos);
});
```

**3. getOwnerInfo**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerId = {  // EntityId object
  // ... set the fields you need
};
entityGroupService.getOwnerInfo(ownerId).subscribe(ownerInfo => {
  console.log('Get Owner Info:', ownerInfo);
});
```

**4. getEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.getEntityGroup(entityGroupId).subscribe(entityGroup => {
  console.log('Get Entity Group:', entityGroup);
});
```

**5. getDeviceEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.getDeviceEntityGroup(entityGroupId).subscribe(deviceEntityGroup => {
  console.log('Get Device Entity Group:', deviceEntityGroup);
});
```

**6. fetchOtaPackageGroupInfo**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const group = {  // EntityGroupInfo object
  // ... set the fields you need
};
entityGroupService.fetchOtaPackageGroupInfo(group).subscribe(otaPackageGroupInfo => {
  console.log('Fetch Ota Package Group Info:', otaPackageGroupInfo);
});
```

**7. updateDeviceGroupOtaPackage**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const deviceGroupOtaPackage = {  // DeviceGroupOtaPackage object
  // ... set the fields you need
};
const otaPackageId = 'otaPackageId';  // e.g. one of the allowed OtaPackageId
const groupId = {  // EntityGroupId object
  // ... set the fields you need
};
const otaPackageType = {  // OtaUpdateType object
  // ... set the fields you need
};
entityGroupService.updateDeviceGroupOtaPackage(deviceGroupOtaPackage, otaPackageId, groupId, otaPackageType).subscribe(savedDeviceGroupOtaPackage => {
  console.log('Saved Device Group Ota Package:', savedDeviceGroupOtaPackage);
});
```

**8. saveDeviceGroupOtaPackage**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const deviceGroupOtaPackage = {  // DeviceGroupOtaPackage object
  // ... set the fields you need
};
entityGroupService.saveDeviceGroupOtaPackage(deviceGroupOtaPackage).subscribe(savedDeviceGroupOtaPackage => {
  console.log('Saved Device Group Ota Package:', savedDeviceGroupOtaPackage);
});
```

**9. saveDeviceEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroup = {  // DeviceEntityGroupInfo object
  // ... set the fields you need
};
const originalEntityGroup = {  // DeviceEntityGroupInfo object
  // ... set the fields you need
};
entityGroupService.saveDeviceEntityGroup(entityGroup, originalEntityGroup).subscribe(savedDeviceEntityGroup => {
  console.log('Saved Device Entity Group:', savedDeviceEntityGroup);
});
```

**10. getEntityGroupEntityInfo**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.getEntityGroupEntityInfo(entityGroupId).subscribe(entityGroupEntityInfo => {
  console.log('Get Entity Group Entity Info:', entityGroupEntityInfo);
});
```

**11. saveEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroup = {  // EntityGroup object
  // ... set the fields you need
};
entityGroupService.saveEntityGroup(entityGroup).subscribe(savedEntityGroup => {
  console.log('Saved Entity Group:', savedEntityGroup);
});
```

**12. makeEntityGroupPublic**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.makeEntityGroupPublic(entityGroupId).subscribe(makeEntityGroupPublic => {
  console.log('Make Entity Group Public:', makeEntityGroupPublic);
});
```

**13. makeEntityGroupPrivate**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
entityGroupService.makeEntityGroupPrivate(entityGroupId).subscribe(makeEntityGroupPrivate => {
  console.log('Make Entity Group Private:', makeEntityGroupPrivate);
});
```

**14. shareEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const shareGroupRequest = {  // ShareGroupRequest object
  // ... set the fields you need
};
entityGroupService.shareEntityGroup(entityGroupId, shareGroupRequest).subscribe(shareEntityGroup => {
  console.log('Share Entity Group:', shareEntityGroup);
});
```

**15. shareEntityGroupV2**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const shareGroupRequest = {  // ShareGroupRequest object
  // ... set the fields you need
};
entityGroupService.shareEntityGroupV2(entityGroupId, shareGroupRequest).subscribe(shareEntityGroupV2 => {
  console.log('Share Entity Group V2:', shareEntityGroupV2);
});
```

**16. getEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroups(pageLink, groupType).subscribe(entityGroups => {
  console.log('List of Entity Groups:', entityGroups);
});
```

**17. getEntityGroupEntityInfos**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupEntityInfos(pageLink, groupType).subscribe(entityGroupEntityInfos => {
  console.log('List of Entity Group Entity Infos:', entityGroupEntityInfos);
});
```

**18. getAllEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageSize = 10;
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroups(pageSize, groupType).subscribe(allEntityGroups => {
  console.log('List of All Entity Groups:', allEntityGroups);
});
```

**19. getAllEntityGroupsByPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroupsByPageLink(pageLink, groupType).subscribe(allEntityGroupsByPageLinks => {
  console.log('List of All Entity Groups By Page Links:', allEntityGroupsByPageLinks);
});
```

**20. getSharedEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getSharedEntityGroups(pageLink, groupType).subscribe(sharedEntityGroups => {
  console.log('List of Shared Entity Groups:', sharedEntityGroups);
});
```

**21. getSharedEntityGroupEntityInfos**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getSharedEntityGroupEntityInfos(pageLink, groupType).subscribe(sharedEntityGroupEntityInfos => {
  console.log('List of Shared Entity Group Entity Infos:', sharedEntityGroupEntityInfos);
});
```

**22. getEntityGroupIdsForEntityId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityId = 'your-entity-id';
entityGroupService.getEntityGroupIdsForEntityId(entityType, entityId).subscribe(entityGroupIdsForEntitys => {
  console.log('List of Entity Group Ids For Entity Ids:', entityGroupIdsForEntitys);
});
```

**23. getEntityGroupsByIds**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityGroupService.getEntityGroupsByIds(entityGroupIds).subscribe(entityGroupsBys => {
  console.log('List of Entity Groups By Ids:', entityGroupsBys);
});
```

**24. getEntityGroupEntityInfosByIds**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityGroupService.getEntityGroupEntityInfosByIds(entityGroupIds).subscribe(entityGroupEntityInfosBys => {
  console.log('List of Entity Group Entity Infos By Ids:', entityGroupEntityInfosBys);
});
```

**25. getEntityGroupsHierarchyByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupsHierarchyByOwnerId(pageLink, ownerType, ownerId, groupType).subscribe(entityGroupsHierarchyByOwners => {
  console.log('List of Entity Groups Hierarchy By Owner Ids:', entityGroupsHierarchyByOwners);
});
```

**26. getEntityGroupEntityInfosHierarchyByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupEntityInfosHierarchyByOwnerId(pageLink, ownerType, ownerId, groupType).subscribe(entityGroupEntityInfosHierarchyByOwners => {
  console.log('List of Entity Group Entity Infos Hierarchy By Owner Ids:', entityGroupEntityInfosHierarchyByOwners);
});
```

**27. getEntityGroupsByOwnerIdAndPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityGroupService.getEntityGroupsByOwnerIdAndPageLink(ownerType, ownerId, groupType, pageLink).subscribe(entityGroupsByOwnerIdAndPageLinks => {
  console.log('List of Entity Groups By Owner Id And Page Links:', entityGroupsByOwnerIdAndPageLinks);
});
```

**28. getEntityGroupsByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupsByOwnerId(ownerType, ownerId, groupType).subscribe(entityGroupsByOwners => {
  console.log('List of Entity Groups By Owner Ids:', entityGroupsByOwners);
});
```

**29. getEntityGroupEntityInfosByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupEntityInfosByOwnerId(pageLink, ownerType, ownerId, groupType).subscribe(entityGroupEntityInfosByOwners => {
  console.log('List of Entity Group Entity Infos By Owner Ids:', entityGroupEntityInfosByOwners);
});
```

**30. getAllEntityGroupsByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageSize = 10;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroupsByOwnerId(pageSize, ownerType, ownerId, groupType).subscribe(allEntityGroupsByOwners => {
  console.log('List of All Entity Groups By Owner Ids:', allEntityGroupsByOwners);
});
```

**31. getAllEntityGroupsByOwnerIdAndPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEntityGroupsByOwnerIdAndPageLink(pageLink, ownerType, ownerId, groupType).subscribe(allEntityGroupsByOwnerIdAndPageLinks => {
  console.log('List of All Entity Groups By Owner Id And Page Links:', allEntityGroupsByOwnerIdAndPageLinks);
});
```

**32. getEntityGroupsByPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupsByPageLink(pageLink, groupType).subscribe(entityGroupsByPageLinks => {
  console.log('List of Entity Groups By Page Links:', entityGroupsByPageLinks);
});
```

**33. getEntityGroupAllByOwnerId**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerType = {  // EntityType object
  // ... set the fields you need
};
const ownerId = 'your-owner-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEntityGroupAllByOwnerId(ownerType, ownerId, groupType).subscribe(entityGroupAllByOwner => {
  console.log('Get Entity Group All By Owner Id:', entityGroupAllByOwner);
});
```

**34. addEntityToEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityId = 'your-entity-id';
entityGroupService.addEntityToEntityGroup(entityGroupId, entityId).subscribe(addEntityToEntityGroup => {
  console.log('Add Entity To Entity Group:', addEntityToEntityGroup);
});
```

**35. addEntitiesToEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityGroupService.addEntitiesToEntityGroup(entityGroupId, entityIds).subscribe(addEntitiesToEntityGroup => {
  console.log('Add Entities To Entity Group:', addEntitiesToEntityGroup);
});
```

**36. changeEntityOwner**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const ownerId = {  // EntityId object
  // ... set the fields you need
};
const entityId = {  // EntityId object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityGroupService.changeEntityOwner(ownerId, entityId, entityGroupIds).subscribe(changeEntityOwner => {
  console.log('Change Entity Owner:', changeEntityOwner);
});
```

**37. removeEntityFromEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityId = 'your-entity-id';
entityGroupService.removeEntityFromEntityGroup(entityGroupId, entityId).subscribe(result => {
  console.log('Delete Entity From Entity Group result:', result);
});
```

**38. removeEntitiesFromEntityGroup**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityGroupService.removeEntitiesFromEntityGroup(entityGroupId, entityIds).subscribe(result => {
  console.log('Delete Entities From Entity Group result:', result);
});
```

**39. getEntityGroupEntity**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const entityGroupId = 'your-entity-group-id';
const entityId = 'your-entity-id';
entityGroupService.getEntityGroupEntity(entityGroupId, entityId).subscribe(entityGroupEntity => {
  console.log('Get Entity Group Entity:', entityGroupEntity);
});
```

**40. getEdgeEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const edgeId = 'your-edge-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getEdgeEntityGroups(pageLink, edgeId, groupType).subscribe(edgeEntityGroups => {
  console.log('List of Edge Entity Groups:', edgeEntityGroups);
});
```

**41. getAllEdgeEntityGroups**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageSize = 10;
const edgeId = 'your-edge-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEdgeEntityGroups(pageSize, edgeId, groupType).subscribe(allEdgeEntityGroups => {
  console.log('List of All Edge Entity Groups:', allEdgeEntityGroups);
});
```

**42. getAllEdgeEntityGroupsByPageLink**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const edgeId = 'your-edge-id';
const groupType = {  // EntityType object
  // ... set the fields you need
};
entityGroupService.getAllEdgeEntityGroupsByPageLink(pageLink, edgeId, groupType).subscribe(allEdgeEntityGroupsByPageLinks => {
  console.log('List of All Edge Entity Groups By Page Links:', allEdgeEntityGroupsByPageLinks);
});
```

**43. assignEntityGroupToEdge**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const edgeId = 'your-edge-id';
const entityGroupId = 'your-entity-group-id';
const groupType = 'your-group-type';
entityGroupService.assignEntityGroupToEdge(edgeId, entityGroupId, groupType).subscribe(assignEntityGroupToEdge => {
  console.log('Assign Entity Group To Edge:', assignEntityGroupToEdge);
});
```

**44. unassignEntityGroupFromEdge**

```javascript
const entityGroupService = self.ctx.entityGroupService;
const edgeId = 'your-edge-id';
const entityGroupId = 'your-entity-group-id';
const groupType = 'your-group-type';
entityGroupService.unassignEntityGroupFromEdge(edgeId, entityGroupId, groupType).subscribe(unassignEntityGroupFromEdge => {
  console.log('Unassign Entity Group From Edge:', unassignEntityGroupFromEdge);
});
```
