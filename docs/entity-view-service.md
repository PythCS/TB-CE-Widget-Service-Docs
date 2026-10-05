# ENTITY VIEW SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViews**

```javascript
const entityViewService = self.ctx.entityViewService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getTenantEntityViews(pageLink, type).subscribe(tenantEntityViews => {
  console.log('List of Tenant Entity Views:', tenantEntityViews);
});
```

**2. getCustomerEntityViews**

```javascript
const entityViewService = self.ctx.entityViewService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getCustomerEntityViews(customerId, pageLink, type).subscribe(customerEntityViews => {
  console.log('List of Customer Entity Views:', customerEntityViews);
});
```

**3. getEntityView**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityViewId = 'your-entity-view-id';
entityViewService.getEntityView(entityViewId).subscribe(entityView => {
  console.log('Get Entity View:', entityView);
});
```

**4. getEntityViews**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityViewIds = ['your-entity-view-i-1', 'your-entity-view-i-2'];
entityViewService.getEntityViews(entityViewIds).subscribe(entityViews => {
  console.log('List of Entity Views:', entityViews);
});
```

**5. getUserEntityViews**

```javascript
const entityViewService = self.ctx.entityViewService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getUserEntityViews(pageLink, type).subscribe(userEntityViews => {
  console.log('List of User Entity Views:', userEntityViews);
});
```

**6. getAllEntityViewInfos**

```javascript
const entityViewService = self.ctx.entityViewService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getAllEntityViewInfos(includeCustomers, pageLink, type).subscribe(allEntityViewInfos => {
  console.log('List of All Entity View Infos:', allEntityViewInfos);
});
```

**7. getCustomerEntityViewInfos**

```javascript
const entityViewService = self.ctx.entityViewService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
entityViewService.getCustomerEntityViewInfos(includeCustomers, customerId, pageLink, type).subscribe(customerEntityViewInfos => {
  console.log('List of Customer Entity View Infos:', customerEntityViewInfos);
});
```

**8. getEntityViewInfo**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityViewId = 'your-entity-view-id';
entityViewService.getEntityViewInfo(entityViewId).subscribe(entityViewInfo => {
  console.log('Get Entity View Info:', entityViewInfo);
});
```

**9. saveEntityView**

```javascript
const entityViewService = self.ctx.entityViewService;
const entityView = {  // EntityView object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = entityViewService.saveEntityView(entityView, entityGroupIds);
console.log('Result:', result);
```

**10. getEntityViewTypes**

```javascript
const entityViewService = self.ctx.entityViewService;
entityViewService.getEntityViewTypes().subscribe(entityViewTypes => {
  console.log('List of Entity View Types:', entityViewTypes);
});
```

**11. findByQuery**

```javascript
const entityViewService = self.ctx.entityViewService;
const query = {  // EntityViewSearchQuery object
  // ... set the fields you need
};
entityViewService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```
