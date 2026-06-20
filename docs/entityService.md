# ENTITY SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ENTITY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
entityService.getEntityObservable('type', 'your-entity-id').subscribe(entityObservable => {
  console.log('Get Entity Observable: entityObservable');
});
```

**2. getEntity**

```javascript
entityService.getEntity('type', 'your-entity-id').subscribe(entity => {
  console.log('Get Entity: entity');
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable('type', 'your-id').subscribe(entitiesObservable => {
  console.log('Get Entities Observable: entitiesObservable');
});
```

**4. getEntities**

```javascript
entityService.getEntities('type', 'your-id').subscribe(entities => {
  console.log('Get Entities: entities');
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(singleTenantByPageLinkObservable => {
  console.log('Get Single Tenant By Page Link Observable:singleTenantByPageLinkObservable');
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(singleCustomerByPageLinkObservable => {
  console.log('Get Single Customer By Page Link Observable:singleCustomerByPageLinkObservable');
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getEntitiesByPageLinkObservable('type', pageLink, 'type').subscribe(entitiesByPageLinkObservable => {
  console.log('Get Entities By Page Link Observable:entitiesByPageLinkObservable');
});
```

**8. getEntitiesByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getEntitiesByPageLink('type', pageLink, 'type').subscribe(entitiesByPageLink => {
  console.log('Get Entities By Page Link: entitiesByPageLink');
});
```

**9. getEntitiesByNameFilter**

```javascript
const entityNameFilter = entityNameFilter;
const pageSize = pageSize;
entityService.getEntitiesByNameFilter('type', entityNameFilter, pageSize, 'type').subscribe(entitiesByNameFilter => {
  console.log('Get Entities By Name Filter: entitiesByNameFilter');
});
```

**10. findEntityDataByQuery**

```javascript
const query = query;
entityService.findEntityDataByQuery(query).subscribe(results => {
  console.log('Find Entity Data By Query: results');
});
```

**11. findEntityKeysByQuery**

```javascript
const query = query;
entityService.findEntityKeysByQuery(query, 'SERVER_SCOPE').subscribe(results => {
  console.log('Find Entity Keys By Query: results');
});
```

**12. findAlarmDataByQuery**

```javascript
const query = query;
entityService.findAlarmDataByQuery(query).subscribe(results => {
  console.log('Find Alarm Data By Query: results');
});
```

**13. findEntityInfosByFilterAndName**

```javascript
const filter = filter;
entityService.findEntityInfosByFilterAndName(filter, 'searchText').subscribe(results => {
  console.log('Find Entity Infos By Filter And Name:results');
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
const filter = filter;
entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(results => {
  console.log('Find Single Entity Info By Entity Filter:results');
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes('type').subscribe(aliasfiltertypesbyentitytypes => {
  console.log('Get Alias Filter Types By Entity Types:aliasfiltertypesbyentitytypes');
});
```

**16. filterAliasByEntityTypes**

```javascript
const entityAlias = entityAlias;
entityService.filterAliasByEntityTypes(entityAlias, 'type').subscribe(result => {
  console.log('Filter Alias By Entity Types: result');
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes('type', 'type').subscribe(result => {
  console.log('Filter Alias Filter Type By Entity Types:result');
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType('type', 'type').subscribe(result => {
  console.log('Filter Alias Filter Type By Entity Type:result');
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList('type', 'type').subscribe(result => {
  console.log('Prepare Allowed Entity Types List:result');
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys('type', 'searchText').subscribe(entityfieldkeys => {
  console.log('Get Entity Field Keys: entityfieldkeys');
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys('searchText').subscribe(alarmkeys => {
  console.log('Get Alarm Keys: alarmkeys');
});
```

**22. getEntityKeys**

```javascript
const query = query;
entityService.getEntityKeys('your-entity-id', query, 'type').subscribe(entitykeys => {
  console.log('Get Entity Keys: entitykeys');
});
```

**23. getEntityKeysByEntityFilter**

```javascript
const filter = filter;
entityService.getEntityKeysByEntityFilter(filter, 'type', 'type').subscribe(entityKeysByEntityFilter => {
  console.log('Get Entity Keys By Entity Filter:entityKeysByEntityFilter');
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
const filter = filter;
entityService.getEntityKeysByEntityFilterAndScope(filter, 'type', 'type', 'SERVER_SCOPE').subscribe(entityKeysByEntityFilterAndScope => {
  console.log('Get Entity Keys By Entity Filter And Scope:entityKeysByEntityFilterAndScope');
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
const subscriptionsInfo = subscriptionsInfo;
entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo).subscribe(result => {
  console.log('Create Datasources From Subscriptions Info:result');
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
const subscriptionInfo = subscriptionInfo;
entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo).subscribe(result => {
  console.log('Create Alarm Source From Subscription Info:result');
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'type', pageLink).subscribe(assignedToEdgeEntitiesByType => {
  console.log('Get Assigned To Edge Entities By Type:assignedToEdgeEntitiesByType');
});
```

**28. case**

```javascript
entityService.case().subscribe(result => {
  console.log('Case: result');
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable('type').subscribe(entitySubtypesObservable => {
  console.log('Get Entity Subtypes Observable:entitySubtypesObservable');
});
```
