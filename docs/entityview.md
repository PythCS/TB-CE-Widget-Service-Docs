### **ENTITY VIEW SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityviewservice = $injector.get(self.ctx.servicesMap.get('entityviewservice'));

// Alternative: Direct context access
const entityviewservice = self.ctx.entityViewService;
```

**1. getTenantEntityViewInfos**

```javascript
const entityviewservice = self.ctx.entityViewService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityviewservice.getTenantEntityViewInfos(pageLink, 'your-type').subscribe(tenantentityviewinfos => {
  console.log('Tenantentityviewinfos:', tenantentityviewinfos);
});
```

**2. getCustomerEntityViewInfos**

```javascript
const entityviewservice = self.ctx.entityViewService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityviewservice.getCustomerEntityViewInfos(pageLink, 'your-customer-id', 'your-type').subscribe(customerentityviewinfos => {
  console.log('Customerentityviewinfos:', customerentityviewinfos);
});
```

**3. getEntityView**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.getEntityView('your-entityview-id').subscribe(entityview => {
  console.log('Entityview:', entityview);
});
```

**4. getEntityViews**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.getEntityViews('your-entityviews-id').subscribe(entityviews => {
  console.log('Entityviews:', entityviews);
});
```

**5. getEntityViewInfo**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.getEntityViewInfo('your-entityview-id').subscribe(entityviewinfo => {
  console.log('Entityviewinfo:', entityviewinfo);
});
```

**6. saveEntityView**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.saveEntityView(entityView).subscribe(saveentityview => {
  console.log('Saveentityview:', saveentityview);
});
```

**7. getEntityViewTypes**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.getEntityViewTypes().subscribe(entityviewtypes => {
  console.log('Entityviewtypes:', entityviewtypes);
});
```

**8. makeEntityViewPublic**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.makeEntityViewPublic('your-entityview-id').subscribe(makeentityviewpublic => {
  console.log('Makeentityviewpublic:', makeentityviewpublic);
});
```

**9. assignEntityViewToCustomer**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.assignEntityViewToCustomer('your-customer-id', 'your-entityview-id').subscribe(assignentityviewtocustomer => {
  console.log('Assignentityviewtocustomer:', assignentityviewtocustomer);
});
```

**10. findByQuery**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.findByQuery(query).subscribe(byquery => {
  console.log('Byquery:', byquery);
});
```

**11. assignEntityViewToEdge**

```javascript
const entityviewservice = self.ctx.entityViewService;
entityviewservice.assignEntityViewToEdge('your-edge-id', 'your-entityview-id').subscribe(assignentityviewtoedge => {
  console.log('Assignentityviewtoedge:', assignentityviewtoedge);
});
```

**12. getEdgeEntityViews**

```javascript
const entityviewservice = self.ctx.entityViewService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityviewservice.getEdgeEntityViews(pageLink, 'your-edge-id', 'your-type').subscribe(edgeentityviews => {
  console.log('Edgeentityviews:', edgeentityviews);
});
```

