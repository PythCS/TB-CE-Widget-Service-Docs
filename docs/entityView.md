# Entity View

```javascript
// Service name: entityView
// File: entity-view.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const entityView = self.ctx.entityViewService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const entityView = $injector.get(self.ctx.servicesMap.get('entityView'));
```

### **1. getTenantEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityView.getTenantEntityViewInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **2. getCustomerEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityView.getCustomerEntityViewInfos(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **3. getEntityView**

```javascript
entityView.getEntityView(entityViewId).subscribe(entityView => {
  console.log('Entity View:', entityView);
});
```

### **4. getEntityViews**

```javascript
entityView.getEntityViews(entityViewIds).subscribe(entityViews => {
  console.log('Entity Views:', entityViews);
});
```

### **5. getEntityViewInfo**

```javascript
entityView.getEntityViewInfo(entityViewId).subscribe(entityView => {
  console.log('Entity View:', entityView);
});
```

### **6. saveEntityView**

```javascript
entityView.saveEntityView(entityView).subscribe(entityView => {
  console.log('Entity View:', entityView);
});
```

### **7. getEntityViewTypes**

```javascript
entityView.getEntityViewTypes().subscribe(entityViews => {
  console.log('Entity Views:', entityViews);
});
```

### **8. makeEntityViewPublic**

```javascript
entityView.makeEntityViewPublic(entityViewId).subscribe(entityView => {
  console.log('Entity View:', entityView);
});
```

### **9. assignEntityViewToCustomer**

```javascript
entityView.assignEntityViewToCustomer(customerId, entityViewId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **10. findByQuery**

```javascript
entityView.findByQuery(query).subscribe(findByQuerys => {
  console.log('Find By Querys:', findByQuerys);
});
```

### **11. assignEntityViewToEdge**

```javascript
entityView.assignEntityViewToEdge(edgeId, entityViewId).subscribe(entityView => {
  console.log('Entity View:', entityView);
});
```

### **12. getEdgeEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityView.getEdgeEntityViews(pageLink).subscribe(entityViews => {
  console.log('Entity Views:', entityViews);
});
```
