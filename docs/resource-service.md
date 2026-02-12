# RESOURCE

File and resource management.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

## Methods

### getResources

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const resourceType = {
  // your resourceType object
};
const resourceSubType = {
  // your resourceSubType object
};

resourceService.getResources(pageLink, resourceType, resourceSubType).subscribe(info => {
  console.log('Info:', info);
});
```

### getTenantResources

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

resourceService.getTenantResources(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getResource

```javascript
const resourceId = 'your-resource-id';

resourceService.getResource(resourceId).subscribe(result => {
  console.log('Resource:', result);
});
```

### getResourceInfoById

```javascript
const resourceId = 'your-resource-id';

resourceService.getResourceInfoById(resourceId).subscribe(info => {
  console.log('Info:', info);
});
```

### getResourceInfo

```javascript
const type = {
  // your type object
};
const scope = {
  // your scope object
};
const key = 'your-key';

resourceService.getResourceInfo(type, scope, key).subscribe(info => {
  console.log('Info:', info);
});
```

### downloadResource

```javascript
const resourceId = 'your-resource-id';

resourceService.downloadResource(resourceId).subscribe(result => {
  console.log('downloadResource:', result);
});
```

### saveResources

```javascript
const resources = {
  // your resources object
};

resourceService.saveResources(resources).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### saveResource

```javascript
const resource = {
  // your resource object
};

resourceService.saveResource(resource).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### uploadResources

```javascript
const resources = {
  // your resources object
};

resourceService.uploadResources(resources).subscribe(result => {
  console.log('uploadResources:', result);
});
```

### uploadResource

```javascript
const resource = {
  // your resource object
};

resourceService.uploadResource(resource).subscribe(result => {
  console.log('uploadResource:', result);
});
```

### updatedResourceInfo

```javascript
const resourceId = 'your-resource-id';
const updatedResources = {
  // your updatedResources object
};

resourceService.updatedResourceInfo(resourceId, updatedResources).subscribe(result => {
  console.log('Updated Result:', result);
});
```

### updatedResourceData

```javascript
const resourceId = 'your-resource-id';
const data = new File(['content'], 'file.txt', { type: 'text/plain' });

resourceService.updatedResourceData(resourceId, data).subscribe(result => {
  console.log('Updated Result:', result);
});
```

### getResourcesByIds

```javascript
const ids = 'your-s-id';

resourceService.getResourcesByIds(ids).subscribe(info => {
  console.log('Info:', info);
});
```

