# ENTITY SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityId = 'your-entity-id';
entityService.getEntityObservable(entityType, entityId).subscribe(entityObservable => {
  console.log('Get Entity Observable:', entityObservable);
});
```

**2. saveEntityObservable**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
entityService.saveEntityObservable(entity).subscribe(savedEntityObservable => {
  console.log('Saved Entity Observable:', savedEntityObservable);
});
```

**3. getEntity**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityId = 'your-entity-id';
entityService.getEntity(entityType, entityId).subscribe(entity => {
  console.log('Get Entity:', entity);
});
```

**4. saveEntity**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
entityService.saveEntity(entity).subscribe(savedEntity => {
  console.log('Saved Entity:', savedEntity);
});
```

**5. saveGroupEntityObservable**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityService.saveGroupEntityObservable(entity, entityGroupIds).subscribe(savedGroupEntityObservable => {
  console.log('Saved Group Entity Observable:', savedGroupEntityObservable);
});
```

**6. saveGroupEntity**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // BaseData<EntityId> object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
entityService.saveGroupEntity(entity, entityGroupIds).subscribe(savedGroupEntity => {
  console.log('Saved Group Entity:', savedGroupEntity);
});
```

**7. getEntitiesObservable**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityService.getEntitiesObservable(entityType, entityIds).subscribe(entitiesObservables => {
  console.log('List of Entities Observables:', entitiesObservables);
});
```

**8. getEntities**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityIds = ['your-entity-i-1', 'your-entity-i-2'];
entityService.getEntities(entityType, entityIds).subscribe(entities => {
  console.log('List of Entities:', entities);
});
```

**9. getSingleTenantByPageLinkObservable**

```javascript
const entityService = self.ctx.entityService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(singleTenantByPageLinkObservables => {
  console.log('List of Single Tenant By Page Link Observables:', singleTenantByPageLinkObservables);
});
```

**10. getEntitiesByPageLinkObservable**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = 'value';
entityService.getEntitiesByPageLinkObservable(entityType, pageLink, subType).subscribe(entitiesByPageLinkObservables => {
  console.log('List of Entities By Page Link Observables:', entitiesByPageLinkObservables);
});
```

**11. getEntitiesByPageLink**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = 'value';
entityService.getEntitiesByPageLink(entityType, pageLink, subType).subscribe(entitiesByPageLinks => {
  console.log('List of Entities By Page Links:', entitiesByPageLinks);
});
```

**12. getEntitiesByNameFilter**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const entityNameFilter = 'your-entity-name-filter';
const pageSize = 10;
const subType = 'value';
entityService.getEntitiesByNameFilter(entityType, entityNameFilter, pageSize, subType).subscribe(entitiesByNameFilters => {
  console.log('List of Entities By Name Filters:', entitiesByNameFilters);
});
```

**13. getEntityGroupEntitiesByPageLink**

```javascript
const entityService = self.ctx.entityService;
const entityGroupId = 'your-entity-group-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const entityGroupType = {  // EntityType object
  // ... set the fields you need
};
entityService.getEntityGroupEntitiesByPageLink(entityGroupId, pageLink, entityGroupType).subscribe(entityGroupEntitiesByPageLinks => {
  console.log('List of Entity Group Entities By Page Links:', entityGroupEntitiesByPageLinks);
});
```

**14. getEntityGroupEntities**

```javascript
const entityService = self.ctx.entityService;
const entityGroupId = 'your-entity-group-id';
const entityGroupType = {  // EntityType object
  // ... set the fields you need
};
const pageSize = 10;
entityService.getEntityGroupEntities(entityGroupId, entityGroupType, pageSize).subscribe(entityGroupEntities => {
  console.log('List of Entity Group Entities:', entityGroupEntities);
});
```

**15. findEntityDataByQuery**

```javascript
const entityService = self.ctx.entityService;
const query = {  // EntityDataQuery object
  // ... set the fields you need
};
entityService.findEntityDataByQuery(query).subscribe(entityDataByQuerys => {
  console.log('List of Entity Data By Querys:', entityDataByQuerys);
});
```

**16. findEntityKeysByQuery**

```javascript
const entityService = self.ctx.entityService;
const query = {  // EntityDataQuery object
  // ... set the fields you need
};
const scope = {  // AttributeScope object
  // ... set the fields you need
};
entityService.findEntityKeysByQuery(query, scope).subscribe(entityKeysByQuery => {
  console.log('Find Entity Keys By Query:', entityKeysByQuery);
});
```

**17. findEntityKeysByQueryV2**

```javascript
const entityService = self.ctx.entityService;
const query = {  // EntityDataQuery object
  // ... set the fields you need
};
const scopes = [];  // e.g. array of scopes values
entityService.findEntityKeysByQueryV2(query, scopes).subscribe(entityKeysByQueryV2 => {
  console.log('Find Entity Keys By Query V2:', entityKeysByQueryV2);
});
```

**18. findAlarmDataByQuery**

```javascript
const entityService = self.ctx.entityService;
const query = {  // AlarmDataQuery object
  // ... set the fields you need
};
entityService.findAlarmDataByQuery(query).subscribe(alarmDataByQuerys => {
  console.log('List of Alarm Data By Querys:', alarmDataByQuerys);
});
```

**19. findEntityInfosByFilterAndName**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
const searchText = 'searchText';
entityService.findEntityInfosByFilterAndName(filter, searchText).subscribe(entityInfosByFilterAndNames => {
  console.log('List of Entity Infos By Filter And Names:', entityInfosByFilterAndNames);
});
```

**20. findSingleEntityInfoByEntityFilter**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(singleEntityInfoByEntityFilter => {
  console.log('Find Single Entity Info By Entity Filter:', singleEntityInfoByEntityFilter);
});
```

**21. getAliasFilterTypesByEntityTypes**

```javascript
const entityService = self.ctx.entityService;
const entityTypes = [];  // e.g. array of entity-types values
const result = entityService.getAliasFilterTypesByEntityTypes(entityTypes);
console.log('Result:', result);
```

**22. filterAliasByEntityTypes**

```javascript
const entityService = self.ctx.entityService;
const entityAlias = {  // EntityAlias object
  // ... set the fields you need
};
const entityTypes = [];  // e.g. array of entity-types values
const result = entityService.filterAliasByEntityTypes(entityAlias, entityTypes);
console.log('Result:', result);
```

**23. filterAliasFilterTypeByEntityTypes**

```javascript
const entityService = self.ctx.entityService;
const aliasFilterType = {  // AliasFilterType object
  // ... set the fields you need
};
const entityTypes = [];  // e.g. array of entity-types values
const result = entityService.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes);
console.log('Result:', result);
```

**24. filterAliasFilterTypeByEntityType**

```javascript
const entityService = self.ctx.entityService;
const aliasFilterType = {  // AliasFilterType object
  // ... set the fields you need
};
const entityType = 'entityType';  // e.g. one of the allowed EntityType
const result = entityService.filterAliasFilterTypeByEntityType(aliasFilterType, entityType);
console.log('Result:', result);
```

**25. prepareAllowedEntityTypesList**

```javascript
const entityService = self.ctx.entityService;
const allowedEntityTypes = [];  // e.g. array of allowed-entity-types values
const useAliasEntityTypes = true;
const operation = {  // Operation object
  // ... set the fields you need
};
const result = entityService.prepareAllowedEntityTypesList(allowedEntityTypes, useAliasEntityTypes, operation);
console.log('Result:', result);
```

**26. getEntityFieldKeys**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
const searchText = 'value';
const result = entityService.getEntityFieldKeys(entityType, searchText);
console.log('Result:', result);
```

**27. getAlarmKeys**

```javascript
const entityService = self.ctx.entityService;
const searchText = 'value';
const result = entityService.getAlarmKeys(searchText);
console.log('Result:', result);
```

**28. getEntityKeys**

```javascript
const entityService = self.ctx.entityService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const query = 'your-query';
const type = {  // DataKeyType object
  // ... set the fields you need
};
entityService.getEntityKeys(entityId, query, type).subscribe(entityKeys => {
  console.log('List of Entity Keys:', entityKeys);
});
```

**29. getEntityKeysByEntityFilter**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
const types = [];  // e.g. array of types values
const entityTypes = [];  // e.g. array of entity-types values
entityService.getEntityKeysByEntityFilter(filter, types, entityTypes).subscribe(entityKeysByEntityFilters => {
  console.log('List of Entity Keys By Entity Filters:', entityKeysByEntityFilters);
});
```

**30. getEntityKeysByEntityFilterAndScope**

```javascript
const entityService = self.ctx.entityService;
const filter = {  // EntityFilter object
  // ... set the fields you need
};
const types = [];  // e.g. array of types values
const entityTypes = [];  // e.g. array of entity-types values
const scope = {  // AttributeScope object
  // ... set the fields you need
};
entityService.getEntityKeysByEntityFilterAndScope(filter, types, entityTypes, scope).subscribe(entityKeysByEntityFilterAndScopes => {
  console.log('List of Entity Keys By Entity Filter And Scopes:', entityKeysByEntityFilterAndScopes);
});
```

**31. createDatasourcesFromSubscriptionsInfo**

```javascript
const entityService = self.ctx.entityService;
const subscriptionsInfo = [];  // e.g. array of subscriptions-info values
const result = entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo);
console.log('Result:', result);
```

**32. createAlarmSourceFromSubscriptionInfo**

```javascript
const entityService = self.ctx.entityService;
const subscriptionInfo = {  // SubscriptionInfo object
  // ... set the fields you need
};
const result = entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo);
console.log('Result:', result);
```

**33. getAssignedToEdgeEntitiesByType**

```javascript
const entityService = self.ctx.entityService;
const edgeId = 'your-edge-id';
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getAssignedToEdgeEntitiesByType(edgeId, entityType, pageLink).subscribe(assignedToEdgeEntitiesByType => {
  console.log('Get Assigned To Edge Entities By Type:', assignedToEdgeEntitiesByType);
});
```

**34. getEdgeEventContent**

```javascript
const entityService = self.ctx.entityService;
const entity = {  // EdgeEvent object
  // ... set the fields you need
};
entityService.getEdgeEventContent(entity).subscribe(edgeEventContent => {
  console.log('Get Edge Event Content:', edgeEventContent);
});
```

**35. getEntitySubtypesObservable**

```javascript
const entityService = self.ctx.entityService;
const entityType = {  // EntityType object
  // ... set the fields you need
};
entityService.getEntitySubtypesObservable(entityType).subscribe(entitySubtypesObservables => {
  console.log('List of Entity Subtypes Observables:', entitySubtypesObservables);
});
```
