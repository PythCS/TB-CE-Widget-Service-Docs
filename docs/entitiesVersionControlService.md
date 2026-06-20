# ENTITIES VERSION CONTROL SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ENTITIES VERSION CONTROL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList().subscribe(result => {
  console.log('Clear Branch List: result');
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(results => {
  console.log('List Branches: results');
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo('your-id', 'your-id').subscribe(entityDataInfo => {
  console.log('Get Entity Data Info: entityDataInfo');
});
```

**4. saveEntitiesVersion**

```javascript
const request = request;
entitiesVersionControlService.saveEntitiesVersion(request).subscribe(savedEntitiesVersion => {
  console.log('Save Entities Version: savedEntitiesVersion');
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus('your-id').subscribe(versioncreaterequeststatus => {
  console.log('Get Version Create Request Status:versioncreaterequeststatus');
});
```

**6. listEntityVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = branch;
entitiesVersionControlService.listEntityVersions(pageLink, branch, 'your-id').subscribe(results => {
  console.log('List Entity Versions: results');
});
```

**7. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = branch;
entitiesVersionControlService.listEntityTypeVersions(pageLink, branch, 'type').subscribe(results => {
  console.log('List Entity Type Versions: results');
});
```

**8. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = branch;
entitiesVersionControlService.listVersions(pageLink, branch).subscribe(results => {
  console.log('List Versions: results');
});
```

**9. loadEntitiesVersion**

```javascript
const request = request;
entitiesVersionControlService.loadEntitiesVersion(request).subscribe(result => {
  console.log('Load Entities Version: result');
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus('your-id').subscribe(versionloadrequeststatus => {
  console.log('Get Version Load Request Status:versionloadrequeststatus');
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion('your-entity-id', 'your-id').subscribe(result => {
  console.log('Compare Entity Data To Version:result');
});
```

**12. entityLoadErrorToMessage**

```javascript
const entityLoadError = entityLoadError;
entitiesVersionControlService.entityLoadErrorToMessage(entityLoadError).subscribe(result => {
  console.log('Entity Load Error To Message: result');
});
```
