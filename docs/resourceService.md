# RESOURCE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **RESOURCE SERVICE**

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
resourceService.getResources(pageLink, 'type', 'type').subscribe(resources => {
  console.log('Get Resources: resources');
});
```

**2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resourceService.getTenantResources(pageLink).subscribe(tenantresources => {
  console.log('Get Tenant Resources: tenantresources');
});
```

**3. getResource**

```javascript
resourceService.getResource('your-resource-id').subscribe(resource => {
  console.log('Get Resource: resource');
});
```

**4. getResourceInfoById**

```javascript
resourceService.getResourceInfoById('your-resource-id').subscribe(resourceInfoById => {
  console.log('Get Resource Info By Id: resourceInfoById');
});
```

**5. getResourceInfo**

```javascript
const key = key;
resourceService.getResourceInfo('type', 'SERVER_SCOPE', key).subscribe(resourceInfo => {
  console.log('Get Resource Info: resourceInfo');
});
```

**6. downloadResource**

```javascript
resourceService.downloadResource('your-resource-id').subscribe(result => {
  console.log('Download Resource: result');
});
```

**7. saveResources**

```javascript
const resources = resources;
resourceService.saveResources(resources).subscribe(savedResources => {
  console.log('Save Resources: savedResources');
});
```

**8. saveResource**

```javascript
const resource = resource;
resourceService.saveResource(resource).subscribe(savedResource => {
  console.log('Save Resource: savedResource');
});
```

**9. uploadResources**

```javascript
const resources = resources;
resourceService.uploadResources(resources).subscribe(result => {
  console.log('Upload Resources: result');
});
```

**10. uploadResource**

```javascript
const resource = resource;
resourceService.uploadResource(resource).subscribe(result => {
  console.log('Upload Resource: result');
});
```

**11. updatedResourceInfo**

```javascript
const updatedResources = updatedResources;
resourceService.updatedResourceInfo('your-resource-id', updatedResources).subscribe(result => {
  console.log('Updated Resource Info: result');
});
```

**12. updatedResourceData**

```javascript
const data = data;
resourceService.updatedResourceData('your-resource-id', data).subscribe(result => {
  console.log('Updated Resource Data: result');
});
```

**13. getResourcesByIds**

```javascript
resourceService.getResourcesByIds('your-id').subscribe(resourcesbyids => {
  console.log('Get Resources By Ids: resourcesbyids');
});
```
