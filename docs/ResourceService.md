# ResourceService

### **RESOURCESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
resourceService.getResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-resourcetype', 'your-resourcesubtype', { /* your config */ }).subscribe(reource => {
  console.log('Resources:', reource);
});
```

**2. getTenantResources**

```javascript
resourceService.getTenantResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantreource => {
  console.log('Tenant Resources:', tenantreource);
});
```

**3. getResource**

```javascript
resourceService.getResource('your-resource-id', { /* your config */ }).subscribe(resource => {
  console.log('Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
resourceService.getResourceInfoById('your-resource-id', { /* your config */ }).subscribe(resourceinfobyid => {
  console.log('Resource Info By Id:', resourceinfobyid);
});
```

**5. getResourceInfo**

```javascript
resourceService.getResourceInfo('your-type', { /* your scope */ }, 'your-key', { /* your config */ }).subscribe(resourceinfo => {
  console.log('Resource Info:', resourceinfo);
});
```

**6. downloadResource**

```javascript
resourceService.downloadResource('your-resource-id').subscribe(result => {
  console.log('Result:', result);
});
```

**7. saveResources**

```javascript
resourceService.saveResources(['id1', 'id2'], { /* your config */ }).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**8. saveResource**

```javascript
resourceService.saveResource({ /* your resource */ }, { /* your config */ }).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**9. uploadResources**

```javascript
resourceService.uploadResources(['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. uploadResource**

```javascript
resourceService.uploadResource({ /* your resource */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. updatedResourceInfo**

```javascript
resourceService.updatedResourceInfo('your-resource-id', { /* your updatedResources */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. updatedResourceData**

```javascript
resourceService.updatedResourceData('your-resource-id', { /* your data */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. getResourcesByIds**

```javascript
resourceService.getResourcesByIds(['id1', 'id2'], { /* your config */ }).subscribe(reourcebyid => {
  console.log('Resources By Ids:', reourcebyid);
});
```
