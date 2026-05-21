# EntityViewService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('EntityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViewInfos**

```javascript
entityViewService.getTenantEntityViewInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(tenant => {
  console.log('Fetched  Tenant Entity View Infos tenant:', tenant);
});
```

**2. getCustomerEntityViewInfos**

```javascript
entityViewService.getCustomerEntityViewInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(entity => {
  console.log('Fetched  Customer Entity View Infos entity:', entity);
});
```

**3. getEntityView**

```javascript
entityViewService.getEntityView('your-entityview-id').subscribe(entity => {
  console.log('Fetched  Entity View entity:', entity);
});
```

**4. getEntityViews**

```javascript
entityViewService.getEntityViews('your-entityviewids-value').subscribe(entity => {
  console.log('Fetched  Entity Views entity:', entity);
});
```

**5. getEntityViewInfo**

```javascript
entityViewService.getEntityViewInfo('your-entityview-id').subscribe(entity => {
  console.log('Fetched  Entity View Info entity:', entity);
});
```

**6. saveEntityView**

```javascript
entityViewService.saveEntityView('your-entityview-value').subscribe(entity => {
  console.log('Saved  Entity View entity:', entity);
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes().subscribe(entity => {
  console.log('Fetched  Entity View Types entity:', entity);
});
```

**8. makeEntityViewPublic**

```javascript
entityViewService.makeEntityViewPublic('your-entityview-id').subscribe(entity => {
  console.log('make Entity View Public entity:', entity);
});
```

**9. assignEntityViewToCustomer**

```javascript
entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entityview-id').subscribe(entity => {
  console.log('assign Entity View To Customer entity:', entity);
});
```

**10. findByQuery**

```javascript
entityViewService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**11. assignEntityViewToEdge**

```javascript
entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entityview-id').subscribe(entity => {
  console.log('assign Entity View To Edge entity:', entity);
});
```

**12. getEdgeEntityViews**

```javascript
entityViewService.getEdgeEntityViews('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(entity => {
  console.log('Fetched  Edge Entity Views entity:', entity);
});
```
