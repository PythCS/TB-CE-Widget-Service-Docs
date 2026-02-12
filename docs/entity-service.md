# ENTITY

Generic entity operations and queries.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

## Methods

### getEntityObservable

```javascript
const entityType = {
  // your entityType object
};
const entityId = 'your-entity-id';

entityService.getEntityObservable(entityType, entityId).subscribe(result => {
  console.log('EntityObservable:', result);
});
```

### getEntity

```javascript
const entityType = {
  // your entityType object
};
const entityId = 'your-entity-id';

entityService.getEntity(entityType, entityId).subscribe(result => {
  console.log('Entity:', result);
});
```

### getEntitiesObservable

```javascript
const entityType = {
  // your entityType object
};
const entityIds = 'your-entitys-id';

entityService.getEntitiesObservable(entityType, entityIds).subscribe(result => {
  console.log('EntitiesObservable:', result);
});
```

### getEntities

```javascript
const entityType = {
  // your entityType object
};
const entityIds = 'your-entitys-id';

entityService.getEntities(entityType, entityIds).subscribe(result => {
  console.log('Entities:', result);
});
```

### getSingleTenantByPageLinkObservable

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(result => {
  console.log('SingleTenantByPageLinkObservable:', result);
});
```

### getSingleCustomerByPageLinkObservable

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### getEntitiesByPageLinkObservable

```javascript
const entityType = {
  // your entityType object
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = {
  // your subType object
};

entityService.getEntitiesByPageLinkObservable(entityType, pageLink, subType).subscribe(result => {
  console.log('EntitiesByPageLinkObservable:', result);
});
```

### getEntitiesByPageLink

```javascript
const entityType = {
  // your entityType object
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = {
  // your subType object
};

entityService.getEntitiesByPageLink(entityType, pageLink, subType).subscribe(result => {
  console.log('EntitiesByPageLink:', result);
});
```

### getEntitiesByNameFilter

```javascript
const entityType = {
  // your entityType object
};
const entityNameFilter = 'your-entitynamefilter';
const pageSize = 100;
const subType = {
  // your subType object
};

entityService.getEntitiesByNameFilter(entityType, entityNameFilter, pageSize, subType).subscribe(result => {
  console.log('EntitiesByNameFilter:', result);
});
```

### findEntityDataByQuery

```javascript
const query = {
  // your query object
};

entityService.findEntityDataByQuery(query).subscribe(result => {
  console.log('findEntityDataByQuery:', result);
});
```

### findEntityKeysByQuery

```javascript
const query = {
  // your query object
};
const scope = {
  // your scope object
};

entityService.findEntityKeysByQuery(query, scope).subscribe(result => {
  console.log('findEntityKeysByQuery:', result);
});
```

### findAlarmDataByQuery

```javascript
const query = {
  // your query object
};

entityService.findAlarmDataByQuery(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### findEntityInfosByFilterAndName

```javascript
const filter = {
  // your filter object
};
const searchText = 'your-searchtext';

entityService.findEntityInfosByFilterAndName(filter, searchText).subscribe(info => {
  console.log('Info:', info);
});
```

### findSingleEntityInfoByEntityFilter

```javascript
const filter = {
  // your filter object
};

entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(info => {
  console.log('Info:', info);
});
```

### getAliasFilterTypesByEntityTypes

```javascript
const entityTypes = {
  // your entityTypes object
};

const result = entityService.getAliasFilterTypesByEntityTypes(entityTypes);
console.log('AliasFilterTypesByEntityTypes:', result);
```

### filterAliasByEntityTypes

```javascript
const entityAlias = {
  // your entityAlias object
};
const entityTypes = {
  // your entityTypes object
};

const result = entityService.filterAliasByEntityTypes(entityAlias, entityTypes);
console.log('Result:', result);
```

### filterAliasFilterTypeByEntityTypes

```javascript
const aliasFilterType = {
  // your aliasFilterType object
};
const entityTypes = {
  // your entityTypes object
};

const result = entityService.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes);
console.log('Result:', result);
```

### filterAliasFilterTypeByEntityType

```javascript
const aliasFilterType = {
  // your aliasFilterType object
};
const entityType = {
  // your entityType object
};

const result = entityService.filterAliasFilterTypeByEntityType(aliasFilterType, entityType);
console.log('Result:', result);
```

### prepareAllowedEntityTypesList

```javascript
const allowedEntityTypes = {
  // your allowedEntityTypes object
};
const useAliasEntityTypes = true;

const result = entityService.prepareAllowedEntityTypesList(allowedEntityTypes, useAliasEntityTypes);
console.log('prepareAllowedEntityTypesList:', result);
```

### getEntityFieldKeys

```javascript
const entityType = {
  // your entityType object
};
const searchText = {
  // your searchText object
};

const result = entityService.getEntityFieldKeys(entityType, searchText);
console.log('Result:', result);
```

### getAlarmKeys

```javascript
const searchText = {
  // your searchText object
};

const result = entityService.getAlarmKeys(searchText);
console.log('Result:', result);
```

### getEntityKeys

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const query = 'your-query';
const type = {
  // your type object
};

entityService.getEntityKeys(entityId, query, type).subscribe(result => {
  console.log('Result:', result);
});
```

### getEntityKeysByEntityFilter

```javascript
const filter = {
  // your filter object
};
const types = {
  // your types object
};
const entityTypes = {
  // your entityTypes object
};

entityService.getEntityKeysByEntityFilter(filter, types, entityTypes).subscribe(result => {
  console.log('EntityKeysByEntityFilter:', result);
});
```

### getEntityKeysByEntityFilterAndScope

```javascript
const filter = {
  // your filter object
};
const types = {
  // your types object
};
const entityTypes = {
  // your entityTypes object
};
const scope = {
  // your scope object
};

entityService.getEntityKeysByEntityFilterAndScope(filter, types, entityTypes, scope).subscribe(result => {
  console.log('EntityKeysByEntityFilterAndScope:', result);
});
```

### createDatasourcesFromSubscriptionsInfo

```javascript
const subscriptionsInfo = {
  // your subscriptionsInfo object
};

const result = entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo);
console.log('createDatasourcesFromSubscriptionsInfo:', result);
```

### createAlarmSourceFromSubscriptionInfo

```javascript
const subscriptionInfo = {
  // your subscriptionInfo object
};

const result = entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo);
console.log('createAlarmSourceFromSubscriptionInfo:', result);
```

### resolveAlias

```javascript
const entityAlias = {
  // your entityAlias object
};
const stateParams = {
  // your stateParams object
};

entityService.resolveAlias(entityAlias, stateParams).subscribe(info => {
  console.log('Info:', info);
});
```

### of

```javascript
const info = entityService.of();
console.log('Info:', info);
```

### resolveAliasFilter

```javascript
const filter = {
  // your filter object
};
const stateParams = {
  // your stateParams object
};

entityService.resolveAliasFilter(filter, stateParams).subscribe(result => {
  console.log('Result:', result);
});
```

### checkEntityAlias

```javascript
const entityAlias = {
  // your entityAlias object
};

entityService.checkEntityAlias(entityAlias).subscribe(result => {
  console.log('Result:', result);
});
```

### resolveAlarmFilter

```javascript
const alarmFilterConfig = {
  // your alarmFilterConfig object
};

const alarm = entityService.resolveAlarmFilter(alarmFilterConfig);
console.log('Alarm:', alarm);
```

### saveEntityParameters

```javascript
const entityType = {
  // your entityType object
};
const entityData = {
  // your entityData object
};
const update = true;

entityService.saveEntityParameters(entityType, entityData, update).subscribe(info => {
  console.log('Info:', info);
});
```

### getSaveEntityObservable

```javascript
const entityType = {
  // your entityType object
};
const entityData = {
  // your entityData object
};

entityService.getSaveEntityObservable(entityType, entityData).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getUpdateEntityTasks

```javascript
const entityType = {
  // your entityType object
};
const entityData = {
  // your entityData object
};
const entity = { entityType: 'DEVICE', id: 'your-entity-id' };

entityService.getUpdateEntityTasks(entityType, entityData, entity).subscribe(result => {
  console.log('Updated Result:', result);
});
```

### saveEntityData

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const entityData = {
  // your entityData object
};

entityService.saveEntityData(entityId, entityData).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getStateEntityInfo

```javascript
const filter = {
  // your filter object
};
const stateParams = {
  // your stateParams object
};

const result = entityService.getStateEntityInfo(filter, stateParams);
console.log('StateEntityInfo:', result);
```

### createDatasourceFromSubscriptionInfo

```javascript
const subscriptionInfo = {
  // your subscriptionInfo object
};

const result = entityService.createDatasourceFromSubscriptionInfo(subscriptionInfo);
console.log('createDatasourceFromSubscriptionInfo:', result);
```

### validateSubscriptionInfo

```javascript
const subscriptionInfo = {
  // your subscriptionInfo object
};

const info = entityService.validateSubscriptionInfo(subscriptionInfo);
console.log('Info:', info);
```

### getAssignedToEdgeEntitiesByType

```javascript
const edgeId = 'your-edge-id';
const entityType = {
  // your entityType object
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

entityService.getAssignedToEdgeEntitiesByType(edgeId, entityType, pageLink).subscribe(result => {
  console.log('AssignedToEdgeEntitiesByType:', result);
});
```

### case

```javascript
entityService.case().subscribe(device => {
  console.log('Device:', device);
});
```

### getEntitySubtypesObservable

```javascript
const entityType = {
  // your entityType object
};

entityService.getEntitySubtypesObservable(entityType).subscribe(result => {
  console.log('Result:', result);
});
```

