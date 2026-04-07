# EntityViewService

### **ENTITYVIEWSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViewInfos**

```javascript
entityViewService.getTenantEntityViewInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantentityviewinfo => {
  console.log('Tenant Entity View Infos:', tenantentityviewinfo);
});
```

**2. getCustomerEntityViewInfos**

```javascript
entityViewService.getCustomerEntityViewInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomerentityviewinfo => {
  console.log('Customer Entity View Infos:', cutomerentityviewinfo);
});
```

**3. getEntityView**

```javascript
entityViewService.getEntityView('your-entityview-id', { /* your config */ }).subscribe(entityview => {
  console.log('Entity View:', entityview);
});
```

**4. getEntityViews**

```javascript
entityViewService.getEntityViews('your-entityviews-id', { /* your config */ }).subscribe(entityview => {
  console.log('Entity Views:', entityview);
});
```

**5. getEntityViewInfo**

```javascript
entityViewService.getEntityViewInfo('your-entityview-id', { /* your config */ }).subscribe(entityviewinfo => {
  console.log('Entity View Info:', entityviewinfo);
});
```

**6. saveEntityView**

```javascript
entityViewService.saveEntityView({ /* your entityView */ }, { /* your config */ }).subscribe(savedEntityView => {
  console.log('Saved EntityView:', savedEntityView);
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes({ /* your config */ }).subscribe(entityviewtype => {
  console.log('Entity View Types:', entityviewtype);
});
```

**8. makeEntityViewPublic**

```javascript
entityViewService.makeEntityViewPublic('your-entityview-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. assignEntityViewToCustomer**

```javascript
entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entityview-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. findByQuery**

```javascript
entityViewService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. assignEntityViewToEdge**

```javascript
entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entityview-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. getEdgeEntityViews**

```javascript
entityViewService.getEdgeEntityViews('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(edgeentityview => {
  console.log('Edge Entity Views:', edgeentityview);
});
```
