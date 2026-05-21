# ResourceService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('ResourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
resourceService.getResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-resourcetype-value', 'your-resourcesubtype-value').subscribe(result => {
  console.log('Fetched  Resources result:', result);
});
```

**2. getTenantResources**

```javascript
resourceService.getTenantResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Resources tenant:', tenant);
});
```

**3. getResource**

```javascript
resourceService.getResource('your-resource-id').subscribe(result => {
  console.log('Fetched  Resource result:', result);
});
```

**4. getResourceInfoById**

```javascript
resourceService.getResourceInfoById('your-resource-id').subscribe(info => {
  console.log('Fetched  Resource Info By Id info:', info);
});
```

**5. getResourceInfo**

```javascript
resourceService.getResourceInfo('your-type-value', 'your-scope-value', 'your-api-key').subscribe(info => {
  console.log('Fetched  Resource Info info:', info);
});
```

**6. downloadResource**

```javascript
resourceService.downloadResource('your-resource-id').subscribe(result => {
  console.log('download Resource result:', result);
});
```

**7. saveResources**

```javascript
resourceService.saveResources('your-resources-value').subscribe(result => {
  console.log('Saved  Resources result:', result);
});
```

**8. saveResource**

```javascript
resourceService.saveResource('your-resource-value').subscribe(result => {
  console.log('Saved  Resource result:', result);
});
```

**9. uploadResources**

```javascript
resourceService.uploadResources('your-resources-value').subscribe(result => {
  console.log('upload Resources result:', result);
});
```

**10. uploadResource**

```javascript
resourceService.uploadResource('your-resource-value').subscribe(result => {
  console.log('upload Resource result:', result);
});
```

**11. updatedResourceInfo**

```javascript
resourceService.updatedResourceInfo('your-resource-id', 'your-updatedresources-value').subscribe(info => {
  console.log('updated Resource Info info:', info);
});
```

**12. updatedResourceData**

```javascript
resourceService.updatedResourceData('your-resource-id', 'your-data-value').subscribe(data => {
  console.log('updated Resource Data data:', data);
});
```

**13. getResourcesByIds**

```javascript
resourceService.getResourcesByIds('your-ids-value').subscribe(result => {
  console.log('Fetched  Resources By Ids result:', result);
});
```
