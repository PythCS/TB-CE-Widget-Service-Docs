# ENTITY SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
self.ctx.entityService.getEntityObservable('your-entitytype-value', 'your-entity-id').subscribe(entityObservable => {
  console.log('Get Entity Observable:', entityObservable);
});
```

**2. getEntity**

```javascript
self.ctx.entityService.getEntity('your-entitytype-value', 'your-entity-id').subscribe(entity => {
  console.log('Get Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
self.ctx.entityService.getEntitiesObservable('your-entitytype-value', 'your-entityids-value').subscribe(entitiesObservable => {
  console.log('Get Entities Observable:', entitiesObservable);
});
```

**4. getEntities**

```javascript
self.ctx.entityService.getEntities('your-entitytype-value', 'your-entityids-value').subscribe(entities => {
  console.log('Get Entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(singleTenantByPageLinkObservable => {
  console.log('Get Single Tenant By Page Link Observable:', singleTenantByPageLinkObservable);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(singleCustomerByPageLinkObservable => {
  console.log('Get Single Customer By Page Link Observable:', singleCustomerByPageLinkObservable);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getEntitiesByPageLinkObservable('your-entitytype-value', pageLink, 'your-subtype-value').subscribe(entitiesByPageLinkObservable => {
  console.log('Get Entities By Page Link Observable:', entitiesByPageLinkObservable);
});
```

**8. getEntitiesByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getEntitiesByPageLink('your-entitytype-value', pageLink, 'your-subtype-value').subscribe(entitiesByPageLink => {
  console.log('Get Entities By Page Link:', entitiesByPageLink);
});
```

**9. getEntitiesByNameFilter**

```javascript
self.ctx.entityService.getEntitiesByNameFilter('your-entitytype-value', 'your-entitynamefilter-value', 0, 'your-subtype-value').subscribe(entitiesByNameFilter => {
  console.log('Get Entities By Name Filter:', entitiesByNameFilter);
});
```

**10. findEntityDataByQuery**

```javascript
self.ctx.entityService.findEntityDataByQuery('your-query-value').subscribe(entityDataByQuery => {
  console.log('Find Entity Data By Query:', entityDataByQuery);
});
```

**11. findEntityKeysByQuery**

```javascript
self.ctx.entityService.findEntityKeysByQuery('your-query-value', 'your-scope-value').subscribe(entityKeysByQuery => {
  console.log('Find Entity Keys By Query:', entityKeysByQuery);
});
```

**12. findAlarmDataByQuery**

```javascript
self.ctx.entityService.findAlarmDataByQuery('your-query-value').subscribe(alarmDataByQuery => {
  console.log('Find Alarm Data By Query:', alarmDataByQuery);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
self.ctx.entityService.findEntityInfosByFilterAndName('your-filter-value', 'your-searchtext-value').subscribe(entityInfosByFilterAndName => {
  console.log('Find Entity Infos By Filter And Name:', entityInfosByFilterAndName);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
self.ctx.entityService.findSingleEntityInfoByEntityFilter('your-filter-value').subscribe(singleEntityInfoByEntityFilter => {
  console.log('Find Single Entity Info By Entity Filter:', singleEntityInfoByEntityFilter);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
self.ctx.entityService.getAliasFilterTypesByEntityTypes('your-entitytypes-value').subscribe(aliasFilterTypesByEntityTypes => {
  console.log('Get Alias Filter Types By Entity Types:', aliasFilterTypesByEntityTypes);
});
```

**16. filterAliasByEntityTypes**

```javascript
self.ctx.entityService.filterAliasByEntityTypes('your-entityalias-value', 'your-entitytypes-value').subscribe(filterAliasByEntityTypes => {
  console.log('Filter Alias By Entity Types:', filterAliasByEntityTypes);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
self.ctx.entityService.filterAliasFilterTypeByEntityTypes('your-aliasfiltertype-value', 'your-entitytypes-value').subscribe(filterAliasFilterTypeByEntityTypes => {
  console.log('Filter Alias Filter Type By Entity Types:', filterAliasFilterTypeByEntityTypes);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
self.ctx.entityService.filterAliasFilterTypeByEntityType('your-aliasfiltertype-value', 'your-entitytype-value').subscribe(filterAliasFilterTypeByEntityType => {
  console.log('Filter Alias Filter Type By Entity Type:', filterAliasFilterTypeByEntityType);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
self.ctx.entityService.prepareAllowedEntityTypesList('your-allowedentitytypes-value', true).subscribe(prepareAllowedEntityTypesList => {
  console.log('Prepare Allowed Entity Types List:', prepareAllowedEntityTypesList);
});
```

**20. getEntityFieldKeys**

```javascript
self.ctx.entityService.getEntityFieldKeys('your-entitytype-value', 'your-searchtext-value').subscribe(entityFieldKeys => {
  console.log('Get Entity Field Keys:', entityFieldKeys);
});
```

**21. getAlarmKeys**

```javascript
self.ctx.entityService.getAlarmKeys('your-searchtext-value').subscribe(alarmKeys => {
  console.log('Get Alarm Keys:', alarmKeys);
});
```

**22. getEntityKeys**

```javascript
self.ctx.entityService.getEntityKeys('your-entity-id', 'your-query-value', 'your-type-value').subscribe(entityKeys => {
  console.log('Get Entity Keys:', entityKeys);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
self.ctx.entityService.getEntityKeysByEntityFilter('your-filter-value', 'your-types-value', 'your-entitytypes-value').subscribe(entityKeysByEntityFilter => {
  console.log('Get Entity Keys By Entity Filter:', entityKeysByEntityFilter);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
self.ctx.entityService.getEntityKeysByEntityFilterAndScope('your-filter-value', 'your-types-value', 'your-entitytypes-value', 'your-scope-value').subscribe(entityKeysByEntityFilterAndScope => {
  console.log('Get Entity Keys By Entity Filter And Scope:', entityKeysByEntityFilterAndScope);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
self.ctx.entityService.createDatasourcesFromSubscriptionsInfo('your-subscriptionsinfo-value').subscribe(datasourcesFromSubscriptionsInfo => {
  console.log('Create Datasources From Subscriptions Info:', datasourcesFromSubscriptionsInfo);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
self.ctx.entityService.createAlarmSourceFromSubscriptionInfo('your-subscriptioninfo-value').subscribe(alarmSourceFromSubscriptionInfo => {
  console.log('Create Alarm Source From Subscription Info:', alarmSourceFromSubscriptionInfo);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'your-entitytype-value', pageLink).subscribe(assignedToEdgeEntitiesByType => {
  console.log('Get Assigned To Edge Entities By Type:', assignedToEdgeEntitiesByType);
});
```

**28. case**

```javascript
self.ctx.entityService.case().subscribe(case => {
  console.log('Case:', case);
});
```

**29. getEntitySubtypesObservable**

```javascript
self.ctx.entityService.getEntitySubtypesObservable('your-entitytype-value').subscribe(entitySubtypesObservable => {
  console.log('Get Entity Subtypes Observable:', entitySubtypesObservable);
});
```
