# EntityService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('EntityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
entityService.getEntityObservable('your-entitytype-value', 'your-entity-id').subscribe(entity => {
  console.log('Fetched  Entity Observable entity:', entity);
});
```

**2. getEntity**

```javascript
entityService.getEntity('your-entitytype-value', 'your-entity-id').subscribe(entity => {
  console.log('Fetched  Entity entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable('your-entitytype-value', 'your-entityids-value').subscribe(entities => {
  console.log('Fetched  Entities Observable entities:', entities);
});
```

**4. getEntities**

```javascript
entityService.getEntities('your-entitytype-value', 'your-entityids-value').subscribe(entities => {
  console.log('Fetched  Entities entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
entityService.getSingleTenantByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Single Tenant By Page Link Observable tenant:', tenant);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
entityService.getSingleCustomerByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Single Customer By Page Link Observable result:', result);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
entityService.getEntitiesByPageLinkObservable('your-entitytype-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype-value').subscribe(entities => {
  console.log('Fetched  Entities By Page Link Observable entities:', entities);
});
```

**8. getEntitiesByPageLink**

```javascript
entityService.getEntitiesByPageLink('your-entitytype-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype-value').subscribe(entities => {
  console.log('Fetched  Entities By Page Link entities:', entities);
});
```

**9. getEntitiesByNameFilter**

```javascript
entityService.getEntitiesByNameFilter('your-entitytype-value', 'your-entitynamefilter-value', 0, 'your-subtype-value').subscribe(entities => {
  console.log('Fetched  Entities By Name Filter entities:', entities);
});
```

**10. findEntityDataByQuery**

```javascript
entityService.findEntityDataByQuery('your-query-value').subscribe(entity => {
  console.log('find Entity Data By Query entity:', entity);
});
```

**11. findEntityKeysByQuery**

```javascript
entityService.findEntityKeysByQuery('your-query-value', 'your-scope-value').subscribe(entity => {
  console.log('find Entity Keys By Query entity:', entity);
});
```

**12. findAlarmDataByQuery**

```javascript
entityService.findAlarmDataByQuery('your-query-value').subscribe(alarm => {
  console.log('find Alarm Data By Query alarm:', alarm);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
entityService.findEntityInfosByFilterAndName('your-filter-value', 'your-searchtext-value').subscribe(entity => {
  console.log('find Entity Infos By Filter And Name entity:', entity);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
entityService.findSingleEntityInfoByEntityFilter('your-filter-value').subscribe(entity => {
  console.log('find Single Entity Info By Entity Filter entity:', entity);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes('your-entitytypes-value').subscribe(entity => {
  console.log('Fetched  Alias Filter Types By Entity Types entity:', entity);
});
```

**16. filterAliasByEntityTypes**

```javascript
entityService.filterAliasByEntityTypes('your-entityalias-value', 'your-entitytypes-value').subscribe(entity => {
  console.log('filter Alias By Entity Types entity:', entity);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes('your-aliasfiltertype-value', 'your-entitytypes-value').subscribe(entity => {
  console.log('filter Alias Filter Type By Entity Types entity:', entity);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType('your-aliasfiltertype-value', 'your-entitytype-value').subscribe(entity => {
  console.log('filter Alias Filter Type By Entity Type entity:', entity);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList('your-allowedentitytypes-value', true).subscribe(entity => {
  console.log('prepare Allowed Entity Types List entity:', entity);
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys('your-entitytype-value', 'your-searchtext-value').subscribe(entity => {
  console.log('Fetched  Entity Field Keys entity:', entity);
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys('your-searchtext-value').subscribe(alarm => {
  console.log('Fetched  Alarm Keys alarm:', alarm);
});
```

**22. getEntityKeys**

```javascript
entityService.getEntityKeys('your-entity-id', 'your-query-value', 'your-type-value').subscribe(entity => {
  console.log('Fetched  Entity Keys entity:', entity);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
entityService.getEntityKeysByEntityFilter('your-filter-value', 'your-types-value', 'your-entitytypes-value').subscribe(entity => {
  console.log('Fetched  Entity Keys By Entity Filter entity:', entity);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
entityService.getEntityKeysByEntityFilterAndScope('your-filter-value', 'your-types-value', 'your-entitytypes-value', 'your-scope-value').subscribe(entity => {
  console.log('Fetched  Entity Keys By Entity Filter And Scope entity:', entity);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
entityService.createDatasourcesFromSubscriptionsInfo('your-subscriptionsinfo-value').subscribe(data => {
  console.log('create Datasources From Subscriptions Info data:', data);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
entityService.createAlarmSourceFromSubscriptionInfo('your-subscriptioninfo-value').subscribe(alarm => {
  console.log('create Alarm Source From Subscription Info alarm:', alarm);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'your-entitytype-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(entities => {
  console.log('Fetched  Assigned To Edge Entities By Type entities:', entities);
});
```

**28. case**

```javascript
entityService.case().subscribe(result => {
  console.log('case result:', result);
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable('your-entitytype-value').subscribe(entity => {
  console.log('Fetched  Entity Subtypes Observable entity:', entity);
});
```
