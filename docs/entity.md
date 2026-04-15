# Entity

```javascript
// Service name: entity
// File: entity.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const entity = self.ctx.entityService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const entity = $injector.get(self.ctx.servicesMap.get('entity'));
```

### **1. getEntityObservable**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
entity.getEntityObservable(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **2. getEntity**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
entity.getEntity(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **3. getEntitiesObservable**

```javascript
entity.getEntitiesObservable(entityType, entityIds).subscribe(entitiesObservables => {
  console.log('Entities Observables:', entitiesObservables);
});
```

### **4. getEntities**

```javascript
entity.getEntities(entityType, entityIds).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **5. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entity.getSingleTenantByPageLinkObservable(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entity.getSingleCustomerByPageLinkObservable(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **7. getEntitiesByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entity.getEntitiesByPageLinkObservable(pageLink).subscribe(entitiesByPageLinkObservables => {
  console.log('Entities By Page Link Observables:', entitiesByPageLinkObservables);
});
```

### **8. getEntitiesByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entity.getEntitiesByPageLink(pageLink).subscribe(entitiesByPageLinks => {
  console.log('Entities By Page Links:', entitiesByPageLinks);
});
```

### **9. getEntitiesByNameFilter**

```javascript
entity.getEntitiesByNameFilter(entityType, entityNameFilter, pageSize, subType).subscribe(entitiesFilters => {
  console.log('Entities Filters:', entitiesFilters);
});
```

### **10. findEntityDataByQuery**

```javascript
entity.findEntityDataByQuery(query).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **11. findEntityKeysByQuery**

```javascript
entity.findEntityKeysByQuery(query).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **12. findAlarmDataByQuery**

```javascript
entity.findAlarmDataByQuery(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **13. findEntityInfosByFilterAndName**

```javascript
entity.findEntityInfosByFilterAndName(filter, searchText).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **14. findSingleEntityInfoByEntityFilter**

```javascript
entity.findSingleEntityInfoByEntityFilter(filter).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **15. getAliasFilterTypesByEntityTypes**

```javascript
entity.getAliasFilterTypesByEntityTypes(entityTypes).subscribe(aliasFilterTypesTypes => {
  console.log('Alias Filter Types Types:', aliasFilterTypesTypes);
});
```

### **16. filterAliasByEntityTypes**

```javascript
entity.filterAliasByEntityTypes(entityAlias, entityTypes).subscribe(filterAliasType => {
  console.log('Filter Alias Type:', filterAliasType);
});
```

### **17. filterAliasFilterTypeByEntityTypes**

```javascript
entity.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes).subscribe(filterAliasFilterTypeType => {
  console.log('Filter Alias Filter Type Type:', filterAliasFilterTypeType);
});
```

### **18. filterAliasFilterTypeByEntityType**

```javascript
entity.filterAliasFilterTypeByEntityType(aliasFilterType, entityType).subscribe(filterAliasFilterTypeType => {
  console.log('Filter Alias Filter Type Type:', filterAliasFilterTypeType);
});
```

### **19. prepareAllowedEntityTypesList**

```javascript
entity.prepareAllowedEntityTypesList(allowedEntityTypes).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **20. getEntityFieldKeys**

```javascript
entity.getEntityFieldKeys(entityType, searchText).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **21. getAlarmKeys**

```javascript
entity.getAlarmKeys(searchText).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **22. getEntityKeys**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
entity.getEntityKeys(entityId).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **23. getEntityKeysByEntityFilter**

```javascript
entity.getEntityKeysByEntityFilter(filter, types).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **24. getEntityKeysByEntityFilterAndScope**

```javascript
entity.getEntityKeysByEntityFilterAndScope(filter, types).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **25. createDatasourcesFromSubscriptionsInfo**

```javascript
entity.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo).subscribe(createDatasourcesFromSubscriptions => {
  console.log('Create Datasources From Subscriptions:', createDatasourcesFromSubscriptions);
});
```

### **26. createAlarmSourceFromSubscriptionInfo**

```javascript
entity.createAlarmSourceFromSubscriptionInfo(subscriptionInfo).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **27. getAssignedToEdgeEntitiesByType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entity.getAssignedToEdgeEntitiesByType(pageLink).subscribe(edges => {
  console.log('Edges:', edges);
});
```

### **28. case**

```javascript
// This method is used internally by the service
```

### **29. getEntitySubtypesObservable**

```javascript
entity.getEntitySubtypesObservable(entityType).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```
