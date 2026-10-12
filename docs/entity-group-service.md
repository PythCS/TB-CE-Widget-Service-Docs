# ENTITY GROUP SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityGroupService = $injector.get(self.ctx.servicesMap.get('entityGroupService'));

// Alternative: Direct context access
const entityGroupService = self.ctx.entityGroupService;
```

**1. getOwners**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getOwners(pageLink).subscribe(owners => {
  console.log('Get Owners:', owners);
});
```

**2. getOwnerInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getOwnerInfos(pageLink).subscribe(ownerInfos => {
  console.log('Get Owner Infos:', ownerInfos);
});
```

**3. getOwnerInfo**

```javascript
self.ctx.entityGroupService.getOwnerInfo('your-owner-id').subscribe(ownerInfo => {
  console.log('Get Owner Info:', ownerInfo);
});
```

**4. getEntityGroup**

```javascript
self.ctx.entityGroupService.getEntityGroup('your-entitygroup-id').subscribe(entityGroup => {
  console.log('Get Entity Group:', entityGroup);
});
```

**5. getDeviceEntityGroup**

```javascript
self.ctx.entityGroupService.getDeviceEntityGroup('your-entitygroup-id').subscribe(deviceEntityGroup => {
  console.log('Get Device Entity Group:', deviceEntityGroup);
});
```

**6. fetchOtaPackageGroupInfo**

```javascript
self.ctx.entityGroupService.fetchOtaPackageGroupInfo('your-group-value').subscribe(fetchOtaPackageGroupInfo => {
  console.log('Fetch Ota Package Group Info:', fetchOtaPackageGroupInfo);
});
```

**7. updateDeviceGroupOtaPackage**

```javascript
self.ctx.entityGroupService.updateDeviceGroupOtaPackage('your-devicegroupotapackage-value', 'your-otapackage-id', 'your-group-id', 'your-otapackagetype-value').subscribe(deviceGroupOtaPackage => {
  console.log('Update Device Group Ota Package:', deviceGroupOtaPackage);
});
```

**8. saveDeviceGroupOtaPackage**

```javascript
self.ctx.entityGroupService.saveDeviceGroupOtaPackage('your-devicegroupotapackage-value').subscribe(deviceGroupOtaPackage => {
  console.log('Save Device Group Ota Package:', deviceGroupOtaPackage);
});
```

**9. saveDeviceEntityGroup**

```javascript
self.ctx.entityGroupService.saveDeviceEntityGroup('your-entitygroup-value', 'your-originalentitygroup-value').subscribe(deviceEntityGroup => {
  console.log('Save Device Entity Group:', deviceEntityGroup);
});
```

**10. getEntityGroupEntityInfo**

```javascript
self.ctx.entityGroupService.getEntityGroupEntityInfo('your-entitygroup-id').subscribe(entityGroupEntityInfo => {
  console.log('Get Entity Group Entity Info:', entityGroupEntityInfo);
});
```

**11. saveEntityGroup**

```javascript
self.ctx.entityGroupService.saveEntityGroup('your-entitygroup-value').subscribe(entityGroup => {
  console.log('Save Entity Group:', entityGroup);
});
```

**12. makeEntityGroupPublic**

```javascript
self.ctx.entityGroupService.makeEntityGroupPublic('your-entitygroup-id').subscribe(makeEntityGroupPublic => {
  console.log('Make Entity Group Public:', makeEntityGroupPublic);
});
```

**13. makeEntityGroupPrivate**

```javascript
self.ctx.entityGroupService.makeEntityGroupPrivate('your-entitygroup-id').subscribe(makeEntityGroupPrivate => {
  console.log('Make Entity Group Private:', makeEntityGroupPrivate);
});
```

**14. shareEntityGroup**

```javascript
self.ctx.entityGroupService.shareEntityGroup('your-entitygroup-id', 'your-sharegrouprequest-value').subscribe(shareEntityGroup => {
  console.log('Share Entity Group:', shareEntityGroup);
});
```

**15. shareEntityGroupV2**

```javascript
self.ctx.entityGroupService.shareEntityGroupV2('your-entitygroup-id', 'your-sharegrouprequest-value').subscribe(shareEntityGroupV2 => {
  console.log('Share Entity Group V 2:', shareEntityGroupV2);
});
```

**16. getEntityGroups**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroups(pageLink, 'your-grouptype-value').subscribe(entityGroups => {
  console.log('Get Entity Groups:', entityGroups);
});
```

**17. getEntityGroupEntityInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupEntityInfos(pageLink, 'your-grouptype-value').subscribe(entityGroupEntityInfos => {
  console.log('Get Entity Group Entity Infos:', entityGroupEntityInfos);
});
```

**18. getAllEntityGroups**

```javascript
self.ctx.entityGroupService.getAllEntityGroups(0, 'your-grouptype-value').subscribe(allEntityGroups => {
  console.log('Get All Entity Groups:', allEntityGroups);
});
```

**19. getAllEntityGroupsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getAllEntityGroupsByPageLink(pageLink, 'your-grouptype-value').subscribe(allEntityGroupsByPageLink => {
  console.log('Get All Entity Groups By Page Link:', allEntityGroupsByPageLink);
});
```

**20. getSharedEntityGroups**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getSharedEntityGroups(pageLink, 'your-grouptype-value').subscribe(sharedEntityGroups => {
  console.log('Get Shared Entity Groups:', sharedEntityGroups);
});
```

**21. getSharedEntityGroupEntityInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getSharedEntityGroupEntityInfos(pageLink, 'your-grouptype-value').subscribe(sharedEntityGroupEntityInfos => {
  console.log('Get Shared Entity Group Entity Infos:', sharedEntityGroupEntityInfos);
});
```

**22. getEntityGroupIdsForEntityId**

```javascript
self.ctx.entityGroupService.getEntityGroupIdsForEntityId('your-entitytype-value', 'your-entity-id').subscribe(entityGroupIdsForEntityId => {
  console.log('Get Entity Group Ids For Entity Id:', entityGroupIdsForEntityId);
});
```

**23. getEntityGroupsByIds**

```javascript
self.ctx.entityGroupService.getEntityGroupsByIds('your-entitygroupids-value').subscribe(entityGroupsByIds => {
  console.log('Get Entity Groups By Ids:', entityGroupsByIds);
});
```

**24. getEntityGroupEntityInfosByIds**

```javascript
self.ctx.entityGroupService.getEntityGroupEntityInfosByIds('your-entitygroupids-value').subscribe(entityGroupEntityInfosByIds => {
  console.log('Get Entity Group Entity Infos By Ids:', entityGroupEntityInfosByIds);
});
```

**25. getEntityGroupsHierarchyByOwnerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupsHierarchyByOwnerId(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupsHierarchyByOwnerId => {
  console.log('Get Entity Groups Hierarchy By Owner Id:', entityGroupsHierarchyByOwnerId);
});
```

**26. getEntityGroupEntityInfosHierarchyByOwnerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupEntityInfosHierarchyByOwnerId(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupEntityInfosHierarchyByOwnerId => {
  console.log('Get Entity Group Entity Infos Hierarchy By Owner Id:', entityGroupEntityInfosHierarchyByOwnerId);
});
```

**27. getEntityGroupsByOwnerIdAndPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupsByOwnerIdAndPageLink('your-ownertype-value', 'your-owner-id', 'your-grouptype-value', pageLink).subscribe(entityGroupsByOwnerIdAndPageLink => {
  console.log('Get Entity Groups By Owner Id And Page Link:', entityGroupsByOwnerIdAndPageLink);
});
```

**28. getEntityGroupsByOwnerId**

```javascript
self.ctx.entityGroupService.getEntityGroupsByOwnerId('your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupsByOwnerId => {
  console.log('Get Entity Groups By Owner Id:', entityGroupsByOwnerId);
});
```

**29. getEntityGroupEntityInfosByOwnerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupEntityInfosByOwnerId(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupEntityInfosByOwnerId => {
  console.log('Get Entity Group Entity Infos By Owner Id:', entityGroupEntityInfosByOwnerId);
});
```

**30. getAllEntityGroupsByOwnerId**

```javascript
self.ctx.entityGroupService.getAllEntityGroupsByOwnerId(0, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(allEntityGroupsByOwnerId => {
  console.log('Get All Entity Groups By Owner Id:', allEntityGroupsByOwnerId);
});
```

**31. getAllEntityGroupsByOwnerIdAndPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getAllEntityGroupsByOwnerIdAndPageLink(pageLink, 'your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(allEntityGroupsByOwnerIdAndPageLink => {
  console.log('Get All Entity Groups By Owner Id And Page Link:', allEntityGroupsByOwnerIdAndPageLink);
});
```

**32. getEntityGroupsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEntityGroupsByPageLink(pageLink, 'your-grouptype-value').subscribe(entityGroupsByPageLink => {
  console.log('Get Entity Groups By Page Link:', entityGroupsByPageLink);
});
```

**33. getEntityGroupAllByOwnerId**

```javascript
self.ctx.entityGroupService.getEntityGroupAllByOwnerId('your-ownertype-value', 'your-owner-id', 'your-grouptype-value').subscribe(entityGroupAllByOwnerId => {
  console.log('Get Entity Group All By Owner Id:', entityGroupAllByOwnerId);
});
```

**34. addEntityToEntityGroup**

```javascript
self.ctx.entityGroupService.addEntityToEntityGroup('your-entitygroup-id', 'your-entity-id').subscribe(addEntityToEntityGroup => {
  console.log('Add Entity To Entity Group:', addEntityToEntityGroup);
});
```

**35. addEntitiesToEntityGroup**

```javascript
self.ctx.entityGroupService.addEntitiesToEntityGroup('your-entitygroup-id', 'your-entityids-value').subscribe(addEntitiesToEntityGroup => {
  console.log('Add Entities To Entity Group:', addEntitiesToEntityGroup);
});
```

**36. changeEntityOwner**

```javascript
self.ctx.entityGroupService.changeEntityOwner('your-owner-id', 'your-entity-id', 'your-entitygroupids-value').subscribe(changeEntityOwner => {
  console.log('Change Entity Owner:', changeEntityOwner);
});
```

**37. removeEntityFromEntityGroup**

```javascript
self.ctx.entityGroupService.removeEntityFromEntityGroup('your-entitygroup-id', 'your-entity-id').subscribe(entityFromEntityGroup => {
  console.log('Remove Entity From Entity Group:', entityFromEntityGroup);
});
```

**38. removeEntitiesFromEntityGroup**

```javascript
self.ctx.entityGroupService.removeEntitiesFromEntityGroup('your-entitygroup-id', 'your-entityids-value').subscribe(entitiesFromEntityGroup => {
  console.log('Remove Entities From Entity Group:', entitiesFromEntityGroup);
});
```

**39. getEntityGroupEntity**

```javascript
self.ctx.entityGroupService.getEntityGroupEntity('your-entitygroup-id', 'your-entity-id').subscribe(entityGroupEntity => {
  console.log('Get Entity Group Entity:', entityGroupEntity);
});
```

**40. getEdgeEntityGroups**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getEdgeEntityGroups(pageLink, 'your-edge-id', 'your-grouptype-value').subscribe(edgeEntityGroups => {
  console.log('Get Edge Entity Groups:', edgeEntityGroups);
});
```

**41. getAllEdgeEntityGroups**

```javascript
self.ctx.entityGroupService.getAllEdgeEntityGroups(0, 'your-edge-id', 'your-grouptype-value').subscribe(allEdgeEntityGroups => {
  console.log('Get All Edge Entity Groups:', allEdgeEntityGroups);
});
```

**42. getAllEdgeEntityGroupsByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityGroupService.getAllEdgeEntityGroupsByPageLink(pageLink, 'your-edge-id', 'your-grouptype-value').subscribe(allEdgeEntityGroupsByPageLink => {
  console.log('Get All Edge Entity Groups By Page Link:', allEdgeEntityGroupsByPageLink);
});
```

**43. assignEntityGroupToEdge**

```javascript
self.ctx.entityGroupService.assignEntityGroupToEdge('your-edge-id', 'your-entitygroup-id', 'your-grouptype-value').subscribe(entityGroupToEdge => {
  console.log('Assign Entity Group To Edge:', entityGroupToEdge);
});
```

**44. unassignEntityGroupFromEdge**

```javascript
self.ctx.entityGroupService.unassignEntityGroupFromEdge('your-edge-id', 'your-entitygroup-id', 'your-grouptype-value').subscribe(entityGroupFromEdge => {
  console.log('Unassign Entity Group From Edge:', entityGroupFromEdge);
});
```
