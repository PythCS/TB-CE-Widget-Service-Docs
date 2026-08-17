# ENTITY VIEW SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getTenantEntityViewInfos(pageLink, 'your-type-value').subscribe(tenantEntityViewInfos => {
  console.log('Get Tenant Entity View Infos:', tenantEntityViewInfos);
});
```

**2. getCustomerEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getCustomerEntityViewInfos('your-customer-id', pageLink, 'your-type-value').subscribe(customerEntityViewInfos => {
  console.log('Get Customer Entity View Infos:', customerEntityViewInfos);
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

**5. getEntityViewInfo**

```javascript
self.ctx.entityViewService.getEntityViewInfo('your-entityview-id').subscribe(entityViewInfo => {
  console.log('Get Entity View Info:', entityViewInfo);
});
```

**6. saveEntityView**

```javascript
self.ctx.entityViewService.saveEntityView('your-entityview-value').subscribe(entityView => {
  console.log('Save Entity View:', entityView);
});
```

**7. getEntityViewTypes**

```javascript
self.ctx.entityViewService.getEntityViewTypes().subscribe(entityViewTypes => {
  console.log('Get Entity View Types:', entityViewTypes);
});
```

**8. makeEntityViewPublic**

```javascript
self.ctx.entityViewService.makeEntityViewPublic('your-entityview-id').subscribe(makeEntityViewPublic => {
  console.log('Make Entity View Public:', makeEntityViewPublic);
});
```

**9. assignEntityViewToCustomer**

```javascript
self.ctx.entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entityview-id').subscribe(entityViewToCustomer => {
  console.log('Assign Entity View To Customer:', entityViewToCustomer);
});
```

**10. findByQuery**

```javascript
self.ctx.entityViewService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**11. assignEntityViewToEdge**

```javascript
self.ctx.entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entityview-id').subscribe(entityViewToEdge => {
  console.log('Assign Entity View To Edge:', entityViewToEdge);
});
```

**12. getEdgeEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getEdgeEntityViews('your-edge-id', pageLink, 'your-type-value').subscribe(edgeEntityViews => {
  console.log('Get Edge Entity Views:', edgeEntityViews);
});
```
