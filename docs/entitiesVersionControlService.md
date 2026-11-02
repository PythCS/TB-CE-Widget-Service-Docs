# ENTITIES VERSION CONTROL SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList().subscribe(branchList => {
  console.log('Clear Branch List:', branchList);
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(branches => {
  console.log('List Branches:', branches);
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo('your-externalentity-id', 'your-internalentity-id', 'your-version-id').subscribe(entityDataInfo => {
  console.log('Get Entity Data Info:', entityDataInfo);
});
```

**4. saveEntitiesVersion**

```javascript
entitiesVersionControlService.saveEntitiesVersion('your-request-value').subscribe(entitiesVersion => {
  console.log('Save Entities Version:', entitiesVersion);
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus('your-request-id').subscribe(versionCreateRequestStatus => {
  console.log('Get Version Create Request Status:', versionCreateRequestStatus);
});
```

**6. listEntityVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listEntityVersions(pageLink, 'your-branch-value', 'your-externalentity-id', 'your-internalentity-id').subscribe(entityVersions => {
  console.log('List Entity Versions:', entityVersions);
});
```

**7. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listEntityTypeVersions(pageLink, 'your-branch-value', 'your-entitytype-value').subscribe(entityTypeVersions => {
  console.log('List Entity Type Versions:', entityTypeVersions);
});
```

**8. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listVersions(pageLink, 'your-branch-value').subscribe(versions => {
  console.log('List Versions:', versions);
});
```

**9. loadEntitiesVersion**

```javascript
entitiesVersionControlService.loadEntitiesVersion('your-request-value').subscribe(loadEntitiesVersion => {
  console.log('Load Entities Version:', loadEntitiesVersion);
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus('your-request-id').subscribe(versionLoadRequestStatus => {
  console.log('Get Version Load Request Status:', versionLoadRequestStatus);
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion('your-entity-id', 'your-version-id').subscribe(compareEntityDataToVersion => {
  console.log('Compare Entity Data To Version:', compareEntityDataToVersion);
});
```

**12. entityLoadErrorToMessage**

```javascript
entitiesVersionControlService.entityLoadErrorToMessage('your-entityloaderror-value').subscribe(entityLoadErrorToMessage => {
  console.log('Entity Load Error To Message:', entityLoadErrorToMessage);
});
```
