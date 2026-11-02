# RESOURCE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.resourceService.getResources(pageLink, 'your-resourcetype-value', 'your-resourcesubtype-value').subscribe(resources => {
  console.log('Get Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.resourceService.getTenantResources(pageLink).subscribe(tenantResources => {
  console.log('Get Tenant Resources:', tenantResources);
});
```

**3. getResource**

```javascript
self.ctx.resourceService.getResource('your-resource-id').subscribe(resource => {
  console.log('Get Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
self.ctx.resourceService.getResourceInfoById('your-resource-id').subscribe(resourceInfoById => {
  console.log('Get Resource Info By Id:', resourceInfoById);
});
```

**5. getResourceInfo**

```javascript
self.ctx.resourceService.getResourceInfo('your-type-value', 'your-scope-value', 'your-key-value').subscribe(resourceInfo => {
  console.log('Get Resource Info:', resourceInfo);
});
```

**6. downloadResource**

```javascript
self.ctx.resourceService.downloadResource('your-resource-id').subscribe(downloadResource => {
  console.log('Download Resource:', downloadResource);
});
```

**7. saveResources**

```javascript
self.ctx.resourceService.saveResources('your-resources-value').subscribe(resources => {
  console.log('Save Resources:', resources);
});
```

**8. saveResource**

```javascript
self.ctx.resourceService.saveResource('your-resource-value').subscribe(resource => {
  console.log('Save Resource:', resource);
});
```

**9. uploadResources**

```javascript
self.ctx.resourceService.uploadResources('your-resources-value').subscribe(uploadResources => {
  console.log('Upload Resources:', uploadResources);
});
```

**10. uploadResource**

```javascript
self.ctx.resourceService.uploadResource('your-resource-value').subscribe(uploadResource => {
  console.log('Upload Resource:', uploadResource);
});
```

**11. updatedResourceInfo**

```javascript
self.ctx.resourceService.updatedResourceInfo('your-resource-id', 'your-updatedresources-value').subscribe(dResourceInfo => {
  console.log('Updated Resource Info:', dResourceInfo);
});
```

**12. updatedResourceData**

```javascript
self.ctx.resourceService.updatedResourceData('your-resource-id', 'your-data-value').subscribe(dResourceData => {
  console.log('Updated Resource Data:', dResourceData);
});
```

**13. getResourcesByIds**

```javascript
self.ctx.resourceService.getResourcesByIds('your-ids-value').subscribe(resourcesByIds => {
  console.log('Get Resources By Ids:', resourcesByIds);
});
```
