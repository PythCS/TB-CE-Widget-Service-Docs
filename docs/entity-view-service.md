# ENTITY VIEW SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getTenantEntityViews(pageLink, 'your-type-value').subscribe(tenantEntityViews => {
  console.log('Get Tenant Entity Views:', tenantEntityViews);
});
```

**2. getCustomerEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getCustomerEntityViews('your-customer-id', pageLink, 'your-type-value').subscribe(customerEntityViews => {
  console.log('Get Customer Entity Views:', customerEntityViews);
});
```

**3. getEntityView**

```javascript
self.ctx.entityViewService.getEntityView('your-entityview-id').subscribe(entityView => {
  console.log('Get Entity View:', entityView);
});
```

**4. getEntityViews**

```javascript
self.ctx.entityViewService.getEntityViews('your-entityviewids-value').subscribe(entityViews => {
  console.log('Get Entity Views:', entityViews);
});
```

**5. getUserEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getUserEntityViews(pageLink, 'your-type-value').subscribe(userEntityViews => {
  console.log('Get User Entity Views:', userEntityViews);
});
```

**6. getAllEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getAllEntityViewInfos(true, pageLink, 'your-type-value').subscribe(allEntityViewInfos => {
  console.log('Get All Entity View Infos:', allEntityViewInfos);
});
```

**7. getCustomerEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getCustomerEntityViewInfos(true, 'your-customer-id', pageLink, 'your-type-value').subscribe(customerEntityViewInfos => {
  console.log('Get Customer Entity View Infos:', customerEntityViewInfos);
});
```

**8. getEntityViewInfo**

```javascript
self.ctx.entityViewService.getEntityViewInfo('your-entityview-id').subscribe(entityViewInfo => {
  console.log('Get Entity View Info:', entityViewInfo);
});
```

**9. saveEntityView**

```javascript
self.ctx.entityViewService.saveEntityView('your-entityview-value', 'your-entitygroupids-value').subscribe(entityView => {
  console.log('Save Entity View:', entityView);
});
```

**10. getEntityViewTypes**

```javascript
self.ctx.entityViewService.getEntityViewTypes().subscribe(entityViewTypes => {
  console.log('Get Entity View Types:', entityViewTypes);
});
```

**11. findByQuery**

```javascript
self.ctx.entityViewService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```
