# RESOURCE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
const resourceService = self.ctx.resourceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const resourceType = [];  // e.g. array of resource-type values
const resourceSubType = {  // ResourceSubType object
  // ... set the fields you need
};
resourceService.getResources(pageLink, resourceType, resourceSubType).subscribe(resources => {
  console.log('List of Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const resourceService = self.ctx.resourceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resourceService.getTenantResources(pageLink).subscribe(tenantResources => {
  console.log('List of Tenant Resources:', tenantResources);
});
```

**3. getResource**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
resourceService.getResource(resourceId).subscribe(resource => {
  console.log('Get Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
resourceService.getResourceInfoById(resourceId).subscribe(resourceInfoBy => {
  console.log('Get Resource Info By Id:', resourceInfoBy);
});
```

**5. getResourceInfo**

```javascript
const resourceService = self.ctx.resourceService;
const type = {  // ResourceType object
  // ... set the fields you need
};
const scope = {  // TBResourceScope object
  // ... set the fields you need
};
const key = 'key-value';
resourceService.getResourceInfo(type, scope, key).subscribe(resourceInfo => {
  console.log('Get Resource Info:', resourceInfo);
});
```

**6. downloadResource**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
resourceService.downloadResource(resourceId).subscribe(downloadResource => {
  console.log('Download Resource:', downloadResource);
});
```

**7. saveResources**

```javascript
const resourceService = self.ctx.resourceService;
const resources = [];  // e.g. array of resources values
resourceService.saveResources(resources).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**8. saveResource**

```javascript
const resourceService = self.ctx.resourceService;
const resource = {  // Resource object
  // ... set the fields you need
};
resourceService.saveResource(resource).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**9. uploadResources**

```javascript
const resourceService = self.ctx.resourceService;
const resources = [];  // e.g. array of resources values
resourceService.uploadResources(resources).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**10. uploadResource**

```javascript
const resourceService = self.ctx.resourceService;
const resource = {  // Resource object
  // ... set the fields you need
};
resourceService.uploadResource(resource).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**11. updatedResourceInfo**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
const updatedResources = {  // Partial<Omit<Resource object
  // ... set the fields you need
};
resourceService.updatedResourceInfo(resourceId, updatedResources).subscribe(saveddResourceInfo => {
  console.log('Saved Updated Resource Info:', saveddResourceInfo);
});
```

**12. updatedResourceData**

```javascript
const resourceService = self.ctx.resourceService;
const resourceId = 'your-resource-id';
const data = {  // File object
  // ... set the fields you need
};
resourceService.updatedResourceData(resourceId, data).subscribe(saveddResourceData => {
  console.log('Saved Updated Resource Data:', saveddResourceData);
});
```

**13. getResourcesByIds**

```javascript
const resourceService = self.ctx.resourceService;
const ids = [];  // e.g. array of ids values
resourceService.getResourcesByIds(ids).subscribe(resourcesBys => {
  console.log('List of Resources By Ids:', resourcesBys);
});
```
