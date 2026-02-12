### **RESOURCE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceservice = $injector.get(self.ctx.servicesMap.get('resourceservice'));

// Alternative: Direct context access
const resourceservice = self.ctx.resourceService;
```

**1. getResources**

```javascript
const resourceservice = self.ctx.resourceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resourceservice.getResources(pageLink).subscribe(resources => {
  console.log('Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const resourceservice = self.ctx.resourceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resourceservice.getTenantResources(pageLink).subscribe(tenantresources => {
  console.log('Tenantresources:', tenantresources);
});
```

**3. getResource**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.getResource('your-resource-id').subscribe(resource => {
  console.log('Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.getResourceInfoById('your-resource-id').subscribe(resourceinfobyid => {
  console.log('Resourceinfobyid:', resourceinfobyid);
});
```

**5. getResourceInfo**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.getResourceInfo(type, scope, 'your-key').subscribe(resourceinfo => {
  console.log('Resourceinfo:', resourceinfo);
});
```

**6. downloadResource**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.downloadResource('your-resource-id').subscribe(downresource => {
  console.log('Downresource:', downresource);
});
```

**7. saveResources**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.saveResources(resources).subscribe(saveresources => {
  console.log('Saveresources:', saveresources);
});
```

**8. saveResource**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.saveResource(resource).subscribe(saveresource => {
  console.log('Saveresource:', saveresource);
});
```

**9. uploadResources**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.uploadResources(resources).subscribe(upresources => {
  console.log('Upresources:', upresources);
});
```

**10. uploadResource**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.uploadResource(resource).subscribe(upresource => {
  console.log('Upresource:', upresource);
});
```

**11. updatedResourceInfo**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.updatedResourceInfo('your-resource-id', updatedResources).subscribe(updatedresourceinfo => {
  console.log('Updatedresourceinfo:', updatedresourceinfo);
});
```

**12. updatedResourceData**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.updatedResourceData('your-resource-id', data).subscribe(updatedresourcedata => {
  console.log('Updatedresourcedata:', updatedresourcedata);
});
```

**13. getResourcesByIds**

```javascript
const resourceservice = self.ctx.resourceService;
resourceservice.getResourcesByIds('your-ids-id').subscribe(resourcesbyids => {
  console.log('Resourcesbyids:', resourcesbyids);
});
```

