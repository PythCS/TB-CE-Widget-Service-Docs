# Resource

```javascript
// Service name: resource
// File: resource.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const resource = self.ctx.resourceService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const resource = $injector.get(self.ctx.servicesMap.get('resource'));
```

### **1. getResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resource.getResources(pageLink).subscribe(resources => {
  console.log('Resources:', resources);
});
```

### **2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resource.getTenantResources(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **3. getResource**

```javascript
resource.getResource(resourceId).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **4. getResourceInfoById**

```javascript
resource.getResourceInfoById(resourceId).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **5. getResourceInfo**

```javascript
resource.getResourceInfo(type, scope, key).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **6. downloadResource**

```javascript
resource.downloadResource(resourceId).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **7. saveResources**

```javascript
resource.saveResources(resources).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **8. saveResource**

```javascript
resource.saveResource(resource).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **9. uploadResources**

```javascript
resource.uploadResources(resources).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **10. uploadResource**

```javascript
resource.uploadResource(resource).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **11. updatedResourceInfo**

```javascript
resource.updatedResourceInfo(resourceId, updatedResources).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **12. updatedResourceData**

```javascript
resource.updatedResourceData(resourceId, data).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **13. getResourcesByIds**

```javascript
resource.getResourcesByIds(ids).subscribe(resources => {
  console.log('Resources:', resources);
});
```
