# ENTITY VIEW SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ENTITY VIEW SERVICE**

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
entityViewService.getTenantEntityViewInfos(pageLink, 'type').subscribe(tenantentityviewinfos => {
  console.log('Get Tenant Entity View Infos: tenantentityviewinfos');
});
```

**2. getCustomerEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityViewService.getCustomerEntityViewInfos('your-customer-id', pageLink, 'type').subscribe(customerentityviewinfos => {
  console.log('Get Customer Entity View Infos:customerentityviewinfos');
});
```

**3. getEntityView**

```javascript
entityViewService.getEntityView('your-entity-view-id').subscribe(entityView => {
  console.log('Get Entity View: entityView');
});
```

**4. getEntityViews**

```javascript
entityViewService.getEntityViews('your-id').subscribe(entityviews => {
  console.log('Get Entity Views: entityviews');
});
```

**5. getEntityViewInfo**

```javascript
entityViewService.getEntityViewInfo('your-entity-view-id').subscribe(entityViewInfo => {
  console.log('Get Entity View Info: entityViewInfo');
});
```

**6. saveEntityView**

```javascript
const entityView = entityView;
entityViewService.saveEntityView(entityView).subscribe(savedEntityView => {
  console.log('Save Entity View: savedEntityView');
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes().subscribe(entityviewtypes => {
  console.log('Get Entity View Types: entityviewtypes');
});
```

**8. makeEntityViewPublic**

```javascript
entityViewService.makeEntityViewPublic('your-entity-view-id').subscribe(result => {
  console.log('Make Entity View Public: result');
});
```

**9. assignEntityViewToCustomer**

```javascript
entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entity-view-id').subscribe(result => {
  console.log('Assign Entity View To Customer:result');
});
```

**10. findByQuery**

```javascript
const query = query;
entityViewService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**11. assignEntityViewToEdge**

```javascript
entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entity-view-id').subscribe(result => {
  console.log('Assign Entity View To Edge: result');
});
```

**12. getEdgeEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityViewService.getEdgeEntityViews('your-edge-id', pageLink, 'type').subscribe(edgeentityviews => {
  console.log('Get Edge Entity Views: edgeentityviews');
});
```
