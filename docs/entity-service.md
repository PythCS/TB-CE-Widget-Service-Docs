# EntityService

**Source:** `entity.service.ts`  
**Direct context access:** `entityService`

---

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
entityService.getEntityObservable(null, /* entityId */ null).subscribe(entityObservable => {
  console.log('EntityObservable:', entityObservable);
});
```

**2. getEntity**

```javascript
entityService.getEntity(null, /* entityId */ null).subscribe(entity => {
  console.log('Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable(null, ['id1', 'id2']).subscribe(entitiesObservable => {
  console.log('EntitiesObservable:', entitiesObservable);
});
```

**4. getEntities**

```javascript
entityService.getEntities(null, ['id1', 'id2']).subscribe(entities => {
  console.log('Entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
entityService.getSingleTenantByPageLinkObservable(self.ctx.pageLink(10, 0, null, null, null)).subscribe(singleTenantByPageLinkObservable => {
  console.log('SingleTenantByPageLinkObservable:', singleTenantByPageLinkObservable);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
entityService.getSingleCustomerByPageLinkObservable(self.ctx.pageLink(10, 0, null, null, null)).subscribe(singleCustomerByPageLinkObservable => {
  console.log('SingleCustomerByPageLinkObservable:', singleCustomerByPageLinkObservable);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
entityService.getEntitiesByPageLinkObservable(null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(entitiesByPageLinkObservable => {
  console.log('EntitiesByPageLinkObservable:', entitiesByPageLinkObservable);
});
```

**8. getEntitiesByPageLink**

```javascript
entityService.getEntitiesByPageLink(null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(entitiesByPageLink => {
  console.log('EntitiesByPageLink:', entitiesByPageLink);
});
```

**9. getEntitiesByNameFilter**

```javascript
entityService.getEntitiesByNameFilter(null, /* entityNameFilter */ null, 0, null).subscribe(entitiesByNameFilter => {
  console.log('EntitiesByNameFilter:', entitiesByNameFilter);
});
```

**10. findEntityDataByQuery**

```javascript
entityService.findEntityDataByQuery(null).subscribe(entityDataByQuery => {
  console.log('EntityDataByQuery:', entityDataByQuery);
});
```

**11. findEntityKeysByQuery**

```javascript
entityService.findEntityKeysByQuery(null, null).subscribe(entityKeysByQuery => {
  console.log('EntityKeysByQuery:', entityKeysByQuery);
});
```

**12. findAlarmDataByQuery**

```javascript
entityService.findAlarmDataByQuery(null).subscribe(alarmDataByQuery => {
  console.log('AlarmDataByQuery:', alarmDataByQuery);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
entityService.findEntityInfosByFilterAndName(entityFilter, /* searchText */ null).subscribe(entityInfosByFilterAndName => {
  console.log('Entity infosByFilter Name:', entityInfosByFilterAndName);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
entityService.findSingleEntityInfoByEntityFilter(entityFilter).subscribe(singleEntityInfoByEntityFilter => {
  console.log('SingleEntity infoByEntityFilter:', singleEntityInfoByEntityFilter);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes(/* entityTypes */ null).subscribe(aliasFilterTypesByEntityTypes => {
  console.log('AliasFilterTypesByEntityTypes:', aliasFilterTypesByEntityTypes);
});
```

**16. filterAliasByEntityTypes**

```javascript
entityService.filterAliasByEntityTypes(/* entityAlias */ null, /* entityTypes */ null).subscribe(filterAliasByEntityTypes => {
  console.log('filterAliasByEntityTypes:', filterAliasByEntityTypes);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes(/* aliasFilterType */ null, /* entityTypes */ null).subscribe(filterAliasFilterTypeByEntityTypes => {
  console.log('filterAliasFilterTypeByEntityTypes:', filterAliasFilterTypeByEntityTypes);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType(/* aliasFilterType */ null, /* entityType */ null).subscribe(filterAliasFilterTypeByEntityType => {
  console.log('filterAliasFilterTypeByEntityType:', filterAliasFilterTypeByEntityType);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList(/* allowedEntityTypes */ null, false).subscribe(prepareAllowedEntityTypesList => {
  console.log('prepareAllowedEntityTypesList:', prepareAllowedEntityTypesList);
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys(null, null).subscribe(entityFieldKeys => {
  console.log('EntityFieldKeys:', entityFieldKeys);
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys(null).subscribe(alarmKeys => {
  console.log('AlarmKeys:', alarmKeys);
});
```

**22. getEntityKeys**

```javascript
entityService.getEntityKeys(entityId, /* query */ null, null).subscribe(entityKeys => {
  console.log('EntityKeys:', entityKeys);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
entityService.getEntityKeysByEntityFilter(entityFilter, /* types */ null, /* entityTypes */ null).subscribe(entityKeysByEntityFilter => {
  console.log('EntityKeysByEntityFilter:', entityKeysByEntityFilter);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
entityService.getEntityKeysByEntityFilterAndScope(entityFilter, /* types */ null, /* entityTypes */ null, null).subscribe(entityKeysByEntityFilterAndScope => {
  console.log('EntityKeysByEntityFilter Scope:', entityKeysByEntityFilterAndScope);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
entityService.createDatasourcesFromSubscriptionsInfo(/* subscriptionsInfo */ null).subscribe(datasourcesFromSubscriptionsInfo => {
  console.log('createDatasourcesFromSubscriptions:', datasourcesFromSubscriptionsInfo);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
entityService.createAlarmSourceFromSubscriptionInfo(/* subscriptionInfo */ null).subscribe(alarmSourceFromSubscriptionInfo => {
  console.log('createAlarmSourceFromSubscription:', alarmSourceFromSubscriptionInfo);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
entityService.getAssignedToEdgeEntitiesByType(/* edgeId */ null, null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(assignedToEdgeEntitiesByType => {
  console.log('AssignedToEdgeEntitiesByType:', assignedToEdgeEntitiesByType);
});
```

**28. case**

```javascript
entityService.case().subscribe(case => {
  console.log('case:', case);
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable(null).subscribe(entitySubtypesObservable => {
  console.log('EntitySubtypesObservable:', entitySubtypesObservable);
});
```

---

*Auto-generated by ThingsBoardDocUpdater*