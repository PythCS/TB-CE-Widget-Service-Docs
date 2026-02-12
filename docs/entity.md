### **ENTITY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityservice = $injector.get(self.ctx.servicesMap.get('entityservice'));

// Alternative: Direct context access
const entityservice = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntityObservable(entityType, 'your-entity-id').subscribe(entityobservable => {
  console.log('Entityobservable:', entityobservable);
});
```

**2. getEntity**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntity(entityType, 'your-entity-id').subscribe(entity => {
  console.log('Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntitiesObservable(entityType, 'your-entitys-id').subscribe(entitiesobservable => {
  console.log('Entitiesobservable:', entitiesobservable);
});
```

**4. getEntities**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntities(entityType, 'your-entitys-id').subscribe(entities => {
  console.log('Entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
const entityservice = self.ctx.entityService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityservice.getSingleTenantByPageLinkObservable(pageLink).subscribe(singletenantbypagelinkobservable => {
  console.log('Singletenantbypagelinkobservable:', singletenantbypagelinkobservable);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const entityservice = self.ctx.entityService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityservice.getSingleCustomerByPageLinkObservable(pageLink).subscribe(singlecustomerbypagelinkobservable => {
  console.log('Singlecustomerbypagelinkobservable:', singlecustomerbypagelinkobservable);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const entityservice = self.ctx.entityService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityservice.getEntitiesByPageLinkObservable(pageLink, entityType, 'your-subtype').subscribe(entitiesbypagelinkobservable => {
  console.log('Entitiesbypagelinkobservable:', entitiesbypagelinkobservable);
});
```

**8. getEntitiesByPageLink**

```javascript
const entityservice = self.ctx.entityService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityservice.getEntitiesByPageLink(pageLink, entityType, 'your-subtype').subscribe(entitiesbypagelink => {
  console.log('Entitiesbypagelink:', entitiesbypagelink);
});
```

**9. getEntitiesByNameFilter**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntitiesByNameFilter(entityType, 'Device Name', 10, 'your-subtype').subscribe(entitiesbynamefilter => {
  console.log('Entitiesbynamefilter:', entitiesbynamefilter);
});
```

**10. findEntityDataByQuery**

```javascript
const entityservice = self.ctx.entityService;
entityservice.findEntityDataByQuery(query).subscribe(entitydatabyquery => {
  console.log('Entitydatabyquery:', entitydatabyquery);
});
```

**11. findEntityKeysByQuery**

```javascript
const entityservice = self.ctx.entityService;
entityservice.findEntityKeysByQuery(query).subscribe(entitykeysbyquery => {
  console.log('Entitykeysbyquery:', entitykeysbyquery);
});
```

**12. findAlarmDataByQuery**

```javascript
const entityservice = self.ctx.entityService;
entityservice.findAlarmDataByQuery(query).subscribe(alarmdatabyquery => {
  console.log('Alarmdatabyquery:', alarmdatabyquery);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
const entityservice = self.ctx.entityService;
entityservice.findEntityInfosByFilterAndName(filter, 'your-searchtext').subscribe(entityinfosbyfilterandname => {
  console.log('Entityinfosbyfilterandname:', entityinfosbyfilterandname);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
const entityservice = self.ctx.entityService;
entityservice.findSingleEntityInfoByEntityFilter(filter).subscribe(singleentityinfobyentityfilter => {
  console.log('Singleentityinfobyentityfilter:', singleentityinfobyentityfilter);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.getAliasFilterTypesByEntityTypes(entityTypes);
console.log('Result:', result);
```

**16. filterAliasByEntityTypes**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.filterAliasByEntityTypes(entityAlias, entityTypes);
console.log('Result:', result);
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes);
console.log('Result:', result);
```

**18. filterAliasFilterTypeByEntityType**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.filterAliasFilterTypeByEntityType(aliasFilterType, entityType);
console.log('Result:', result);
```

**19. prepareAllowedEntityTypesList**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.prepareAllowedEntityTypesList(allowedEntityTypes, true);
console.log('Result:', result);
```

**20. getEntityFieldKeys**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.getEntityFieldKeys(entityType, 'your-searchtext');
console.log('Result:', result);
```

**21. getAlarmKeys**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.getAlarmKeys('your-searchtext');
console.log('Result:', result);
```

**22. getEntityKeys**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntityKeys('your-entity-id', 'your-query', type).subscribe(entitykeys => {
  console.log('Entitykeys:', entitykeys);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntityKeysByEntityFilter(filter, types).subscribe(entitykeysbyentityfilter => {
  console.log('Entitykeysbyentityfilter:', entitykeysbyentityfilter);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntityKeysByEntityFilterAndScope(filter, types).subscribe(entitykeysbyentityfilterandscope => {
  console.log('Entitykeysbyentityfilterandscope:', entitykeysbyentityfilterandscope);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo);
console.log('Result:', result);
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.createAlarmSourceFromSubscriptionInfo(subscriptionInfo);
console.log('Result:', result);
```

**27. resolveAlias**

```javascript
const entityservice = self.ctx.entityService;
entityservice.resolveAlias(entityAlias, stateParams).subscribe(resolvealias => {
  console.log('Resolvealias:', resolvealias);
});
```

**28. of**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.of();
console.log('Result:', result);
```

**29. resolveAliasFilter**

```javascript
const entityservice = self.ctx.entityService;
entityservice.resolveAliasFilter(filter, stateParams).subscribe(resolvealiasfilter => {
  console.log('Resolvealiasfilter:', resolvealiasfilter);
});
```

**30. checkEntityAlias**

```javascript
const entityservice = self.ctx.entityService;
entityservice.checkEntityAlias(entityAlias).subscribe(checkentityalias => {
  console.log('Checkentityalias:', checkentityalias);
});
```

**31. resolveAlarmFilter**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.resolveAlarmFilter();
console.log('Result:', result);
```

**32. saveEntityParameters**

```javascript
const entityservice = self.ctx.entityService;
entityservice.saveEntityParameters(entityType, entityData, true).subscribe(saveentityparameters => {
  console.log('Saveentityparameters:', saveentityparameters);
});
```

**33. getSaveEntityObservable**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getSaveEntityObservable(entityType, entityData).subscribe(saveentityobservable => {
  console.log('Saveentityobservable:', saveentityobservable);
});
```

**34. getUpdateEntityTasks**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getUpdateEntityTasks(entityType, entityData, entity).subscribe(updateentitytasks => {
  console.log('Updateentitytasks:', updateentitytasks);
});
```

**35. saveEntityData**

```javascript
const entityservice = self.ctx.entityService;
entityservice.saveEntityData('your-entity-id', entityData).subscribe(saveentitydata => {
  console.log('Saveentitydata:', saveentitydata);
});
```

**36. getStateEntityInfo**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.getStateEntityInfo(filter, stateParams);
console.log('Result:', result);
```

**37. createDatasourceFromSubscriptionInfo**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.createDatasourceFromSubscriptionInfo(subscriptionInfo);
console.log('Result:', result);
```

**38. validateSubscriptionInfo**

```javascript
const entityservice = self.ctx.entityService;
const result = entityservice.validateSubscriptionInfo(subscriptionInfo);
console.log('Result:', result);
```

**39. getAssignedToEdgeEntitiesByType**

```javascript
const entityservice = self.ctx.entityService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityservice.getAssignedToEdgeEntitiesByType(pageLink, 'your-edge-id', entityType).subscribe(assignedtoedgeentitiesbytype => {
  console.log('Assignedtoedgeentitiesbytype:', assignedtoedgeentitiesbytype);
});
```

**40. case**

```javascript
const entityservice = self.ctx.entityService;
entityservice.case().subscribe(case => {
  console.log('Case:', case);
});
```

**41. getEntitySubtypesObservable**

```javascript
const entityservice = self.ctx.entityService;
entityservice.getEntitySubtypesObservable(entityType).subscribe(entitysubtypesobservable => {
  console.log('Entitysubtypesobservable:', entitysubtypesobservable);
});
```

