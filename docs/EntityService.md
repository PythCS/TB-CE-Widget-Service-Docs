# EntityService

### **ENTITYSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
entityService.getEntityObservable('your-entitytype', 'your-entity-id', { /* your config */ }).subscribe(entityobservable => {
  console.log('Entity Observable:', entityobservable);
});
```

**2. getEntity**

```javascript
entityService.getEntity('your-entitytype', 'your-entity-id', { /* your config */ }).subscribe(entity => {
  console.log('Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable('your-entitytype', 'your-entitys-id', { /* your config */ }).subscribe(entitiesobservable => {
  console.log('Entities Observable:', entitiesobservable);
});
```

**4. getEntities**

```javascript
entityService.getEntities('your-entitytype', 'your-entitys-id', { /* your config */ }).subscribe(entity => {
  console.log('Entities:', entity);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
entityService.getSingleTenantByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(singletenantbypagelinkobservable => {
  console.log('Single Tenant By Page Link Observable:', singletenantbypagelinkobservable);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
entityService.getSingleCustomerByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(singlecustomerbypagelinkobservable => {
  console.log('Single Customer By Page Link Observable:', singlecustomerbypagelinkobservable);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
entityService.getEntitiesByPageLinkObservable('your-entitytype', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype', { /* your config */ }).subscribe(entitiesbypagelinkobservable => {
  console.log('Entities By Page Link Observable:', entitiesbypagelinkobservable);
});
```

**8. getEntitiesByPageLink**

```javascript
entityService.getEntitiesByPageLink('your-entitytype', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype', { /* your config */ }).subscribe(entitiesbypagelink => {
  console.log('Entities By Page Link:', entitiesbypagelink);
});
```

**9. getEntitiesByNameFilter**

```javascript
entityService.getEntitiesByNameFilter('your-entitytype', 'your-entityNameFilter', 100, 'your-subtype', { /* your config */ }).subscribe(entitiesbynamefilter => {
  console.log('Entities By Name Filter:', entitiesbynamefilter);
});
```

**10. findEntityDataByQuery**

```javascript
entityService.findEntityDataByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. findEntityKeysByQuery**

```javascript
entityService.findEntityKeysByQuery({ /* your query */ }, { /* your scope */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. findAlarmDataByQuery**

```javascript
entityService.findAlarmDataByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
entityService.findEntityInfosByFilterAndName({ /* your filter */ }, 'your-searchText', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
entityService.findSingleEntityInfoByEntityFilter({ /* your filter */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes('your-entitytypes').subscribe(aliafiltertypebyentitytype => {
  console.log('Alias Filter Types By Entity Types:', aliafiltertypebyentitytype);
});
```

**16. filterAliasByEntityTypes**

```javascript
entityService.filterAliasByEntityTypes({ /* your entityAlias */ }, 'your-entitytypes').subscribe(result => {
  console.log('Result:', result);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes('your-aliasfiltertype', 'your-entitytypes').subscribe(result => {
  console.log('Result:', result);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType('your-aliasfiltertype', 'your-entitytype').subscribe(result => {
  console.log('Result:', result);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList('your-allowedentitytypes', 'your-usealiasentitytypes').subscribe(result => {
  console.log('Result:', result);
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys('your-entitytype', { /* your searchText */ }).subscribe(entityfieldkey => {
  console.log('Entity Field Keys:', entityfieldkey);
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys({ /* your searchText */ }).subscribe(alarmkey => {
  console.log('Alarm Keys:', alarmkey);
});
```

**22. getEntityKeys**

```javascript
entityService.getEntityKeys('your-entity-id', { /* your query */ }, 'your-type', { /* your config */ }).subscribe(entitykey => {
  console.log('Entity Keys:', entitykey);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
entityService.getEntityKeysByEntityFilter({ /* your filter */ }, 'your-types', 'your-entitytypes', { /* your config */ }).subscribe(entitykeysbyentityfilter => {
  console.log('Entity Keys By Entity Filter:', entitykeysbyentityfilter);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
entityService.getEntityKeysByEntityFilterAndScope({ /* your filter */ }, 'your-types', 'your-entitytypes', { /* your scope */ }, { /* your config */ }).subscribe(entitykeysbyentityfilterandscope => {
  console.log('Entity Keys By Entity Filter And Scope:', entitykeysbyentityfilterandscope);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
entityService.createDatasourcesFromSubscriptionsInfo({ /* your subscriptionsInfo */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
entityService.createAlarmSourceFromSubscriptionInfo({ /* your subscriptionInfo */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'your-entitytype', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(assignedtoedgeentitiesbytype => {
  console.log('Assigned To Edge Entities By Type:', assignedtoedgeentitiesbytype);
});
```

**28. case**

```javascript
entityService.case().subscribe(result => {
  console.log('Result:', result);
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable('your-entitytype').subscribe(entitysubtypesobservable => {
  console.log('Entity Subtypes Observable:', entitysubtypesobservable);
});
```
