# ENTITY VIEW

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

## Methods

### getTenantEntityViewInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

entityViewService.getTenantEntityViewInfos(pageLink, type).subscribe(info => {
  console.log('Info:', info);
});
```

### getCustomerEntityViewInfos

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

entityViewService.getCustomerEntityViewInfos(customerId, pageLink, type).subscribe(info => {
  console.log('Info:', info);
});
```

### getEntityView

```javascript
const entityViewId = 'your-entityview-id';

entityViewService.getEntityView(entityViewId).subscribe(result => {
  console.log('EntityView:', result);
});
```

### getEntityViews

```javascript
const entityViewIds = 'your-entityviews-id';

entityViewService.getEntityViews(entityViewIds).subscribe(result => {
  console.log('EntityViews:', result);
});
```

### getEntityViewInfo

```javascript
const entityViewId = 'your-entityview-id';

entityViewService.getEntityViewInfo(entityViewId).subscribe(info => {
  console.log('Info:', info);
});
```

### saveEntityView

```javascript
const entityView = {
  // your entityView object
};

entityViewService.saveEntityView(entityView).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getEntityViewTypes

```javascript
entityViewService.getEntityViewTypes().subscribe(result => {
  console.log('EntityViewTypes:', result);
});
```

### makeEntityViewPublic

```javascript
const entityViewId = 'your-entityview-id';

entityViewService.makeEntityViewPublic(entityViewId).subscribe(result => {
  console.log('makeEntityViewPublic:', result);
});
```

### assignEntityViewToCustomer

```javascript
const customerId = 'your-customer-id';
const entityViewId = 'your-entityview-id';

entityViewService.assignEntityViewToCustomer(customerId, entityViewId).subscribe(result => {
  console.log('assignEntityViewToCustomer:', result);
});
```

### findByQuery

```javascript
const query = {
  // your query object
};

entityViewService.findByQuery(query).subscribe(result => {
  console.log('findByQuery:', result);
});
```

### assignEntityViewToEdge

```javascript
const edgeId = 'your-edge-id';
const entityViewId = 'your-entityview-id';

entityViewService.assignEntityViewToEdge(edgeId, entityViewId).subscribe(result => {
  console.log('assignEntityViewToEdge:', result);
});
```

### getEdgeEntityViews

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

entityViewService.getEdgeEntityViews(edgeId, pageLink, type).subscribe(info => {
  console.log('Info:', info);
});
```

